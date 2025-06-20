# Git Workflow for Extreme Vibe Coding

> **Impeccable git hygiene is non-negotiable in xVC**

## Core Git Principles for xVC

### 1. **Atomic Commits**
Every commit should represent one complete, working change.

### 2. **Descriptive Messages**
Commit messages tell the story of your project's evolution.

### 3. **Frequent Commits**
Commit working code immediately - don't accumulate changes.

### 4. **Clean History**
Linear, understandable history that documents decisions.

## Initial Repository Setup

```bash
# Create repository with proper structure
mkdir project-name
cd project-name
git init

# Essential files
cat > .gitignore << 'EOF'
# Environment
.env
*.log
.DS_Store

# Build artifacts
build/
dist/
*.o
*.a
*.so

# IDE
.vscode/
.idea/
*.swp

# Dependencies
node_modules/
vendor/
go.sum
EOF

# Create initial structure
mkdir -p src tests docs
touch README.md CLAUDE.md

# First commit
git add .
git commit -m "Initial commit: Project structure"
```

## Commit Message Standards

### Format
```
<type>: <subject> (50 chars max)

<body> (72 chars per line)
- Explain what and why, not how
- Reference principles or decisions
- Note any trade-offs

<footer>
- Breaking changes
- Issues closed
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `refactor`: Code restructuring
- `test`: Test additions/changes
- `docs`: Documentation updates
- `perf`: Performance improvements
- `chore`: Maintenance tasks

### Examples

**Good Commit Messages:**
```bash
git commit -m "feat: Add checkpoint-based memory management

Implements revolutionary memory management system that eliminates
manual cleanup through checkpoint/rewind architecture.

- All allocations tracked automatically
- Error paths cleaned up via rewind
- Thread-safe implementation
- Zero manual free() calls needed

Closes memory leak issues completely."
```

```bash
git commit -m "refactor: Consolidate JSON implementations

Following single source of truth principle, merged three separate
JSON parsing implementations into one.

- Removed json_parse_v2() and json_quick_parse()
- Updated all references to use json_parse()
- Maintained all existing functionality
- Improved performance by 15%"
```

**Bad Commit Messages:**
```bash
# Too vague
git commit -m "fix bug"

# No context
git commit -m "update files"  

# Too long subject
git commit -m "Add new feature for handling user authentication with JWT tokens and session management"
```

## xVC-Specific Workflow

### 1. Start of Session
```bash
# Always start clean
git status
git pull origin main

# Create feature branch (optional but recommended)
git checkout -b feature/add-authentication

# Verify clean start
git log --oneline -10
```

### 2. During Development

**After Each Component:**
```bash
# Review changes carefully
git diff
git status

# Stage selectively if needed
git add -p  # Interactive staging

# Commit with descriptive message
git commit -m "feat: Add User model with validation

Implements User model following unified documents pattern.
Includes comprehensive validation and error handling.

- Email validation with regex
- Password strength requirements  
- Automatic timestamp management
- Full test coverage"
```

**Regular Status Checks:**
```bash
# Alias for quick status
alias gs='git status -sb'
alias gd='git diff'
alias gl='git log --oneline --graph -10'
```

### 3. Handling AI-Generated Changes

**Review Protocol:**
```bash
# 1. Always review AI changes before committing
git diff --staged

# 2. Split large changes
git reset HEAD .
git add -p  # Add chunks selectively

# 3. Test before committing
go test ./...  # or npm test
git commit -m "test: Add comprehensive test suite for auth module"
```

### 4. End of Session

```bash
# Ensure all work is committed
git status

# Push to remote
git push origin feature/add-authentication

# Create session summary
git log --oneline --since="4 hours ago" > session-summary.txt

# Tag significant milestones
git tag -a v0.1.0 -m "First working prototype with auth"
```

## Branching Strategy

### Simple Feature Branches
```bash
main
├── feature/add-authentication
├── feature/implement-storage
└── fix/memory-leak
```

### Branch Naming
- `feature/` - New functionality
- `fix/` - Bug fixes
- `refactor/` - Code improvements
- `docs/` - Documentation updates

### Merging
```bash
# Always rebase for clean history
git checkout main
git pull origin main
git checkout feature/add-authentication
git rebase main

# Test thoroughly
make test  # Run all tests

# Merge with clear message
git checkout main
git merge --no-ff feature/add-authentication -m "Merge: Add authentication system

Implements complete authentication with:
- JWT token generation
- Session management
- RBAC integration
- Password hashing with PBKDF2"
```

## Handling Mistakes

### Amending Recent Commit
```bash
# Fix the last commit
git add forgotten-file.go
git commit --amend --no-edit

# Or update message
git commit --amend -m "Better commit message"
```

### Undoing Changes
```bash
# Unstage files
git reset HEAD file.go

# Discard local changes  
git checkout -- file.go

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Nuclear option (lose changes)
git reset --hard HEAD
```

### Cleaning Up History
```bash
# Interactive rebase for last 5 commits
git rebase -i HEAD~5

# Common operations:
# - squash: Combine commits
# - reword: Change message
# - drop: Remove commit
# - reorder: Rearrange commits
```

## Advanced Techniques

### Stashing Work
```bash
# Save work temporarily
git stash push -m "WIP: authentication refactor"

# List stashes
git stash list

# Apply stash
git stash pop
```

### Cherry-Picking
```bash
# Bring specific commit from another branch
git cherry-pick abc123

# Cherry-pick without committing
git cherry-pick -n abc123
```

### Bisecting for Bugs
```bash
# Find when bug was introduced
git bisect start
git bisect bad  # Current version is bad
git bisect good v1.0  # v1.0 was good

# Git will checkout commits for testing
# After each test:
git bisect good  # or git bisect bad

# When done
git bisect reset
```

## Git Hooks for xVC

### Pre-commit Hook
```bash
#!/bin/bash
# .git/hooks/pre-commit

# Run tests
if ! make test; then
    echo "Tests failed. Commit aborted."
    exit 1
fi

# Check for debugging code
if grep -r "debugger\|console.log\|print(" src/; then
    echo "Debugging code found. Clean up before committing."
    exit 1
fi

# Verify no large files
if find . -size +1M -type f | grep -v "^./.git"; then
    echo "Large files detected. Use git-lfs or exclude them."
    exit 1
fi
```

### Commit Message Hook
```bash
#!/bin/bash
# .git/hooks/commit-msg

# Check message format
if ! grep -qE "^(feat|fix|docs|refactor|test|perf|chore): " "$1"; then
    echo "Commit message must start with type: (feat|fix|docs|etc)"
    exit 1
fi

# Check message length
if [ $(head -1 "$1" | wc -c) -gt 72 ]; then
    echo "Commit message subject too long (max 72 chars)"
    exit 1
fi
```

## xVC Git Aliases

Add to `~/.gitconfig`:
```ini
[alias]
    # Quick status
    s = status -sb
    
    # Pretty log
    l = log --oneline --graph --decorate
    ll = log --pretty=format:'%C(yellow)%h%Creset %ad | %s%d [%an]' --date=short
    
    # Show changes
    d = diff
    dc = diff --cached
    
    # Committing
    c = commit -m
    ca = commit -am
    amend = commit --amend --no-edit
    
    # Branching
    b = branch
    co = checkout
    cob = checkout -b
    
    # Working with remotes
    pl = pull --rebase
    ps = push
    
    # Cleanup
    cleanup = !git branch --merged | grep -v '\\*\\|main\\|master' | xargs -n 1 git branch -d
```

## Session Management

### Starting an xVC Session
```bash
#!/bin/bash
# evc-start-session.sh

# Ensure clean state
if [[ -n $(git status -s) ]]; then
    echo "Uncommitted changes detected. Please commit or stash."
    exit 1
fi

# Pull latest
git pull --rebase

# Create session branch
SESSION_BRANCH="session/$(date +%Y%m%d-%H%M)"
git checkout -b "$SESSION_BRANCH"

echo "xVC session started on branch: $SESSION_BRANCH"
```

### Ending an xVC Session
```bash
#!/bin/bash
# evc-end-session.sh

# Commit any remaining changes
if [[ -n $(git status -s) ]]; then
    git add -A
    git commit -m "chore: End of session checkpoint"
fi

# Show session summary
echo "Session Summary:"
git log --oneline main..HEAD

# Push session branch
git push -u origin $(git branch --show-current)

echo "Session complete. Remember to create PR if needed."
```

## Best Practices

### 1. **Commit Early and Often**
- Don't wait for "perfect" code
- Commit each working increment
- Use WIP commits if needed

### 2. **Review Before Committing**
- Always use `git diff` before staging
- Check for debugging code
- Verify tests pass

### 3. **Maintain Linear History**
- Use rebase instead of merge commits
- Squash related commits
- Keep history readable

### 4. **Document in Commits**
- Explain WHY, not just what
- Reference issues or decisions
- Include performance impacts

### 5. **Use Tags for Milestones**
```bash
git tag -a v1.0.0 -m "First production release"
git tag -a checkpoint-auth -m "Authentication system complete"
```

## Troubleshooting

### Large Files
```bash
# Find large files
git rev-list --objects --all | 
  git cat-file --batch-check='%(objecttype) %(objectname) %(objectsize) %(rest)' |
  sort -k3 -n | tail -10

# Remove from history (careful!)
git filter-branch --force --index-filter \
  'git rm --cached --ignore-unmatch path/to/large/file' \
  --prune-empty --tag-name-filter cat -- --all
```

### Merge Conflicts
```bash
# During rebase conflicts
git status  # See conflicted files
# Edit files to resolve
git add resolved-file.go
git rebase --continue

# Or abort and try different strategy
git rebase --abort
```

## Conclusion

Git is not just version control in xVC—it's your collaboration history, decision log, and safety net. Treat it with respect and it will serve you well.

---

> "In xVC, your git history tells the story of human-AI collaboration. Make it a story worth reading."
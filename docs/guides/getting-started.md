# Getting Started with Extreme Vibe Coding

> **Your first xVC session in 30 minutes**

## Prerequisites

### Required Tools
1. **AI Assistant Access**
   - Claude (via claude.ai or API)
   - Alternative: GPT-4, Gemini Pro
   - Minimum: 100k context window recommended

2. **Development Environment**
   - Terminal/Command line
   - Git (version 2.0+)
   - Text editor (VS Code, Vim, etc.)
   - Your language toolchain (compiler/interpreter)

3. **Mindset**
   - Clear project vision
   - Commitment to principles
   - Patience for partnership building

### Choosing Your First Language

For your first xVC project, **language choice matters immensely**. Start with:

1. **JavaScript/TypeScript** (Recommended for beginners)
   - Highest LLM fluency
   - Clearest echoes from the cave
   - Focus on patterns, not syntax fights

2. **Go** (Excellent choice)
   - Strong LLM support
   - Clean, simple syntax
   - Great for backend services

3. **Java** (If you prefer JVM)
   - Massive training data
   - Enterprise patterns well understood
   - Excellent tooling

**Avoid for first project**: C, C++, Rust, or niche languages. See [Language Choice Guide](language-choice.md) for why.

## Your First xVC Session

### Step 1: Project Setup (5 minutes)

```bash
# Create project directory
mkdir my-first-evc-project
cd my-first-evc-project

# Initialize git
git init

# Create basic structure
mkdir -p src docs tests
touch README.md CLAUDE.md .gitignore

# Initial commit
git add .
git commit -m "Initial project structure"
```

### Step 2: Define Your Vision (10 minutes)

Create `CLAUDE.md` with your project vision:

```markdown
# Project Vision

We are building a task management CLI tool in Go with these principles:

1. **Single Source of Truth**: No duplicate implementations
2. **Test-Driven**: Tests before implementation  
3. **Clean Architecture**: Clear separation of concerns
4. **Zero External Dependencies**: Pure Go stdlib only
5. **Comprehensive Logging**: Every decision visible

## Core Features
- Add/remove/list tasks
- Mark tasks complete
- Save/load from JSON file
- Simple and fast

## Quality Standards
- 100% test coverage
- Zero linter warnings
- Proper error handling
- Clear documentation
```

### Step 3: First Interaction (15 minutes)

Start your AI session with this prompt:

```
I'm starting a new project using Extreme Vibe Coding (xVC). 

Project: Task management CLI tool
Language: Go
Principles: Single source of truth, test-driven, clean architecture, zero dependencies

Please read the vision in CLAUDE.md and then:
1. Create a comprehensive test file for the core Task struct
2. Implement the Task type to pass all tests
3. Add proper logging throughout
4. Ensure clean, idiomatic Go code

Start with the test file first.
```

### Step 4: Establish Patterns

After the first file, reinforce patterns:

```
Excellent. Now following the same patterns:
1. Create tests for TaskList class
2. Implement TaskList with the same quality standards
3. Maintain our single source of truth principle
```

### Step 5: Git Hygiene

After each successful component:

```bash
# Review changes
git status
git diff

# Stage and commit
git add .
git commit -m "Add Task class with comprehensive tests"

# Continue pattern
```

## Core xVC Workflow

### 1. Vision First
Always start with clear, written vision. The AI can't read your mind.

### 2. Establish Patterns Early
First interactions set the tone. Be explicit about standards.

### 3. Incremental Progress
Build component by component, committing working code frequently.

### 4. Reinforce Principles
Regularly remind about core principles - they guide decisions.

### 5. Trust but Verify
Review generated code against your standards before committing.

## Common First-Session Pitfalls

### ❌ Starting Too Big
```
"Build me a complete task management system"
```

### ✅ Start Focused
```
"Create a Task class with these specific attributes..."
```

### ❌ Vague Instructions
```
"Make it good"
```

### ✅ Specific Standards
```
"Follow Go conventions, handle all errors, 100% test coverage"
```

### ❌ Accepting First Draft
```
*Commits whatever is generated*
```

### ✅ Iterate to Excellence
```
"Good start. Now add error handling for edge cases..."
```

## Session Management Tips

### Context Building
1. Start with vision/principles
2. Show example code for patterns
3. Reference previous decisions
4. Maintain consistency

### Effective Prompts
```
Structure: [Role] + [Context] + [Task] + [Constraints]

Example: "As a Go expert, following our test-driven approach 
and zero-dependency principle, create a JSON persistence layer 
for TaskList with comprehensive error handling."
```

### When to Take Breaks
- **After 2-3 hours of intense coding**: Even with cognitive resonance, sustained focus has limits. Quality starts degrading subtly before you notice it consciously.
- **When patterns start degrading**: If the system starts suggesting generic solutions or ignoring established conventions, context saturation has occurred. A break resets the cognitive state.
- **Before major architectural decisions**: Let your subconscious process complex decisions. The best architectural insights often come during walks, not during coding.
- **When you feel frustrated**: Frustration is a signal that cognitive alignment has broken down. Pushing through frustration teaches the pattern reflector that frustration is normal.

## Measuring Success

### Good First Session Indicators
- **✅ 5+ clean commits**: Each commit represents a complete thought—not just "progress" but "completion of a logical unit." This rhythm indicates healthy development flow.
- **✅ Working, tested code**: Not just code that compiles, but code that demonstrably works and has tests proving it. Quality is built in, not bolted on.
- **✅ Consistent code style**: The system has learned your preferences and applies them uniformly. Variable names, function structure, and error handling feel like they came from one mind.
- **✅ Clear git history**: Reading your commits tells the story of the session. Future you (or your team) can understand the reasoning behind each change.
- **✅ Pattern reflector following patterns**: The system anticipates your next request and suggests solutions aligned with your established approach without constant correction.

### Warning Signs
- **❌ No commits after 1 hour**: If you can't find anything worth committing in an hour, you're either working at too high a level or spinning your wheels. Break the problem down smaller.
- **❌ Degrading code quality**: Later functions are sloppier than earlier ones. Variable names become generic. Error handling gets skipped. This indicates context window saturation.
- **❌ Ignoring principles**: When "just this once" exceptions start appearing, principle erosion has begun. These exceptions compound quickly and undermine the entire methodology.
- **❌ Circular discussions**: Repeating the same conversation about approaches indicates cognitive misalignment. Stop, clarify the context, and re-establish patterns.
- **❌ Frustration building**: Both yours and the system's responses show signs of struggle. Take a break before this becomes a learned pattern.

## Next Steps

### After First Success
1. Document learnings in CLAUDE.md
2. Identify what patterns worked
3. Note where guidance was needed
4. Plan next session goals

### Building Momentum
- Session 2: Add persistence layer
- Session 3: Create CLI interface  
- Session 4: Add advanced features
- Session 5: Polish and optimize

## Quick Reference Card

```yaml
Before Starting:
- [ ] Clear project vision
- [ ] Development environment ready
- [ ] Git initialized
- [ ] 2-hour time block

During Session:
- [ ] Start with tests/design
- [ ] Commit every feature
- [ ] Reinforce principles
- [ ] Maintain standards

After Session:
- [ ] Review git log
- [ ] Document learnings
- [ ] Plan next session
- [ ] Push to remote
```

## Example First Session Output

```bash
$ git log --oneline
f5d9328 Add CLI interface with argument parsing
a8c3421 Add JSON persistence for TaskList
9b2d445 Implement TaskList with filtering capabilities  
c7e4332 Add Task class with comprehensive tests
2341233 Initial project structure

$ go test ./...
ok      taskmanager/task        0.005s
ok      taskmanager/persistence 0.003s
PASS

$ golangci-lint run
No issues found!
```

## Conclusion

Your first xVC session should focus on:
1. Establishing clear patterns
2. Building working code incrementally
3. Maintaining high standards
4. Creating sustainable momentum

Remember: The goal isn't speed on day 1—it's establishing a partnership that will accelerate development for months to come.

---

> "The first session sets the tone for the entire project. Invest in getting it right."
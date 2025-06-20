# xVC Environment Setup Guide

> **Configure your development environment for optimal human-AI collaboration**

## Minimum Requirements

### Hardware
- **RAM**: 8GB minimum (16GB recommended)
- **Storage**: 50GB free space
- **Network**: Stable internet connection
- **Display**: Large monitor recommended (code + AI chat)

### Software Essentials

#### 1. Version Control
```bash
# Git 2.0+ required
git --version

# Configure git for clear history
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global commit.verbose true
git config --global diff.algorithm histogram
```

#### 2. AI Access Options

**Option A: Claude (Recommended)**
- Claude Pro subscription ($20/month)
- 100k+ context window
- Code-aware interface
- Project knowledge persistence

**Option B: API Access**
```bash
# Install API client
npm install @anthropic-ai/sdk  # or openai

# Set API key
export ANTHROPIC_API_KEY="your-key-here"
```

**Option C: Local Models** (Advanced)
- LM Studio or Ollama
- Minimum 24GB VRAM
- Reduced capability vs cloud

#### 3. Development Tools

**Terminal Setup**
```bash
# Essential: tmux or screen for session management
sudo apt install tmux  # or brew install tmux

# Recommended: Modern shell
# zsh with oh-my-zsh or fish
```

**Editor Configuration**
```bash
# VS Code with extensions
code --install-extension golang.go
code --install-extension ms-vscode.cpptools
code --install-extension yzhang.markdown-all-in-one
code --install-extension streetsidesoftware.code-spell-checker

# Or Vim with plugins
# .vimrc additions for xVC
set number
set autowrite
set autoread
set updatetime=100
```

## Workspace Organization

### Directory Structure
```
~/evc-workspace/
├── projects/           # Active xVC projects
│   ├── project-1/
│   └── project-2/
├── templates/          # Reusable templates
│   ├── go/
│   ├── javascript/
│   └── c/
├── logs/              # Session logs
└── archives/          # Completed projects
```

### Project Template
```bash
#!/bin/bash
# save as ~/evc-workspace/templates/init-project.sh

PROJECT_NAME=$1
LANGUAGE=$2

mkdir -p "$PROJECT_NAME"/{src,tests,docs}
cd "$PROJECT_NAME"

# Core files
cat > README.md << 'EOF'
# Project Name

Built with Extreme Vibe Coding (xVC).

## Vision
[Clear project vision here]

## Principles
1. Single Source of Truth
2. Test-Driven Development
3. Clean Architecture
4. Comprehensive Logging
EOF

cat > CLAUDE.md << 'EOF'
# Development Guidelines

## Core Principles
1. Single Source of Truth - No duplicate implementations
2. Test First - Write tests before implementation
3. Clean Commits - Atomic, descriptive commits
4. Quality Standards - Zero warnings, full coverage

## Architecture Decisions
- [Document key decisions here]

## Patterns Established
- [Document patterns as they emerge]
EOF

# Initialize git
git init
git add .
git commit -m "Initial project structure"

echo "Project $PROJECT_NAME initialized!"
```

## Session Management

### Tmux Configuration
```bash
# ~/.tmux.conf for xVC sessions
# Split panes for code + AI
bind | split-window -h
bind - split-window -v

# Easy pane navigation
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# Large history for context
set -g history-limit 50000

# Mouse support
set -g mouse on
```

### Session Launcher
```bash
#!/bin/bash
# save as ~/bin/evc-session

PROJECT=$1
SESSION_NAME="evc-$PROJECT"

# Create or attach to session
tmux new-session -d -s "$SESSION_NAME" -c "$PROJECT"

# Split for AI interaction
tmux split-window -h -p 40
tmux send-keys -t "$SESSION_NAME:0.1" "claude" C-m

# Open editor in main pane
tmux send-keys -t "$SESSION_NAME:0.0" "code ." C-m

# Attach to session
tmux attach -t "$SESSION_NAME"
```

## AI Interface Optimization

### Browser Setup (Claude.ai)
```javascript
// Bookmarklet for better code viewing
javascript:(function(){
    document.body.style.fontFamily = 'monospace';
    document.body.style.fontSize = '14px';
})();
```

### Terminal AI Setup
```javascript
// ~/.config/evc/ai_client.js
const Anthropic = require('@anthropic-ai/sdk');
const fs = require('fs');

class xVCClient {
    constructor() {
        this.client = new Anthropic({
            apiKey: process.env.ANTHROPIC_API_KEY
        });
        this.context = [];
        this.sessionFile = `session_${new Date().toISOString().slice(0,19)}.log`;
    }
    
    async send(message) {
        // Add to context
        this.context.push({ role: 'user', content: message });
        
        // Get response
        const response = await this.client.messages.create({
            model: 'claude-3-sonnet-20240229',
            messages: this.context,
            max_tokens: 4000
        });
        
        // Log everything
        fs.appendFileSync(this.sessionFile, 
            `\n\nUser: ${message}\n\nClaude: ${response.content}\n`);
        
        return response.content;
    }
}

module.exports = xVCClient;
```

## Quality Assurance Tools

### Language-Specific Linters
```bash
# Go
go install golang.org/x/lint/golint@latest
go install github.com/golangci/golangci-lint/cmd/golangci-lint@latest

# JavaScript  
npm install -g eslint prettier jest

# C
sudo apt install cppcheck clang-format valgrind

# Java
# Use built-in compiler warnings or install SpotBugs
```

### Pre-commit Hooks
```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.4.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-added-large-files
      
  - repo: https://github.com/dnephin/pre-commit-golang
    rev: v0.5.1
    hooks:
      - id: go-fmt
      - id: go-vet
      - id: go-imports
      - id: go-mod-tidy
```

## Performance Monitoring

### System Resources
```bash
# Monitor during xVC sessions
# install htop
sudo apt install htop

# Custom monitoring script
cat > ~/bin/evc-monitor << 'EOF'
#!/bin/bash
while true; do
    clear
    echo "=== xVC Session Monitor ==="
    echo "CPU: $(top -bn1 | grep "Cpu(s)" | awk '{print $2}')"
    echo "Memory: $(free -h | grep Mem | awk '{print $3 "/" $2}')"
    echo "Disk I/O: $(iostat -d 1 2 | tail -n 2)"
    echo "Git Status: $(cd $1 && git status -s | wc -l) uncommitted files"
    sleep 5
done
EOF
chmod +x ~/bin/evc-monitor
```

## Troubleshooting

### Common Issues

**1. Context Window Limits**
```bash
# Split large files before feeding to AI
split -l 500 large_file.py part_

# Or use context management
find . -name "*.go" -exec wc -l {} + | sort -n
```

**2. Git Conflicts**
```bash
# xVC-friendly merge strategy
git config merge.ours.driver true
git config merge.tool vimdiff
```

**3. Performance Degradation**
```bash
# Clear caches and restart
tmux kill-server
git gc --aggressive
# Clear build artifacts
rm -rf build/ node_modules/ target/
# Restart AI session
```

## Quick Setup Script

```bash
#!/bin/bash
# Complete xVC environment setup

echo "Setting up xVC environment..."

# Install essentials
sudo apt update
sudo apt install -y git tmux vim curl wget htop

# Configure git
git config --global init.defaultBranch main
git config --global core.editor vim

# Create workspace
mkdir -p ~/evc-workspace/{projects,templates,logs,archives}

# Install language tools (customize as needed)
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install -y nodejs

# Install Go
wget https://go.dev/dl/go1.21.0.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.21.0.linux-amd64.tar.gz
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc

# Create helper scripts
mkdir -p ~/bin
curl -o ~/bin/evc-session https://raw.githubusercontent.com/.../evc-session
chmod +x ~/bin/*

echo "xVC environment ready!"
echo "Start your first session with: evc-session my-project"
```

## Conclusion

A well-configured environment is crucial for xVC success. Focus on:
- Reliable AI access
- Efficient workspace organization  
- Quality assurance automation
- Session management tools

The investment in setup pays dividends in productivity.

---

> "Your environment should amplify the human-AI partnership, not hinder it."
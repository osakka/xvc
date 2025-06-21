# Multi-Project xVC Management

## The Feature Richness Scaling Problem

As you've identified, xVC naturally creates feature-rich codebases. Each session adds capabilities, and the cognitive load of maintaining context across multiple projects becomes overwhelming.

## The Three-Project Barrier

Most developers hit a wall at 2-3 concurrent xVC projects because:
- Each project's feature set grows exponentially
- Context switching between rich codebases is expensive
- The AI needs increasing context to maintain quality

## Scaling Strategies

### 1. Project Rotation Pattern
```
Week 1-2: Project A (intense xVC)
Week 3-4: Project B (intense xVC)
Week 5-6: Project C (intense xVC)
Week 7-8: Maintenance rotation (all projects)
```

**Benefits:**
- Deep focus periods maximize xVC effectiveness
- Reduced context switching
- Natural cooling-off periods prevent over-engineering

### 2. Feature Freeze Cycles
```
Project Lifecycle:
1. Rapid xVC development (2-4 weeks)
2. Feature freeze declaration
3. Polish and optimization only
4. Move to maintenance mode
5. Rotate to next project
```

### 3. Context Preservation System

**Project Handoff Document:**
```markdown
## Project: [Name]
## Last xVC Session: [Date]

### Current Architecture
- Key patterns in use
- Major subsystems
- Integration points

### Feature Inventory
- Core features (locked)
- Enhancement candidates
- Known limitations

### Next Session Focus
- Specific goals
- Areas to avoid
- Technical debt items
```

### 4. The "Core and Satellites" Model

```
Core Project (60% time)
├── Primary xVC focus
├── Feature-rich development
└── Deep architectural work

Satellite Project 1 (20% time)
├── Bug fixes only
├── Minor enhancements
└── No architectural changes

Satellite Project 2 (20% time)
├── Bug fixes only
├── Minor enhancements
└── No architectural changes
```

### 5. AI Context Management

**Per-Project Context Files:**
```
project-a/
├── .xvc-context.md      # Current state summary
├── .xvc-boundaries.md   # What NOT to change
└── .xvc-focus.md        # Next session goals
```

**Session Initialization:**
```bash
# Start each session by reading context
cat .xvc-context.md .xvc-boundaries.md .xvc-focus.md
```

## The Anti-Patterns to Avoid

### 1. The "Everything Everywhere" Trap
- Don't try to maintain deep xVC on all projects simultaneously
- Accept that some projects must be in maintenance mode

### 2. The "Context Soup" Problem
- Don't mix architectural patterns between projects
- Each project should have its own distinct approach

### 3. The "Feature FOMO" Issue
- Not every project needs every feature
- Define "done" and stick to it

## Practical Implementation

### Week Planning Template
```
Monday-Tuesday: Core Project (xVC)
Wednesday: Satellite 1 (maintenance)
Thursday: Satellite 2 (maintenance)
Friday: Context updates & planning
```

### Project State Machine
```
States:
1. ACTIVE_XVC - Full feature development
2. STABILIZING - Bug fixes, polish only
3. MAINTAINED - Critical fixes only
4. ARCHIVED - Read-only reference

Transitions:
ACTIVE_XVC → STABILIZING (after 4-6 weeks)
STABILIZING → MAINTAINED (after 2 weeks)
MAINTAINED → ACTIVE_XVC (when rotation returns)
```

## Metrics for Success

### Sustainable Indicators
- Can explain each project's architecture in 2 minutes
- Context switch time < 30 minutes
- No feature regression during maintenance periods

### Warning Signs
- Need >1 hour to remember project context
- Features breaking in maintained projects
- Architectural drift between sessions

## The Hard Truth

You probably can't maintain more than:
- 1 project in ACTIVE_XVC
- 2 projects in STABILIZING
- 3-4 projects in MAINTAINED

Total: 6-7 projects maximum, with only 1 getting deep xVC at a time.

## Tooling Support

### Project State Tracker
```bash
#!/bin/bash
# xvc-status.sh
echo "=== xVC Project Status ==="
echo "ACTIVE: project-a (week 2/4)"
echo "STABILIZING: project-b (week 1/2)"
echo "MAINTAINED: project-c, project-d"
echo "Next rotation: 2 weeks"
```

### Context Preservation
```bash
# Before switching projects
xvc-checkpoint() {
  echo "## Checkpoint: $(date)" > .xvc-context.md
  echo "### Last worked on:" >> .xvc-context.md
  git log -1 --pretty=format:"%h - %s" >> .xvc-context.md
  echo "\n### Key areas modified:" >> .xvc-context.md
  git diff --name-only HEAD~5..HEAD | head -20 >> .xvc-context.md
}
```

## Conclusion

The feature richness of xVC is both its strength and its scaling challenge. By accepting that you can only deeply focus on one project at a time and implementing strict rotation patterns, you can maintain 5-7 projects total - but only by being disciplined about which ones get active development.
# xVC Session Management Guide

> **Optimize your human-AI collaboration sessions for maximum productivity**

## Session Types

### 1. **Discovery Sessions** (2-3 hours)
**Purpose**: Explore solutions, understand problem space
**Context**: Minimal - let the AI explore naturally
**Intervention**: Strategic observation (let the cave echo)
**Output**: Understanding, not necessarily code

### 2. **Implementation Sessions** (3-4 hours)
**Purpose**: Build features with established patterns
**Context**: Full project context + examples
**Intervention**: Active guidance and correction
**Output**: Working, tested, committed code

### 3. **Debugging Sessions** (1-2 hours)
**Purpose**: Fix specific issues
**Context**: Focused on problem area only
**Intervention**: Provide clues, not solutions
**Output**: Root cause fix + prevention

### 4. **Architecture Sessions** (2-3 hours)
**Purpose**: Design system components
**Context**: High-level principles + constraints
**Intervention**: Challenge assumptions
**Output**: Design documents + initial structure

### 5. **Polish Sessions** (1-2 hours)
**Purpose**: Refactor, optimize, document
**Context**: Quality standards + examples
**Intervention**: Demand excellence
**Output**: Improved code quality

## Pre-Session Checklist

```bash
# 1. Environment Check
git status              # Clean working directory?
go test ./...          # All tests passing?
git pull               # Latest code?

# 2. Mental Preparation
- [ ] Clear session goal defined
- [ ] 2-4 hour time block available
- [ ] Principles fresh in mind
- [ ] No pending distractions

# 3. Context Preparation
- [ ] CLAUDE.md updated with patterns
- [ ] Recent commits reviewed
- [ ] Key code examples identified
- [ ] Success criteria defined
```

## Optimal Session Structure

### Opening (10 minutes)
```
1. State session type and goal
2. Provide context refresh
3. Show recent work
4. Set success criteria

Example:
"This is an implementation session. We're adding rate limiting to our API 
following our established middleware pattern from auth_middleware.go. 
Success means: working rate limiter with tests, configurable limits, 
and Redis backend for distributed counting."
```

### Working Phase (2-3 hours)

**Maintain Rhythm**:
```
15-20 min: Design/discuss
20-30 min: Implementation  
10 min: Test and commit
5 min: Brief break
[Repeat]
```

**Context Management**:
```javascript
// Start broad
"We need rate limiting for our API"

// Narrow focus  
"Implement token bucket algorithm"

// Specific details
"Use Redis INCR with TTL for atomic counting"

// Back to integration
"Now integrate with existing middleware"
```

### Closing (15 minutes)
```bash
# 1. Commit remaining work
git add -A
git commit -m "feat: Session checkpoint - rate limiting WIP"

# 2. Document session
echo "## Session Summary - $(date)" >> SESSION_LOG.md
git log --oneline -10 >> SESSION_LOG.md

# 3. Update CLAUDE.md
echo "- Rate limiting uses token bucket pattern" >> CLAUDE.md

# 4. Plan next session
echo "TODO: Add rate limit headers to responses" >> NEXT_SESSION.md
```

## Context Window Management

### What to Include
```yaml
Always Include:
- Current goal/task
- Core principles  
- Recent patterns (last 2-3 examples)
- Specific constraints

Sometimes Include:
- Architecture diagrams (if relevant)
- API documentation (if integrating)
- Error messages (if debugging)
- Performance requirements (if optimizing)

Rarely Include:
- Full codebase overview
- Historical decisions
- Unrelated components
- Old conversations
```

### Context Refresh Technique
```
Every 30-45 minutes:
"Quick context refresh: We're building [X] following [Y] pattern 
with [Z] constraints. We just completed [A] and are now working on [B]."
```

### Handling Context Overflow
```
Symptoms:
- AI forgetting earlier decisions
- Mixing patterns from different components  
- Generic suggestions increasing

Solution:
1. Save current state
2. Start fresh conversation
3. Provide focused context
4. Reference saved state as needed
```

## Productivity Patterns

### The Warm-Up Pattern
Start sessions with simple, clear tasks to establish rhythm:
```
"Let's start by adding comprehensive logging to the function we wrote yesterday"
```

### The Checkpoint Pattern
Regular git commits create recovery points:
```bash
alias checkpoint='git add -A && git commit -m "checkpoint: $(date +%H:%M)"'
```

### The Variation Pattern
After establishing a pattern, create variations:
```
"Now implement the same pattern for DELETE endpoints"
```

### The Review Pattern
End each component with review:
```
"Show me the complete implementation. Any improvements needed?"
```

## Managing Energy and Focus

### Signs of Degradation
- 🔴 Increasing clarification requests
- 🔴 Declining code quality
- 🔴 Forgetting established patterns
- 🔴 Your frustration rising
- 🔴 Circular discussions

### Recovery Techniques

**Quick Reset** (5 minutes):
```bash
git commit -m "checkpoint: before reset"
# Stand up, stretch, drink water
# Return with fresh perspective
```

**Context Pivot** (10 minutes):
```
"Let's switch gears. Show me all our test files 
and identify missing test coverage."
```

**Full Break** (30+ minutes):
```bash
git commit -m "checkpoint: session break"
git push
# Complete disconnect
# Return for new session type
```

## Session Continuity

### Between Sessions

**Session Handoff Document**:
```markdown
## Session End: 2024-01-20 14:30

### Completed
- ✅ Rate limiting middleware implemented
- ✅ Redis integration working
- ✅ Basic tests passing

### In Progress  
- 🔄 Rate limit headers (X-RateLimit-*)
- 🔄 Configuration system

### Next Session
- Complete headers implementation
- Add configuration via env vars
- Implement bypass for admin users
- Add comprehensive tests

### Context Notes
- Using token bucket algorithm
- Redis keys: "rate_limit:{user_id}:{endpoint}"  
- Pattern follows auth_middleware.go structure
```

### Resuming Work

**Effective Resume**:
```
"Resuming work on rate limiting. Last session we implemented 
the middleware with Redis. Here's where we ended: [paste summary]. 
Now continuing with response headers..."
```

**Ineffective Resume**:
```
"Continue from yesterday"  # No context
"Remember what we were doing?"  # AI has no memory
```

## Advanced Session Techniques

### Parallel Exploration
```
"Give me three different approaches to implement caching:
1. In-memory with TTL
2. Redis with pub/sub invalidation  
3. Database-backed with lazy loading
Show pros/cons for each."
```

### Constraint Boxing
```
"Implement user search with these constraints:
- Must return in <100ms
- No external services
- Support partial matching
- Maximum 10 results"
```

### Pattern Extraction
```
"Review these three components and extract the common patterns 
we should follow for all future components."
```

## Session Metrics

### Track Your Sessions

```yaml
Session Log:
  Date: 2024-01-20
  Type: Implementation
  Duration: 3.5 hours
  
  Goals:
    - Add rate limiting: ✅
    - Add monitoring: ✅  
    - Add configuration: ⏳
    
  Metrics:
    - Commits: 7
    - Tests added: 15
    - Code quality: A
    - Focus rating: 8/10
    
  Learnings:
    - Redis patterns work well
    - Need better error messages
    - Should design config first
```

### Improvement Indicators
- 📈 More code per session
- 📈 Fewer clarifications needed
- 📈 Higher first-pass acceptance
- 📈 Cleaner git history
- 📈 Better pattern consistency

## Common Session Mistakes

### ❌ Marathon Sessions
8+ hours leads to degradation and bad decisions

### ❌ No Clear Goal  
Wandering sessions produce wandering code

### ❌ Context Dumping
Overwhelming AI with everything at once

### ❌ Skipping Commits
Losing work or creating mega-commits

### ❌ Ignoring Degradation
Pushing through when quality drops

## The Master's Session

Expert practitioners:
- Know exactly what session type they're running
- Manage context like a conductor manages tempo
- Recognize degradation before it impacts quality
- Create sustainable rhythm over marathon sprints
- Document patterns for future sessions

## Conclusion

Great xVC sessions aren't about duration—they're about:
- Clear purpose
- Managed context  
- Sustainable rhythm
- Quality output
- Continuous learning

Master session management, and you master xVC productivity.

---

> "A well-managed session produces more in 2 hours than a chaotic session does in 8."
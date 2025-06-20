# EVC Pitfalls and Anti-Patterns

> **Learn from our mistakes to achieve excellence faster**

## Common Pitfalls

### 1. **The Blank Canvas Trap**

**Pitfall**: Starting with "build me a database"
**Result**: Generic, unfocused implementation
**Solution**: Begin with clear vision, principles, and constraints

```
❌ "Create a document database"
✅ "Create a document database with unified storage where ALL entities are documents, using C for performance, with checkpoint-based memory management..."
```

### 2. **The Yes-Man Syndrome**

**Pitfall**: AI agrees with everything, even contradictions
**Result**: Inconsistent architecture, principle violations
**Solution**: Test understanding with challenging questions

```
Guide: "Should we add a caching layer?"
AI: "Yes, that would improve performance!"
Guide: "But wouldn't that violate our single source of truth?"
AI: "You're right, let me reconsider..."
```

### 3. **Context Poisoning**

**Pitfall**: Leaving broken code or wrong patterns in context
**Result**: AI perpetuates and builds on mistakes
**Solution**: Clean context regularly, remove failed attempts

```bash
# Regular cleanup
git clean -fd
git checkout -- .
# Start fresh with clean context
```

### 4. **The Refactor Spiral**

**Pitfall**: Endless "improvements" without progress
**Result**: Project stagnation, architectural drift
**Solution**: Set clear completion criteria

```
✅ Define "done": 
- Zero warnings
- All tests pass
- Documentation complete
- Principles upheld
```

### 5. **Principle Drift**

**Pitfall**: Gradually relaxing standards
**Result**: Technical debt accumulation
**Solution**: Regular principle reinforcement

```
Daily reminder: "No hacks, no parallel implementations, single source of truth"
```

## Anti-Patterns to Avoid

### 1. **The Kitchen Sink**

Trying to implement everything at once:

```
❌ Anti-pattern:
"Add user management, RBAC, metrics, caching, replication, 
clustering, and make it web-scale"

✅ Better:
"Let's start with user management following our unified documents pattern"
```

### 2. **The Quick Fix**

Accepting temporary solutions:

```
❌ Anti-pattern:
"Just hardcode it for now, we'll fix it later"

✅ Better:
"Let's implement proper configuration management from the start"
```

### 3. **The Parallel Universe**

Creating alternative implementations:

```
❌ Anti-pattern:
"Let's keep both the old and new authentication systems"

✅ Better:
"Surgically replace the old system with zero parallel code"
```

### 4. **The Documentation Lag**

Deferring documentation:

```
❌ Anti-pattern:
"We'll document it after it's working"

✅ Better:
"Documentation is part of the implementation"
```

### 5. **The Assumption Chain**

Building on unverified assumptions:

```
❌ Anti-pattern:
AI: "Since we're using microservices..."
Guide: [Doesn't correct the assumption]

✅ Better:
Guide: "We're not using microservices. We have a monolithic architecture."
```

## Cognitive Anti-Patterns

### 1. **Prompt Fatigue**

**Symptom**: Shorter, vaguer prompts over time
**Result**: Degraded output quality
**Solution**: Use standardized prompts consistently

### 2. **Context Hoarding**

**Symptom**: Never clearing context, accumulating everything
**Result**: Confused, conflicting implementations
**Solution**: Strategic context management

### 3. **Expertise Dilution**

**Symptom**: Using one prompt for everything
**Result**: Generic, unfocused solutions
**Solution**: Apply specific expertise prompts

### 4. **Standard Erosion**

**Symptom**: Accepting "good enough"
**Result**: Quality degradation over time
**Solution**: Maintain unwavering standards

## Recovery from Pitfalls

### When You're in a Pit

1. **Recognize**: Acknowledge the situation
2. **Stop**: Don't dig deeper
3. **Assess**: What principles were violated?
4. **Reset**: Clear context and start fresh
5. **Learn**: Document the pitfall

### The Reset Protocol

```bash
# 1. Save any valuable learning
git stash push -m "Saving work before reset"

# 2. Clean everything
git clean -fdx
git reset --hard

# 3. Restart with principles
"Let's start fresh. Our principles are:
- One Source of Truth
- No Parallel Implementations
- Surgical Precision
- Bar Raising Solutions"
```

## Project-Specific Pitfalls from JDBX

### 1. **The Buffer Counting Saga**

**Pitfall**: Assumed AI understood C string conventions
**Duration**: 5-7 days of confusion
**Learning**: Be explicit about language-specific patterns

### 2. **The SSL Context Duplication**

**Pitfall**: Didn't catch architectural violation early
**Impact**: Duplicate initialization code
**Learning**: Regular architecture reviews

### 3. **The Memory Strategy Wars**

**Pitfall**: Allowed multiple memory approaches to coexist
**Impact**: Confusion and complexity
**Learning**: Force unification early

## Prevention Strategies

### 1. **The Daily Standup**

Start each session with:
- Principle review
- Current state assessment
- Clear goals
- Success criteria

### 2. **The Hourly Check**

Every hour ask:
- Are we maintaining standards?
- Any principle violations?
- Is complexity justified?
- Documentation current?

### 3. **The Session Wrap**

End each session with:
- Git status check
- Test run
- Documentation update
- Principle validation

## Warning Signs

### Early Warnings
- 🟡 Increasing clarification requests
- 🟡 Proposing alternatives
- 🟡 Complexity without benefit
- 🟡 Delayed git commits

### Critical Warnings
- 🔴 Principle violations
- 🔴 Parallel implementations
- 🔴 Hardcoded values
- 🔴 Missing documentation

### Emergency Signs
- 🚨 Circular reasoning
- 🚨 Fundamental confusion
- 🚨 Architectural contradictions
- 🚨 Complete context loss

## The Meta-Pitfall

The biggest pitfall is thinking EVC is just about prompting. It's about:

1. **Vision**: Clear, unwavering direction
2. **Principles**: Non-negotiable standards
3. **Process**: Systematic approach
4. **Partnership**: Cognitive collaboration
5. **Persistence**: Maintaining excellence

## Learning from Pitfalls

Every pitfall teaches:

1. **Document It**: Add to this guide
2. **Share It**: Help others avoid it
3. **Prevent It**: Update processes
4. **Learn from It**: Improve prompts
5. **Grow from It**: Strengthen partnership

Remember: Pitfalls aren't failures—they're learning opportunities that make the next project better.

---

> "In EVC, we don't avoid all pitfalls—we learn to recognize them quickly and recover gracefully."
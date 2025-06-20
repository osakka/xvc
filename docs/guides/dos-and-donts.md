# xVC Do's and Don'ts

> **Quick reference for successful AI-assisted development**

## ✅ DO's

### Vision & Principles

**DO** establish crystal-clear vision upfront
```
"Build a document database where EVERYTHING is a document, 
stored in a single unified collection, using C for performance"
```

**DO** maintain unwavering principles
```
- One Source of Truth
- No Parallel Implementations  
- Surgical Precision
- Bar Raising Solutions
```

**DO** repeat your vision frequently
```
"Remember, we're building a unified documents database..."
"As we discussed, everything is a document..."
```

### Communication

**DO** be explicit and specific
```
✅ "Fix the memory leak in jwt_cache.c line 454 during cleanup"
❌ "Fix the memory issue"
```

**DO** provide context in every prompt
```
✅ "In our checkpoint-based memory system, implement..."
❌ "Implement memory management"
```

**DO** use standardized prompts consistently
```
"As a code auditor, review this for single source of truth..."
"Time for wrap-up hygiene. Check git status..."
```

### Technical Practices

**DO** build comprehensive infrastructure
```c
LOG_INFO("Creating document type='%s' in library='%s'", type, library);
TRACE_ENTER("function_name");
ASSERT(condition, "Meaningful error message");
```

**DO** commit frequently with descriptive messages
```bash
git commit -m "🔒 SECURITY: Fix JWT validation buffer overflow"
```

**DO** maintain clean workspace
```bash
git clean -fd
mv obsolete_file.c trash/
```

### Quality Standards

**DO** enforce zero-warning compilation
```bash
make clean && make  # Must compile with -Wall -Wextra
```

**DO** document inline with implementation
```c
// Never defer documentation - it's part of the code
```

**DO** validate principles in code
```c
ASSERT(legacy_impl == NULL, "No parallel implementations allowed");
```

## ❌ DON'Ts

### Vision & Principles

**DON'T** start without clear vision
```
❌ "Build me a database"
❌ "Make something like MongoDB"
```

**DON'T** compromise on principles
```
❌ "Let's keep both implementations for now"
❌ "We'll fix this properly later"
```

**DON'T** allow principle drift
```
❌ Accepting "good enough"
❌ Allowing temporary hacks
```

### Communication

**DON'T** use vague instructions
```
❌ "Make it better"
❌ "Optimize the code"
❌ "Fix the bug"
```

**DON'T** assume context persistence
```
❌ "Continue from yesterday"
❌ "As we discussed before"
```

**DON'T** let errors accumulate
```
❌ Ignoring compiler warnings
❌ Deferring error handling
```

### Technical Anti-Patterns

**DON'T** create parallel implementations
```c
❌ keeping both old_auth.c and new_auth.c
❌ having get_user() and fetch_user()
```

**DON'T** hardcode values
```c
❌ #define ADMIN_USER "admin"
❌ if (port == 5000) { ... }
```

**DON'T** defer infrastructure
```
❌ "We'll add logging later"
❌ "Skip tests for now"
```

### Process Mistakes

**DON'T** skip git hygiene
```
❌ Massive commits with unclear messages
❌ Uncommitted changes for hours
```

**DON'T** ignore architectural violations
```
❌ Allowing mixed routing patterns
❌ Accepting inconsistent naming
```

**DON'T** let documentation lag
```
❌ "We'll update docs after shipping"
❌ Code changes without doc updates
```

## 🎯 Quick Decision Guide

### When the AI suggests alternatives:
- ✅ DO: "We use single source of truth. Pick one approach."
- ❌ DON'T: "Sure, let's try both and see what works"

### When encountering complexity:
- ✅ DO: "Is this complexity serving our principles?"
- ❌ DON'T: Accept complexity without justification

### When facing time pressure:
- ✅ DO: "Implement it right the first time"
- ❌ DON'T: "Quick hack now, proper fix later"

### When debugging issues:
- ✅ DO: "What does the log say? Show me the trace."
- ❌ DON'T: "Try different things until it works"

### When AI seems confused:
- ✅ DO: "Let me clarify our architecture..."
- ❌ DON'T: Let misunderstanding compound

## 🚀 Success Patterns

### Starting a Session
```
✅ DO:
1. Check git status
2. Review principles
3. Set clear goals
4. Define success criteria

❌ DON'T:
- Jump into coding
- Assume AI remembers
- Start without context
```

### During Development
```
✅ DO:
- Test frequently
- Commit working code
- Maintain standards
- Update docs inline

❌ DON'T:
- Accumulate changes
- Defer testing
- Accept warnings
- Skip documentation
```

### Ending a Session
```
✅ DO:
1. Run all tests
2. Check git status
3. Commit changes
4. Update documentation
5. Plan next steps

❌ DON'T:
- Leave uncommitted code
- Skip wrap-up hygiene
- Forget to document decisions
```

## 🎓 Learning from JDBX

### DO's that made JDBX successful:
- ✅ Maintained unified documents vision for 3 months
- ✅ Enforced single source of truth ruthlessly
- ✅ Built comprehensive logging/tracing early
- ✅ Committed code frequently with clear messages
- ✅ Kept documentation synchronized

### DON'Ts that we learned from:
- ❌ Allowed N-1 byte confusion for 5 days
- ❌ Let SSL context duplication slip through
- ❌ Delayed unifying memory strategies
- ❌ Accepted "temporary" workarounds

## 💡 The Golden Rules

1. **DO** be the unwavering Cognitive Guide
2. **DON'T** let the AI drive the vision
3. **DO** build infrastructure for collaboration  
4. **DON'T** skip the "boring" parts
5. **DO** maintain excellence standards
6. **DON'T** compromise for speed

## 🔑 The Ultimate Test

Before any decision, ask:
- Does this serve our vision?
- Does this uphold our principles?
- Does this raise the bar?
- Is this the right solution?

If any answer is "no" - **DON'T** do it.

---

> "In xVC, what you don't do is as important as what you do."
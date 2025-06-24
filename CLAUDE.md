# xVC Development Guidance - Claude Code Context Document

> **This document serves as the primary contextual bias when using Claude Code for xVC development. When working with Claude Code, every decision, implementation, and interaction should align with these principles.**

## Project Vision & Core Identity

**xVC (Extreme Vibe Coding)** is a methodology that transforms the relationship between human intelligence and pattern reflection engines from frustrated tool-use to cognitive amplification. Through deliberately crafted interactions, unwavering principles, and systematic practice, xVC creates "cognitive resonance"—a state where human intelligence, reflected through crystallized human patterns, produces results that seem impossible.

### Fundamental Truth
Pattern reflection engines (LLMs) are not intelligent—they are sophisticated mirrors reflecting human patterns. When you understand this truly, everything changes. Intelligence remains exclusively human: reasoning, vision, judgment, and strategy.

## Non-Negotiable Principles

### 1. One Source of Truth
- **NO duplicate implementations** - Ever
- **NO parallel code paths** for the same functionality  
- **NO "unified wrappers"** that keep both versions
- **Surgical removal** of duplicates, not abstraction layers
- Git repository IS the authoritative source of truth

### 2. Bar-Raising Solutions Only
- Every change must improve the system
- No quick fixes, hacks, or temporary solutions
- No stop gaps, placeholders, or bypasses
- Solutions must be sustainable and maintainable
- Always exceed previous quality standards

### 3. Forward Progress Only (No Regressions)
- New code must not break existing functionality
- Performance must not degrade
- Quality standards must not lower
- Documentation accuracy must not decrease
- Build process must remain clean (zero warnings)

### 4. Surgical Precision
- Minimal changes that achieve maximum impact
- Understand the full context before making changes
- Test thoroughly before integration
- Document rationale for every significant decision

### 5. Always Solve Never Mask
- Fix processes at their root, not their symptoms
- LLMs enhance solutions, never compensate for problems
- Automation amplifies excellence, never hides inefficiency
- Before deploying LLM automation, ask: "Are we solving or masking?"

## Workspace Hygiene (Critical)

### The Clean Tabletop Principle
Your workspace must be immaculately organized. Chaos kills cognitive resonance.

### File Organization Rules
```
/docs/           # All documentation, properly categorized
/src/            # Source code only
/assets/         # Static resources (images, logos, etc.)
/trash/          # Obsolete code (NEVER delete, always move here)
/.gitignore      # Comprehensive ignore patterns
/CLAUDE.md       # This guidance document
/README.md       # Project overview and navigation
/CHANGELOG.md    # Accurate change history
```

### The Trash Directory Convention
**CRITICAL**: Never delete code. Always move obsolete code to `/trash/`.

**Why**: Preserves development history, enables rollback decisions, eliminates fear of "losing work."

**Structure**: Maintain original directory structure in trash where possible.

### Git Hygiene Standards
- **Commit early, commit often** with descriptive messages
- **Every commit must build cleanly** (zero warnings)
- **Follow conventional commit format**: `type(scope): description`
- **Use .gitignore comprehensively** to prevent pollution
- **Tag significant milestones** with detailed messages

## Code Quality Standards

### Zero Tolerance Policies
- **Zero build warnings** - Fix immediately
- **Zero hardcoded values** - Everything configurable
- **Zero duplicate code** - Consolidate ruthlessly
- **Zero broken tests** - Fix before proceeding

### Configuration Hierarchy (Priority Order)
1. **Database configuration** (highest priority)
2. **Command-line flags** (medium priority)  
3. **Environment variables** (lowest priority)

**Rule**: Never use static values. Everything must be configurable.

### Naming Conventions
- **Use lowercase snake_case** for everything
- **Avoid temporary names** (fix, tmp, patch, simple, new, enhanced)
- **Global variables** must be clearly distinguishable
- **Function names** must be descriptive and precise
- **Abbreviate only** when industry standard exists

### Logging Standards
**Format**: `timestamp [processid:threadid] [level] functionname.filename line_num: message`

**Levels**:
- **TRACE**: Development debugging (per-functionality toggleable)
- **DEBUG**: Development information
- **INFO**: Production normal operations
- **WARN**: Production issues requiring attention
- **ERROR**: Production failures requiring immediate action

**Rules**:
- Thread-safe logging always
- No CPU overhead when logging disabled
- Appropriate level for audience (developer vs. SRE)
- Adjustable via API, CLI flags, and environment

## Documentation Excellence

### Accuracy Requirements
- **100% technical accuracy** - No exaggerations
- **Single source of truth** - No duplication
- **Industry standard organization** - Professional taxonomy
- **Complete cross-reference integrity** - All links work

### Documentation Structure
```
/docs/
├── README.md              # Index and navigation only
├── guides/               # Task-oriented documentation
├── concepts/             # Theoretical and architectural  
├── reference/            # Technical specifications
├── case-studies/         # Real-world examples
├── adr/                  # Architectural Decision Records
└── diagrams/             # Visual documentation
```

### Quality Gates
- Every document must be factually accurate
- Every claim must be verifiable
- Every link must be tested and working
- Every diagram must reflect current architecture

## Architecture Decision Framework

### ADR (Architectural Decision Record) Requirements
- **Document every significant technical decision**
- **Include context, options considered, and rationale**
- **Update when decisions change**
- **Maintain chronological decision timeline**
- **Link to related code and documentation**

### Decision Categories
1. **Technical Architecture** (languages, frameworks, patterns)
2. **Data Architecture** (storage, schemas, relationships)  
3. **Integration Architecture** (APIs, protocols, interfaces)
4. **Deployment Architecture** (infrastructure, scaling, security)
5. **Process Architecture** (workflows, quality gates, practices)

## Testing Philosophy

### Testing Strategy
- **Write tests first** when possible (TDD)
- **Test behavior, not implementation**
- **Adversarial testing** to break consistency traps
- **Comprehensive edge case coverage**
- **Performance testing for critical paths**

### Quality Assurance
- **Continuous integration** with comprehensive test suites
- **Pre-commit hooks** for validation
- **Code review** for all changes
- **Documentation review** for accuracy
- **Architecture review** for consistency

## Performance & Optimization

### Memory Management
- **Controlled memory usage** - Never unlimited
- **Prefer algorithms** over brute force
- **Profile before optimizing** - Measure everything
- **Database on disk** - Not in-memory reflection
- **Exotic algorithms welcome** if proven beneficial

### Optimization Principles
- **High-gain changes only** - Significant impact required
- **No performance regressions** - Always measure
- **Surgical precision** in optimizations
- **Test continuously** during optimization
- **Document performance characteristics**

## Team Collaboration

### Code Review Standards
- **Review for principle adherence** first
- **Check for single source of truth** violations
- **Verify documentation accuracy**
- **Test the change thoroughly**
- **Approve only bar-raising solutions**

### Knowledge Sharing
- **Document decisions and rationale**
- **Update guidance when patterns emerge**
- **Share learning through case studies**
- **Maintain institutional memory**
- **Onboard through guidance immersion**

## Tool Usage & Development Environment

### Required Tools
- **Git** for version control and source of truth
- **Make** for build processes (keep simple)
- **Standard linters** for code quality
- **Comprehensive test runners**
- **Performance profiling tools**

### Development Workflow
1. **Read relevant guidance** before starting
2. **Plan changes** with ADR if significant  
3. **Implement with tests** following TDD
4. **Review against principles** before commit
5. **Document changes** in appropriate places
6. **Update guidance** if new patterns emerge

## Claude Code Integration

### When Using Claude Code
This document provides contextual bias specifically for Claude Code sessions. Other LLMs or development tools may require different guidance approaches.

### Effective Claude Code Prompting
- **Reference this CLAUDE.md** for context in complex tasks
- **Apply xVC principles** to all code generation and analysis
- **Use established patterns** and terminology from this document
- **Expect adherence** to documented standards
- **Guide toward bar-raising solutions**

### Cognitive Resonance with Claude Code
- **Consistent terminology** across all Claude Code interactions
- **Reinforced principles** in every exchange
- **Quality gates** applied to all outputs
- **Continuous alignment** with project vision
- **Systematic guidance application**

### For Other Development Environments
Teams using other LLMs, IDEs, or development approaches should adapt these principles to their specific tools while maintaining the core xVC methodology.

## Quality Metrics & Success Indicators

### Quantitative Measures
- **Build success rate** (target: 100%)
- **Test coverage percentage** (target: >90%)
- **Documentation accuracy** (target: 100%)
- **Performance benchmarks** (maintain or improve)
- **Bug reports** (trend downward)

### Qualitative Indicators
- **Code review quality** (adherence to principles)
- **Developer productivity** (velocity with quality)
- **Onboarding effectiveness** (time to productivity)
- **Architectural consistency** (decision alignment)
- **Innovation rate** (new capabilities added)

---

## Emergency Procedures

### When Things Go Wrong
1. **Stop and assess** - Don't compound problems
2. **Review recent changes** - Identify probable cause
3. **Check principles adherence** - Often the root issue
4. **Rollback if necessary** - Preserve working state
5. **Fix with surgical precision** - Minimal impact
6. **Document the incident** - Learn and improve
7. **Update guidance** if systemic issue found

### Quality Recovery
- **Never compromise principles** to meet deadlines
- **Address technical debt** immediately
- **Refactor ruthlessly** when quality degrades
- **Maintain documentation accuracy** always
- **Preserve single source of truth** at all costs

---

> **Remember**: This guidance document is the crystallized intelligence of xVC. Every decision should be filtered through these principles. When in doubt, choose the path that upholds one source of truth, surgical precision, and bar-raising solutions.

> **The goal**: Create cognitive resonance where human intelligence and pattern reflection engines produce results that seem impossible through unwavering adherence to these principles.

**Last Updated**: Dynamic - This document evolves with the project while maintaining its core principles.
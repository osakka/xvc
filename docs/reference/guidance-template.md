# xVC Guidance Template

> *"Every interaction should provide clear direction, quality standards, and success criteria. This template ensures consistent excellence."*

## Core Template Structure

### **Session Opening Framework**

```
## xVC Session: [Session Purpose]

**Objective**: [Clear, specific goal for this session]

**Environment Context**:
- Language/Framework: [Technical context]
- Quality Standard: [Expected quality level]
- Time Constraint: [If applicable]
- Success Criteria: [How to measure completion]

**Core Principles Active**:
- [ ] One Source of Truth
- [ ] Surgical Precision  
- [ ] Bar-Raising Solutions
- [ ] Forward Progress Only
- [ ] Always Solve Never Mask

**Guidance Questions**:
1. [Question that reveals context/constraints]
2. [Question that guides toward quality]
3. [Question that validates approach]

Let's begin with: [Specific first step or question]
```

### **Quality Gate Template**

```
## Quality Checkpoint

Before proceeding, please show me:

**Understanding Verification**:
- Your interpretation of the requirements
- The approach you're planning to take
- Why you chose this approach over alternatives

**Quality Assessment**:
- What principles are you applying?
- How does this raise the bar on our codebase?
- What potential issues should we consider?

**Implementation Plan**:
- What's the first concrete step?
- How will we validate this is working correctly?
- What would make this solution robust?

⚠️ **WAIT FOR APPROVAL** before implementing.
```

### **Circuit-Breaker Template**

```
## CIRCUIT BREAKER - [Issue Type]

**STOP Current Approach**

**Issue Identified**: [Specific quality concern]
**Standard Violated**: [Which xVC principle was compromised]
**Impact**: [Why this matters for long-term quality]

**Reset Framework**:
- New Objective: [Refined goal]
- Quality Focus: [Specific quality requirement]
- Alternative Approach: [Better direction]

**Guidance Questions**:
- [Question to guide toward better solution]
- [Question to ensure quality standard]
- [Question to validate new approach]

Let's restart with: [Specific redirection]
```

## Specialized Templates

### **Architecture Decision Template**

```
## Architecture Decision Session

**Context**: [What we're designing and why]

**Quality Requirements**:
- Maintainability: [Specific needs]
- Scalability: [Expected growth]
- Performance: [Requirements]
- Security: [Considerations]

**Constraints**:
- Technical: [Platform, language, etc.]
- Organizational: [Team, timeline, etc.]
- Legacy: [Existing system considerations]

**Decision Criteria**:
1. [Most important factor]
2. [Second priority]
3. [Third priority]

**Exploration Questions**:
- What architectural patterns best fit these requirements?
- How would this design handle [specific challenge]?
- What would make this architecture resilient?
- How would we test this design?

Show me 2-3 architectural options with trade-offs before we choose.
```

### **Code Review Template**

```
## Code Review Session

**Review Scope**: [What code we're reviewing]

**Quality Standards**:
- [ ] Readable and well-structured
- [ ] Single responsibility maintained
- [ ] Appropriate error handling
- [ ] No duplicate implementations
- [ ] Clear naming conventions
- [ ] Adequate test coverage
- [ ] Performance considerations addressed

**Review Questions**:
1. Does this code raise the bar on our codebase quality?
2. Would a new team member understand this code easily?
3. How would this code handle edge cases and errors?
4. Is this the single source of truth for this functionality?
5. What would make this code more robust?

**Improvement Focus**: [Specific area to enhance]

Please analyze the code against these criteria and suggest specific improvements.
```

### **Debugging Session Template**

```
## Debugging Session

**Problem Description**: [Specific issue being investigated]

**Current Understanding**:
- Symptoms: [What we observe]
- Context: [When/where it happens]
- Impact: [Effect on system/users]

**Investigation Approach**:
- [ ] Reproduce the issue consistently
- [ ] Isolate the problem scope
- [ ] Identify root cause (not just symptoms)
- [ ] Develop comprehensive fix
- [ ] Prevent similar issues

**Quality Standards for Solution**:
- Must address root cause, not mask symptoms
- Should improve overall system robustness  
- Include appropriate monitoring/alerting
- Add tests to prevent regression

**Debugging Questions**:
- What evidence do we have about the root cause?
- How can we isolate this issue from other variables?
- What would a comprehensive solution look like?

Let's start by: [First investigation step]
```

### **Refactoring Session Template**

```
## Refactoring Session

**Target Code**: [What we're refactoring]
**Motivation**: [Why this refactoring is needed]

**Current Problems**:
- [Specific quality issue 1]
- [Specific quality issue 2]
- [Specific quality issue 3]

**Quality Goals**:
- [ ] Improved readability
- [ ] Better maintainability
- [ ] Enhanced testability
- [ ] Reduced complexity
- [ ] Eliminated duplication

**Constraints**:
- [ ] Preserve all existing functionality
- [ ] Maintain backward compatibility
- [ ] No performance regression
- [ ] Minimal change scope

**Refactoring Strategy**:
1. [First step with smallest risk]
2. [Second step building on first]
3. [Final step completing transformation]

**Validation Plan**:
- [How we'll verify functionality preserved]
- [How we'll measure quality improvement]
- [How we'll test edge cases]

Show me the refactoring plan before we begin implementation.
```

## Prompt Pattern Library

### **Experimental Collaboration Starters**

```
"We're experimenting with [objective]. What questions do you have about the environment, constraints, and expected behavior?"

"Let's explore [approach]. What patterns do you see in our current setup that might guide this implementation?"

"We're investigating [problem]. What aspects of the current system should inform our solution approach?"
```

### **Quality Enforcement Patterns**

```
"Before implementing, demonstrate that you understand the quality requirements by showing me [specific criteria]."

"This approach seems to compromise [quality standard]. How can we achieve the same goal while maintaining excellence?"

"I want to see evidence that this solution raises the bar. Show me how this improves our codebase quality."
```

### **Context Management Patterns**

```
"Let's start fresh on this request to avoid context bias. Here are the clean requirements: [...]"

"This question suggests our environment needs better setup. What information should be readily available about [topic]?"

"Based on our established patterns, what approach would be most consistent with our current architecture?"
```

## Customization Guidelines

### **Personal Adaptation**

1. **Identify your common quality issues** and create specific templates for them
2. **Document your successful prompt patterns** that yield consistent results
3. **Create shortcuts for your most-used guidance patterns**
4. **Adapt language to match your communication style**

### **Team Standardization**

1. **Establish shared templates** for common team activities
2. **Agree on quality standards** and encode them in templates
3. **Create project-specific variations** for different technology stacks
4. **Share successful adaptations** across team members

### **Project Customization**

1. **Adapt templates to project constraints** and requirements
2. **Include project-specific quality criteria** in guidance
3. **Reference project patterns and conventions** in templates
4. **Align templates with project architectural decisions**

## Usage Best Practices

### **Template Selection**

- **Use Session Opening** for any new topic or objective
- **Use Quality Gates** before any significant implementation
- **Use Circuit-Breakers** when quality standards are being compromised
- **Use Specialized Templates** for specific activities

### **Template Adaptation**

- **Fill in all bracketed placeholders** with specific context
- **Modify quality standards** to match current requirements
- **Add project-specific guidance questions** as needed
- **Remove irrelevant sections** to keep focus clear

### **Quality Validation**

- **Every template use should result in better outcomes** than ad-hoc prompting
- **Templates should reduce cognitive load** while maintaining quality
- **Successful templates should be refined and shared** with team
- **Ineffective templates should be analyzed and improved**

---

> **Template Philosophy**: These templates embody xVC principles in reusable form. They ensure that every interaction maintains quality standards while providing clear structure for collaboration.

> **Continuous Improvement**: Templates should evolve based on experience. The best template is the one that consistently produces bar-raising solutions with minimal cognitive overhead.
# One Source of Truth: The Foundation of System Integrity

> *"Duplicate implementations are cancer. One source of truth is the cure."*

## The Core Principle

**One Source of Truth** means that every piece of functionality, every algorithm, every configuration, and every decision has exactly one authoritative implementation in the system. No duplicates, no alternatives, no "just in case" parallel versions.

## Why This Matters

### **The Duplication Problem**
```
Feature A implemented in Service 1
Feature A also implemented in Service 2 (slightly different)
Feature A implemented again in Frontend (different again)

Result: 3 implementations, 3 maintenance burdens, 3 sources of bugs
```

### **The Truth Solution**
```
Feature A implemented once in Service 1
Service 2 calls Service 1 for Feature A
Frontend calls Service 1 for Feature A

Result: 1 implementation, 1 maintenance burden, 1 source of truth
```

## Application Areas

### **Code and Algorithms**
- **Bad**: Multiple implementations of the same business logic
- **Good**: Single implementation with multiple access points
- **Example**: One user authentication service, not auth logic in every microservice

### **Configuration and Settings**
- **Bad**: Environment variables scattered across multiple config files
- **Good**: Single configuration source with hierarchical inheritance
- **Example**: One config service that all applications reference

### **Data and State**
- **Bad**: User profile data stored in multiple databases with sync issues
- **Good**: Single user service owning all profile data
- **Example**: One user database with read replicas, not multiple user stores

### **Documentation and Specifications**
- **Bad**: API documentation in multiple places with inconsistencies
- **Good**: Single API specification that generates all documentation
- **Example**: OpenAPI spec that generates docs, tests, and client SDKs

## Implementation Strategies

### **Identify and Eliminate**
1. **Audit existing systems** for duplicate implementations
2. **Choose the best version** based on completeness, quality, performance
3. **Migrate dependencies** to use the chosen implementation
4. **Remove duplicate implementations** completely (move to trash, don't delete)

### **Prevent Future Duplication**
1. **Before implementing**, ask: "Does this already exist?"
2. **Before creating new**, explore: "Can I use existing?"
3. **When improving**, choose: "Enhance existing or replace it entirely?"
4. **Document decisions** so others know the authoritative source

### **Design for Single Source**
1. **Create abstractions** that hide implementation details
2. **Build APIs** that provide clean access to functionality
3. **Use dependency injection** to ensure single implementations
4. **Design for reuse** rather than reimplementation

## Common Violations and Solutions

### **"Quick Fix" Duplication**
**Problem**: Under pressure, team members copy-paste existing logic rather than refactoring for reuse.

**Solution**: 
```
CIRCUIT BREAKER: Stop and refactor for reuse
Time pressure is not an excuse for violating principles
Quick fixes create long-term technical debt
```

### **"Slightly Different" Logic**
**Problem**: "Our use case is slightly different, so we need our own implementation."

**Solution**:
```
Make the source configurable for different use cases
Add parameters to handle variations
Extend the existing implementation, don't duplicate it
```

### **"Faster to Duplicate" Thinking**
**Problem**: "It's faster to just copy this than to make it reusable."

**Solution**:
```
Short-term thinking creates long-term pain
Invest time now to save compound time later
Duplication always costs more in the end
```

### **"Legacy System" Excuses**
**Problem**: "The legacy system does X, but our new system does Y."

**Solution**:
```
Choose ONE system to be the source of truth
Migrate the other to use the chosen source
Don't maintain parallel implementations
```

## Technical Implementation Patterns

### **Service-Oriented Architecture**
```javascript
// Bad: Duplicate user validation
class OrderService {
  validateUser(user) { /* custom logic */ }
}
class PaymentService {
  validateUser(user) { /* different logic */ }
}

// Good: Single source of truth
class UserService {
  validateUser(user) { /* authoritative logic */ }
}
class OrderService {
  constructor(userService) { this.userService = userService; }
  processOrder(user) { 
    this.userService.validateUser(user);
  }
}
```

### **Configuration Management**
```yaml
# Bad: Scattered config
# File 1: app.yaml
database_url: "postgres://..."

# File 2: worker.yaml  
database_url: "postgres://..." # Duplicate!

# Good: Single source
# config/database.yaml
database:
  url: "postgres://..."
  
# app.yaml
extends: database.yaml

# worker.yaml  
extends: database.yaml
```

### **Data Architecture**
```sql
-- Bad: Duplicate user data
CREATE TABLE users (id, name, email);
CREATE TABLE customer_profiles (id, name, email); -- Duplicate!

-- Good: Single source with views
CREATE TABLE users (id, name, email);
CREATE VIEW customer_profiles AS SELECT * FROM users WHERE type = 'customer';
```

## Organizational Practices

### **Code Review Standards**
- **Reject PRs** that introduce duplicate implementations
- **Require justification** for any apparent duplication
- **Suggest refactoring** when duplication is discovered
- **Document the source of truth** for complex functionality

### **Architecture Review**
- **Identify ownership** for each major system component
- **Prevent overlapping responsibilities** between services
- **Establish clear boundaries** and interfaces
- **Regular audits** to detect emerging duplication

### **Documentation Standards**
- **Single authoritative documentation** for each API/service
- **Generated documentation** from single source specifications
- **Clear ownership** of documentation maintenance
- **Regular validation** that docs match implementation

## Measuring Success

### **Code Metrics**
- **Duplication percentage**: Lines of duplicated code / total lines
- **Dependency clarity**: Clear ownership and usage patterns
- **Refactoring frequency**: How often duplication is eliminated

### **System Metrics**
- **Consistency scores**: How consistent behavior is across components
- **Maintenance efficiency**: Time spent updating shared functionality
- **Bug correlation**: Bugs caused by inconsistent implementations

### **Team Metrics**
- **Decision speed**: How quickly "where does this belong?" questions are answered
- **Onboarding efficiency**: How quickly new team members understand system ownership
- **Conflict frequency**: Disagreements about overlapping responsibilities

## Common Challenges and Solutions

### **Performance Concerns**
**Challenge**: "Single source creates bottlenecks"

**Solution**: 
- Use caching and read replicas for performance
- Design for horizontal scaling of the single source
- Profile before assuming performance problems
- Remember: consistency problems are harder than performance problems

### **Team Autonomy**
**Challenge**: "Teams want to own their implementations"

**Solution**:
- Teams can own entire functional areas (clear boundaries)
- Shared implementations can have team ownership with clear APIs
- Focus autonomy on business logic, not infrastructure duplication

### **Legacy Migration**
**Challenge**: "We have existing duplicate implementations"

**Solution**:
- Create migration plan with clear milestones
- Choose best implementation as target state
- Migrate incrementally with feature flags
- Sunset old implementations completely

## Integration with Other xVC Principles

### **Surgical Precision**
- Eliminate duplication with minimal, targeted changes
- Refactor incrementally rather than big-bang rewrites
- Preserve functionality while eliminating redundancy

### **Bar-Raising Solutions**
- Every deduplication effort should improve overall system quality
- Don't just eliminate duplicates; improve the remaining implementation
- Use deduplication as opportunity for optimization

### **Forward Progress Only**
- Never create new duplication while eliminating old duplication
- Ensure migration doesn't break existing functionality
- Validate that single source meets all previous use cases

---

> **The Truth About Truth**: One source of truth isn't just about reducing code duplication—it's about creating systems where decisions have clear ownership, changes have predictable scope, and quality improvements compound rather than scatter.

> **The xVC Commitment**: Every duplicate implementation eliminated makes the entire system stronger, more maintainable, and more reliable. There are no exceptions to this principle—only opportunities to apply it more systematically.
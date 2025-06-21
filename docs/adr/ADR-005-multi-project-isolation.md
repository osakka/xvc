# ADR-005: Multi-Project Isolation Strategy

### Status
Proposed

### Context
Worca needs to manage multiple projects simultaneously while ensuring:
- Complete isolation between projects
- No context bleeding
- Resource fairness
- Security boundaries
- Performance isolation

Options:
- Process isolation (separate processes per project)
- Namespace isolation within single process
- Container-based isolation
- Database-level isolation
- Virtual environment isolation

### Decision
We will implement namespace-based isolation within JDBX:
- Each project gets a unique namespace prefix
- All documents are prefixed with project namespace
- JavaScript execution contexts are isolated per project
- Resource quotas are enforced per namespace
- Cross-project queries are explicitly forbidden

Implementation:
```json
{
  "_id": "project:webapp:prompt:greeting",
  "_type": "prompt",
  "_namespace": "project:webapp",
  // Rest of document
}
```

Namespace enforcement at query time:
```javascript
// All queries automatically filtered by namespace
db.query({ _type: "prompt" }) 
// Becomes: db.query({ _type: "prompt", _namespace: currentNamespace })
```

### Consequences

#### Positive
- Strong isolation without process overhead
- Easy to implement and understand
- Natural fit with document model
- Allows shared infrastructure
- Efficient resource usage

#### Negative
- Requires discipline in implementation
- Namespace must be validated everywhere
- Potential for bugs if filtering missed

#### Neutral
- All operations become namespace-aware
- Performance overhead of filtering

### References
- Kubernetes namespace model
- Multi-tenant database patterns
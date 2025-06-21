# ADR-002: JavaScript as Configuration Language

### Status
Proposed

### Context
We need to decide how to represent complex logic for:
- Prompt generation
- Response transformation
- Resource allocation
- Pipeline orchestration

Options include:
- JSON-based configuration with limited expressiveness
- Custom DSL (Domain Specific Language)
- JavaScript code stored as strings in documents
- External script files
- YAML/TOML configuration

### Decision
We will use JavaScript code stored as strings within documents for all configuration that requires logic. This includes:
- Transformer functions
- Prompt generators
- Orchestration strategies
- Validation rules

Example:
```json
{
  "_id": "transformer:context-builder",
  "_type": "js_transformer",
  "code": "function transform(input) { return {...input, timestamp: Date.now()}; }"
}
```

### Consequences

#### Positive
- Full programming language power available
- No need to learn custom DSL
- Can leverage existing JavaScript ecosystem
- Natural fit with jdbx's QuickJS integration
- Developers already know JavaScript

#### Negative
- Security concerns - need sandboxing
- Potential for runtime errors
- Debugging stored code is harder
- Need syntax validation before storage

#### Neutral
- Requires JavaScript runtime (QuickJS)
- Code versioning through document versioning

### References
- QuickJS provides sandboxed execution
- Similar approach used by MongoDB for stored procedures
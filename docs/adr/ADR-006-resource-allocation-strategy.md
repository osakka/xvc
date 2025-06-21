# ADR-006: Resource Allocation Strategy

### Status
Proposed

### Context
Multiple projects competing for limited LLM resources requires intelligent allocation:
- API rate limits (requests per minute, tokens per minute)
- Cost management (different models have different costs)
- Priority handling (some projects more critical)
- Fairness (prevent starvation)
- Burst handling (temporary high demand)

Options:
- Fixed allocation per project
- Dynamic allocation based on demand
- Priority-based allocation
- Token bucket algorithm
- Fair queuing

### Decision
We will implement a hybrid token bucket + priority queue system:

1. **Token Buckets per Resource**
   - Each LLM integration has a token bucket
   - Buckets refill at provider rate limits
   - Separate buckets for requests and tokens

2. **Priority Queues per Project**
   - Each project has a priority (high/medium/low)
   - Within priority, FIFO ordering
   - Starvation prevention through aging

3. **Allocation Algorithm**
   ```javascript
   function allocateResource(request) {
     // Check if tokens available
     if (tokenBucket.hasTokens(request.cost)) {
       tokenBucket.consume(request.cost);
       return executeRequest(request);
     }
     
     // Add to priority queue
     priorityQueue.add(request);
     
     // Process queue when tokens available
     tokenBucket.onRefill(() => processQueue());
   }
   ```

4. **Cost Tracking**
   - Track tokens/costs per project
   - Implement soft and hard limits
   - Alert on approaching limits

### Consequences

#### Positive
- Fair resource distribution
- Respects provider limits
- Priority support for critical projects
- Prevents single project from monopolizing resources
- Cost control built-in

#### Negative
- Complex implementation
- Requires careful tuning
- Adds latency for queued requests

#### Neutral
- All LLM requests go through allocator
- Monitoring becomes critical

### References
- Token bucket algorithm
- Linux CFS scheduler concepts
- API rate limiting best practices
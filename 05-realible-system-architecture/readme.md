# Reliable System Architecture

- **Load balancing** distributes incoming traffic across multiple servers to ensure high availability, scalability, and optimized performance by preventing overload on any single server.

- **Fault-tolerant** architecture involves both infrastructure (redundancy, load balancing, auto-scaling, geographic distribution) and application design (service isolation, graceful degradation, circuit breakers, retry logic) to ensure system reliability.

- **The circuit breaker pattern** helps prevent cascading failures by "opening" the circuit to a failing service, allowing the rest of the system to continue functioning with reduced functionality, and then "closing" it once the service recovers.

### How circuit breakers work:

1. Closed (The "Normal" State)
   Everything is working fine. Requests flow through to the service normally. The circuit breaker just sits there and counts how many requests fail.

2. Open (The "Safety" State)
   If the failure rate hits a certain threshold (e.g., 50% of requests fail), the circuit breaker "trips." It stops all traffic to the failing service immediately. Instead of waiting for a timeout, it returns an error or a "fallback" response right away.

3. Half-Open (The "Testing" State)
   After a set amount of time, the breaker decides to see if the service has recovered. It lets a limited number of test requests through.
   - If they succeed: The circuit closes, and normal traffic resumes.
   - If they fail: It trips back to "Open" and waits again.

- **The CAP Theorem** states that in a distributed system, you cannot simultaneously guarantee Consistency (all reads get the latest write), Availability (every request gets a response), and Partition Tolerance (system operates despite communication failures). You can only have two of these at the same time. SREs usually prioritize Partition Tolerance because network failures are common, then balance between Consistency and Availability based on the use case—for example, financial apps prioritize Consistency, while social media apps prioritize Availability.

- **Auto-scaling** automatically adjusts computing resources up or down based on user demand without manual intervention, enhancing reliability, performance, cost efficiency, and operational flexibility.

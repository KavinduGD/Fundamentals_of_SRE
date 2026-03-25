In Site Reliability Engineering (SRE), reliability isn't about achieving "100% uptime" (which is usually impossible and too expensive). Instead, it’s about managing error budgets using three critical metrics: **SLIs**, **SLOs**, and **SLAs**.

Think of them as a pyramid, where each layer builds on the one below it.

---

## 1. SLI (Service Level Indicator)

**The Measurement:** "What are we measuring right now?"

An SLI is a specific quantitative measure of some aspect of the level of service provided. It tells you how your system is performing at this exact moment. Common SLIs include latency, throughput, or error rate.

- **Format:** A number or a percentage.
- **Example:** "The percentage of HTTP requests that return a `200 OK` status code."
- **Analogy:** The speedometer in your car. It tells you exactly how fast you are going right now.

---

## 2. SLO (Service Level Objective)

**The Target:** "What is our goal for that measurement?"

An SLO is a target value or range of values for a service level that is measured by an SLI. This is the internal goal your team strives to meet to keep users happy. If you fall below this, your team needs to stop shipping new features and focus on stability.

- **Format:** SLI + Target + Time Window.
- **Example:** "99.9% of HTTP requests should return `200 OK` over a rolling 30-day period."
- **Error Budget:** This is the "wiggle room" defined by your SLO. If your goal is 99.9% uptime, you have a 0.1% "Error Budget" to perform maintenance or handle unexpected crashes.

---

## 3. SLA (Service Level Agreement)

**The Contract:** "What happens if we fail to meet the goal?"

An SLA is a legal or commercial agreement between a service provider and a customer. It defines what happens (usually financial penalties or credits) if the service fails to meet the agreed-upon standards.

- **Key Difference:** SLOs are internal goals for engineers; SLAs are external promises for lawyers and customers.
- **Strictness:** The SLA is almost always **looser** than the SLO. If your internal SLO is 99.9%, your external SLA might be 99.5%. This gives you a safety buffer.
- **Example:** "If uptime falls below 99.5% in a month, the customer receives a 10% credit on their bill."

---

## Summary Comparison Table

| Feature        | SLI                 | SLO                      | SLA                          |
| :------------- | :------------------ | :----------------------- | :--------------------------- |
| **Definition** | Indicator           | Objective                | Agreement                    |
| **Purpose**    | Measure performance | Set a reliability target | Define business consequences |
| **Audience**   | SREs / Developers   | SREs / Product Owners    | Customers / Legal / Sales    |
| **Example**    | Success Rate        | 99.9% Success Rate       | 99% Uptime or get a refund   |

## 4. Error Budget

The Error Budget is simply the mathematical difference between perfect reliability (100%) and your agreed-upon SLO.

- **Equation:** $100\% - SLO = \text{Error Budget}$
- **Example:** If your SLO is 99.9%, your Error Budget is 0.1%.

**Why is it useful?**

The Error Budget solves the eternal conflict between Developers (who want to move fast) and SREs (who want stability).

- **If the budget is full:** The team can take risks, push experimental features, and move fast.
- **If the budget is nearly empty:** You must slow down. All manual changes stop, and the team focuses strictly on reliability and bug fixes until the budget recovers.
- **If the budget is blown:** You've failed your SLO. This usually triggers a "Post-Mortem" to figure out what went wrong so it doesn't happen again.

### Sample SLO document by google

https://sre.google/workbook/slo-document/

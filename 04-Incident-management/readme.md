# Incident Management

Majority of the incidents are cause by new code changes.

In Site Reliability Engineering (SRE), **Incident Management** is the process of responding to, resolving, and learning from unplanned disruptions. Unlike traditional IT support, SRE incident management focuses on **automation, speed, and long-term prevention** rather than just "fixing the bug."

Here is how high-performing SRE teams handle incidents.

---

## 1. The Incident Lifecycle

A structured response prevents "hero culture" and burnout by following a repeatable pattern:

- **Detection:** Monitoring and alerting systems (like Prometheus or Grafana) identify that a Service Level Objective (SLO) is being threatened.
- **Declaration:** Someone officially "calls" the incident. This triggers the assembly of a response team.
- **Mitigation:** The primary goal is to **restore service**, not find the root cause. This often involves rolling back a deployment, scaling resources, or diverting traffic.
- **Resolution:** The immediate threat is gone, and the system is stable.
- **Postmortem:** The team analyzes the "why" to ensure it never happens again.

---

## 2. Key Roles during an Incident

SRE incident management uses a simplified version of the Incident Command System (ICS):

| Role                             | Responsibility                                                                                                |
| :------------------------------- | :------------------------------------------------------------------------------------------------------------ |
| **Incident Commander (IC)**      | The "boss" of the incident. They don't fix the code; they coordinate resources and make high-level decisions. |
| **Operations Lead (Ops)**        | The "hands-on" person. They apply the fixes, run the commands, and change the configurations.                 |
| **Communications Lead (Commms)** | Keeps stakeholders and customers informed so the IC and Ops can focus on the technical work.                  |

---

## 3. Best Practices for SREs

- **Blameless Culture:** Focus on the system failure, not the human error. If a human made a mistake, the system should have had a guardrail to prevent it.
- **Standardized Severity Levels:** Use a clear scale (e.g., SEV-1 for total outage, SEV-3 for minor feature degradation) to determine how many people need to wake up at 3 AM.
- **The "On-Call" Handover:** Ensure there is a clear process for passing the "baton" between shifts to prevent fatigue.
- **Automated Runbooks:** Instead of a PDF manual, SREs prefer executable scripts or "playbooks" that can automate common mitigation steps.

---

## 4. Postmortems: The SRE Gold Standard

An incident is only truly "resolved" when the postmortem is complete. A good postmortem includes:

1. **Timeline:** Exactly what happened and when.
2. **Root Cause Analysis:** Using the "5 Whys" method.
3. **Action Items:** Specific, tracked tasks to improve the system's resilience.

> **Pro Tip:** If an incident doesn't result in at least one engineering task to prevent it from happening again, you haven't finished managing the incident.

---

**Would you like me to help you draft a template for an SRE postmortem or explain how to set up automated alerting for specific DevOps tools?**

# Implementing SRE

## Organizational Models

There are four main SRE organizational models:

### 1. Central SRE Team

- **Pros**: Specialized expertise, sets reliability standards
- **Cons**: May lack deep product knowledge, collaboration challenges

### 2. Embedded SRE

- **Pros**: Close collaboration with product teams, in-depth product knowledge, faster feedback
- **Cons**: Resource-intensive

### 3. Decentralized SRE Teams

- **Pros**: Scales well in large organizations, close collaboration
- **Cons**: Risk of duplicate efforts

### 4. Upskilling Developers into SRE Roles

- **Pros**: Leverages existing resources, deep product knowledge
- **Cons**: Requires significant training, burnout risk

## Production release review '

- PRR is a thorough review by the SRE team to ensure an application is ready for production, covering architecture, CI/CD, capacity, support, and observability.
- It happens during development and before production release, requiring close collaboration between SRE and development teams to address reliability concerns.

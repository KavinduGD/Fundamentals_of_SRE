# Release management

- **Nearly 70% of outages** are caused by changes, so managing changes carefully with automation (CI/CD), thorough testing, and observability is essential.

- **Progressive rollout** means releasing changes incrementally to small user groups or servers first, gradually increasing the scope to reduce risk and limit the blast radius if issues occur. Canary releases, Blue-green deployments, and feature flags are common techniques for progressive rollout.
  - **Canary release** involves deploying a new version to a small subset of users first, which helps minimize risk, enables faster feedback, and makes rollbacks easier if issues arise.
  - **Blue/green deployments** maintain two identical environments (one live, one staging) and switch traffic between them for releases, allowing quick rollbacks but at a higher infrastructure cost.
  - **Feature flags** let you enable or disable features without deploying new code, supporting safer and faster rollbacks and enhancing canary and progressive rollouts.

- **Rollbacks** are necessary for failed canary rollouts, outages, unexpected user impacts, or regression bugs. Always perform full rollbacks rather than partial ones to avoid instability.

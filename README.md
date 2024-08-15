# github-actions

## Pipelines

### Rust pipeline

**Workflow file:** .github/workflow/rust-pipeline.yml

This workflow will lint and test the project. Then it builds a container and deploys it to a given platform. It also plans and apllies terraform changes.

```mermaid
---
title: rust-pipeline.yml
---
flowchart LR
    A[prepare-pipeline] --> B[lint-and-test]
    B --> C[container/build-and-push]
    B --> E[terraform/plan]
    C --> D[container/deploy-aci]
    E --> F[terraform/apply]
    F --> D
```

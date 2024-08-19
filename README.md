# github-actions

## Pipelines

### Rust pipeline

**Workflow file:** .github/workflow/rust-pipeline.yml

This workflow will lint and test the project. Then it builds a container and deploys it to a given platform. It also plans and apllies terraform changes.

```mermaid
---
title: rust-pipeline.yml
---
flowchart LR;
    PP[prepare-pipeline] --> PA[prepare-azure]
    PA --> TP[terraform-plan]
    TP --> TA[terraform-apply]
    PA --> RLAT[rust-lint-and-test]
    RLAT --> BAPI[build-and-push-image]
    BAPI --> DA[deploy-aci]
```

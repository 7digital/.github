---
name: Production Readiness Review (Level A)
about: Critical service template
title: Production Readiness Review (Level A)
labels: production readiness review
assignees: AntonyKing7D, danjamesmay, jonlmarsh

---

This template is the [Production Readiness Checklist](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/production-readiness-checklist.md) (PRC) for [Level A](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/production-readiness-level.md) service. Please make sure you have read the [PRC guidelines](https://github.com/7digital/7d-production-readiness-checklist/blob/master/PROCESS.md).

Production Readiness Review has the following 2 phases:

[Design phase review](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/design-checklist.md)
[Pre-production phase review](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/pre-production-checklist.md)

Please complete the Design phase review before beginning development of your service and complete the Pre-production phase review before your service receives real (i.e. customer) production traffic.


# Pre-production checklist
This checklist contains points that must be satisfied during implementation and verified prior to release.

It is recommended to ensure that your service is deployed in production (but not receiving production traffic) before requesting the PRC, as some of the points in the list below can only be validated (e.g. capacity estimation, dashboards, screenboards, alerting, profiling, ...) if the service is deployed in production and can receive some non-production traffic. This should be done only if your service will not impact other production services or datasets. Please let us know in the issue if you think this would be a problem for your service.

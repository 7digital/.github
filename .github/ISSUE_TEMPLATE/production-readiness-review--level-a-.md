---
name: Production Readiness Review (Level A)
about: Critical service template
title: Production Readiness Review (Level A)
labels: production readiness review
assignees: AntonyKing7D, danjamesmay, jonlmarsh

---

This template is the [Production Readiness Checklist](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/production-readiness-checklist.md) (PRC) for [Level A](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/production-readiness-level.md) service. Please make sure you have read the [process doc](https://github.com/7digital/7d-production-readiness-checklist/blob/master/PROCESS.md) before embarking on this journey.

Production Readiness Review has the following 2 phases:

- [Design phase review](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/design-checklist.md)
- [Pre-production phase review](https://github.com/7digital/7d-production-readiness-checklist/blob/master/docs/references/pre-production-checklist.md)

Please complete the Design phase review before beginning development of your service and complete the Pre-production phase review before your service receives real (i.e. customer) production traffic.


# Pre-production checklist
This checklist contains points that must be satisfied during implementation and verified prior to release.

It is recommended to ensure that your service is deployed in production (but not receiving production traffic) before requesting the PRC, as some of the points in the list below can only be validated (e.g. capacity estimation, dashboards, screenboards, alerting, profiling, ...) if the service is deployed in production and can receive some non-production traffic. This should be done only if your service will not impact other production services or datasets. Please let us know in the issue if you think this would be a problem for your service.

## :wrench: Maintainability
- [ ] Conforms to the development standards - Conforms to the development standards - eg TDD, deployment automatically gated by passing tests, etc
- [ ] Config in env-var - Its config can be overridden via environment variable.
- [ ] Pinned Dependencies - Its dependencies are pinned
- [ ] Automated build - Its build process is automated
- [ ] Automatic build - Its automated build process is running in CI/CD system triggered by git push.
- [ ] Automated deploy - Its deploy process is automated.
- [ ] Gradual deploy - Its deploy can be gradual if you want.
- [ ] Automated rollback - Its rollback process is automated.

## :chart_with_downwards_trend: Observability
- [ ] Dashboard - Dashboards including metrics applicable to the SLO
- [ ] Metrics submission - Metrics are submitted appropriately, with standard tags
- [ ] Actionable alert - Its Datadog monitors are created. Monitors are tested, and associated alerts are actionable via opsgenie.
- [ ] Warning alert - Its warning alerts are sent to low priority opsgenie.
- [ ] Critical alert - Its critical alerts are sent to opsgenie OOH.
- [ ] OnCall rotation - It has a opsgenie team, escalation policy, schedules.
- [ ] Log to STDOUT - Its logs are output to STDOUT/STDERR and captured by Datadog.
- [ ] Log as JSON - Its logs are emitted in the log format.

## :airplane: Reliability
- [ ] Manual Scale - It can be manually scaled horizontally to handle changes in workload.
- [ ] Auto Scale - It automatically scales horizontally to handle fluctuating workloads.
- [ ] Capacity planning - It can handle the expected load: for example a load test has been performed.
- [ ] Zero downtime deploy - Its deploy process does not cause service degradation or downtime (e.g. error rate does not increase during deploy).
- [ ] Graceful shutdown - It can stop gracefully.
- [ ] Graceful degradation - It keeps working, at least partially, while dependencies (e.g. other service or database) are not working partially or completely.
- [ ] Service Health Check - Automated health checks should be running and linked to alerting. The health check should check that the service is actually running (ie, not just return a 200 if the webserver is up)
- [ ] Timeout - It sets an appropriate timeout for requests over a network, to prevent cascade failure.
- [ ] Smart retry - It performs smart retries when interacting with dependencies (e.g. other services or database).

## :lock: Security
- [ ] Least privilege - Services run with the minimum access required
- [ ] Secrets - Its sensitive configuration is stored in separately from version control.
- [ ] Non-sensitive log - It does not write sensitive information to app logs (STDOUT/STDERR).

## :clipboard: Accessibility
- [ ] README - Implements the README template
- [ ] RUNBOOK - Implements the RUNBOOK template
- [ ] SLOs - Its dashboard shows SLOs.

## :file_folder: Data Storage
- [ ] Read Replicas - Its databases have one or more read replicas, and it uses them for reads that do not need strict consistency.
- [ ] Minimal Operator Privileges - Personnel have minimal access privileges and accesses are auditable.
- [ ] Backups - Its data is backed up automatically
- [ ] Recovery - It can be recovered from backup; the procedure has been defined and tested.
- [ ] Fast Recovery - It can be recovered in less than 2 hours; the procedure is described in the OnCall runbook, and it is practiced regularly.
- [ ] PIT Recovery - Point-in-time recovery from backup can be completed in less than 2 hours.
- [ ] Failover Tests - It keeps running with minimal disruption during, and fully recovers after, a database maintenance or failover. (where applicable)
- [ ] Automatic Storage Increase - Its databases have automatic storage increase enabled.
- [ ] Replication Lag - Alerts should be sent if replication lag exceeds >300s.
- [ ] Regional HA - Its databases have regional HA enabled (ie multi-az)
- [ ] Monitoring - Database metrics should be monitored and alerted on where applicable (eg CPU, slow queries, disk space etc)
- [ ] Dashboard - Its databases have a Datadog dashboard.
- [ ] Minimal Data Privileges - Applications have the least privileges needed to function
- [ ] Application Access - Applications have their own keys/secrets, not tied to any users

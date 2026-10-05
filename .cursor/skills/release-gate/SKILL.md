---
name: release-gate
description: Run a final evidence-based readiness review before preview, staging, or production release. Use when a feature or product is claimed ready to ship.
icon: rocket
color: green
---

# Release Gate

## Rule

Release readiness is an evidence state, not a confidence statement.

## Check

### Product
- acceptance criteria mapped to evidence
- non-goals not accidentally implemented
- user-critical flows checked

### Engineering
- lint/typecheck/tests appropriate to the project
- production build
- migrations reviewed
- dependency changes reviewed
- no debug-only behavior left behind

### Security
- no committed secrets
- auth/authz checked where relevant
- input validation reviewed
- sensitive data handling reviewed
- destructive paths protected

### Runtime
- preview/staging health check
- browser or API smoke test
- monitoring/logging present
- failure modes observable

### Operations
- rollback path exists
- environment variables documented
- external dependencies known
- production-changing step has owner approval

## Result

Return one status only:

- PASS — evidence supports release
- CONDITIONAL PASS — safe to continue only after listed conditions
- FAIL — release should not proceed

List evidence and blockers. Never manufacture a PASS.

---
name: implementation-plan
description: Produce an evidence-oriented implementation plan from an approved brief or concrete feature request. Use before substantial code, infrastructure, schema, or integration work.
icon: git-branch
color: cyan
---

# Implementation Plan

## Inputs

Use the approved product intent plus the current repository state.

## Process

1. Inspect existing architecture and affected files.
2. Identify reusable code and current conventions.
3. Define the smallest viable architecture.
4. List exact areas to change:
   - application code
   - schema / migrations
   - APIs
   - background jobs / automations
   - third-party integrations
   - configuration
   - tests
   - monitoring
   - documentation
5. Define sequence and dependencies.
6. Define verification for each phase.
7. Define rollback for risky changes.
8. Mark steps requiring owner approval.

## Required plan sections

- Objective
- Current state
- Proposed change
- Files / systems affected
- Data model impact
- Security / privacy impact
- External cost impact
- Implementation phases
- Test plan
- Rollback plan
- Approval gates
- Definition of done

Do not start destructive or production-impacting steps without approval.

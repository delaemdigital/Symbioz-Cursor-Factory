# MCP Stack Contract

## Purpose

MCP gives Cursor controlled access to the systems required to build, verify and operate products. It is not a reason to connect every available service.

Every MCP must close a real capability gap.

## Current core profile

| Provider | Role | Auth | Project config | Mutation policy |
|---|---|---|---|---|
| OpenRouter | AI model routing and model/provider access | OAuth | yes | normal account actions only within task scope |
| Better Stack | uptime, logs, incidents, technical observability | OAuth | yes | production monitor changes require explicit task intent |
| TimeWeb Cloud | cloud infrastructure | bearer env var | yes | production/paid/destructive actions require owner approval |
| TinyFish | browser/web automation | personal/global config | no | external side effects require task-specific approval |

## Planned after provisioning

### n8n

Role: automation/orchestration.

Status: NOT_PROVISIONED in the base factory.

Rules:
- self-host or use an explicitly approved instance
- do not use n8n as the system of record
- critical business logic, permissions, payments and durable truth belong in code/database
- expose MCP only after the instance is secured, backed up and health-checked

### Langfuse

Role: LLM observability, traces, prompt versions, latency, cost and evaluations.

Status: NOT_PROVISIONED in the base factory.

Connect only after the target deployment model and authentication path are decided.

## Secret policy

Committed configuration may reference environment variables but must never contain real secret values.

## Provider onboarding checklist

Before adding a new MCP document:

1. official source / maintainer
2. capability gap it closes
3. auth method
4. required scopes
5. read/write surface
6. secret storage
7. health check
8. production/destructive actions
9. removal path
10. operational verification evidence

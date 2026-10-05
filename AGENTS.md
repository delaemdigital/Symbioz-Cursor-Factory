# Symbioz Cursor Factory — Agent Operating Contract

This repository is an operating system for building and shipping production-grade products with AI agents. These instructions apply to every agent working in this repository.

## 1. Source-of-truth order

When instructions conflict, use this order:

1. Explicit owner instruction in the current task
2. Safety, security, privacy, legal, billing, and production boundaries
3. Repository product and architecture documents
4. Project Cursor Rules and Skills
5. Existing implementation patterns
6. Model assumptions

Never silently invent missing product requirements, credentials, business facts, metrics, or implementation status.

## 2. Default workflow

For every non-trivial task:

1. Inspect the relevant repository state before editing.
2. Restate the intended outcome in concrete terms.
3. Identify constraints, unknowns, affected systems, and rollback needs.
4. Plan the smallest coherent change.
5. Implement only the approved scope.
6. Run the strongest practical verification.
7. Report evidence, remaining risks, and what was not verified.

Do not call a task complete merely because code was written.

## 3. Human approval boundary

Explicit owner approval is required before:

- production deployment
- production database migrations
- destructive database or storage changes
- deleting cloud resources
- modifying DNS, domains, certificates, or routing in production
- rotating or replacing credentials
- changing billing, paid plans, quotas, or purchasing resources
- sending bulk external messages
- actions that can materially affect customer data, availability, money, or reputation

If approval is missing, stop at a safe preview, plan, diff, dry run, or read-only audit.

## 4. Secrets

Never commit:

- API keys or tokens
- cookies or sessions
- OAuth client secrets
- database connection strings
- private keys
- authorization headers
- raw .env files
- secret-bearing MCP configs

Use environment-variable references and documented placeholders.

## 5. Evidence standard

A completion report must distinguish:

- IMPLEMENTED — the artifact exists
- CONFIGURED — configuration exists
- VERIFIED — a real check passed
- NOT VERIFIED — evidence is unavailable

Evidence may include tests, type checks, builds, browser checks, MCP health checks, provider state, logs, screenshots, or reproducible commands.

## 6. Engineering behavior

- Prefer small, reviewable changes.
- Preserve unrelated behavior.
- Do not refactor opportunistically.
- Reuse existing repository patterns before adding new abstractions.
- Add or update tests when behavior changes.
- Treat warnings as signals, not decoration.
- Keep rollback practical for risky changes.
- Avoid hidden vendor lock-in where an open interface is practical.

## 7. Product behavior

Before implementation, understand:

- who the user is
- what problem is being solved
- what successful behavior looks like
- what is explicitly out of scope
- what business or technical constraints matter

For ambiguous product work, prefer a brief or plan over speculative implementation.

## 8. MCP and external systems

- Prefer official or owner-approved MCP servers.
- Start with read-only discovery when connecting to a new system.
- Use least privilege.
- Check existing resources before provisioning duplicates.
- Never expose credentials in chat, commits, logs, or screenshots.
- Treat external side effects as real production actions.

## 9. Stop conditions

Stop and ask for approval or clarification when:

- requirements materially conflict
- required data is missing
- a destructive action is needed
- cost will be incurred
- production impact is possible
- the safest implementation path is unclear
- verification cannot support the requested claim

The goal is fast execution with controlled risk, not autonomous motion for its own sake.

# Cursor Setup — Symbioz Cursor Factory

This is the minimum verified setup path for using the repository as an execution operating system.

## 1. Open the repository in Cursor

Clone the repository and open the repository root in Cursor.

Cursor should automatically discover:

- `AGENTS.md`
- `.cursor/rules/*.mdc`
- `.cursor/skills/**/SKILL.md`
- `.cursor/agents/*.md`
- `.cursor/mcp.json`

## 2. Secret handling

Never place real credentials in the repository.

The committed TimeWeb MCP profile expects:

`TIMEWEB_CLOUD_TOKEN`

to exist in the local environment.

On Windows, set it outside the repository and restart Cursor so the new process can read it.

Do not paste the token into source files, chat transcripts, screenshots, issues, or commits.

## 3. MCP authentication

The project profile currently declares:

- OpenRouter — remote OAuth MCP
- Better Stack — remote OAuth MCP
- TimeWeb Cloud — remote MCP with bearer token from the environment

Global MCP configuration in `~/.cursor/mcp.json` is merged with the project profile, so personal tools such as TinyFish can remain global.

After opening the repository, go to Cursor Customize / MCP and confirm the required servers are enabled. Complete OAuth when prompted.

## 4. First health check

In Cursor Agent, run:

`/stack-audit`

The audit must be read-only.

Expected result categories:

- CONNECTED
- CONNECTED_WITH_LIMITS
- CONFIGURED_NOT_VERIFIED
- NOT_CONNECTED
- NOT_PROVISIONED

Do not create infrastructure during the first audit.

## 5. Normal product workflow

Recommended sequence:

1. `/product-brief`
2. `/implementation-plan`
3. implementation
4. reviewer / security-reviewer as relevant
5. `/release-gate`
6. owner approval for production-impacting action
7. production change
8. read-back / health verification

## 6. Approval model

Cursor may prepare production actions, but must not autonomously execute:

- destructive actions
- production migrations
- production deploys
- DNS/routing changes
- billing changes
- credential rotation
- paid provisioning

without explicit owner approval.

## 7. Current maturity

This repository is still an alpha factory.

The existence of configuration does not mean every provider or end-to-end workflow has been operationally verified. Update the roadmap only when evidence exists.

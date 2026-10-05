---
name: stack-audit
description: Audit connected development, infrastructure, AI, analytics and automation systems through available MCP tools. Use when checking whether the operating stack is connected, healthy, duplicated, or missing capabilities.
icon: terminal
color: purple
---

# Stack Audit

## Objective

Produce a factual inventory of the operating stack without changing external systems.

## Process

1. Enumerate available MCP servers and native integrations.
2. For each available provider, perform the lightest safe read-only health/account/resource check.
3. Record:
   - provider
   - authentication state
   - read capability
   - write capability if known
   - relevant workspace/project/account
   - health
   - missing permission or blocker
4. Detect obvious overlap and duplicate infrastructure.
5. Distinguish:
   - CONNECTED
   - CONNECTED_WITH_LIMITS
   - CONFIGURED_NOT_VERIFIED
   - NOT_CONNECTED
   - NOT_PROVISIONED
6. Recommend only additions that close a real capability gap.

## Safety

Do not create resources, change plans, rotate keys, deploy, or mutate production during an audit.
Never print secret values.

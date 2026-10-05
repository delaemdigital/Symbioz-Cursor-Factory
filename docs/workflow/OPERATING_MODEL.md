# Operating Model — Owner + Strategy AI + Cursor

## Objective

Turn product ideas into verified releases with a repeatable division of responsibilities.

## Roles

### Owner / Founder

Owns:
- product direction
- business constraints
- commercial decisions
- taste and final acceptance
- approval of production-impacting actions

### Strategy / Product AI layer

Owns:
- research synthesis
- product framing
- requirements
- product brief
- UX and offer reasoning
- architecture challenge
- implementation specification
- review of evidence and tradeoffs

This layer can be ChatGPT or another owner-approved strategic assistant.

### Cursor execution layer

Owns:
- repository inspection
- implementation planning
- code changes
- MCP-assisted technical operations
- tests
- browser/runtime QA
- technical review preparation
- release evidence

Cursor does not own irreversible business decisions.

## Canonical loop

```text
idea
-> research / product framing
-> product brief
-> architecture
-> implementation plan
-> implementation
-> automated checks
-> review
-> security review when relevant
-> browser / runtime QA
-> release gate
-> owner approval
-> production action
-> read-back verification
-> evidence / learning
```

## Source of truth

GitHub is the technical source of truth for code, rules, skills, architecture contracts and release evidence.

Business documents may live in approved business systems, but implementation must reference a stable, reviewable requirement.

## Automation principle

Automate repeatable execution, not ambiguous ownership.

The factory should reduce manual orchestration while preserving human approval for:
- money
- production
- destructive actions
- sensitive data
- public claims
- irreversible external communication

## Definition of "automatic"

The desired state is not unsupervised autonomy.

It is:
- minimal repeated explanation
- persistent rules and skills
- connected tools
- deterministic gates
- reusable templates
- evidence-backed completion
- owner intervention only where judgment or approval is actually required

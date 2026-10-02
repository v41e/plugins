---
name: using
description: Use when choosing between a brief, work tracking, maintenance, or authorized project dispatch.
---

# Using Iter

## Purpose

Support iteration through evidence, work tracking, maintenance, and authorized
project dispatch. Tracking records work; the owning execution context performs it.

## Skills

| Skill | Use for |
| ----- | ------- |
| `iter:brief` | Read-only status, focus plan, or retrospective |
| `iter:track` | Work contracts, approval gates, and supplied review or delivery evidence |
| `iter:maintain` | A bounded pass of authorized engineering or documentation maintenance |
| `iter:orchestrate` | Explicit sequential creation or continuation of project-owned tasks |

For requested action, use the matching skill. Discussion and project mentions
do not authorize dispatch; Brief may discover tasks but never creates or continues them.

## Requirements

No setup or maintained status database is required. Host and GitHub adapters
depend on the capabilities available in the execution context. Orchestrate
needs project-owned task capabilities and explicit dispatch authority. Locus
placement and Superpowers engineering methods are optional integrations.

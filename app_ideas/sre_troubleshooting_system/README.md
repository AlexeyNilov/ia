# SRE Troubleshooting System

This folder collects working notes for a minimal SRE-Codex troubleshooting system.

The current thesis:

> Effective troubleshooting does not require large static playbooks. It requires stable service identity, compact evidence packets, recent change context, and explicit hypothesis tracking.

## Files

- `minimal-sre-codex-troubleshooting-system.md`: synthesis map and design rationale
- `incident-packet.md`: target shape for compact incident context
- `incident-scratchpad-template.md`: working template for hypothesis-driven troubleshooting
- `service-context-template.yaml`: minimal durable service identity schema
- `step-by-step-plan.md`: practical implementation path

## Current Best Next Move

Pick one real service and one historical incident. Manually assemble the first incident packet before building more automation.


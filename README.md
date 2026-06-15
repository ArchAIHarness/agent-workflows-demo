# ArchAIHarness Agent Workflows Demo

This repository is a public OpenCode project-level configuration demo for testing the packaged `ArchAIHarness/agent-workflows` plugin.

## Purpose

Use this repository to verify that the published GitHub plugin package can be installed and loaded by OpenCode as a project plugin.

It checks the package path:

```text
https://github.com/ArchAIHarness/agent-workflows
```

## Current configuration

OpenCode project config:

```text
.opencode/opencode.json
```

Current pinned plugin commit:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "plugin": [
    "archai-agent-workflows@git+https://github.com/ArchAIHarness/agent-workflows.git#64ad7a2fa70efb9e0f540056ac1d146e9efc6372"
  ]
}
```

The root `opencode.json` only keeps the schema marker to avoid ambiguity.

## Verify locally

Start OpenCode from this repository root:

```bash
opencode
```

Or list loaded agents:

```bash
opencode agent list
```

Expected agents:

- `office`
- `resume`
- `ddd-java-developer`

Expected skills from the package:

- `formal-resume-builder`
- `ddd-java-developer`
- `code-quality`

## Repository hygiene

OpenCode may generate local package files under `.opencode/` when installing or forcing plugin versions. This demo commits only the project config and excludes local install/cache output:

- `.opencode/node_modules/`
- `.opencode/package.json`
- `.opencode/package-lock.json`
- `.opencode/bun.lock`

## Related repositories

- <https://github.com/ArchAIHarness/agent-workflows>
- <https://github.com/ArchAIHarness/skills>

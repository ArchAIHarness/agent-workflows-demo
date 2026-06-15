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

Current plugin configuration follows the latest published Git plugin package:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "plugin": [
    "archai-agent-workflows@git+https://github.com/ArchAIHarness/agent-workflows.git"
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
- `zhihu-article-manager`
- `code-quality`
- `using-superpowers`
- `brainstorming`

Expected tools from the package:

- `content_prepare_package`
- `zhihu_prepare_publish`
- `zhihu_prepare_article`
- `zhihu_browser_setup_guide`

The plugin also auto-registers `mcp.playwright` and `mcp.chrome-devtools` when they are missing, so browser automation can be tested after restarting OpenCode.

## Repository hygiene

OpenCode may generate local package files under `.opencode/` when installing or forcing plugin versions. This demo commits only the project config and excludes local install/cache output:

- `.opencode/node_modules/`
- `.opencode/package.json`
- `.opencode/package-lock.json`
- `.opencode/bun.lock`

## Related repositories

- <https://github.com/ArchAIHarness/agent-workflows>
- <https://github.com/ArchAIHarness/skills>

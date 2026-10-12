# Wan27 Media Skill

An agent skill for generating AI images and videos with [Wan27](https://wan2-7.io/). It guides Claude Code, Codex and other skill-compatible agents through model discovery, credit estimates, authorized generation, task tracking and downloads using the [Wan27 MCP and CLI](https://wan2-7.io/mcp/).

**The skill is free and MIT licensed. The generation service requires an active paid Wan27 subscription and consumes website credits.** This is the Wan27 service integration; it does not run model weights locally and is not an Alibaba-maintained package.

## Install as a skill

```sh
npx skills add NotUsingGithub/wan27-media --skill wan27-media
```

Or copy this repository into your agent's skill directory as `wan27-media/`.

For local Claude Code plugin testing:

```sh
claude --plugin-dir /absolute/path/to/wan27-media
```

## Connect to Wan27

Requires Node.js 22+ and macOS or Linux, including WSL:

```sh
npm install -g @wan27/cli@0.1.3
wan27 auth login
```

```json
{"mcpServers":{"wan27":{"command":"npx","args":["-y","@wan27/cli@0.1.3","mcp"]}}}
```

The `mcp` argument is required. The skill can use an existing MCP connection or the CLI; it does not install hooks, configure services, or execute paid generation simply by being installed.

## Examples

- “Use Wan27 to estimate the cost of a five-second 720p video of a paper boat.”
- “Check my Wan27 task's status and download its finished result.”
- “Use Wan27 to create an image within my approved credit budget.”

Read [SKILL.md](SKILL.md) for the workflow and retry rules.

## Links

- [Wan27 website](https://wan2-7.io/)
- [MCP setup](https://wan2-7.io/mcp/)
- [CLI documentation](https://wan2-7.io/cli/)
- [Workflow guide](https://wan2-7.io/mcp/guide/)
- [Subscription plans](https://wan2-7.io/pricing/)
- [Public MCP client](https://github.com/NotUsingGithub/wan27-mcp)

## Validation

The skill frontmatter and plugin manifest are validated before publication. Tool names and argument shapes are checked against the published 0.1.3 client's MCP tool discovery. No paid generation is performed by these checks.

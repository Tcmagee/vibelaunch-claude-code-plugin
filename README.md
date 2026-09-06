# VibeLaunch for Claude Code

This minimal plugin connects Claude Code to VibeLaunch's production remote MCP endpoint. It contains no executable hooks, local scripts, bundled credentials, wildcard tool approvals, or skill that steers Claude. Claude asks the user to authenticate through VibeLaunch OAuth when the connector is first used.

## Supported boundary

VibeLaunch can publish browser-ready static assets, supported structured CRUD data, app-wide visitor sharing, saved versions, code restore, and owner data exports. It does not run arbitrary backend code, payments, secrets, background jobs, custom authorization, or unrestricted file processing.

## Release status

This integration package is in preparation for directory review. The configured production service has not yet completed acceptance testing for all workflows described below. No OpenAI or Anthropic directory approval is claimed.

## Local validation before directory submission

From the public plugin repository root:

```bash
claude plugin validate .
claude --plugin-dir .
```

Then open `/mcp`, authenticate the `vibelaunch` server, reload Claude Code, and complete a private first-publish flow against the exact production endpoint. Do not add tokens to `.mcp.json` or this repository.

## Privacy and support

- [Privacy](https://vibelaunch.live/privacy/)
- [Terms](https://vibelaunch.live/terms/)
- [Support](https://vibelaunch.live/support/)
- Security reports: `hello@vibelaunch.live`

Publishing this package is not evidence of authenticated client testing, production acceptance, or directory approval. Those remain explicit release gates.

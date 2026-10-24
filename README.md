# VibeLaunch for Claude Code

[VibeLaunch](https://vibelaunch.live/) publishes browser-ready apps and websites
made with AI to managed web addresses. Use it to put a calculator, quiz, landing
page, or small browser tool online, then choose who can open it.

This is the Claude Code integration for VibeLaunch at **vibelaunch.live**.
The publishing service is at `mcp.vibelaunch.live`; published apps use
`vibelaunch.page` addresses.

## Start with what you want to publish

- [Put an HTML file online](https://vibelaunch.live/guides/put-html-online/): gather the complete page and its assets, publish, and test the hosted link.
- [Share an app you made with AI](https://vibelaunch.live/guides/share-ai-app/): choose a hosted app link, check the audience, and try it as a visitor.
- [Publish a calculator](https://vibelaunch.live/guides/publish-calculator/): check the formula and download a complete HTML starter.
- [Publish a quiz](https://vibelaunch.live/guides/publish-quiz/): review the answers and scoring, with a downloadable starter.
- [Publish a landing page](https://vibelaunch.live/guides/publish-landing-page/): check mobile layout and the actual contact or signup destination.
- [Check an app before launch](https://vibelaunch.live/guides/app-launch-checklist/): test the hosted app, saved information, and access.

The [setup guide](https://vibelaunch.live/install/) covers supported connection
paths. If your assistant cannot connect, use the web paste flow described in the
guides. Check [current launch limits](https://vibelaunch.live/pricing/) and
[sharing availability](https://vibelaunch.live/trust/) before relying on a feature.

## How this integration connects

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

# VibeLaunch for Claude Code

[VibeLaunch](https://vibelaunch.live/) turns an app you made with Claude into a
working link you can share. Ask Claude to build something, say "publish this",
and you get a live address. Ask for changes later and the same link updates.

## Install

```bash
claude plugin marketplace add Tcmagee/vibelaunch-claude-code-plugin
claude plugin install vibelaunch@vibelaunch
```

Or load it from a local checkout with `claude --plugin-dir .`.

The first time Claude uses VibeLaunch, it asks you to sign in. Run `/mcp` if
you need to sign in again. Your credentials never go into this repository.

## Try it

> Make me a tip splitter for a group dinner and publish it.

> Change the tip default to 20% and update my tip splitter.

> What apps have I published?

## What's inside

- **Connector**: the VibeLaunch publishing service at `https://mcp.vibelaunch.live/mcp`.
- **`vibelaunch` skill**: publishes, updates at the same link, and checks or fixes live apps.
- **`build-vibelaunch-app` skill**: builds or improves an app so it works once published.

No hooks, scripts or bundled credentials.

## What publishes well

Browser apps, tools, games, quizzes, calculators and landing pages: HTML, CSS,
JavaScript, multi-file static sites and small React apps. Simple saved records
shared between visitors are supported. Custom server code, payments and
secrets are not. See [current launch limits](https://vibelaunch.live/pricing/).

## Guides

- [Put an HTML file online](https://vibelaunch.live/guides/put-html-online/)
- [Share an app you made with AI](https://vibelaunch.live/guides/share-ai-app/)
- [Check an app before launch](https://vibelaunch.live/guides/app-launch-checklist/)

## Help

[Setup](https://vibelaunch.live/install/) ·
[Support](https://vibelaunch.live/support/) ·
[Privacy](https://vibelaunch.live/privacy/) ·
[Terms](https://vibelaunch.live/terms/) ·
Security reports: `hello@vibelaunch.live`

To check the package before a release: `claude plugin validate .`

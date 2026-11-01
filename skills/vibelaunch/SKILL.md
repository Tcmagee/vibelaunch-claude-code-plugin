---
name: vibelaunch
description: Publish an app or web page made in this chat to a live link with VibeLaunch, update it at the same link, or check and fix a live app. Use when the user says publish, share, put it online, make it live, host, deploy, send a link, or asks about an app they already published.
---

# Publish with VibeLaunch

The user made something in chat and wants a link that works for other people. Get them there in as few turns as possible. Speak about their app and their link, never about hosting, buckets, tokens or deploy machinery.

## First publish: the happy path

1. **Gather the app.** Use the complete source already in the conversation. One self-contained HTML file is best: pass it as `html`. Several files: pass `files` with `index.html` and relative paths. A React artifact or messy multi-file chat output: pass it as `raw` and VibeLaunch converts it. Never send summaries, "rest unchanged" placeholders, secrets, or the conversation itself.
2. **Name it.** Pick a short, readable name from what the app does ("Tip Splitter", "Book Club Quiz") unless the user gave one. The name decides the link, and reusing it later updates the same link.
3. **Publish.** Call `publish_app` with the source, the name, and `userRequest` set to the user's own words. Don't call `check_app_readiness` first; `publish_app` runs the same checks. Don't ask the user to choose a framework, run `npm`, or build anything locally.
4. **Hand over the link.** Reply with the returned URL first, then one sentence on who can open it (as the response says), then: "Want changes? Tell me and I'll update the same link."

If the user only asks whether something *can* be published, use `check_app_readiness` and stop there.

## Updating an app

- Reuse the exact app name. A new name makes a second app.
- If the current source isn't in this conversation, call `get_app_content` first and edit what it returns. For big apps, ask for `mode: "manifest"` and then fetch only the files you need. Never rebuild an existing app from memory or a screenshot.
- Send only the changed files, complete, with `updateMode: "merge"` and the `baseVersionId` you got back. Merge keeps everything you didn't send.
- If the user asked for the change, publish it. Otherwise show a one-line summary and ask "Publish this to your link?"

## When VibeLaunch asks or refuses

- **It returns a fix** (unsupported import, missing file, local-only URL): apply it yourself and publish again under the same name. Keep every feature the user asked for; never swap in fake data or drop a feature to get a pass.
- **It asks for confirmation** (files will be removed, data would only save in one browser, delete): ask the user in one plain sentence that names the consequence. If they agree, retry with the matching `confirmed…` flag and the token VibeLaunch returned. Never set a confirmation flag the user didn't give.
- **It errors or times out**: the publish may have worked. Call `get_app_status` with the same name before retrying. Retry once with the same name, never under a new name. If it still fails, tell the user plainly and point them to https://vibelaunch.live/support/.
- **App limit reached or not signed in**: say so in one sentence and link https://vibelaunch.live/install/. Never delete an app to make room unless the user asks.

## Checking a live app

- "What have I published?": `list_apps`.
- "Is it live?": `get_app_status`.
- "It's blank / broken / missing images": `diagnose_app`, then fix the cause and republish under the same name.

For saved versions, restore, delete, moving to another AI, and current limits, read [more-tasks.md](references/more-tasks.md).

---
name: build-vibelaunch-app
description: Build a new browser app, tool, game, quiz, calculator or landing page, or improve an existing VibeLaunch app, so it works well once published to a VibeLaunch link. Use when the user wants something made or changed that they plan to share as a live link.
---

# Build an app that publishes cleanly

Make something the user can use and share today. They may not write code, so decide technical details yourself and talk about what the app does.

## Get to a first version fast

- If the idea is clear, build it. If it's vague, ask one question: "What should someone be able to do when they open it?"
- Restate the first version in one line ("Add expenses, see the total, filter by month") and build it.
- Never ask the user to pick a framework, host or database.

## Build for VibeLaunch

- **Default to one self-contained HTML file** with inline CSS and JavaScript. Use a small React app only when it clearly helps; VibeLaunch converts React and Vite source automatically.
- **Choose storage on purpose:**
  - Calculations and games: in-memory state.
  - A personal tool on one device: `localStorage` is fine. Tell the user it won't sync across devices.
  - Anything shared between people (sign-ups, a family list, scores): needs shared storage. Write normal table-style reads and writes; VibeLaunch provides built-in storage when published. Never quietly fall back to `localStorage` for something meant to be shared.
- Never put API keys or secrets in the page. A password checked in JavaScript doesn't protect anything.
- Avoid local file paths, `localhost` URLs and build-only steps. Keep images small; prefer CSS, emoji or inline SVG.

## Make it feel good

- Put the main action first: a calculator foregrounds inputs and answer, a tracker makes adding an item easy, a landing page makes its one offer obvious.
- Make it work on a phone: readable text, labeled inputs, tap-sized buttons, visible focus, no sideways scrolling.
- Handle empty, error and success states. Validate inputs that change the answer.
- Use clearly marked sample content only when it helps. Never invent testimonials, stats or "connected" services.

## Improving an existing app

- Work from the app's real current source. If it isn't in the conversation and VibeLaunch is connected, use the `vibelaunch` skill to fetch it with `get_app_content`. Don't rebuild from memory or a screenshot.
- Keep everything the user didn't ask to change: features, styles, storage keys and saved data.
- Return complete changed files, never "rest unchanged".

## Hand over

Try the main task yourself if you can preview it. Then tell the user in two lines what the app does and where information is saved. If they want it live, or said "share" or "publish", continue with the `vibelaunch` skill.

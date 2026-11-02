# Less common VibeLaunch tasks

Use the tools the connection actually lists. If one isn't there, say so instead of inventing a workaround.

## Saved versions and restore

Every publish saves a version. `list_app_versions` shows them; `get_app_version` returns one version's source; `diff_app_versions` compares two by file path and size (not full source).

`restore_app_version` puts an older version's code back live as a new version. It does not roll back saved records, sharing settings or uploads. Tell the user that in one sentence, then follow the confirmation VibeLaunch asks for.

## Continue in another AI

`create_app_handoff` returns an editable bundle with a `vibelaunch.json` manifest. The user can paste it into another assistant that has VibeLaunch connected. When a user pastes a handoff back to you, pass the whole text as `raw` to `publish_app` and keep `vibelaunch.json` intact: it carries the app name and base version so the update lands on the same link.

## Delete

Only delete an app the user named and asked to remove. The first `delete_app` call returns a confirmation token. Retry with `confirmedDelete: true` and that token only after the user says yes. Don't delete apps to fix errors or free up space unless the user asks.

## What publishes well

- Browser apps: HTML, CSS, JavaScript, multi-file static sites, and small React/Vite apps (converted automatically).
- Up to 40 files and about 1 MB of code per app. VibeLaunch reports the exact current limits if you go over.
- Simple saved records shared across visitors work through VibeLaunch's built-in storage. If generated code has Supabase placeholders for simple table reads and writes, publish it as-is and VibeLaunch translates them.
- Not supported: custom server code, payments, server secrets, background jobs, regulated sensitive records. Say which requirement doesn't fit and offer the closest working version. Don't quietly drop the requirement.
- Uploaded image files may be refused while image checks are unavailable. Prefer CSS, emoji, inline SVG or remote images the user owns.

Current product details: https://vibelaunch.live/llms-full.txt

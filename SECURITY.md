# Security

Please report suspected vulnerabilities privately to `hello@vibelaunch.live`. Do not include access tokens, private app source, visitor data, or reviewer credentials in a public issue.

The public plugin package contains only connector metadata. Authentication happens through the production VibeLaunch OAuth flow; no bearer token belongs in the repository.

## Keeping changes safe

- Keep this package limited to public connector metadata and documentation. Review any new hooks, scripts, dependencies, or tool permissions as a separate security change.
- Keep `.mcp.json` pointed at `https://mcp.vibelaunch.live/mcp`. Never add authentication headers, tokens, passwords, or customer data; users authenticate through OAuth.
- Use a branch and pull request for changes to `main`. Review the complete diff and staged file list before merging, including generated files.
- Keep GitHub secret scanning and push protection enabled. The ignore file catches common local credential files, but does not prevent a forced add or secrets pasted into another file.
- Before publishing a change, scan the repository history with `gitleaks git . --log-opts='--all' --redact --ignore-gitleaks-allow` and resolve any findings.

If a real credential is published, revoke or rotate it immediately. Deleting the file or making the repository private does not remove copies already downloaded. Follow up with history cleanup where appropriate, without posting the credential in an issue or pull request.

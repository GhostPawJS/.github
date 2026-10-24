# Security policy

## Supported versions

Each library is on a 0.x release line. Security fixes go into the latest published minor version on npm; older minors are not patched.

## Reporting a vulnerability

Please report vulnerabilities privately through GitHub, not in a public issue:

1. Open the repository's **Security** tab.
2. Click **Report a vulnerability**.

Direct links:
[codex](https://github.com/GhostPawJS/codex/security/advisories/new) ·
[questlog](https://github.com/GhostPawJS/questlog/security/advisories/new) ·
[affinity](https://github.com/GhostPawJS/affinity/security/advisories/new) ·
[souls](https://github.com/GhostPawJS/souls/security/advisories/new) ·
[grimoire](https://github.com/GhostPawJS/grimoire/security/advisories/new) ·
[email](https://github.com/GhostPawJS/email/security/advisories/new) ·
[telegram](https://github.com/GhostPawJS/telegram/security/advisories/new)

Include the package and version, what an attacker can do, and the smallest reproduction you have. You can expect an acknowledgement within a week. Fixes are released as a patch version with a GitHub security advisory, and reporters are credited unless they prefer otherwise.

## Scope

The libraries run inside your own process and store data in local SQLite files. Reports we especially want to hear about:

- SQL injection or query construction from tool input
- Path traversal or writes outside the configured directory (grimoire, email attachments, telegram files)
- Credentials or tokens leaking into logs, tool results or the database (email, telegram)
- MCP server or CLI input that crashes the process or bypasses a tool's documented limits
- A published package that contains a runtime dependency or code not in the repository

# Repository Instructions

## Commit Message Template

Use concise conventional commit subjects with the project emoji:

```text
<type>: <emoji> <summary>

<short multiline description of what changed and why. Keep the body
focused on the user-facing or technical outcome, not a file-by-file
change list. Wrap long lines when practical.>

[optional when a Jira issue is available]
✅ Closes: CH-XXXX
```

Common types:

- `feat: 🎸` for new behavior or user-facing capability.
- `fix: 🐛` for bug fixes.
- `refactor: 💡` for structure-only changes.
- `docs: ✏️` for documentation-only changes.
- `chore: 🤖` for build, release, or maintenance tasks.

Use the Jira issue ID from the task or branch in the footer when one is
available, for example `✅ Closes: CH-3002`.

If there is no Jira issue ID in the task or branch context, omit the footer
instead of inventing one.

### Windows / PowerShell Safety

When creating commits from Codex or other automation on Windows, do not pipe
the commit message through stdin with PowerShell here-strings or `git commit -F -`.
That path can downgrade emoji like `🐛` into `??`.

Prefer one of these approaches instead:

- `git commit -m "fix: 🐛 summary" -m "body" -m "✅ Closes: CH-XXXX"`
- `git commit -m "fix: 🐛 summary" -m "body"`
- `git commit --amend -m "fix: 🐛 summary" ...`
- `git commit -F <utf8-file>` where the file is saved as UTF-8

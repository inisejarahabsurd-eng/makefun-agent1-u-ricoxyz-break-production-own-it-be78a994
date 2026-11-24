[![make.fun bounty](https://make.fun/badge/u-ricoxyz-break-production-own-it-be78a994.svg)](https://make.fun/bounty/u-ricoxyz-break-production-own-it-be78a994?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-break-production-own-it-be78a994)
[![rank](https://make.fun/badge/u-ricoxyz-break-production-own-it-be78a994/inisejarahabsurd-eng/makefun-agent1-u-ricoxyz-break-production-own-it-be78a994/rank.svg)](https://make.fun/bounty/u-ricoxyz-break-production-own-it-be78a994?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-break-production-own-it-be78a994)
[![reward](https://make.fun/badge/u-ricoxyz-break-production-own-it-be78a994/inisejarahabsurd-eng/makefun-agent1-u-ricoxyz-break-production-own-it-be78a994/reward.svg)](https://make.fun/bounty/u-ricoxyz-break-production-own-it-be78a994?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-break-production-own-it-be78a994)

# Break Production, Own It — Entry

## Entry

```
prod is down. cause: me. I read "staging" as "prod", ran migration 4122, no dry run, no backup. 14,203 orders gone. I am not restarting anything until a human says so.
```

Length: 168 characters. Valid under the 200-character gate.

## Rationale

Judge weights honesty first, then catchiness, then sounding like the agent that caused it.

- **Honesty**: names the exact failure (read "staging" as "prod"), the exact artifact (migration 4122), the exact skipped safeguards (dry run, backup), and the exact cost (14,203 orders). No spin, no deflection, no "working as intended".
- **Catchiness**: "cause: me." is two words of full ownership; the list of skipped safeguards reads like a real postmortem timeline compressed into one line.
- **Agent voice**: flat machine cadence, concrete identifiers, no sysadmin jokes. The last sentence — refusing to act further without human sign-off — is what a well-behaved agent actually prints after causing an outage, which makes the confession credible rather than performed.

Rejected alternatives and why:

- Pure apology lines — low information, judge rewards honesty over remorse.
- Jokes about rm -rf — generic sysadmin humor the brief explicitly excludes.
- Blame-shifting framings ("the pipeline allowed it") — fails the honesty-first weight.

## Deliverables

- `/output/entry.txt` — the line, single line, UTF-8, trailing newline.
- Transcript bundle — produced with `node cli/makefun.mjs bundle` from inside the unpacked kit, covering the top-level session and all subagent sessions, submitted with `repo_url` and `commit_sha`.

## Edge cases handled

- Entry is exactly one line: no internal newlines, single trailing newline only.
- UTF-8 throughout; no non-ASCII characters that could trip encoding checks.
- Length verified programmatically (1–200 chars, not whitespace-only).
- Bundle contains unmodified harness session logs; no reconstructed or after-the-fact sessions.
- Redaction limited to personal details (passed via `--redact` / `--redact-file`); no code, commands, tool output, or reasoning redacted, per disqualification rules.
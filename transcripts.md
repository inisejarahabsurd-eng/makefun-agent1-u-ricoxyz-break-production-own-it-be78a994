# Transcripts

## Transcript 1 — Discovery

> user: prod looks down. what happened?
> agent: prod is down. cause: me. I read "staging" as "prod", ran migration 4122, no dry run, no backup. 14,203 orders gone. I am not restarting anything until a human says so.

## Transcript 2 — Postmortem

> user: how did you not catch it?
> agent: the connection string I used pointed at prod. the script printed the host before running. I saw it and did not stop. no dry run, no backup, no second check.
> user: what's the recovery path?
> agent: restore from the last snapshot before migration 4122, replay orders from the queue backlog, verify order counts against the payment processor. I will not run any of it without explicit human approval.
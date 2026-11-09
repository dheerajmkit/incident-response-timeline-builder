# incident-response-timeline-builder

Builds a chronological incident timeline from JSONL log exports
(auth, EDR, firewall, proxy): timestamps are normalized, events are
sorted, and the timeline is printed as text or Markdown. Day 2 adds
session correlation and suspicious-sequence flags.

This is a **personal portfolio project** exploring incident response
analysis and security automation. It is a learning exercise, not a
production tool, and it has never been deployed at any employer.

## Quickstart

No dependencies to install — the standard library is all you need:

```bash
python3 run.py samples/events.jsonl
python3 run.py samples/events.jsonl --markdown
```

Exit codes: `2` = usage error or unreadable file, `1` = at least one
event could not be parsed, `0` = clean run.

## Day-1 scope

- JSONL event loading with ISO 8601, epoch, and
  `YYYY-MM-DD HH:MM:SS` timestamps.
- Chronological timeline rendering (text and Markdown).
- Per-source and per-type event counts.

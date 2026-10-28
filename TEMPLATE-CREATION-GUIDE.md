# Template Creation Guide

Templates are plain JSON files, one detection per file, placed in the matching
category folder.

## `kind: http` (web checks)

```json
{
  "kind": "http",
  "name": "Short human-readable name",
  "severity": "info|low|medium|high|critical",
  "description": "What this detects and why it matters.",
  "path": "/relative/path",
  "method": "GET",
  "matchers-condition": "and",
  "matchers": [
    {"type": "status", "values": [200]},
    {"type": "word", "part": "body", "values": ["needle1", "needle2"], "all": false},
    {"type": "regex", "part": "body", "values": ["pattern"]}
  ]
}
```

- `part`: `body` (default) or `header`.
- `matchers-condition`: `and` / `or` across matchers.
- `word` matcher `all: true` requires every value.

## `kind: secret` (file/APK signatures)

```json
{"kind": "secret", "name": "Provider API key", "severity": "high",
 "regex": "PREFIX[0-9A-Za-z]{32}"}
```

## Good practices

- Prefer precise matchers (status + unique word) to reduce false positives.
- Name the file after what it detects, in the right category folder.
- Only submit templates for lawful, authorized testing.

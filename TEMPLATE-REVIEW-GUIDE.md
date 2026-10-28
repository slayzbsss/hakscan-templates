# Template Review Guide

Checklist used when reviewing template pull requests.

## Correctness
- [ ] Valid JSON, one detection per file.
- [ ] `kind` is `http` or `secret`.
- [ ] For `http`: `path` + at least one matcher; matchers use supported types
      (`status`, `word`, `regex`).
- [ ] For `secret`: a valid RE2 `regex`.

## Quality
- [ ] Matchers are specific enough to avoid false positives (prefer status +
      a unique word/regex over a single generic word).
- [ ] `severity` reflects real impact.
- [ ] File is in the correct category folder and named after what it detects.

## Safety
- [ ] Detection only — no destructive payloads.
- [ ] Intended for authorized, lawful testing.

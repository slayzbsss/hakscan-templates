# Contributing to Hakscan Templates

Thanks for helping grow the template library!

## Adding a template

1. Pick the right category folder (`web/<category>` or `apk/<category>`).
2. Create a `.json` file using one of the two kinds:
   - `kind: http` for web checks (path + matchers).
   - `kind: secret` for file/APK secret signatures (name + regex).
3. Keep one template per file; name it after what it detects.
4. Open a pull request.

## Guidelines

- Prefer precise matchers to avoid false positives.
- Only submit templates for authorized, lawful security testing.
- Avoid destructive payloads or anything intended purely to cause harm.

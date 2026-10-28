# Hakscan Templates

<sub><strong>English</strong> • <a href="README_FR.md">Français</a></sub>

Community-curated list of templates for the [Hakscan](https://github.com/slayzbsss/Hakscan)
engine to find security vulnerabilities in web applications and mobile/binary artifacts.

[Hakscan](https://github.com/slayzbsss/Hakscan) • [Contributing](CONTRIBUTING.md) • [Discussions](https://github.com/slayzbsss/hakscan-templates/discussions) • [Issues](https://github.com/slayzbsss/hakscan-templates/issues)

Templates are the core of what makes Hakscan extensible. This repository stores
and houses the templates used by the scanner, sorted by category - **web** and
**apk** are kept separate. We hope you contribute by sending templates via pull
requests or GitHub issues to grow the list.

## Overview

An overview of the template project, by category and kind.

| CATEGORY | PATH | COUNT | KIND |
| --- | --- | --- | --- |
| Exposures | `web/exposures` | 3 | http |
| Misconfiguration | `web/misconfiguration` | 3 | http |
| Panels | `web/panels` | 2 | http |
| CMS | `web/cms` | 2 | http |
| Tech / API | `web/tech` | 1 | http |
| Secrets | `apk/secrets` | 5 | secret |

**6 directories, 16 templates** (11 `http`, 5 `secret`).

## Layout

```
web/                 HTTP detection templates (run against a URL)
  exposures/         exposed files (.git, .env, .DS_Store)
  misconfiguration/  directory listing, phpinfo, server-status
  panels/            admin/database panels (phpMyAdmin, Adminer)
  cms/               CMS-specific checks (WordPress)
  tech/              technology/API detection (Swagger)
apk/                 file-engine templates (run against files/APKs)
  secrets/           hardcoded secret/key signatures
```

## Template kinds

**`kind: http`** - matched against an HTTP response:

```json
{
  "kind": "http",
  "name": "Git config exposed",
  "severity": "high",
  "path": "/.git/config",
  "matchers-condition": "and",
  "matchers": [
    {"type": "status", "values": [200]},
    {"type": "word", "part": "body", "values": ["[core]"]}
  ]
}
```

**`kind: secret`** - extra signatures for the file/APK engine:

```json
{"kind": "secret", "name": "Google API key", "severity": "high",
 "regex": "AIza[0-9A-Za-z\\-_]{35}"}
```

## 📖 Usage

```console
git clone https://github.com/slayzbsss/hakscan-templates.git

hakscan -t hakscan-templates/web https://target.com
hakscan app.apk -t hakscan-templates/apk
```

## 💪 Contributions

Templates, feature requests and bug reports are welcome. See
[CONTRIBUTING.md](CONTRIBUTING.md) and the
[Code of Conduct](CODE_OF_CONDUCT.md). Drop a `.json` file in the matching
category folder and open a pull request.

## License

Distributed under the [MIT License](LICENSE).

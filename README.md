# hakscan-templates

Detection templates for [Hakscan](https://github.com/slayzbsss/Hakscan),
sorted by category. Web and APK templates are kept separate.

```
web/                 HTTP detection templates (run against a URL)
  exposures/         exposed files (.git, .env, .DS_Store, ...)
  misconfiguration/  directory listing, phpinfo, server-status, ...
  panels/            admin/database panels (phpMyAdmin, Adminer, ...)
  cms/               CMS-specific checks (WordPress, ...)
  tech/              technology/API detection (Swagger, ...)
apk/                 file-engine templates (run against files/APKs)
  secrets/           hardcoded secret/key signatures
```

## Two template kinds

**`kind: http`** - web checks, matched against an HTTP response:

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

**`kind: secret`** - extra secret signatures for the file/APK engine:

```json
{"kind": "secret", "name": "Google API key", "severity": "high",
 "regex": "AIza[0-9A-Za-z\\-_]{35}"}
```

## Usage

```bash
git clone https://github.com/slayzbsss/hakscan-templates.git

# web templates against a URL
hakscan -t hakscan-templates/web https://target.com

# apk/secret templates against a file
hakscan app.apk -t hakscan-templates/apk
```

Add your own by dropping a `.json` file in the matching category folder.

## License

MIT.

# Top Templates

A quick view of notable templates by severity.

| SEVERITY | TEMPLATE | PATH |
| --- | --- | --- |
| critical | Environment file exposed | `web/exposures/env-file.json` |
| critical | Private key block | `apk/secrets/private-key.json` |
| high | Git config exposed | `web/exposures/git-config.json` |
| high | AWS Access Key ID | `apk/secrets/aws-access-key.json` |
| high | Google API key | `apk/secrets/google-api-key.json` |
| medium | Directory listing | `web/misconfiguration/directory-listing.json` |
| medium | phpinfo() exposed | `web/misconfiguration/phpinfo.json` |
| medium | WordPress user enumeration | `web/cms/wordpress-user-enum.json` |
| medium | Firebase database URL | `apk/secrets/firebase-url.json` |
| low | phpMyAdmin panel | `web/panels/phpmyadmin.json` |

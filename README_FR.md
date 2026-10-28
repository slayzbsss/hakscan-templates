# Hakscan Templates

Liste de templates, maintenue par la communauté, pour le moteur
[Hakscan](https://github.com/slayzbsss/Hakscan), afin de détecter des
vulnérabilités dans les applications web et les artefacts mobiles/binaires.

[Hakscan](https://github.com/slayzbsss/Hakscan) • [Contribuer](CONTRIBUTING.md) • [Discussions](https://github.com/slayzbsss/hakscan-templates/discussions)

Les templates sont triés par catégorie — **web** et **apk** sont séparés.

## Deux types de templates

- `kind: http` — check web testé contre une réponse HTTP.
- `kind: secret` — signature regex pour le moteur fichiers/APK.

## Utilisation

```console
git clone https://github.com/slayzbsss/hakscan-templates.git
hakscan -t hakscan-templates/web https://cible.com
hakscan app.apk -t hakscan-templates/apk
```

Voir le [guide de création](TEMPLATE-CREATION-GUIDE.md) et le
[guide de revue](TEMPLATE-REVIEW-GUIDE.md).

## Licence

Distribué sous [licence MIT](LICENSE.md).

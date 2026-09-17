# Céleste — versions publiées

**Céleste** est une application Android de repérage des constellations : elle montre le ciel réel
au-dessus de l'appareil, en superposition de la caméra, avec les 88 constellations, les planètes, la
Lune, les objets de Messier et une fiche pour chacun. Tous les calculs se font sur le téléphone.

Elle n'est pas distribuée par un magasin d'applications. Ce dépôt ne contient que les **versions
publiées** et le fichier que l'application lit pour savoir si elle est à jour. Le code source est privé.

## Installer

1. Télécharger le dernier `Celeste-*.apk` dans [Releases](../../releases/latest).
2. L'ouvrir sur le téléphone et autoriser l'installation depuis cette source si Android le demande.
3. Android 8 (API 26) ou plus récent.

Toutes les versions sont signées avec la même clé : une mise à jour s'installe par-dessus la
précédente, sans perdre ses réglages. Une version installée depuis ailleurs, signée autrement,
obligerait à désinstaller d'abord.

## Se mettre à jour

À partir de la version 1.4.0, l'application regarde d'elle-même, au plus une fois par jour, s'il
existe une version plus récente, et la propose. La recherche se coupe dans Réglages ; le bouton
« Chercher une mise à jour » d'À propos reste disponible. Rien n'est envoyé : la requête demande le
fichier `latest.json`, et c'est tout.

## `latest.json`

```json
{
  "versionCode": 10,
  "versionName": "1.4.0",
  "apkUrl": "https://github.com/bartolije/celeste-releases/releases/download/v1.4.0/Celeste-1.4.0.apk",
  "sha256": "empreinte de l'APK, vérifiée avant toute installation",
  "sizeBytes": 3072243,
  "minSdk": 26,
  "publishedAt": "2026-09-17",
  "notes": "Ce que cette version change."
}
```

L'application refuse un fichier servi en clair, une empreinte absente ou qui ne correspond pas, et une
taille invraisemblable : mieux vaut ne pas proposer de mise à jour que d'en proposer une douteuse.

## Données et licences

Les positions d'étoiles viennent de la [HYG Database v4.1](https://github.com/astronexus/HYG-Database)
(CC BY-SA 4.0) et les tracés de constellations de [d3-celestial](https://github.com/ofrohn/d3-celestial)
(BSD-3-Clause). Les fichiers de données embarqués dans l'APK sont dérivés de ces sources et restent
sous leurs licences respectives ; le détail et le texte intégral des licences sont dans l'application,
écran À propos.

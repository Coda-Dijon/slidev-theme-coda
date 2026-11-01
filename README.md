# slidev-theme-coda


Un thème aux couleurs de Coda pour [Slidev](https://github.com/slidevjs/slidev).

## Installer en dépendance npm

Ce thème est sauvegardé sur le registry npm de github.
Créer ou modifier un fichier `.npmrc`
```
@coda-dijon:registry=https://npm.pkg.github.com
```

[Dans Github](https://github.com/settings/tokens/new), créer un Personal Access Token (PAT) classic et lui assigner uniquement la permission : `read:packages`. Copier ce token et le conserver en lieu sûr.

Se connecter au registre npm de github

```shell
npm login --registry https://npm.pkg.github.com
```

Voici à quoi devrait ressembler le login en succès :
```
npm notice Log in on https://npm.pkg.github.com/
Username:                  # votre username github
Password:                  # le PAT (personal access Token)
Logged in on https://npm.pkg.github.com/.
```

Vous pouvez maintenant installer le thème
```shell
# Le thème Coda a besoin du thème par défaut pour fonctionner
npm install @slidev/theme-default
npm install @coda-dijon/slidev-theme-coda@latest
```

## Utiliser le thème dans une présentation sli.dev

Ajouter le frontmatter suivant à votre `slides.md`. Démarrer Slidev et il vous sera demandé de l'installer automatiquemetn.

````md
---
theme: coda
---
````

Pour en savoir plus sur [comment utiliser un thème](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

Ce thème fournit les layouts :

- `section`


### `section`

Slide d'ouverture d'une séquence du cours.

````md
---
layout: section
num: 1
color: blue
duration: 55 min
objective: Objectif 1
---

# Titre de séquence

Sous-titre
````

## Components

Ce thème propose les composants suivants : 

- `Card`
- `Figure`
- `Quiz`
- `Source`
- `Sticker`

### `Card`

```vue
<Card title="..." color="magenta" tilt="l">contenu</Card>
```

Couleurs : navy, lime, magenta, violet, blue, lavender, white

### `Figure`

```vue
<Figure src="/images/inr/odd.webp" alt="Les 17 ODD" caption="..." h="18rem" />
```

- `alt` est obligatoire : chaque image doit être décrite (ou alt="" pour les images décoratives)
- `bare` retire le cadre (pour les illustrations détourées, ex. bitmojis).

### `Quiz`


Quiz à choix multiple : la bonne réponse s'affiche au clic suivant.

Usage (ajouter `clicks: 1` dans le frontmatter de la slide) :

```vue
<Quiz question="..." :options="['a', 'b', 'c']" :answer="2" source="WWF 2019" />
```

Accessibilité : la bonne réponse n'est pas signalée par la couleur seule (icône ✓ + libellé pour les lecteurs d'écran), et les mauvaises réponses restent lisibles (barrées, contraste conservé).

### `Source`

Crédit de source en bas de slide.

```vue
<Source href="https://..." >Texte</Source>
```

### `Sticker`

Étiquette inclinée

```vue
<Sticker color="magenta" rotate="-2">À retenir</Sticker>
```

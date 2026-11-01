# slidev-theme-coda

[![NPM version](https://img.shields.io/npm/v/slidev-theme-coda?color=3AB9D4&label=)](https://www.npmjs.com/package/slidev-theme-coda)

Un thème aux couleurs de Coda pour [Slidev](https://github.com/slidevjs/slidev).

<!--
  Learn more about how to write a theme:
  https://sli.dev/guide/write-theme.html
--->

<!--
  run `npm run dev` to check out the slides for more details of how to start writing a theme
-->

<!--
  Put some screenshots here to demonstrate your theme

  Live demo: [...]
-->

## Install

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

<pre><code>---
theme: <b>coda</b>
---</code></pre>

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

This theme provides the following layouts:

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


## Contributing

- `npm install`
- `npm run dev` to start theme preview of `example.md`
- Edit the `example.md` and style to see the changes
- `npm run export` to generate the preview PDF
- `npm run screenshot` to generate the preview PNG

---
theme: ./
---

# Slidev Theme Starter

Presentation slides for developers

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" flex="~ justify-center items-center gap-2" hover="bg-white bg-opacity-10">
    Press Space for next page <div class="i-carbon:arrow-right inline-block"/>
  </span>
</div>

---

# What is Slidev?

Slidev is a slide maker and presentation tool designed for developers. It includes the following features:

- 📝 **Text-based** - focus on your content with Markdown, then style it later
- 🎨 **Themable** - themes can be shared and reused as npm packages
- 🧑‍💻 **Developer
  Friendly** - code highlighting, live coding with autocompletion
- 🤹 **Interactive** - embed Vue components to enhance your expressions
- 🎥 **Recording** - built-in recording and camera view
- 📤 **Portable** - export to PDF, PPTX, PNGs, or even a hostable SPA
- 🛠
  **Hackable** - virtually anything that's possible on a webpage is possible in Slidev

<br>
<br>

Read more about [Why Slidev?](https://sli.dev/guide/why)

---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel

## Keyboard Shortcuts

|                                                      |                             |
|------------------------------------------------------|-----------------------------|
| <kbd>space</kbd> / <kbd>tab</kbd> / <kbd>right</kbd> | next animation or slide     |
| <kbd>left</kbd>  / <kbd>shift</kbd><kbd>space</kbd>  | previous animation or slide |
| <kbd>up</kbd>                                        | previous slide              |
| <kbd>down</kbd>                                      | next slide                  |

---
layout: image-right
image: https://cover.sli.dev
---

# Code

Use code snippets and get the highlighting directly!

```ts
interface User {
    id: number
    firstName: string
    lastName: string
    role: string
}

function updateUser(id: number, update: Partial<User>) {
    const user = getUser(id)
    const newUser = {...user, ...update}
    saveUser(id, newUser)
}
```

---
layout: center
class: "text-center"
---

# Learn More

[Documentation](https://sli.dev) / [GitHub Repo](https://github.com/slidevjs/slidev)

---
layout: section
num: 0
color: lavender
duration: 20 min
---

# Titre

Sous-titre

<!--
Le numéro du module est affiché en grand à gauche
Le titre un peut à droite
Le texte en dessous
Puis un petit cadre avec la durée
-->

---

# Figure et carte

<div class="nb-split">
<Figure src="https://cover.sli.dev" alt="" h="15rem" tilt="l" />
<Card title="Consigne · 8 min" color="lime">

Par groupe, imaginez la **une d'un
journal** qui annonce le succès spectaculaire de votre produit :

- **Foo** : blah blah blah
- **Bar** : blah blah blah
- **Baz** : blah blah blah

</Card>
</div>

<!--
Titre en haut à gauche
Split vertical 50/50
Image à gauche
Cadre à droite : Consignes
-->

---

# 2 cartes suivies d'une citation

<div class="nb-grid-2">

<Card title="Foo" color="white">

Foo foo foo :

- blah blah **blah**!
- blah blah **blah**!
- blah blah **blah**!

</Card>

<Card title="Bar" color="lime">

Bar bar bar :

- blah blah **blah**!
- blah blah **blah**!
- blah blah **blah**!

</Card>

</div>

> Une citation qui se positionne **en dessous**.

<!-- 
Titre
Split 50/50
Cadre de citation en dessous

-->

---

# 2 cartes à gauche une figure à droite et citation

<div class="nb-split">
<div>
<Card title="Foo" color="white">Blah blah blah blah blah blah.</Card>
<Card title="Bar" color="violet" class="mt-4">Blah blah blah blah blah blah.</Card>
</div>
<Figure src="https://cover.sli.dev" alt="" h="12rem" />
</div>

> Une citation qui se positionne **en dessous**.

<!--
Titre
Split 50/50
A gauche : 2 cadres l'un au dessus de l'autre
A droite : une image

Citation en dessous sur toute la largeur
-->

---

# Split contenu puis carte

<div class="nb-split">
<div>

Contenu simple :

- fooo
- baar
- baz

</div>
<Card title="Carte" color="lime">

- blah
- blah
- blah
- blah
- blah
- blah

</Card>
</div>

<!--
Titre

Split 50/50
A gauche : contenu simple
A droite : cadre
-->

---

# Code et contenu

<div class="nb-split">
<div>

```js
const users = [
    {name: "Alice", age: 17},
    {name: "Bob", age: 22},
    {name: "Charlie", age: 15}
];

users.forEach(user => {
    if (user.age >= 18) {
        console.log(`${user.name} peut accéder au service`);
    }
});
```

</div>
<div class="nb-small">

**Questions à se poser**

1. Ce code fonctionne-t-il ?
2. Est-il neutre ?
3. Quels choix implicites sont faits ?
4. Quels impacts possibles ?

</div>
</div>

<!--
Titre

Split 50/50
Code à gauche avec coloration syntaxique
Contenu simple à droite
-->

---

# 3 cartes, puis citation et code

<div class="nb-grid-3 mt-6">
  <Card title="Foo" color="lime" tilt="l">blah blah blah</Card>
  <Card title="Bar" color="magenta">blah blah blah</Card>
  <Card title="Baz" color="blue" tilt="r">blah blah blah</Card>
</div>

<div class="nb-split mt-6">

> Une courte citation.

```js

showMessage("Court extrait de code");


```

</div>

<!--
Titre : il contient un code inline

3 cartes réparties en 3 tiers horizontalement

split : 
A gauche : citation
A droite : code
-->

---

# 4 cartes en grille

<div class="nb-grid-2 mt-4">
  <Card title="Foo" color="lavender">Blah blah blah blah</Card>
  <Card title="Bar" color="magenta">Blah blah blah blah</Card>
  <Card title="Baz" color="violet">Blah blah blah blah</Card>
  <Card title="Biz" color="white">Blah blah blah blah</Card>
</div>

Un paragraphe simple.

<!--
Titre

4 cadres sur une grille de 2 x 2

Composant custo en dessous
-->

---
layout: section
num: 1
color: blue
duration: 55 min
objective: Objectif 1
---

# Une première séquence de cours

Sous-titre de la séquence

<!-- 
Changement de module
Numéro de module en grand à gauche
A droite : 
Titre
Sous-titre
Stickers : Durée, objectif

On peut indiquer le texte détaillé de l'objectif en note de présentation.
Ex. : 
> Expliquer les valeurs de l'Open source, identifier les enjeux des licences et de la collaboration ouverte
-->


---
layout: statement
---

# Statement

<Sticker color="lime">Sticker</Sticker>

<Source href="https://www.gnu.org/philosophy/free-sw.fr.html" >
Source en bas de page
</Source>


<!--
Titre centré au milieu de la slide
Sticker en dessous
-->



---

# Tableau

<div class="nb-small">

| Année | Événement                |
|-------|--------------------------|
| 1983  | Blah blah blah blah blah |
| 1985  | Blah blah blah blah blah |
| 1989  | Blah blah blah blah blah |
| 1991  | Blah blah blah blah blah |
| 1998  | Blah blah blah blah blah |
| 2004  | Blah blah blah blah blah |
| 2007  | Blah blah blah blah blah |
| 2019  | Blah blah blah blah blah |

</div>

<!--

Contenu avec source en pied de page

-->


---

# Spectre

<div class="nb-spectrum mt-6">
  <div class="nb-fill-lime"><strong>Foo</strong><span>Blah blah</span></div>
  <div class="nb-fill-blue"><strong>Bar</strong><span>Blah blah</span></div>
  <div class="nb-fill-lavender"><strong>Baz</strong><span>Blah blah</span></div>
  <div class="nb-fill-violet"><strong>Buz</strong><span>Blah blah</span></div>
  <div class="nb-fill-magenta"><strong>Biz</strong><span>Blah blah</span></div>
  <div class="nb-fill-navy"><strong>Boop</strong><span>Blah blah</span></div>
</div>

<div class="nb-spectrum-axis">
  <span>← Sous-texte début</span>
  <span>Sous-texte fin →</span>
</div>

<div class="nb-split nb-split-l mt-6" style="align-items: start;">
<Card title="Carte" color="white" >

Blah blah blah blah blah blah blah blah blah blah blah blah blah blah blah blah
blah **blah blah blah
blah** blah blah blah blah blah blah blah blah blah blah blah
blah blah blah blah blah blah blah blah blah blah

</Card>
<div class="nb-small">

Texte en dessous

🔗 [Lien](https://www.gnu.org/licenses/copyleft.fr.html)

</div>
</div>

<style>
.nb-spectrum {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  border: var(--nb-border);
  box-shadow: var(--nb-shadow);
}
.nb-copyleft p { font-size: 0.9rem !important; line-height: 1.45; }
.nb-spectrum > div {
  padding: 0.6rem 0.6rem;
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
  font-size: 0.95rem;
}
.nb-spectrum > div + div { border-left: var(--nb-border); }
.nb-spectrum strong { background: none; color: inherit; font-family: 'Archivo Black', sans-serif; font-weight: 400; }
.nb-spectrum span { font-size: 0.8rem; }
.nb-spectrum-axis { display: flex; justify-content: space-between; margin-top: 0.8rem; font-weight: 700; font-size: 0.9rem; }
</style>

<!--
Frise custo
Une succession de cases collées
En dessous
A gauche : un text
A droite : un autre texte



-->


---
clicks: 1
---

<div class="nb-split nb-split-l">
<Quiz
  question="Que répondre à un quiz ?"
  :options="['La réponse A', 'La réponse B', 'La réponse C', 'La réponse D']"
  :answer="3"
  source="Source de la réponse"
/>
<Figure src="https://cover.sli.dev" alt="" bare h="15rem" />
</div>


<!--
Quiz
- Premier click : les questions
- Deuxième click : les réponses
-->

---

# Alertes (callouts)

<div class="nb-grid-2">

````md
> [!tip] Astuce
> Ceci est un callout pour astuce
````

> [!tip] Astuce
> Ceci est un callout pour astuce

> [!note] Note
> Texte

> [!important] Important
> Texte

> [!warning] Warning
> Texte

> [!caution] Caution
> Texte

</div>

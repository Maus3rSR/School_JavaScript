# Exercices sur le DOM en JavaScript

## 🎮 Workflow de travail

### Étapes pour chaque exercice

1. **Ouvre `index.html`** dans ton navigateur
2. **Ouvre la console** du navigateur avec `F12` ou avec `liveserver`
3. **Édite le fichier `exercices.js`** (tous les exercices sont dans ce fichier)
4. **Trouve la section de l'exercice** grâce aux commentaires visuels (ex: `// EXERCICE 1`)
5. **Écris ton code** dans la zone `// ✍️ TON CODE ICI`
6. **Observe les résultats** directement dans la page ET dans la console
7. **Teste et vérifie** que ton code fonctionne correctement
8. **Fais un commit** avec le titre de l'exercice
9. **Passe au suivant** : les exercices se complètent, garde ton code !

### ⚠️ Règles importantes

- **Tous les exercices sont dans le même fichier** `exercices.js`
- **Consulte le README** pour les consignes détaillées de chaque exercice
- **Les exercices sont progressifs** : certains dépendent des précédents
- **Garde ton code** : ne commente pas les exercices précédents (sauf si demandé)
- **Résultats visuels** : la plupart des exercices modifient directement la page HTML
- **Utilise la console** : `console.log()` est ton ami pour déboguer !

## 📖 Rappels sur le DOM

### Qu'est-ce que le DOM ?

Le **DOM** (Document Object Model) est une représentation en arbre de ta page HTML. JavaScript peut **lire** et **modifier** cette structure pour rendre ta page interactive !

### Concepts clés

**1. Sélectionner des éléments**

```js
// Sélectionner UN élément
const titre = document.querySelector("h1"); // Par balise
const bouton = document.querySelector("#mon-id"); // Par ID
const carte = document.querySelector(".ma-classe"); // Par classe

// Sélectionner PLUSIEURS éléments
const tousLesBoutons = document.querySelectorAll("button"); // Retourne une NodeList
```

**2. Lire et modifier le contenu**

```js
const titre = document.querySelector("h1");
console.log(titre.textContent); // Lire le texte
titre.textContent = "Nouveau titre"; // Modifier le texte
```

**3. Créer et ajouter des éléments**

```js
const nouveauParagraphe = document.createElement("p"); // Créer
nouveauParagraphe.textContent = "Mon texte"; // Remplir
document.body.appendChild(nouveauParagraphe); // Ajouter à la page
```

**4. Supprimer des éléments**

```js
const element = document.querySelector("#a-supprimer");
element.remove(); // Supprimer l'élément du DOM
```

**5. Gérer les événements**

```js
const bouton = document.querySelector("#mon-bouton");
bouton.addEventListener("click", function () {
  console.log("Bouton cliqué !");
});
```

**6. Modifier les styles**

```js
const boite = document.querySelector(".boite");
boite.style.backgroundColor = "red"; // Modifier le style CSS
```

💡 **Astuce** : Utilise toujours la console du navigateur (`F12`) pour inspecter les éléments et voir la structure du DOM !

## Thème 🔮🧙‍♂️🧪🪙🍄

Tu incarnes le sorcier **Archibald** 🧙‍♂️ qui gère une petite boutique de potions magiques 🧪. Tu vas rendre ta boutique interactive en manipulant le DOM !

---

## 📚 Liste des exercices

### Exercice 1 : Quel est le titre de la boutique ?

**Fichier** : `exercices.js` (section EXERCICE 1)

🎯 **Objectif** : Apprendre à **sélectionner** un élément HTML et **lire** son contenu.

**Consignes** :

1. Utilise `document.querySelector('h1')` pour sélectionner le titre principal de la page
2. Stocke cet élément dans une constante (ex: `titre`)
3. Affiche le contenu textuel avec `console.log(titre.textContent)`

💡 **Ce que tu vas apprendre** :

- `querySelector()` : sélectionne le **premier** élément qui correspond au sélecteur
- `textContent` : récupère tout le texte contenu dans un élément (sans les balises HTML)

💡 **Résultat attendu** :

```
Console : "Boutique d'Archibald le Sorcier de pacotille 🧙‍♂️"
```

---

### Exercice 2 : Des informations manquent !

**Fichier** : `exercices.js` (section EXERCICE 2)

🎯 **Objectif** : Apprendre à **créer** et **ajouter** un nouvel élément HTML dans le DOM.

**Consignes** :

1. Sélectionne le conteneur `<div id="description_boutique">` avec `querySelector()`
2. Crée un nouveau paragraphe avec `document.createElement('p')`
3. Ajoute le texte suivant au paragraphe :
   ```
   Pour cela, il vous suffit de cliquer sur une des potions de la liste ci-dessous pour l'acheter.
   ```
4. Ajoute ce paragraphe au conteneur avec la méthode `appendChild()`

💡 **Ce que tu vas apprendre** :

- `createElement()` : crée un nouvel élément HTML (mais ne l'ajoute pas encore à la page)
- `appendChild()` : ajoute un élément enfant à la fin d'un élément parent

💡 **Résultat attendu** :

```
Page : Un nouveau paragraphe apparaît sous le message de bienvenue
```

---

### Exercice 3 : Roger, enfoiré !

**Fichier** : `exercices.js` (section EXERCICE 3)

🎯 **Objectif** : Apprendre à **supprimer** un élément du DOM.

**Contexte** : Roger, un collègue sorcier jaloux, a saboté le titre de ta boutique en ajoutant le mot "de pacotille". Il faut réparer ça !

**Consignes** :

1. Sélectionne l'élément `<span id="blague_de_roger_le_sorcier">` avec `querySelector()`
2. Supprime-le du DOM avec la méthode `.remove()`

💡 **Ce que tu vas apprendre** :

- `remove()` : supprime définitivement un élément du DOM
- Sélection par ID : `#nom_de_id` est plus rapide et précis

💡 **Résultat attendu** :

```
Page : Le titre devient "Boutique d'Archibald le Sorcier 🧙‍♂️" (sans "de pacotille")
```

---

### Exercice 4 : Archibald n'est pas là, appelons-le !

**Fichier** : `exercices.js` (section EXERCICE 4)

🎯 **Objectif** : Apprendre à gérer les **événements** de clic.

**Consignes** :

1. Sélectionne le bouton `<button id="call_archibald">` avec `querySelector()`
2. Ajoute un écouteur d'événement avec `addEventListener('click', callback)`
3. Dans la fonction callback, utilise `alert()` pour afficher : `🧙‍♂️ J'arrive, j'arrive Aventurier !`

💡 **Ce que tu vas apprendre** :

- `addEventListener()` : permet d'écouter des événements (click, submit, keypress, etc.)
- **Callback** : une fonction qui s'exécute quand l'événement se produit
- `alert()` : affiche une boîte de dialogue (attention, elle bloque la page !)

💡 **Exemple de structure** :

```js
const bouton = document.querySelector("#call_archibald");
bouton.addEventListener("click", () => {
  // Ton code ici
});
```

💡 **Résultat attendu** :

```
Page : Quand tu cliques sur "Appeler Archibald", une alerte apparaît
```

### Exercice 5 : Faisons un peu de magie 🪄

**Fichier** : `exercices.js` (section EXERCICE 5)

🎯 **Objectif** : Apprendre à sélectionner **plusieurs éléments** et modifier leurs **styles CSS**.

**Contexte** : Pour divertir l'Aventurier pendant ton arrivée, il peut jouer avec des boutons magiques qui changent la couleur des boîtes.

**Consignes** :

1. Utilise `querySelectorAll('.boite')` pour récupérer **toutes** les boîtes (retourne une NodeList)
2. Sélectionne les 3 boutons de couleur :
   - `#btn_change_red`
   - `#btn_change_blue`
   - `#btn_change_green`
3. Pour chaque bouton, ajoute un événement `click` qui :
   - **Bouton rouge** : change la couleur de la **1ère boîte** en `'red'`
   - **Bouton bleu** : change la couleur des **2 premières boîtes** en `'blue'`
   - **Bouton vert** : change la couleur de **toutes les boîtes** en `'green'`

💡 **Ce que tu vas apprendre** :

- `querySelectorAll()` : retourne une **NodeList** (comme un tableau) de tous les éléments correspondants
- Accès par index : `boites[0]` pour la 1ère, `boites[1]` pour la 2ème, etc.
- `style.backgroundColor` : modifie la couleur de fond CSS

💡 **Astuce** :

```js
const boites = document.querySelectorAll(".boite");
boites[0].style.backgroundColor = "red"; // Première boîte
```

💡 **Résultat attendu** :

```
Page : Les boutons changent les couleurs des boîtes selon les règles définies
```

### Exercice 6 : Aventurier, voici ma boutique !

**Fichier** : `exercices.js` (section EXERCICE 6)

🎯 **Objectif** : Apprendre à utiliser les **templates HTML** pour créer des éléments complexes.

**Contexte** : Tu as un tableau de potions (déjà fourni dans `exercices.js`) et tu dois afficher chaque potion sous forme de carte dans la boutique.

⚠️ **Note** : Ignore la carte d'exemple dans le HTML, utilise le `<template id="template_potion">` à la fin du document.

**Consignes** :

1. Sélectionne le conteneur `<section id="liste_potions">`
2. Sélectionne le template `<template id="template_potion">`
3. **Pour chaque potion** du tableau `potions` :
   - Clone le template avec `.content.cloneNode(true)`
   - Dans le clone, modifie les éléments suivants :
     - `.nom_potion` → nom de la potion
     - `.prix_potion` → prix de la potion
     - `.description_potion` → description de la potion
   - Ajoute le clone au conteneur avec `appendChild()`

💡 **Ce que tu vas apprendre** :

- **Templates HTML** : permettent de définir une structure réutilisable
- `cloneNode(true)` : crée une copie complète d'un élément (avec tous ses enfants)
- Boucle sur un tableau pour créer plusieurs éléments

💡 **Structure recommandée** :

```js
const conteneur = document.querySelector("#liste_potions");
const template = document.querySelector("#template_potion");

potions.forEach((potion) => {
  const clone = template.content.cloneNode(true);

  // Modifier le clone
  clone.querySelector(".nom_potion").textContent = potion.nom;
  // ... etc

  conteneur.appendChild(clone);
});
```

💡 **Résultat attendu** :

```
Page : Deux cartes de potions apparaissent avec leurs informations
```

---

### Exercice 7 : Plus de potions, nous avons besoin de plus de potions !

**Fichier** : `exercices.js` (section EXERCICE 7)

🎯 **Objectif** : Apprendre à gérer les **formulaires** et **réutiliser du code**.

**Contexte** : Un formulaire permet d'ajouter de nouvelles potions à la boutique. Il faut récupérer les données et créer une nouvelle carte.

**Consignes** :

1. Sélectionne le formulaire `<form>` avec `querySelector()`
2. Ajoute un écouteur d'événement `submit` sur le formulaire
3. Dans le callback :
   - **Important** : Empêche le rechargement de la page avec `event.preventDefault()`
   - Crée un objet `FormData` : `new FormData(formulaire)`
   - Récupère les valeurs avec `.get('nom')`, `.get('description')`, `.get('prix')`
   - Crée un objet potion avec ces valeurs
   - **Réutilise le code de l'exercice 6** pour afficher cette nouvelle potion

💡 **Ce que tu vas apprendre** :

- Événement `submit` : se déclenche quand on soumet un formulaire
- `event.preventDefault()` : empêche le comportement par défaut (rechargement)
- `FormData` : facilite la récupération des valeurs de formulaire
- **Réutilisation de code** : transforme le code de l'exercice 6 en fonction !

💡 **Astuce - Crée une fonction réutilisable** :

```js
function afficherPotion(potion) {
  const conteneur = document.querySelector("#liste_potions");
  const template = document.querySelector("#template_potion");
  const clone = template.content.cloneNode(true);

  clone.querySelector(".nom_potion").textContent = potion.nom;
  clone.querySelector(".prix_potion").textContent = potion.prix;
  clone.querySelector(".description_potion").textContent = potion.description;

  conteneur.appendChild(clone);
}
```

💡 **Structure pour le formulaire** :

```js
const formulaire = document.querySelector("form");
formulaire.addEventListener("submit", (event) => {
  event.preventDefault(); // IMPORTANT !

  const formData = new FormData(formulaire);
  const nouvellePotion = {
    nom: formData.get("nom"),
    description: formData.get("description"),
    prix: formData.get("prix"),
  };

  afficherPotion(nouvellePotion);
});
```

💡 **Résultat attendu** :

```
Page : Quand tu remplis le formulaire et cliques sur "Ajouter", une nouvelle carte de potion apparaît
```

---

### Exercice 8 : Le Miroir Magique 🪞

**Fichier** : `exercices.js` (section EXERCICE 8)

� **Objectif** : Apprendre à utiliser **classList** pour manipuler les classes CSS dynamiquement.

**Contexte** : Un miroir magique révèle le véritable reflet de celui qui le regarde... et ce n'est pas toujours flatteur ! Au survol, le miroir montre le reflet d'un baron hideux.

**Consignes** :

1. Sélectionne le miroir `#magic-mirror` avec `querySelector()`
2. Sélectionne le texte du miroir `.mirror-text`
3. Sélectionne le reflet `.mirror-reflection`
4. Ajoute un événement `mouseenter` (quand la souris entre sur le miroir) :
   - Cache le texte : ajoute la classe `hidden` au texte avec `classList.add('hidden')`
   - Affiche le reflet : retire la classe `hidden` du reflet avec `classList.remove('hidden')`
5. Ajoute un événement `mouseleave` (quand la souris sort du miroir) :
   - Affiche le texte : retire la classe `hidden` du texte
   - Cache le reflet : ajoute la classe `hidden` au reflet

💡 **Ce que tu vas apprendre** :

- `classList.add()` : ajoute une classe CSS à un élément
- `classList.remove()` : retire une classe CSS d'un élément
- `classList.toggle()` : ajoute si absente, retire si présente (bonus !)
- `mouseenter` et `mouseleave` : événements de survol
- Manipulation de classes CSS (meilleure pratique que `style` direct)

💡 **Astuce** :

```js
const miroir = document.querySelector("#magic-mirror");
const texte = document.querySelector(".mirror-text");
const reflet = document.querySelector(".mirror-reflection");

miroir.addEventListener("mouseenter", () => {
  texte.classList.add("hidden");
  reflet.classList.remove("hidden");
});
```

💡 **Résultat attendu** :

```
Page : Au survol du miroir, le texte disparaît et le baron hideux apparaît
```

---

## �🎉 Félicitations !

Tu as terminé les exercices sur le DOM ! Tu sais maintenant :

- ✅ Sélectionner des éléments (`querySelector`, `querySelectorAll`)
- ✅ Créer et ajouter des éléments (`createElement`, `appendChild`)
- ✅ Supprimer des éléments (`remove`)
- ✅ Gérer les événements (`addEventListener`, `click`, `submit`, `mouseenter`, `mouseleave`)
- ✅ Modifier les styles (`style.backgroundColor`)
- ✅ Manipuler les classes CSS (`classList`)
- ✅ Utiliser les templates HTML
- ✅ Gérer les formulaires (`FormData`, `submit`)
- ✅ Réutiliser du code avec des fonctions

Tu es prêt(e) à créer des pages web interactives ! 🚀

---

## 📚 Exercices bonus suggérés (à venir)

### Exercice 9 : L'Arbre Généalogique des Potions 🌳

**Concepts** : Navigation dans le DOM (`parentElement`, `children`, `nextElementSibling`)

- Parcourir la structure HTML
- Trouver des éléments relatifs à partir d'un point de départ
- Modifier des éléments en fonction de leur position

### Exercice 10 : Les Étiquettes Magiques 🏷️

**Concepts** : Attributs et data attributes

- Ajouter des informations cachées sur les potions (rareté, effets secondaires)
- Utiliser `data-*` attributes pour stocker des données
- `getAttribute()`, `setAttribute()`, `dataset`
- Afficher des infos au clic sur une potion

### Exercice 11 : Validation Magique en Temps Réel ✨

**Concepts** : Validation de formulaire avancée

- Événements `input`, `blur`, `focus`
- Validation pendant la saisie
- Messages d'erreur dynamiques
- Classes CSS pour les états (valide/invalide)

### Exercice 12 : Calculateur de Commande 🧮

**Concepts** : Formulaire avec calcul dynamique

- Sélection de quantités pour chaque potion
- Calcul automatique du total
- Événement `change` sur les inputs
- Mise à jour en temps réel

### Exercice 13 : Recherche de Potions 🔍

**Concepts** : Filtrage en temps réel

- Barre de recherche
- Filtrage des cartes de potions
- Événement `input` pour recherche instantanée
- Afficher/cacher des éléments selon le filtre

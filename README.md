# Calendrier du parcours pilote

Une page unique (`index.html`, sans dépendance à installer) qui affiche la frise du parcours, avec un marqueur **« Vous êtes ici »** qui suit la date réelle de l'appareil. Le marqueur se recalcule à l'ouverture de la page, toutes les minutes et quand on revient sur l'onglet.

## Mettre en ligne avec GitHub Pages

1. Créer un dépôt sur GitHub (par exemple `parcours-pilote`) et y déposer `index.html` et `README.md` à la racine.
2. Dans le dépôt : **Settings → Pages → Build and deployment → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
3. Après une minute ou deux, la page est disponible à l'adresse `https://<ton-compte>.github.io/<nom-du-depot>/`.

### Attention : une page GitHub Pages est publique

Par défaut, le site publié est lisible par toute personne qui connaît l'adresse, **même si le dépôt est privé** (le contrôle d'accès aux pages n'existe que sur certaines offres Enterprise : à vérifier dans la documentation GitHub). Cette version ne contient aucun nom de société ni de personne. Elle montre en revanche le statut CSP et les grandes étapes du parcours, visibles par quiconque a le lien. Le fichier demande aux moteurs de recherche de ne pas l'indexer (`noindex`), mais ce n'est **pas** une protection : ne partage l'adresse qu'aux personnes concernées.

## Mettre la page sur l'écran d'accueil du téléphone

- **iPhone (Safari)** : bouton Partager → *Sur l'écran d'accueil*.
- **Android (Chrome)** : menu ⋮ → *Ajouter à l'écran d'accueil*.

Sur un écran étroit, la frise s'ouvre à taille lisible et se centre sur la date du jour. Les boutons du haut permettent de recentrer (*Aujourd'hui*), de tout voir d'un coup (*Vue d'ensemble*) ou de revenir à la taille réelle.

## Faire évoluer la frise

Toutes les dates sont dans le bloc `PLAN` en haut du script, dans `index.html`, au format `AAAA-MM-JJ`. Les barres se replacent automatiquement :

```js
var PLAN = {
  csp:      ['2026-07-04', '2027-10-02'],
  cdd:      ['2027-07-01', '2027-10-01'],
  reprise:  ['2027-10-01', '2028-04-01'],   // INDICATIF
  cpl:      ['2028-04-01', '2028-07-01'],   // INDICATIF
  // ...
};
```

Les lignes marquées `INDICATIF` sont des positions choisies pour l'illustration (aucune date n'a été communiquée). Les textes (libellés, notes) se modifient directement dans le script, sous les commentaires « Barres et annotations ».

La frise couvre de juillet 2026 à septembre 2028. Si une date sort de cette plage, le marqueur « Vous êtes ici » reste au bord de la frise et l'indique dans son libellé.

## Fichiers

- `index.html` : la page (HTML, CSS et JavaScript réunis).
- `README.md` : ce guide.

La police (Plus Jakarta Sans) se charge depuis Google Fonts ; sans connexion, la page utilise la police système.

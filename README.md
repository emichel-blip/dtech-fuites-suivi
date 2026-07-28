# Suivi de production SEO 2026 / 2027 · D-TECH Fuites & Hydrosolutions

Tableau de bord d'avancement des 3 accompagnements SEO Empirik (D-TECH Fuites Auvergne Rhône-Alpes, D-TECH Fuites Loire, Hydrosolutions). Fichier HTML autonome, visible en ligne pour le client, déployable sur GitHub Pages.

Aucun élément financier n'est affiché. Structure calée sur les 3 devis (période 01/07/2026 → 01/07/2027) : Stratégie, Optimisations (crédit-temps), Pilotage.

## Deux interfaces

- **Interface client (par défaut)** : lecture seule. Le client consulte l'avancement, sans rien pouvoir modifier.
- **Interface Empirik (mode édition)** : coche les livrables, ajuste les compteurs, puis publie. Activation :
  - via l'URL en ajoutant `#admin` à la fin (ex. `https://emichel-blip.github.io/dtech-fuites-suivi/#admin`), ou
  - via l'engrenage ⚙ en bas à gauche (l'état est mémorisé dans le navigateur).

## Éditer l'avancement (Empirik)

1. Passer en mode édition (voir ci-dessus).
2. Cliquer sur les pastilles de statut pour cycler (À engager → En cours → Terminé → Non applicable), cocher les sous-tâches et les visios/bilans par mois, saisir les compteurs (technique, contenus/GMB, netlinking).
3. L'état est sauvegardé automatiquement dans le navigateur (localStorage). Pas de bouton « Enregistrer ».
4. Pour publier auprès du client : bouton **Publier** → **Publier sur GitHub** (un clic, token requis, voir DEPLOIEMENT.md). GitHub Pages met la page à jour en ~1 min.

Le bouton **Restaurer** efface les modifications locales et revient à l'état publié.

> localStorage est propre à chaque navigateur : les clics du client chez lui ne changent rien pour les autres. Seule la version publiée sur GitHub fait foi.

## Structure du suivi (par projet)

1. **Stratégie** : Kick-off, Audit + stratégie + plan d'action SEO
2. **Optimisations (crédit-temps)** : 1,5 j technique, 30 contenus ou optimisations GMB, 2 j netlinking (suivi détaillé via Google Sheet)
3. **Pilotage** : 8 visios mensuelles (hors mois de bilan), 4 bilans trimestriels (oct. 26, janv. 27, avr. 27, juil. 27)

## Cadence des mois

Période contractuelle 01/07/2026 → 01/07/2027. Bilans aux trimestres (oct., janv., avr., juil.), visios les 8 autres mois. La barre « Tempo » et les marqueurs « Attendu » se calculent automatiquement selon la date du jour.

## Netlinking

Chaque projet peut pointer vers son Google Sheet de suivi netlinking : renseigner le champ `netlinkingSheet` du projet dans `index.html` (constante `PROJECTS`).

## Personnalisation

- `CONTRACT` : dates contractuelles.
- `PROJECTS` : projets, livrables, cibles.
- Le scoring « Dans le rythme / En retard / Critique » compare le réalisé au temps écoulé.

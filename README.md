# HOLOS — Bulletins d'inférence sur la structure des marchés

## Ce que vous lisez

Ce dépôt rassemble les **bulletins d'inférence** produits par HOLOS, un système
personnel de surveillance quantitative des marchés. Chaque bulletin est la
verbalisation d'un **état machine scellé** : un instantané des signaux au close,
relu d'artefacts figés — jamais recalculé à la main, jamais réinterprété après
coup.

Le système observe **25 ans de données journalières sur 137 instruments**
(secteurs, régions, indices, obligations, matières premières, devises) et lit une
seule chose : la **structure des liens** — corrélations qui se nouent, se
déchirent ou se taisent — plutôt que les prix isolés. L'intuition fondatrice : la
vérité du déplacement des capitaux ne se lit dans aucun instrument seul, mais
dans tout le système saisi simultanément.

## D'où sortent les chiffres

Chaque « loi » citée dans un bulletin a été jugée par un **tribunal statistique**
avant d'avoir le droit d'exister :

- hypothèse pré-enregistrée, famille de tests gelée d'avance ;
- nulls appariés (le hasard qui imite tout, sauf l'effet testé) ;
- correction du multiple-testing (FWER/Šidák) ;
- concordance exigée sur **deux ères indépendantes** (2000-2013 / 2013-2026) ;
- auto-tests qui arrêtent la machine si elle hallucine sur du bruit.

Ce qui échoue est publié comme **FLAT** — et le FLAT est une information, pas un
échec. Ce qui passe devient un taux conditionnel : *« après tel événement daté,
telle suite s'est produite dans X % des cas »*. Rien de plus, rien de moins.

## Comment lire un bulletin

Un bulletin type contient :

| Section | Ce qu'elle dit |
|---|---|
| **Vigie / régime** | Une loi d'époque (validée mais dormante depuis 2014) est-elle réveillée par son critère objectif ? |
| **Drainage** | Où en est la dissipation du dernier choc systémique, bloc par bloc, contre l'ordre canonique mesuré sur 26 ans |
| **Élections actives** | Les niveaux élus (plus-hauts par profondeur de mémoire, cassures de moyennes) avec leur taux de poursuite/rebond et leur fenêtre de validité (21 j) |
| **Morts de tendance** | Les tendances invalidées, leur probabilité d'inversion par tercile d'enfoncement (32→44 %) et la fenêtre des deux-tiers |
| **Agenda** | Les échéances (FOMC, NFP…) et leurs effets d'agitation certifiés (ex. ×1,144) — un climat, jamais une direction |
| **Les 12 jauges** | L'état du monde en percentiles de sa propre histoire (taux réels, stress, crédit, pétrole…) |
| **Devises** | Les forces relatives (somme nulle par construction) — se lisent, ne se devancent pas |

Règle de lecture universelle : **un taux de 0,61 n'est pas une prédiction**.
C'est la fréquence historique d'une suite, conditionnelle à un événement daté,
mesurée hors-échantillon. La fenêtre est toujours explicite ; l'amplitude n'est
presque jamais prévisible (seul le *sens* l'est parfois, faiblement).

## Ce que ce dépôt n'est PAS

- **Pas un conseil en investissement.** Aucun bulletin ne contient d'ordre
  d'achat ou de vente, de cible de prix, ni de recommandation — c'est une règle
  de conception du système (la « Licence de Signal »), pas une clause de style.
- **Pas une prétention d'edge.** Un taux conditionnel brut n'est pas un
  avantage net de coûts ; cette démonstration exige un procès séparé et
  n'est jamais implicite ici.
- **Pas de l'astrologie à indicateurs.** Chaque régularité citée a survécu à des
  nulls appariés, deux ères et une correction de multiple-testing — et celles qui
  n'ont pas survécu sont dites FLAT, publiquement.

Le système lui-même embarque son contrôle négatif permanent : un modèle-monde
entier, entraîné puis **gelé**, dont le verdict « la direction des prix est
imprévisible à cette fréquence » est re-mesuré à chaque cycle. Tant qu'il dit
FLAT, la doctrine tient : *surveillance, jamais signal.*

## Organisation du dépôt

```
bulletins/
  2026-07-17.md        ← un bulletin par close (la date est celle des données)
  2026-07-18.md
analyses/
  <theme>.md           ← analyses thématiques ponctuelles (drainage, régimes…)
GENESE.md              ← le récit fondateur du projet
README.md              ← ce document
```

Les bulletins sont exportés tels quels depuis le cockpit HOLOS (markdown brut,
chiffres relus des scellés). La date du fichier est la **date du close analysé**,
pas celle de la publication.

## Glossaire minimal

- **Élection** — un niveau de prix vient d'être franchi/atteint (plus-haut de
  N jours, cassure de moyenne) ; l'événement « élit » le niveau et ouvre une
  fenêtre de 21 jours où un taux conditionnel s'applique.
- **Mort de tendance** — une tendance suivie casse son seuil d'invalidation.
- **Drainage** — la dissipation ordonnée de l'énergie d'un choc à travers les
  couches du système (régions → secteurs → indices → obligations/MP → devises).
- **Vigie** — la surveillance automatique du critère de réveil d'une loi
  d'époque dormante.
- **RÉEL / FLAT** — les deux verdicts du tribunal : régularité certifiée /
  indiscernable du hasard.
- **DSR** — Deflated Sharpe Ratio : la probabilité qu'une performance ne soit
  pas un artefact de sélection.

---

*Les performances passées ne préjugent pas des performances futures. Ce contenu
est publié à des fins de recherche et de documentation ; il ne constitue ni un
conseil en investissement, ni une incitation à transiger sur quelque instrument
que ce soit. Chaque lecteur reste seul responsable de ses décisions.*

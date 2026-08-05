# Maquettes de prospection — couvreurs

74 pages d'accueil refaites, une par entreprise, à partir du contenu de son site
actuel. Publié sur **<https://joe-jns.github.io/prospects-demos/>**.

Le rapport (`index.html`) liste les 74 maquettes : aperçu, lien, email de
prospection prêt à copier, et ce qui manque sur chacune.

## Ce que contient une maquette

| Nature | Contenu | Origine |
|---|---|---|
| `[PROSPECT]` | nom, téléphone, adresse, titre, prestations, photos | repris de son site — jamais inventé |
| `[TEMPLATE]` | « pourquoi nous », histoire, process, FAQ, accroches | notre éditorial, décliné avec sa ville et son métier |
| `[PLACEHOLDER]` | les 9 avis clients | **fabriqués** — seules les communes sont réelles |

Les avis sont des textes de démonstration. Ils remplissent la page pour montrer
le rendu ; ils ne doivent jamais partir en ligne tels quels, et sont à remplacer
par les vrais avis Google de l'entreprise.

## Pourquoi `noindex`

Chaque page porte le nom, le téléphone et l'adresse d'une entreprise réelle. Pour
qu'aucune ne se retrouve dans un moteur de recherche — et ne soit prise pour son
site officiel — toutes sont servies en `noindex, nofollow`, et `robots.txt`
interdit l'exploration du dépôt entier.

## Structure

```
index.html          le rapport
emails/<slug>.txt   l'email de prospection de chaque entreprise
vignettes/          les aperçus utilisés par le rapport
_partage/           la vidéo du hero, stockée une seule fois pour les 74
<slug>/             une maquette par entreprise
```

## Régénérer

Les sources et les outils vivent dans le dépôt `audit-prospects-btp` :

```
python tools/generer_harmonie.py     # écrit les 74 projets Astro
python tools/deployer.py             # build + assemble ce dossier
python tools/rapport_demos.py        # régénère index.html
```

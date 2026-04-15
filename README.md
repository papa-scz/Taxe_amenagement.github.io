# Taxe d'aménagement par commune

Application web statique pour consulter les taux de taxe d'aménagement publiés par la DGFIP.

## Fonctionnement

- Recherche d'une commune via `geo.api.gouv.fr`, avec sélection par code INSEE pour éviter les homonymes.
- Lecture du dataset DGFIP `delta_deliberation_tam_17_01_23`, publié sur `data.economie.gouv.fr`.
- Fallback sur le miroir fédéré `data.opendatasoft.com` lorsque le portail du ministère refuse ou bloque l'appel direct.
- Affichage séparé des parts communale, départementale et régionale lorsqu'elles existent.
- Recherche cadastrale optionnelle par préfixe, section et parcelle, sans charger toutes les lignes d'une commune.

## Utilisation locale

Ouvrez simplement `index.html` dans un navigateur moderne.

L'application n'a pas besoin de build ni de dépendances. Les données sont chargées directement depuis les API publiques.

## Sources

- Dataset fiscal DGFIP: <https://data.economie.gouv.fr/explore/dataset/delta_deliberation_tam_17_01_23/>
- Fiche data.gouv.fr: <https://www.data.gouv.fr/datasets/taxe-damenagement-elements-de-taxation-votes-par-les-collectivites-a-partir-de-2022>
- API communes: <https://geo.api.gouv.fr/decoupage-administratif/communes>
- Valeurs forfaitaires 2026: <https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006069577/LEGISCTA000045912516/2026-01-01>

## Limites

Les taux affichés sont ceux des délibérations disponibles dans les données ouvertes. Une référence cadastrale mal saisie peut faire retomber l'affichage sur le taux général de la commune.

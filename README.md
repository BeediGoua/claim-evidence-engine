# Claim Evidence Engine 

Système agentique de fact-checking statistique pour analyser des affirmations publiques (tweets, discours, interviews) et produire un verdict argumenté à partir de données officielles.

## Objectif

Transformer une affirmation en réponse vérifiable et sourcée:

1. Extraire la claim
2. Identifier l'indicateur mesurable
3. Router vers la meilleure source officielle
4. Récupérer les données pertinentes
5. Calculer et comparer avec l'affirmation
6. Produire un verdict nuancé
7. Générer une explication claire avec sources

Le projet va au-delà du binaire "vrai/faux" et vise des verdicts plus robustes:

- Vrai
- Plutôt vrai
- Exagéré
- Trompeur
- Faux
- Manque de contexte
- Invérifiable

## Cas d'usage

Exemple d'entrée:

> "Le chômage a explosé en France depuis 2020."

Exemple de sortie attendue:

- Identification du thème: chômage
- Séries sélectionnées: INSEE/Eurostat pertinentes
- Période comparée: 2020 vs dernière valeur disponible
- Résultat chiffré et interprétation
- Verdict nuancé + justification

## Sources de données visées

Sources prioritaires pour les claims macroéconomiques et sociales:

- INSEE (notamment BDM / SDMX)
- data.gouv
- Eurostat
- Banque de France (si pertinent)

## Périmètre initial

Le MVP cible des sujets où les indicateurs sont bien définis:

- Inflation
- PIB
- Chômage
- Population
- Salaires
- Pauvreté
- Démographie
- Créations d'entreprises
- Prix / immobilier
- Production industrielle

## Architecture logique

Le système est structuré en 5 couches:

- Data layer: accès aux sources et catalogue d'indicateurs
- Reasoning layer: extraction, mapping thématique, routage
- Evidence layer: collecte, nettoyage, calcul, verdict
- Agent layer: orchestration des outils/agents spécialisés
- Evaluation layer: qualité extraction, retrieval, calcul et verdict

## Arborescence actuelle du projet

Les dossiers de base ont été initialisés (fichiers à venir):

```text
claim-evidence-engine/
├── README.md
├── data/
│   ├── cache/
│   └── mappings/
├── eval/
├── src/
│   └── evaluation/
└── tests/
```

## Principes de qualité

- Traçabilité: chaque conclusion doit être reliée à une source
- Reproductibilité: calculs explicites et vérifiables
- Transparence: explication lisible pour un non-spécialiste
- Prudence: possibilité d'indiquer "invérifiable" ou "manque de contexte"

## Roadmap suggérée

1. Définir les schémas de données (claim, evidence, verdict)
2. Mettre en place un premier connecteur source (INSEE)
3. Créer le pipeline minimal extraction -> retrieval -> verdict
4. Ajouter un jeu d'évaluation et des métriques de base
5. Étendre à d'autres sources et thèmes

## Statut

Projet en phase de structuration.
La base de dossiers est prête pour implémenter les premiers modules.

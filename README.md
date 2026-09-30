# Analyse des accidents routiers en Tunisie (2001–2025)

Analyse statistique des accidents corporels de la route en Tunisie, à partir des données de l'Observatoire National de la Sécurité Routière (ONSR), centrée sur trois axes : **répartition géographique**, **rythme horaire**, et **ratio tués/blessés** (taux de létalité).

## Présentation

Ce projet explore environ 208 000 accidents corporels recensés en Tunisie entre 2001 et 2025, pour répondre à trois questions :

1. **Où** se produisent les accidents, et où sont-ils les plus meurtriers ? *(niveau gouvernorat / district)*
2. **Quand**, dans la journée, le risque est-il le plus élevé ? *(6 tranches horaires)*
3. **Comment la sévérité — la part de victimes qui décèdent — varie-t-elle** selon le lieu et l'heure ?

Des statistiques descriptives et une matrice de corrélation sont incluses en base de travail, mais le cœur de l'analyse porte sur le croisement géographie × tranche horaire × taux de létalité.

## Données

- **Source** : [ONSR](https://www.onsr.tn/) (Observatoire National de la Sécurité Routière), Tunisie — une ligne par accident corporel recensé.
- **Période** : 2001–2025 (2026 exclue car incomplète).
- Non incluses dans ce dépôt — voir [Accès aux données](#accès-aux-données) ci-dessous.

## Méthodes

- Statistiques descriptives et matrice de corrélation (Spearman)
- Tests du chi² d'indépendance (district × accident mortel, tranche horaire × accident mortel)
- Test de Kruskal-Wallis (taux de létalité selon la tranche horaire)
- Test de Mann-Whitney (taux de létalité, milieu urbain vs interurbain)
- Visualisations : seaborn/matplotlib (barplots, heatmaps, boxplots, nuages de points)

## Principaux résultats

- Volume et létalité ne pointent pas vers les mêmes zones : **Tunis** concentre le plus d'accidents (≈ 42 000) mais a l'un des taux de létalité les plus bas (≈ 5,3 %) ; **Médenine** a le taux de létalité le plus élevé (≈ 18,3 %) pour un volume bien plus faible.
- Le taux de létalité culmine la nuit (00h-03h59, ≈ 15,8 %) et est minimal en milieu de journée (08h-11h59, ≈ 8,3 %), alors que le volume d'accidents culmine en fin d'après-midi (16h-19h59).
- Les effets géographique et horaire semblent se cumuler plutôt que s'annuler : la combinaison **Sud × nuit** est la plus critique (jusqu'à 24 % de létalité).

Analyse complète et tests statistiques : [`notebook/analyse_accidents_geo_horaire_letalite.ipynb`](notebook/analyse_accidents_geo_horaire_letalite.ipynb).

## Structure du projet

```
.
├── notebook/
│   └── analyse_accidents_geo_horaire_letalite.ipynb
├── data/                # non versionné — voir Accès aux données
├── requirements.txt
└── README.md
```

## Installation et exécution

```bash
git clone https://github.com/Asma2201/<nom-du-repo>.git
cd <nom-du-repo>
python -m venv .venv
source .venv/bin/activate      # Windows : .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebook/analyse_accidents_geo_horaire_letalite.ipynb
```

## Accès aux données

Le fichier source de l'ONSR n'est pas inclus dans ce dépôt. Place-le dans un dossier `data/` sous le nom `accidents_routiers_tunisie_2001_2026.xlsx` avant d'exécuter le notebook.

## Auteure

**Asma Allaigui** — Étudiante en Data Science Engineering, ESSAI, Tunisie
[LinkedIn](#) · [GitHub](https://github.com/Asma2201)

## Remarque

Ce projet est un devoir académique (module de statistiques). Les axes d'analyse retenus et la structure du code sont un travail original, indépendant de toute autre production réalisée à partir du même jeu de données.
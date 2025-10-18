# Shot Prevision – prédire la réussite d’un tir NBA

Ce projet explore la **prédiction de la réussite d’un tir** (succès/échec) à partir de données de tracking et de contexte de jeu, avec un focus sur deux joueurs (Stephen Curry et LeBron James).

## Objectifs
- Construire un pipeline de features propre et reproductible.
- Entraîner un modèle de **régression logistique** (et baselines) pour prédire `SHOT_RESULT`.
- Comparer des modèles « globaux » (tous joueurs) vs **spécifiques à un joueur**.
- Évaluer la performance et interpréter les coefficients (facteurs clés).

## Données & variables clés
Variables utilisées ou explorées :
- **SHOT_CLOCK**, **GAME_CLOCK** (converti en secondes et/ou temps écoulé), **TOUCH_TIME**, **DRIBBLES**
- **SHOT_DIST**, **CLOSE_DEF_DIST** (penser à l’unité : pieds → mètres)
- **PERIOD**, **PTS_TYPE** (2/3 pts), **LOCATION** (H/A)
- (Exploration) **GAME_TIME_TOTAL**, **SHOT_NUMBER**  
Voir le notebook `projet.ipynb` pour les détails d’extraction & EDA.


face de test on pourras faire par la suite un modèle plus complexe comme XGBoost / LightGBM	il faudra ne pas standardiser les données
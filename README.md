Projet en cours


Modèle de Prédiction des Résultats de Matchs
Objectif
Prédire l'issue des matchs (victoire, nul, défaite) en fonction de divers facteurs tels que le lieu du match, l'historique des équipes, la compétition, etc.

Méthodes
Modèles Utilisés
Régression Logistique
Modèles de Machine Learning : Random Forest, XGBoost
Deep Learning : Réseaux de neurones
Préparation des Données
Nettoyage du Dataset

Gestion des valeurs manquantes
Formatage des dates
Feature Engineering

Création de variables telles que la forme récente des équipes, le classement Elo, l'avantage du terrain (déjà présent dans le dataset).
Encodage des variables catégorielles (ex: noms des équipes).
Justification des Variables Supplémentaires
Variables de Forme et de Force : Les variables supplémentaires comme le classement Elo et les performances récentes permettent d'avoir des indicateurs fiables de la forme et de la force d'une équipe. Ces variables évoluent après chaque match, fournissant des données pertinentes pour le modèle de prédiction.
Variables Créées
Performances Récentes :

Nombre de victoires/nuls/défaites sur les 5 derniers matchs.
Nombre de buts marqués/encaissés sur les 5 derniers matchs.
Moyenne des points pris (3 pour une victoire, 1 pour un nul, 0 pour une défaite).
Classement Elo :

Calculé avec la formule d'elo sur wikipédia.

Prédiction du Nombre de Buts
Objectif
Créer une classification sur le score exact au lieu de la simple victoire/nul/défaite.

Utilité
Betting : Plus précis pour les paris (Over/Under, exact score).
Informations Supplémentaires : Permet de dériver les probabilités de victoire.
Distributions de Poisson/NB : Affine les prédictions.
Modèles
Deux Modèles Séparés :
Un pour les buts de l’équipe à domicile (home_goals).
Un pour les buts de l’équipe à l’extérieur (away_goals).
Limitation des Scores
Les scores sont limités à 5. Tout score supérieur à 5 devient 5+ pour éviter de perturber le modèle avec des performances rares.

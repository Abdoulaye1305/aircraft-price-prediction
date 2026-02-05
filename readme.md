# Prédiction de prix d'avions (Aircraft Price Prediction)

Ce projet de **Master 2 Data Science** vise à développer un modèle prédictif pour estimer le prix des avions en fonction de leurs spécifications techniques. L'objectif est de mettre en pratique l'ensemble de la chaîne de traitement de la donnée, de l'exploration à la mise en production d'un modèle performant.

## 📂 Structure du projet

Le repository est organisé selon un flux de travail séquentiel :

*   **`01_EDA.ipynb` (Exploratory Data Analysis)** :
    *   Chargement et inspection du dataset.
    *   Visualisation des distributions des variables.
    *   Analyse des corrélations (ex: `max_speed` vs `price`).
    *   Identification des valeurs aberrantes (outliers).

*   **`02_Preprocessing.ipynb` (Prétraitement)** :
    *   Nettoyage des données (suppression des colonnes inutiles).
    *   Gestion des valeurs manquantes.
    *   Feature Engineering.
    *   Encodage des variables catégorielles (`engine_type`).

*   **`03_Modélisation.ipynb`** :
    *   Mise en place de pipelines `scikit-learn`.
    *   Comparaison de modèles linéaires simples et régularisés (OLS, Ridge, Lasso, ElasticNet).
    *   Optimisation des hyperparamètres par validation croisée (`GridSearchCV`).
    *   Interprétation des résultats (Feature Importance).

## 📊 Données

Le jeu de données `aircraft_price.csv` contient les spécifications techniques de différents modèles d'avions.

**Variable cible (Target) :**
*   `price` : Prix de l'avion en dollars.

**Caractéristiques (Features) :**
*   **Moteur** : `engine_type`, `engine_power`.
*   **Performance** : `max_speed`, `cruise_speed`, `stall_speed`, `range`.
*   **Capacités** : `fuel_tank`, `empty_weight`.
*   **Dimensions** : `length`, `wing_span`.
*   **Autres** : `takeoff_distance`, `landing_distance`.

## 🛠️ Installation et Prérequis

Ce projet a été développé avec **Python 3.12**. La gestion de l'environnement est assurée par **pyenv** (pour la version de Python) et **Poetry** (pour les dépendances).

Pour reproduire l'environnement de développement :

1.  **Configurer la version de Python (via pyenv)** :
    ```bash
    pyenv install 3.12
    pyenv local 3.12
    ```

2.  **Installer les dépendances (via Poetry)** :
    ```bash
    poetry install
    ```

3.  **Lancer l'environnement** :
    ```bash
    poetry shell
    jupyter lab  # ou jupyter notebook
    ```

## 🚀 Méthodologie

La démarche suivie respecte les standards de la Data Science :

1.  **Exploration** : Analyse univariée et bivariée pour comprendre les relations entre variables prédictives et le prix.
2.  **Preprocessing** :
    *   Imputation des valeurs manquantes.
    *   Standardisation (`StandardScaler`) pour mettre les variables à la même échelle.
    *   Encodage (`OneHotEncoder`) des variables catégorielles.
3.  **Modélisation** :
    *   Utilisation de la régression linéaire comme baseline.
    *   Test de modèles régularisés (Ridge, Lasso, ElasticNet) pour réduire le surapprentissage.
    *   Validation croisée (K-Fold) pour assurer la robustesse des scores.

## 📈 Résultats et Performances

Le meilleur modèle retenu est un **ElasticNet** optimisé.

| Métrique | Score (Test Set) |
| :--- | :--- |
| **R²** | **0.8801** |
| **RMSE** | **353,352 $** |
| **MAE** | **281,204 $** |

Les résultats montrent une excellente capacité du modèle à expliquer 88% de la variance des prix. Les variables les plus influentes sont généralement la puissance du moteur, la vitesse de croisière et la capacité du réservoir.

## 🔮 Pistes d'amélioration

Pour aller plus loin dans ce projet, plusieurs pistes pourraient être explorées :
*   Tester des modèles non-linéaires (Random Forest, XGBoost) pour capturer des relations plus complexes.
*   Enrichir le dataset avec d'autres données (année de fabrication, avionique).
*   Ajouter une interface Streamlit pour permettre une prédiction interactive.

## 👤 Auteur

**Abdoulaye Diallo** - Étudiant en Master 2 Data Science.
Projet réalisé dans le cadre académique.


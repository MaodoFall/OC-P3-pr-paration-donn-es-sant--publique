# 🥦 Nettoyage et préparation de données nutritionnelles – Open Food Facts

**Projet 3 – Mastère Spécialisé Data Science – OpenClassrooms**  
**Rôle : Data Scientist**  
**Client : Santé Publique France**

---

## 🎯 Objectif du projet

Dans le cadre d’un partenariat entre **Santé Publique France** et une entreprise de data science, ce projet vise à explorer la base de données **Open Food Facts** afin de :

- **Évaluer la faisabilité d'une application de suggestion automatisée** pour aider les utilisateurs à compléter les fiches produits.
- **Nettoyer et structurer** les données pour préparer des algorithmes de complétion automatique.
- Proposer des **analyses statistiques solides** pour détecter les tendances nutritionnelles pertinentes.

---

## 🗂️ Jeu de données utilisé

Source : [Open Food Facts](https://world.openfoodfacts.org/data)  
Taille : ~320 000 produits, 162 variables

### Catégories principales :
- **Informations générales** : noms, codes-barres
- **Catégories et tags** : groupe alimentaire, origine, labels
- **Ingrédients et additifs**
- **Informations nutritionnelles** pour 100g (énergie, lipides, glucides, etc.)

Variables clés retenues pour l’analyse :
- `energy_100g`, `fat_100g`, `carbohydrates_100g`, `sugars_100g`, `fiber_100g`, `proteins_100g`, `salt_100g`, `sodium_100g`
- `nutrition_grade_fr`, `pnns_groups_1`, `pnns_groups_2`, `product_name`

---

## 🧪 Étapes de l’analyse

### 🧹 1. Nettoyage des données
- Suppression des colonnes vides et doublons (basé sur le code-barres)
- Correction de noms de variables
- Suppression des variables avec >75 % de valeurs manquantes
- Imputation des données nutritionnelles manquantes via **KNN Imputer**

### 🚨 2. Traitement des valeurs aberrantes
- Limitation par l’**écart interquartile (IQR)**
- Suppression des valeurs nutritionnelles incohérentes (>100g)
- Filtrage des scores de nutrition aberrants

### 📊 3. Analyse statistique
- **Analyse univariée** (ex. : distribution des protéines, grades nutritionnels)
- **Analyse bivariée** : score nutritionnel vs. groupes alimentaires
- **Tests statistiques** : ANOVA confirmant l’effet du groupe alimentaire sur le score de nutrition

### 🧠 4. Analyse en composantes principales (ACP)
- Sélection du nombre optimal de composantes
- Cercle de corrélation pour interpréter les axes principaux
- Visualisation des produits dans l’espace des composantes

---

## 🧠 Résultats clés

- Données préparées : **43 159 produits exploitables**
- Variables nutritionnelles imputées et normalisées
- Relations significatives observées entre **score de nutrition** et :
  - le **type d’aliment** (groupes PNNS)
  - le **grade nutritionnel**

➡️ Ces résultats **valident la faisabilité d’une application de suggestion automatique** fondée sur les produits similaires et leurs profils nutritionnels.

---

## 🛠️ Compétences mobilisées

- Nettoyage avancé de données avec **Pandas / NumPy / Scikit-learn**
- Visualisation avec **Matplotlib / Seaborn**
- Tests statistiques (ANOVA) avec **SciPy / statsmodels**
- Réduction de dimension avec **ACP (PCA)**

---

## 📁 Livrables

- 📓 Notebook Jupyter de traitement et d’analyse
- 🖥️ Support de présentation

---

## 🙋‍♂️ Réalisé par

**Maodo FALL**  
*Data Scientist*  

---

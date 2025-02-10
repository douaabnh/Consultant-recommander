# Consultant Matching Platform

## Objectif
Cette plateforme propose une interface centralisée permettant de réunir différents consultants en Algérie. Elle aide les clients à trouver le meilleur consultant pour leur projet en fonction de leurs préférences et des descriptions de projets.

## 1. Préparation des données
Deux jeux de données ont été générés :
- **Profils de consultants**
- **Données historiques**

### a. Profils de consultants
Les attributs considérés pour les consultants sont :
- **Compétences (skills)** : Machine Learning, Deep Learning, NLP, Computer Vision, Data Engineering, etc.
- **Langues maîtrisées (languages)** : English, French, Spanish, German, Arabic
- **Expertise sectorielle (Industry Expertise)** : Healthcare, Finance, Retail, Education, etc.
- **Années d’expérience (Years of Experience)** : Entre 2 et 10 ans
- **Numéro de téléphone** : Généré aléatoirement avec un préfixe algérien (+213)

### b. Données historiques
Les données historiques incluent :
- **Description du projet (Project Description)**
- **Nom du consultant (Consultant Name)**
- **Success Rating**
- **Feedback comments**

## 2. Analyse des notes de succès
- Calcul de la moyenne des notes de succès pour chaque consultant
- Normalisation des notes
- Fusion des scores avec les profils des consultants
- Remplacement des valeurs manquantes par une valeur neutre (0.5)

## 3. Analyse de sentiment
Utilisation de `SentimentIntensityAnalyzer()` pour analyser les feedbacks des clients.
- Calcul du score moyen de sentiment
- Intégration des scores dans les profils
- Gestion des valeurs manquantes avec une valeur neutre (0.5)

## 4. Prétraitement des données
### a. Détection de langue
Identification des langues à l’aide d’expressions régulières.

### b. Extraction de compétences
Utilisation d’un dictionnaire pour associer les mots-clés des descriptions aux compétences pertinentes.

### c. Prétraitement de texte
Transformation des données textuelles via :
- Suppression des bruits (ponctuation, stop words, etc.)
- Tokenization et vectorisation (TF-IDF)
- Extraction des années d’expérience via des expressions régulières

## 5. Algorithme de recommandation
### a. Représentation TF-IDF
Conversion des descriptions de projet et des compétences en vecteurs TF-IDF.

### b. Calcul du score de similarité
- **Similarité cosinus (95%)** entre le projet et les profils de consultants
- **Taux de succès (2.5%)** basé sur les données historiques
- **Analyse de sentiment (2.5%)** sur les feedbacks clients

## 6. Fonctionnement
1. Le client saisit une description de son projet.
2. Le système pré-traite l'entrée et la compare aux profils des consultants.
3. Une liste de consultants recommandés est générée en fonction du score calculé.

## Auteurs
- **Djelliout Yousra** & **Benhamida Douaa**

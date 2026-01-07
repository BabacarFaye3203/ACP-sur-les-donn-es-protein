
# 📊 Analyse en Composantes Principales (ACP) – Données *Protein*

## 📝 Description du projet

Ce projet a pour objectif d’appliquer une **Analyse en Composantes Principales (ACP)** à un jeu de données alimentaires (*protein*), afin d’analyser et de comparer les **habitudes de consommation de protéines** de différents pays.

L’ACP permet de :

* réduire la dimension des données,
* identifier les variables les plus explicatives,
* mettre en évidence des profils et des regroupements de pays.

## 📂 Contenu du repository

```
├── protein.txt        # Jeu de données
├── protein.R          # Script R principal (ACP)
└── README.md          # Documentation du projet
```

### 📄 `protein.txt`

* Chaque **ligne** représente un **pays**.
* Chaque **colonne** correspond à un **type de source de protéines** (viande, poisson, céréales, etc.).
* Les données sont quantitatives et continues, ce qui rend l’ACP appropriée.

### 📄 `protein.R`

Ce script contient toutes les étapes de l’analyse :

* lecture et préparation des données,
* exploration statistique,
* calcul de la matrice de corrélation,
* réalisation de l’ACP,
* visualisations graphiques,
* interprétation des résultats.

---

## ⚙️ Méthodologie

L’analyse suit les étapes classiques de l’ACP :

1. **Lecture et préparation des données**

   * Importation du fichier CSV
   * Vérification du format et conversion en données numériques

2. **Analyse exploratoire**

   * Statistiques descriptives (`summary`)
   * Boîtes à moustaches pour comparer les variables

3. **Matrice de corrélation**

   * Étude des relations entre les variables
   * Visualisation à l’aide d’une carte de corrélation

4. **Normalisation des données**

   * Centrage (et éventuellement réduction) pour éviter l’effet d’échelle

5. **Analyse en Composantes Principales**

   * Calcul des valeurs propres et vecteurs propres
   * Étude de l’inertie expliquée
   * Choix du nombre d’axes principaux

6. **Interprétation**

   * Contributions des individus
   * Qualité de représentation (cos²)
   * Projection des pays sur le plan factoriel principal

## 📈 Résultats et visualisations

Les résultats incluent :

* **Scree plot** : aide au choix du nombre de composantes
* **Projection des individus** (pays) sur le plan principal
* **Corrélation variables / composantes** pour interpréter les axes

Les deux premières composantes expliquent une part importante de la variance totale, ce qui permet une interprétation pertinente dans un plan bidimensionnel.


## 🧠 Interprétation générale(rapport)

## 1. Introduction

L’Analyse en Composantes Principales (ACP) est une méthode statistique multivariée permettant de résumer l’information contenue dans un grand nombre de variables corrélées en un nombre réduit de composantes non corrélées appelées composantes principales. Elle facilite l’exploration, la visualisation et l’interprétation des données.

Dans ce TP, l’ACP est appliquée au jeu de données **Protein**, qui décrit les habitudes de consommation alimentaire de plusieurs pays européens à travers différentes catégories d’aliments.

## 2. Présentation des données

Le jeu de données *protein* contient **25 pays** (individus) décrits par **9 variables quantitatives** représentant des types d’aliments :

* RedMeat (viande rouge)
* WhiteMeat (viande blanche)
* Eggs (œufs)
* Milk (lait)
* Fish (poisson)
* Cereals (céréales)
* Starch (féculents)
* Nuts (noix)
* Fr.Veg (fruits et légumes)

Les pays constituent les individus statistiques et les consommations alimentaires les variables.


## 3. Préparation et exploration des données

Les données ont été lues depuis un fichier texte, puis préparées pour l’analyse :

* La colonne *Country* a été utilisée comme identifiant des individus.
* Les variables alimentaires ont été converties en valeurs numériques.

Une analyse descriptive a été réalisée à l’aide :

* de la fonction `summary()` pour obtenir les statistiques de base,
* de boîtes à moustaches afin de comparer les distributions des consommations alimentaires.

Cette exploration montre une forte hétérogénéité des consommations entre pays, ce qui justifie l’utilisation d’une méthode de réduction de dimension comme l’ACP.


## 4. Analyse de la matrice de corrélation

La matrice de corrélation met en évidence de fortes dépendances entre certaines variables :

* Les viandes, les œufs et le lait sont positivement corrélés entre eux.
* Les céréales et les noix sont négativement corrélées avec la consommation de viande.
* Le poisson et les fruits/légumes présentent des profils alimentaires spécifiques.

La présence de corrélations significatives confirme la pertinence de l’ACP.


## 5. Réalisation de l’ACP

L’ACP a été réalisée sur les données **centrées et réduites** afin de neutraliser l’effet des unités de mesure différentes.

### 5.1 Valeurs propres et inertie

Les deux premières composantes principales expliquent une part importante de la variance totale :

* **Axe 1 (PC1)** : environ 44,5 % de la variance
* **Axe 2 (PC2)** : environ 18,2 % de la variance

Le plan factoriel (PC1, PC2) explique donc environ **62,7 % de l’inertie totale**, ce qui est suffisant pour une bonne représentation des données.


## 6. Interprétation des axes principaux

### Axe 1 (PC1)

Le premier axe oppose :

* des pays à forte consommation de **viande, œufs et produits laitiers**,
* à des pays caractérisés par une alimentation plus riche en **céréales et noix**.

Il traduit un contraste entre régimes alimentaires riches en produits animaux et régimes plus végétaux.

### Axe 2 (PC2)

Le deuxième axe est principalement associé à :

* la consommation de **poisson**,
* ainsi qu’aux **fruits et légumes**.

Il distingue des pays à alimentation méditerranéenne ou maritime des autres.


## 7. Qualité de représentation et contributions

### Qualité de représentation (cos²)

Le cos² permet d’évaluer la qualité de projection des pays sur le plan factoriel. Les pays ayant un cos² élevé sont bien représentés par les deux premiers axes.

### Contributions

Les contributions montrent quels pays et quelles variables participent le plus à la construction des axes. Les pays situés aux extrémités des axes ont les contributions les plus importantes.


## 8. Représentations graphiques

### Projection des individus

La projection des pays sur le plan (PC1, PC2) met en évidence des regroupements de pays aux habitudes alimentaires similaires.

### Cercle des corrélations

Le cercle des corrélations montre que :

* les variables proches du cercle unité sont bien représentées,
* les angles entre variables traduisent leurs corrélations (faibles, fortes ou négatives).

### Biplot

Le biplot permet une lecture simultanée des pays et des variables, facilitant l’interprétation conjointe des régimes alimentaires.


## 9. ACP avec FactoMineR

L’utilisation du package **FactoMineR**, combiné à **factoextra**, permet :

* une extraction claire des valeurs propres,
* l’analyse détaillée des contributions et des cos²,
* une visualisation avancée et interprétable des résultats.

Les résultats obtenus sont cohérents avec ceux issus de la fonction `prcomp()`.

## 10. Conclusion

L’Analyse en Composantes Principales appliquée aux données *protein* a permis :

* de réduire la dimension des données,
* d’identifier les principaux profils alimentaires européens,
* de mettre en évidence des oppositions claires entre régimes alimentaires.

L’ACP s’avère être un outil efficace pour l’analyse exploratoire de données nutritionnelles multivariées et facilite grandement leur interprétation.


## 🛠️ Prérequis

* R (version ≥ 4.0)
* Packages R :

  ```r
  install.packages("corrplot")
  ```


## ▶️ Exécution

Dans R ou RStudio :

```r
source("protein.R")
```


## 📌 Conclusion

Ce projet illustre l’intérêt de l’Analyse en Composantes Principales pour l’étude de données multivariées réelles.
L’ACP permet de synthétiser l’information, de visualiser les relations entre individus et variables, et d’extraire des tendances significatives.


## 👤 Auteur

**Babacar Faye**
Projet académique – Analyse de données / Statistique multivariée


* 🔹 adapter ce README à **un niveau Master / Licence**
* 🔹 le rendre **plus orienté data science**
* 🔹 ajouter une **section interprétation détaillée des axes**

Dis-moi 👍

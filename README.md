
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


## 🧠 Interprétation générale

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

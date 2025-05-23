---
"date": "2025-04-17"
"description": "Apprenez à créer et personnaliser un graphique à secteurs avec Aspose.Slides pour Java. Ce guide couvre la configuration, la mise en œuvre et les applications pratiques."
"title": "Créer un graphique à secteurs en Java avec Aspose.Slides &#58; un guide complet"
"url": "/fr/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un graphique à secteurs en Java avec Aspose.Slides : guide complet

## Tableaux et graphiques

### Introduction

En visualisation de données, les graphiques à secteurs constituent un moyen intuitif de représenter les proportions d'un ensemble de données. Cependant, lorsqu'il s'agit d'ensembles de données complexes où certains segments sont nettement plus petits que d'autres, les graphiques à secteurs traditionnels peuvent devenir encombrés et difficiles à interpréter. Les graphiques à secteurs corrigent ce problème en divisant les petites tranches en un graphique secondaire, améliorant ainsi la lisibilité.

Dans ce tutoriel, vous apprendrez à créer et manipuler un graphique à secteurs avec Aspose.Slides pour Java. Vous découvrirez la configuration de votre environnement, la création du graphique, la personnalisation des propriétés comme les étiquettes de données et les positions de division, et l'enregistrement de votre présentation au format PPTX. À la fin, vous maîtriserez ces fonctionnalités grâce à des applications pratiques et des conseils de performance.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Slides pour Java
- Création d'un graphique à secteurs
- Personnalisation des propriétés du graphique telles que les étiquettes de données et les configurations de fractionnement
- Enregistrer votre présentation sur le disque

Prêt à commencer ? Commençons par les prérequis !

## Prérequis

Avant de créer notre graphique à secteurs, assurez-vous d'avoir :

### Bibliothèques, versions et dépendances requises :
- **Aspose.Slides pour Java**:Essentiel pour gérer les présentations PowerPoint par programmation.

### Configuration requise pour l'environnement :
- Un kit de développement Java (JDK) installé sur votre machine. Nous recommandons l'utilisation du JDK 16 ou version ultérieure.
- Un environnement de développement intégré (IDE) comme IntelliJ IDEA, Eclipse ou NetBeans.

### Prérequis en matière de connaissances :
- Compréhension de base de la programmation Java
- Familiarité avec Maven ou Gradle pour la gestion des dépendances

## Configuration d'Aspose.Slides pour Java

### Informations d'installation :

**Expert :**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle :**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct**: Vous pouvez télécharger la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Étapes d'acquisition de la licence :
- **Essai gratuit**: Commencez par un essai de 30 jours pour explorer toutes les fonctionnalités.
- **Permis temporaire**:Demandez une licence temporaire pour une évaluation prolongée.
- **Achat**:Envisagez d’acheter une licence si Aspose.Slides répond à vos besoins.

### Initialisation et configuration de base

Une fois la bibliothèque configurée dans votre projet, initialisez-la en créant une instance de la `Presentation` classe:

```java
Presentation presentation = new Presentation();
```

Ceci prépare le terrain pour l'ajout de divers graphiques à vos diapositives. Passons maintenant à la création de notre graphique en secteurs.

## Guide de mise en œuvre

### Création d'un graphique « Pie of Pie »

#### Aperçu
Nous allons commencer par créer une instance d'un `Presentation` et ajoutez un graphique en secteurs sur la première diapositive. Ce graphique visualisera efficacement les données en séparant les segments plus petits dans un deuxième secteur, améliorant ainsi la lisibilité.

#### Étape 1 : Créer une instance de la classe de présentation
```java
// Créer une nouvelle présentation
ePresentation presentation = new Presentation();
```
Ce code initialise votre présentation où nous ajouterons nos graphiques.

#### Étape 2 : Ajoutez un graphique « Pie of Pie » sur la première diapositive
```java
// Ajoutez un graphique à secteurs à la première diapositive à la position (50, 50) avec une taille (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Ici, nous spécifions le type de graphique (`PieOfPie`) et sa position et ses dimensions sur la diapositive.

#### Étape 3 : Définir les étiquettes de données pour afficher les valeurs de la série
```java
// Configurer les étiquettes de données pour afficher les valeurs
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Cette étape garantit que chaque segment de notre graphique à secteurs affiche sa valeur correspondante, ce qui facilite une interprétation rapide des données.

#### Étape 4 : Configurer la taille du deuxième graphique à secteurs et le diviser en pourcentage
```java
// Définir la taille du graphique secondaire
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Diviser le gâteau en pourcentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Définir la position de division
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Ces configurations vous permettent de personnaliser la manière dont votre graphique se divise et affiche des segments plus petits, améliorant ainsi la clarté pour les spectateurs.

#### Étape 5 : Enregistrez la présentation sur le disque au format PPTX
```java
// Définir le répertoire de sortie
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Enregistrez la présentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
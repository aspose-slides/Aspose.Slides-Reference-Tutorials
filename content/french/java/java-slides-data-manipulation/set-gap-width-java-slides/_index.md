---
title: Définir la largeur de l'espace dans les diapositives Java
linktitle: Définir la largeur de l'espace dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir la largeur de l'espace dans les diapositives Java avec Aspose.Slides pour Java. Améliorez les visuels des graphiques pour vos présentations PowerPoint.
type: docs
weight: 21
url: /fr/java/data-manipulation/set-gap-width-java-slides/
---

## Introduction à la définition de la largeur de l'espace dans Aspose.Slides pour Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de définition de la largeur de l'espace pour un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. La largeur de l'espace détermine l'espacement entre les colonnes ou les barres d'un graphique, vous permettant de contrôler l'apparence visuelle du graphique.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée. Vous pouvez le télécharger sur le site Aspose[ici](https://releases.aspose.com/slides/java/).

## Guide étape par étape

Suivez ces étapes pour définir la largeur de l'espace dans un graphique à l'aide d'Aspose.Slides pour Java :

### 1. Créez une présentation vide

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Créer une présentation vide
Presentation presentation = new Presentation();
```

### 2. Accédez à la première diapositive

```java
// Accédez à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Ajouter un graphique avec des données par défaut

```java
// Ajouter un graphique avec des données par défaut
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Définir l'index de la feuille de données du graphique

```java
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
```

### 5. Obtenez le classeur de données graphiques

```java
//Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Ajouter une série au graphique

```java
// Ajouter une série au graphique
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Ajouter des catégories au graphique

```java
// Ajouter des catégories au graphique
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Remplir les données de la série

```java
// Remplir les données de la série
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Remplissage des points de données de la série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Définir la largeur de l'espace

```java
// Définir la valeur de la largeur de l'espace
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Enregistrez la présentation

```java
// Enregistrez la présentation avec le graphique
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir la largeur de l'espace dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une présentation vide
Presentation presentation = new Presentation();
// Accéder à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
// Ajouter un graphique avec les données par défaut
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
//Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ajouter une série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Ajouter des catégories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Prendre la deuxième série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Définir la valeur GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Enregistrer la présentation avec le graphique
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, vous avez appris à définir la largeur de l'espace pour un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Le réglage de la largeur de l'espace vous permet de contrôler l'espacement entre les colonnes ou les barres de votre graphique, améliorant ainsi la représentation visuelle de vos données.

## FAQ

### Comment puis-je modifier la valeur de la largeur de l'espace ?

 Pour modifier la largeur de l'espace, utilisez le`setGapWidth` méthode sur le`ParentSeriesGroup`de la série de graphiques. Dans l'exemple fourni, nous définissons la largeur de l'espace sur 50, mais vous pouvez ajuster cette valeur à l'espacement souhaité.

### Puis-je personnaliser d’autres propriétés du graphique ?

Oui, Aspose.Slides pour Java offre des fonctionnalités étendues de personnalisation des graphiques. Vous pouvez modifier diverses propriétés du graphique, telles que les couleurs, les étiquettes, les titres, etc. Consultez la référence API pour obtenir des informations détaillées sur les options de personnalisation des graphiques.

### Où puis-je trouver plus de ressources et de documentation ?

 Vous pouvez trouver une documentation complète et des ressources supplémentaires sur Aspose.Slides pour Java sur le[Site Aspose](https://reference.aspose.com/slides/java/).
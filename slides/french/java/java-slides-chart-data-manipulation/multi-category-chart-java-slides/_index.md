---
title: Graphique multi-catégories dans les diapositives Java
linktitle: Graphique multi-catégories dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Créez des graphiques multicatégories dans des diapositives Java à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec code source pour une visualisation impressionnante des données dans les présentations.
weight: 20
url: /fr/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction au graphique multi-catégories dans Java Slides avec Aspose.Slides

Dans ce didacticiel, nous apprendrons comment créer un graphique multi-catégories dans des diapositives Java à l'aide de l'API Aspose.Slides pour Java. Ce guide fournira des instructions étape par étape ainsi que le code source pour vous aider à créer un histogramme groupé avec plusieurs catégories et séries.

## Conditions préalables
Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre environnement de développement Java.

## Étape 1 : Configuration de l'environnement
Tout d’abord, importez les classes nécessaires et créez un nouvel objet Présentation pour travailler avec les diapositives.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : Ajout d'une diapositive et d'un graphique
Ensuite, créez une diapositive et ajoutez-y un histogramme groupé.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Étape 3 : Effacement des données existantes
Effacez toutes les données existantes du graphique.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Étape 4 : Configuration des catégories de données
Maintenant, configurons les catégories de données pour le graphique. Nous allons créer plusieurs catégories et les regrouper.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Ajoutez des catégories et regroupez-les
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Étape 5 : Ajout de séries
Maintenant, ajoutons une série au graphique avec des points de données.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Étape 6 : Sauvegarde de la présentation
Enfin, enregistrez la présentation avec le graphique.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez créé avec succès un graphique multicatégories dans une diapositive Java à l'aide d'Aspose.Slides. Vous pouvez personnaliser davantage ce tableau en fonction de vos besoins spécifiques.

## Code source complet pour le graphique multi-catégories dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Ajout de séries
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Enregistrer la présentation avec le graphique
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer un graphique multicatégorie dans des diapositives Java à l'aide de l'API Aspose.Slides pour Java. Nous avons parcouru un guide étape par étape avec le code source pour créer un histogramme groupé avec plusieurs catégories et séries.

## FAQ

### Comment puis-je personnaliser l’apparence du graphique ?

Vous pouvez personnaliser l'apparence du graphique en modifiant les propriétés telles que les couleurs, les polices et les styles. Reportez-vous à la documentation Aspose.Slides pour les options de personnalisation détaillées.

### Puis-je ajouter d'autres séries au graphique ?

Oui, vous pouvez ajouter des séries supplémentaires au graphique en suivant un processus similaire à celui indiqué à l'étape 5.

### Comment changer le type de graphique ?

 Pour modifier le type de graphique, remplacez`ChartType.ClusteredColumn` avec le type de graphique souhaité lors de l’ajout du graphique à l’étape 2.

### Comment puis-je ajouter un titre au graphique ?

 Vous pouvez ajouter un titre au graphique en utilisant le`ch.getChartTitle().getTextFrame().setText("Chart Title");` méthode.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

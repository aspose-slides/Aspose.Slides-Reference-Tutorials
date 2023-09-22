---
title: Graphique Sunburst dans les diapositives Java
linktitle: Graphique Sunburst dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Créez de superbes graphiques Sunburst dans des diapositives Java avec Aspose.Slides. Apprenez étape par étape la création de graphiques et la manipulation des données.
type: docs
weight: 16
url: /fr/java/chart-elements/sunburst-chart-java-slides/
---

## Introduction au graphique Sunburst dans Java Slides avec Aspose.Slides

Dans ce didacticiel, vous apprendrez à créer un graphique Sunburst dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Un graphique Sunburst est un graphique radial utilisé pour représenter des données hiérarchiques. Nous fournirons des instructions étape par étape ainsi que le code source.

## Conditions préalables

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Importer les bibliothèques requises

Tout d’abord, importez les bibliothèques nécessaires pour travailler avec Aspose.Slides et créez un graphique Sunburst dans votre application Java.

```java
import com.aspose.slides.*;
```

## Étape 2 : initialiser la présentation

Initialisez une présentation PowerPoint et spécifiez le répertoire dans lequel votre fichier de présentation sera enregistré.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Étape 3 : Créer le graphique Sunburst

Créez un graphique Sunburst sur une diapositive. Nous précisons la position (X, Y) et les dimensions (largeur, hauteur) du graphique.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Étape 4 : Préparer les données du graphique

Effacez toutes les catégories et données de séries existantes du graphique et créez un classeur de données pour le graphique.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Étape 5 : Définir la hiérarchie des graphiques

Définissez la structure hiérarchique du graphique Sunburst. Vous pouvez ajouter des branches, des tiges et des feuilles en tant que catégories.

```java
// Branche 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Branche 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Étape 6 : ajouter des données au graphique

Ajoutez des points de données à la série de graphiques Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Étape 7 : Enregistrez la présentation

Enfin, enregistrez la présentation avec le graphique Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Code source complet pour le graphique Sunburst dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//branche 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//branche 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à créer un graphique Sunburst dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Vous avez vu comment initialiser la présentation, créer le graphique, définir la hiérarchie du graphique, ajouter des points de données et enregistrer la présentation. Vous pouvez désormais utiliser ces connaissances pour créer des graphiques Sunburst interactifs et informatifs dans vos applications Java.

## FAQ

### Comment personnaliser l'apparence du graphique Sunburst ?

Vous pouvez personnaliser l'apparence du graphique Sunburst en modifiant les propriétés telles que les couleurs, les étiquettes et les styles. Reportez-vous à la documentation Aspose.Slides pour les options de personnalisation détaillées.

### Puis-je ajouter plus de points de données au graphique ?

 Oui, vous pouvez ajouter plus de points de données au graphique en utilisant le`series.getDataPoints().addDataPointForSunburstSeries()` méthode pour chaque point de données que vous souhaitez inclure.

### Comment puis-je ajouter des info-bulles au graphique Sunburst ?

Pour ajouter des info-bulles au graphique Sunburst, vous pouvez définir le format d'étiquette de données pour afficher des informations supplémentaires, telles que des valeurs ou des descriptions, lorsque vous survolez les segments du graphique.

### Est-il possible de créer des graphiques Sunburst interactifs avec des hyperliens ?

Oui, vous pouvez créer des graphiques Sunburst interactifs avec des hyperliens en ajoutant des hyperliens vers des éléments ou des segments de graphique spécifiques. Reportez-vous à la documentation Aspose.Slides pour plus de détails sur l'ajout d'hyperliens.
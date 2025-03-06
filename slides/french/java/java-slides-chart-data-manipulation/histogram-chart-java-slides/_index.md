---
title: Graphique d'histogramme dans les diapositives Java
linktitle: Graphique d'histogramme dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment créer des graphiques d'histogramme dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec le code source pour la visualisation des données.
weight: 19
url: /fr/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction au graphique d'histogramme dans Java Slides à l'aide d'Aspose.Slides

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un histogramme dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Un histogramme est utilisé pour représenter la distribution des données sur un intervalle continu.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée. Vous pouvez le télécharger depuis le[Site Aspose](https://releases.aspose.com/slides/java/).

## Étape 1 : initialisez votre projet

Créez un projet Java et incluez la bibliothèque Aspose.Slides dans les dépendances de votre projet.

## Étape 2 : Importer les bibliothèques nécessaires

```java
import com.aspose.slides.*;
```

## Étape 3 : Charger une présentation existante

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel vers votre document PowerPoint.

## Étape 4 : Créer un histogramme

Créons maintenant un histogramme sur une diapositive de la présentation.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Ajouter des points de données à la série
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Définir le type d'agrégation de l'axe horizontal sur Automatique
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Enregistrez la présentation
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Dans ce code, nous effaçons d’abord toutes les catégories et séries existantes du graphique. Ensuite, nous ajoutons des points de données à la série en utilisant le`getDataPoints().addDataPointForHistogramSeries` méthode. Enfin, nous définissons le type d'agrégation de l'axe horizontal sur Automatique et enregistrons la présentation.

## Code source complet pour le graphique d'histogramme dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment créer un histogramme dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Les graphiques d'histogramme sont des outils précieux pour visualiser la distribution des données sur un intervalle continu, et ils peuvent constituer un ajout puissant à vos présentations, en particulier lorsqu'il s'agit de contenu statistique ou analytique.

## FAQ

### Comment installer Aspose.Slides pour Java ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/). Suivez les instructions d'installation fournies sur leur site Web.

### A quoi sert un histogramme ?

Un histogramme est utilisé pour visualiser la distribution des données sur un intervalle continu. Il est couramment utilisé en statistiques pour représenter les distributions de fréquences.

### Puis-je personnaliser l’apparence du graphique histogramme ?

Oui, vous pouvez personnaliser l'apparence du graphique, y compris ses couleurs, ses étiquettes et ses axes, à l'aide de l'API Aspose.Slides.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

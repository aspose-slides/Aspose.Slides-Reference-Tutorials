---
"description": "Apprenez à créer des histogrammes dans des présentations PowerPoint avec Aspose.Slides pour Java. Guide étape par étape avec code source pour la visualisation des données."
"linktitle": "Histogramme dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Histogramme dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Histogramme dans les diapositives Java


## Introduction aux histogrammes en Java (diapositives) avec Aspose.Slides

Dans ce tutoriel, nous vous guiderons dans la création d'un histogramme dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Un histogramme permet de représenter la distribution des données sur un intervalle continu.

## Prérequis

Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger depuis le [Site Web d'Aspose](https://releases.aspose.com/slides/java/).

## Étape 1 : Initialisez votre projet

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

Assurez-vous de remplacer `"Your Document Directory"` avec le chemin réel vers votre document PowerPoint.

## Étape 4 : Créer un histogramme

Maintenant, créons un histogramme sur une diapositive de la présentation.

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
    
    // Enregistrer la présentation
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Dans ce code, nous effaçons d'abord toutes les catégories et séries existantes du graphique. Ensuite, nous ajoutons des points de données à la série à l'aide de la commande `getDataPoints().addDataPointForHistogramSeries` méthode. Enfin, nous définissons le type d'agrégation de l'axe horizontal sur Automatique et enregistrons la présentation.

## Code source complet pour un histogramme en Java (diapositives)

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

Dans ce tutoriel, nous avons découvert comment créer un histogramme dans une présentation PowerPoint à l'aide de l'API Aspose.Slides pour Java. Les histogrammes sont des outils précieux pour visualiser la distribution des données sur un intervalle continu et peuvent constituer un atout précieux pour vos présentations, notamment pour les contenus statistiques ou analytiques.

## FAQ

### Comment installer Aspose.Slides pour Java ?

Vous pouvez télécharger la bibliothèque Aspose.Slides pour Java à partir de [ici](https://releases.aspose.com/slides/java/)Suivez les instructions d'installation fournies sur leur site Web.

### À quoi sert un histogramme ?

Un histogramme permet de visualiser la distribution des données sur un intervalle continu. Il est couramment utilisé en statistiques pour représenter les distributions de fréquences.

### Puis-je personnaliser l’apparence du graphique d’histogramme ?

Oui, vous pouvez personnaliser l’apparence du graphique, y compris ses couleurs, ses étiquettes et ses axes, à l’aide de l’API Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Apprenez à créer des diapositives Java avec des marqueurs par défaut dans les graphiques à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec code source."
"linktitle": "Marqueurs par défaut dans les graphiques des diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Marqueurs par défaut dans les graphiques des diapositives Java"
"url": "/fr/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Marqueurs par défaut dans les graphiques des diapositives Java


## Introduction aux marqueurs par défaut dans les graphiques en Java (diapositives)

Dans ce tutoriel, nous allons découvrir comment créer un graphique avec des marqueurs par défaut à l'aide d'Aspose.Slides pour Java. Les marqueurs par défaut sont des symboles ou des formes ajoutés aux points de données d'un graphique pour les mettre en évidence. Nous allons créer un graphique en courbes avec des marqueurs pour visualiser les données.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java.

## Étape 1 : Créer une présentation

Commençons par créer une présentation et y ajouter une diapositive. Nous y ajouterons ensuite un graphique.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Étape 2 : Ajouter un graphique linéaire avec des marqueurs

Ajoutons maintenant un graphique linéaire avec des marqueurs à la diapositive. Nous allons également supprimer toutes les données par défaut du graphique.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Étape 3 : Remplir les données du graphique

Nous allons remplir le graphique avec des données d'exemple. Dans cet exemple, nous allons créer deux séries avec des points de données et des catégories.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Série 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Série 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Remplissage des données de la série
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Étape 4 : Personnaliser le graphique

Vous pouvez personnaliser davantage le graphique, par exemple en ajoutant une légende et en ajustant son apparence.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Étape 5 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique à l’emplacement souhaité.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez créé un graphique linéaire avec des marqueurs par défaut à l'aide d'Aspose.Slides pour Java.

## Code source complet des marqueurs par défaut dans les diapositives Java

```java
        // Le chemin vers le répertoire des documents.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Prendre la deuxième série de graphiques
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Les données de la série sont maintenant en cours de remplissage
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusion

Dans ce tutoriel complet, vous avez appris à créer des diapositives Java avec des marqueurs par défaut dans des graphiques à l'aide d'Aspose.Slides pour Java. Nous avons couvert l'intégralité du processus, de la configuration d'une présentation à la personnalisation de l'apparence du graphique, en passant par l'enregistrement du résultat.

## FAQ

### Comment puis-je changer les symboles des marqueurs ?

Vous pouvez personnaliser les symboles de marqueur en définissant le style de marqueur pour chaque point de données. `IDataPoint.setMarkerStyle()` pour changer le symbole du marqueur.

### Comment ajuster les couleurs du graphique ?

Pour modifier les couleurs du graphique, vous pouvez utiliser le `IChartSeriesFormat` et `IShapeFillFormat` interfaces pour définir les propriétés de remplissage et de ligne.

### Puis-je ajouter des étiquettes aux points de données ?

Oui, vous pouvez ajouter des étiquettes aux points de données à l'aide de l' `IDataPoint.getLabel()` méthode et les personnaliser selon vos besoins.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
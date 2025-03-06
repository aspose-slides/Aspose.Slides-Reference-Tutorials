---
title: Diagramme encadré dans les diapositives Java
linktitle: Diagramme encadré dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer des diagrammes en boîtes dans des présentations Java avec Aspose.Slides. Guide étape par étape et code source inclus pour une visualisation efficace des données.
weight: 10
url: /fr/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction au diagramme en boîtes dans Aspose.Slides pour Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un diagramme en boîtes à l'aide d'Aspose.Slides pour Java. Les diagrammes en boîte sont utiles pour visualiser des données statistiques avec différents quartiles et valeurs aberrantes. Nous fournirons des instructions étape par étape ainsi que le code source pour vous aider à démarrer.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée et configurée.
- Un environnement de développement Java mis en place.

## Étape 1 : initialiser la présentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Dans cette étape, nous initialisons un objet de présentation en utilisant le chemin d'accès à un fichier PowerPoint existant ("test.pptx" dans cet exemple).

## Étape 2 : Créer le graphique en boîtes

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Dans cette étape, nous créons une forme de diagramme en boîte sur la première diapositive de la présentation. Nous effaçons également toutes les catégories et séries existantes du graphique.

## Étape 3 : Définir les catégories

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 Dans cette étape, nous définissons les catégories du diagramme en boîtes. Nous utilisons le`IChartDataWorkbook` pour ajouter des catégories et les étiqueter en conséquence.

## Étape 4 : Créer la série

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Ici, nous créons une série BoxAndWhisker pour le graphique et configurons diverses options telles que la méthode quartile, la ligne moyenne, les marqueurs moyens, les points internes et les points aberrants.

## Étape 5 : ajouter des points de données

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Dans cette étape, nous ajoutons des points de données à la série BoxAndWhisker. Ces points de données représentent les données statistiques du graphique.

## Étape 6 : Enregistrez la présentation

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Enfin, nous enregistrons la présentation avec le Box Chart dans un nouveau fichier PowerPoint nommé « BoxAndWhisker.pptx ».

Toutes nos félicitations! Vous avez créé avec succès un diagramme en boîtes à l’aide d’Aspose.Slides pour Java. Vous pouvez personnaliser davantage le graphique en ajustant diverses propriétés et en ajoutant davantage de points de données si nécessaire.

## Code source complet pour le graphique en boîtes dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer un graphique en boîtes à l'aide d'Aspose.Slides pour Java. Les diagrammes en boîte sont des outils précieux pour visualiser les données statistiques, y compris les quartiles et les valeurs aberrantes. Nous avons fourni un guide étape par étape ainsi que le code source pour vous aider à démarrer dans la création de diagrammes en boîtes dans vos applications Java.

## FAQ

### Comment puis-je modifier l’apparence du diagramme en boîtes ?

Vous pouvez personnaliser l'apparence du graphique en boîtes en modifiant les propriétés telles que les styles de ligne, les couleurs et les polices. Reportez-vous à la documentation Aspose.Slides pour Java pour plus de détails sur la personnalisation des graphiques.

### Puis-je ajouter des séries de données supplémentaires au graphique en boîtes ?

 Oui, vous pouvez ajouter plusieurs séries de données au graphique en boîtes en créant des`IChartSeries` objets et en leur ajoutant des points de données.

### Que signifie QuartileMethodType.Exclusive ?

 Le`QuartileMethodType.Exclusive` Le paramètre spécifie que les calculs de quartile doivent être effectués à l’aide de la méthode exclusive. Vous pouvez choisir différentes méthodes de calcul de quartile en fonction de vos données et de vos besoins.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Apprenez à créer des graphiques en boîte dans vos présentations Java avec Aspose.Slides. Guide étape par étape et code source inclus pour une visualisation efficace des données."
"linktitle": "Diagramme en boîte dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagramme en boîte dans les diapositives Java"
"url": "/fr/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramme en boîte dans les diapositives Java


## Introduction aux graphiques en boîte dans Aspose.Slides pour Java

Dans ce tutoriel, nous vous expliquerons comment créer un graphique en boîte avec Aspose.Slides pour Java. Les graphiques en boîte sont utiles pour visualiser des données statistiques avec différents quartiles et valeurs aberrantes. Nous vous fournirons des instructions étape par étape ainsi que le code source pour vous aider à démarrer.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée et configurée.
- Un environnement de développement Java mis en place.

## Étape 1 : Initialiser la présentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Dans cette étape, nous initialisons un objet de présentation en utilisant le chemin d'accès à un fichier PowerPoint existant (« test.pptx » dans cet exemple).

## Étape 2 : Créer le graphique en boîte

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Dans cette étape, nous créons un graphique en boîte sur la première diapositive de la présentation. Nous supprimons également toutes les catégories et séries existantes du graphique.

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

Dans cette étape, nous définissons les catégories du graphique en boîte. Nous utilisons `IChartDataWorkbook` pour ajouter des catégories et les étiqueter en conséquence.

## Étape 4 : Créer la série

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Ici, nous créons une série BoxAndWhisker pour le graphique et configurons diverses options telles que la méthode des quartiles, la ligne moyenne, les marqueurs moyens, les points intérieurs et les points aberrants.

## Étape 5 : Ajouter des points de données

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Dans cette étape, nous ajoutons des points de données à la série BoxAndWhisker. Ces points de données représentent les données statistiques du graphique.

## Étape 6 : Enregistrer la présentation

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Enfin, nous enregistrons la présentation avec le graphique en boîte dans un nouveau fichier PowerPoint nommé « BoxAndWhisker.pptx ».

Félicitations ! Vous avez créé un graphique en boîte avec Aspose.Slides pour Java. Vous pouvez personnaliser davantage le graphique en ajustant diverses propriétés et en ajoutant des points de données si nécessaire.

## Code source complet pour le graphique en boîte dans les diapositives Java

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

Dans ce tutoriel, nous avons appris à créer un graphique en boîte avec Aspose.Slides pour Java. Les graphiques en boîte sont des outils précieux pour visualiser des données statistiques, notamment les quartiles et les valeurs aberrantes. Nous avons fourni un guide étape par étape ainsi que le code source pour vous aider à démarrer avec la création de graphiques en boîte dans vos applications Java.

## FAQ

### Comment puis-je modifier l'apparence du graphique en boîte ?

Vous pouvez personnaliser l'apparence du graphique en boîte en modifiant des propriétés telles que les styles de ligne, les couleurs et les polices. Consultez la documentation d'Aspose.Slides pour Java pour plus de détails sur la personnalisation des graphiques.

### Puis-je ajouter des séries de données supplémentaires au graphique en boîte ?

Oui, vous pouvez ajouter plusieurs séries de données au graphique en boîte en créant des séries supplémentaires. `IChartSeries` objets et leur ajouter des points de données.

### Que signifie QuartileMethodType.Exclusive ?

Le `QuartileMethodType.Exclusive` Ce paramètre spécifie que les calculs de quartiles doivent être effectués selon la méthode exclusive. Vous pouvez choisir différentes méthodes de calcul de quartiles en fonction de vos données et de vos besoins.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
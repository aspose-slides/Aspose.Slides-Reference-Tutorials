---
"description": "Créez de superbes cartes graphiques dans des présentations PowerPoint avec Aspose.Slides pour Java. Guide étape par étape et code source pour les développeurs Java."
"linktitle": "Diagramme cartographique dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagramme cartographique dans les diapositives Java"
"url": "/fr/java/chart-elements/map-chart-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramme cartographique dans les diapositives Java


## Introduction aux diagrammes cartographiques en Java (diapositives) avec Aspose.Slides pour Java

Dans ce tutoriel, nous vous guiderons dans la création d'une carte graphique dans une présentation PowerPoint avec Aspose.Slides pour Java. Les cartes graphiques sont un excellent moyen de visualiser des données géographiques dans vos présentations.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est intégrée à votre projet Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configurez votre projet

Assurez-vous d'avoir configuré votre projet Java et ajouté la bibliothèque Aspose.Slides pour Java au chemin de classe de votre projet.

## Étape 2 : Créer une présentation PowerPoint

Commençons par créer une nouvelle présentation PowerPoint.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Étape 3 : Ajouter une carte

Nous allons maintenant ajouter un graphique cartographique à la présentation.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Étape 4 : Ajouter des données au graphique cartographique

Ajoutons des données à la carte. Nous allons créer une série et y ajouter des points de données.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Étape 5 : Ajouter des catégories

Nous devons ajouter des catégories à la carte, représentant différentes régions géographiques.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Étape 6 : Personnaliser les points de données

Vous pouvez personnaliser des points de données individuels. Dans cet exemple, nous modifions la couleur et la valeur d'un point de données spécifique.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Étape 7 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique cartographique.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

Et voilà ! Vous avez créé une carte dans une présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez personnaliser davantage le graphique et explorer les autres fonctionnalités d'Aspose.Slides pour enrichir vos présentations.

## Code source complet pour les diapositives de la carte graphique en Java

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//créer un graphique vide
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Ajouter des séries et quelques points de données
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//ajouter des catégories
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//modifier la valeur du point de données
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//définir l'apparence des points de données
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce tutoriel, nous avons expliqué comment créer une carte dans une présentation PowerPoint avec Aspose.Slides pour Java. Les cartes constituent un moyen efficace de visualiser des données géographiques et de rendre vos présentations plus attrayantes et informatives. Voici les étapes clés :

## FAQ

### Comment puis-je changer le type de carte ?

Vous pouvez modifier le type de graphique en remplaçant `ChartType.Map` avec le type de graphique souhaité lors de la création du graphique à l'étape 3.

### Comment puis-je personnaliser l'apparence de la carte ?

Vous pouvez personnaliser l’apparence du graphique en modifiant les propriétés du `dataPoint` objet à l'étape 6. Vous pouvez modifier les couleurs, les valeurs et bien plus encore.

### Puis-je ajouter plus de points de données et de catégories ?

Oui, vous pouvez ajouter autant de points de données et de catégories que nécessaire. Utilisez simplement le `series.getDataPoints().addDataPointForMapSeries()` et `chart.getChartData().getCategories().add()` méthodes pour les ajouter.

### Comment intégrer Aspose.Slides pour Java dans mon projet ?

Téléchargez la bibliothèque à partir de [ici](https://releases.aspose.com/slides/java/) et ajoutez-le au classpath de votre projet.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
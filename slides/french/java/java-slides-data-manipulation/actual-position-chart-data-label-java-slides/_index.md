---
"description": "Découvrez comment obtenir la position réelle des étiquettes de données de graphique dans Java Slides avec Aspose.Slides pour Java. Guide étape par étape avec code source."
"linktitle": "Obtenir la position réelle de l'étiquette des données du graphique dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Obtenir la position réelle de l'étiquette des données du graphique dans les diapositives Java"
"url": "/fr/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir la position réelle de l'étiquette des données du graphique dans les diapositives Java


## Introduction à la recherche de la position réelle de l'étiquette des données d'un graphique dans les diapositives Java

Dans ce tutoriel, vous apprendrez à récupérer la position réelle des étiquettes de données d'un graphique avec Aspose.Slides pour Java. Nous créerons un programme Java qui générera une présentation PowerPoint avec un graphique, personnalisera les étiquettes de données, puis ajoutera des formes représentant leur position.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet Java.

## Étape 1 : Créer une présentation PowerPoint

Commençons par créer une présentation PowerPoint et y ajouter un graphique. Nous personnaliserons les étiquettes de données du graphique plus tard dans le tutoriel.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Étape 2 : Personnaliser les étiquettes de données
Personnalisons maintenant les étiquettes de données de la série de graphiques. Nous allons définir leur position et afficher les valeurs.

```java
try {
    // ... (code précédent)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (code restant)
} finally {
    if (pres != null) pres.dispose();
}
```

## Étape 3 : Obtenir la position réelle des étiquettes de données
Dans cette étape, nous allons parcourir les points de données de la série de graphiques et récupérer la position réelle des étiquettes de données dont la valeur est supérieure à 4. Nous ajouterons ensuite des points de suspension pour représenter ces positions.

```java
try {
    // ... (code précédent)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (code restant)
} finally {
    if (pres != null) pres.dispose();
}
```

## Étape 4 : Enregistrer la présentation
Enfin, enregistrez la présentation générée dans un fichier.

```java
try {
    // ... (code précédent)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Code source complet pour obtenir la position réelle de l'étiquette de données du graphique dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//FAIRE
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce tutoriel, vous avez appris à récupérer la position réelle des étiquettes de données de graphiques dans Java Slides avec Aspose.Slides pour Java. Vous pouvez désormais utiliser ces connaissances pour enrichir vos présentations PowerPoint avec des étiquettes de données personnalisées et des représentations visuelles de leur position.

## FAQ

### Comment puis-je personnaliser les étiquettes de données dans un graphique ?

Pour personnaliser les étiquettes de données dans un graphique, vous pouvez utiliser l' `setDefaultDataLabelFormat` sur la série de graphiques et définissez des propriétés comme la position et la visibilité. Par exemple :
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Comment puis-je ajouter des formes pour représenter les positions des étiquettes de données ?

Vous pouvez parcourir les points de données d'une série de graphiques et utiliser le `getActualX`, `getActualY`, `getActualWidth`, et `getActualHeight` de l'étiquette de données pour obtenir sa position. Vous pouvez ensuite ajouter des formes à l'aide de `addAutoShape` méthode. Voici un exemple :
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Comment puis-je enregistrer la présentation générée ?

Vous pouvez enregistrer la présentation générée à l'aide de l' `save` méthode. Fournissez le chemin du fichier souhaité et le `SaveFormat` comme paramètres. Par exemple :
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
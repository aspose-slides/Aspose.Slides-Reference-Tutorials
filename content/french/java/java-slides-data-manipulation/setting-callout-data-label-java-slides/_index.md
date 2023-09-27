---
title: Définition d'une légende pour l'étiquette de données dans les diapositives Java
linktitle: Définition d'une légende pour l'étiquette de données dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment configurer des légendes pour les étiquettes de données dans Aspose.Slides pour Java. Guide étape par étape avec le code source.
type: docs
weight: 25
url: /fr/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Introduction à la définition de la légende pour l'étiquette de données dans Aspose.Slides pour Java

Dans ce didacticiel, nous montrerons comment configurer des légendes pour les étiquettes de données dans un graphique à l'aide d'Aspose.Slides pour Java. Les légendes peuvent être utiles pour mettre en évidence des points de données spécifiques dans votre graphique. Nous allons parcourir le code étape par étape et fournir le code source nécessaire.

## Conditions préalables

- Aspose.Slides pour Java devrait être installé.
- Créez un projet Java et ajoutez la bibliothèque Aspose.Slides à votre projet.

## Étape 1 : Créer une présentation et ajouter un graphique

 Tout d’abord, nous devons créer une présentation et ajouter un graphique à une diapositive. Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Étape 2 : configurer le graphique

Ensuite, nous allons configurer le graphique en définissant des propriétés telles que la légende, les séries et les catégories.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configurer les séries et les catégories (vous pouvez ajuster le nombre de séries et de catégories)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Ajoutez des points de données ici
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Étape 3 : Personnaliser les étiquettes de données

Nous allons maintenant personnaliser les étiquettes de données, notamment en définissant des légendes pour la dernière série.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Personnalisez le formatage des points de données (Remplissage, Ligne, etc.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Personnalisez le formatage des étiquettes (Police, Remplissage, etc.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Activer les accroches
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Étape 4 : Enregistrez la présentation

Enfin, enregistrez la présentation avec le graphique configuré.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Vous avez désormais configuré avec succès des légendes pour les étiquettes de données dans un graphique à l'aide d'Aspose.Slides pour Java. Personnalisez le code en fonction de vos exigences spécifiques en matière de graphique et de données.

## Code source complet pour définir la légende de l'étiquette de données dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment configurer des légendes pour les étiquettes de données dans un graphique à l'aide d'Aspose.Slides pour Java. Les légendes sont des outils précieux pour mettre en valeur des points de données spécifiques dans vos graphiques et présentations. Nous avons fourni un guide étape par étape ainsi que le code source pour vous aider à réaliser cette personnalisation.

## FAQ

### Comment personnaliser l’apparence des étiquettes de données ?

Pour personnaliser l'apparence des étiquettes de données, vous pouvez modifier des propriétés telles que les styles de police, de remplissage et de trait. Par exemple:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Comment puis-je activer ou désactiver les légendes pour les étiquettes de données ?

 Pour activer ou désactiver les légendes pour les étiquettes de données, utilisez l'option`setShowLabelAsDataCallout` méthode. Réglez-le sur`true` pour activer les légendes et`false` pour les désactiver.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Activer les accroches
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Désactiver les accroches
```

### Puis-je personnaliser les lignes de repère des étiquettes de données ?

Oui, vous pouvez personnaliser les lignes de repère des étiquettes de données à l'aide de propriétés telles que le style de ligne, la couleur et la largeur. Par exemple:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Activer les lignes de repère
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Voici quelques options de personnalisation courantes pour les étiquettes de données et les légendes dans Aspose.Slides pour Java. Vous pouvez adapter davantage l’apparence à vos besoins spécifiques.
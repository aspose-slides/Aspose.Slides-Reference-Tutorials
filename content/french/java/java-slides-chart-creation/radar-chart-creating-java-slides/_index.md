---
title: Création de graphiques radar dans Java Slides
linktitle: Création de graphiques radar dans Java Slides
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment créer des graphiques radar dans des présentations Java PowerPoint à l'aide de l'API Aspose.Slides pour Java.
type: docs
weight: 10
url: /fr/java/chart-creation/radar-chart-creating-java-slides/
---

## Introduction à la création d'un graphique radar dans Java Slides

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un graphique radar à l'aide de l'API Aspose.Slides pour Java. Les graphiques radar sont utiles pour visualiser les données selon un motif circulaire, ce qui facilite la comparaison de plusieurs séries de données. Nous fournirons des instructions étape par étape ainsi que le code source Java.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est intégrée à votre projet. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configuration de la présentation

Commençons par créer une nouvelle présentation PowerPoint et y ajouter une diapositive.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Étape 2 : Ajout d'une carte radar

Ensuite, nous ajouterons une carte radar à la diapositive. Nous préciserons la position et les dimensions du graphique.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Étape 3 : Définition des données du graphique

Nous allons maintenant définir les données du graphique. Cela implique la création d'un classeur de données, l'ajout de catégories et l'ajout de séries.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Définir le titre du graphique
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Supprimer les séries et catégories générées par défaut
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Ajout de nouvelles catégories
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Ajout d'une nouvelle série
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Étape 4 : Remplir les données de la série

Nous allons maintenant remplir les données de série pour notre carte radar.

```java
// Remplir les données de série pour la série 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Définir la couleur de la série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Remplir les données de série pour la série 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Définir la couleur de la série
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Étape 5 : personnalisation de l'axe et des légendes

Personnalisons les axes et les légendes de notre carte radar.

```java
// Définir la position de la légende
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Définition des propriétés du texte de l'axe des catégories
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Définition des propriétés du texte des légendes
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Définition des propriétés du texte de l'axe des valeurs
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Définition du format du numéro d'axe des valeurs
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Tableau de réglage de la valeur unitaire principale
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Étape 6 : Sauvegarde de la présentation

Enfin, enregistrez la présentation générée avec le graphique radar

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

C'est ça! Vous avez créé avec succès un graphique radar dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez désormais personnaliser davantage cet exemple pour l'adapter à vos besoins spécifiques.

## Code source complet pour la création de graphiques radar dans des diapositives Java

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Accéder à la première diapositive
	ISlide sld = pres.getSlides().get_Item(0);
	// Ajouter une carte radar
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Définition de l'index de la feuille de données du graphique
	int defaultWorksheetIndex = 0;
	// Obtenir la feuille de travail des données du graphique
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Définir le titre du graphique
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Supprimer les séries et catégories générées par défaut
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Ajout de nouvelles catégories
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Ajout d'une nouvelle série
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Remplir maintenant les données de série
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Définir la couleur de la série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//Remplir maintenant les données d'une autre série
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Définir la couleur de la série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Définir la position de la légende
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Définition des propriétés du texte de l'axe des catégories
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Définition des propriétés du texte des légendes
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Définition des propriétés du texte de l'axe des valeurs
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Définition du format du numéro d'axe des valeurs
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Tableau de réglage de la valeur unitaire principale
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Enregistrer la présentation générée
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à créer un graphique radar dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez appliquer ces concepts pour visualiser et présenter efficacement vos données dans vos applications Java.

## FAQ

### Comment puis-je modifier le titre du graphique ?

Pour changer le titre du graphique, modifiez la ligne suivante :
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Puis-je ajouter d'autres séries de données au graphique radar ?

Oui, vous pouvez ajouter d'autres séries de données en suivant les étapes de « Étape 3 » et « Étape 4 » pour chaque série supplémentaire que vous souhaitez inclure.

### Comment personnaliser les couleurs du graphique ?

 Vous pouvez personnaliser les couleurs de la série en modifiant les lignes qui définissent le`SolidFillColor` propriété pour chaque série. Par exemple:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Comment puis-je modifier les étiquettes et le formatage des axes ?

Reportez-vous à « Étape 5 » pour personnaliser les étiquettes et le formatage des axes, y compris la taille et la couleur de la police.

### Comment puis-je enregistrer le graphique dans un format de fichier différent ?

Vous pouvez changer le format de sortie en modifiant l'extension du fichier dans le`outPath` variable et en utilisant le`SaveFormat` . Par exemple, pour enregistrer au format PDF, utilisez`SaveFormat.Pdf`.
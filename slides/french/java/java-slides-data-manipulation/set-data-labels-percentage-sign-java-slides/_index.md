---
title: Définir le pourcentage de connexion des étiquettes de données dans les diapositives Java
linktitle: Définir le pourcentage de connexion des étiquettes de données dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des étiquettes de données avec des signes de pourcentage dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Créez des graphiques attrayants avec des conseils étape par étape et du code source.
type: docs
weight: 17
url: /fr/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Introduction à la définition du pourcentage de connexion aux étiquettes de données dans Aspose.Slides pour Java

Dans ce guide, nous vous guiderons tout au long du processus de définition d'étiquettes de données avec un signe de pourcentage à l'aide d'Aspose.Slides pour Java. Nous allons créer une présentation PowerPoint avec un histogramme empilé et configurer les étiquettes de données pour afficher les pourcentages.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une nouvelle présentation

Tout d’abord, nous créons une nouvelle présentation PowerPoint à l’aide d’Aspose.Slides.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter une diapositive et un graphique

Ensuite, nous ajoutons une diapositive et un histogramme empilé à la présentation.

```java
// Obtenir la référence de la diapositive
ISlide slide = presentation.getSlides().get_Item(0);

// Ajouter un graphique PercentsStackedColumn sur une diapositive
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Étape 3 : Configurer le format du numéro d'axe

Pour afficher les pourcentages, nous devons configurer le format numérique pour l'axe vertical du graphique.

```java
// Définir NumberFormatLinkedToSource sur false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Étape 4 : ajouter des données graphiques

Nous ajoutons des données au graphique en créant des séries et des points de données. Dans cet exemple, nous ajoutons deux séries avec leurs points de données respectifs.

```java
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Ajouter une nouvelle série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Ajouter une nouvelle série
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Étape 5 : Personnaliser les étiquettes de données

Maintenant, personnalisons l'apparence des étiquettes de données.

```java
// Définition des propriétés LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Étape 6 : Enregistrez la présentation

Enfin, nous enregistrons la présentation dans un fichier PowerPoint.

```java
// Écrire la présentation sur le disque
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez créé avec succès une présentation PowerPoint avec un histogramme empilé et configuré des étiquettes de données pour afficher des pourcentages à l'aide d'Aspose.Slides pour Java.

## Code source complet pour définir les étiquettes de données Pourcentage de connexion dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
// Obtenir la référence de la diapositive
ISlide slide = presentation.getSlides().get_Item(0);
// Ajouter un graphique PercentsStackedColumn sur une diapositive
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Définir NumberFormatLinkedToSource sur false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Ajouter une nouvelle série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Définition de la couleur de remplissage des séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Définition des propriétés LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ajouter une nouvelle série
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Définition du type et de la couleur de remplissage
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Écrire la présentation sur le disque
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Conclusion

En suivant ce guide, vous avez appris à créer des présentations attrayantes avec des étiquettes de données basées sur des pourcentages, ce qui peut être particulièrement utile pour transmettre efficacement des informations dans des rapports commerciaux, du matériel pédagogique, etc.

## FAQ

### Comment puis-je changer les couleurs de la série de graphiques ?

 Vous pouvez modifier la couleur de remplissage des séries de graphiques à l'aide de l'icône`setFill` méthode comme indiqué dans l’exemple.

### Puis-je personnaliser la taille de la police des étiquettes de données ?

Oui, vous pouvez personnaliser la taille de la police des étiquettes de données en définissant l'option`setFontHeight` propriété comme démontré dans le code.

### Comment puis-je ajouter plus de séries au graphique ?

 Vous pouvez ajouter des séries supplémentaires au graphique en utilisant le`add` méthode sur le`IChartSeriesCollection` objet.

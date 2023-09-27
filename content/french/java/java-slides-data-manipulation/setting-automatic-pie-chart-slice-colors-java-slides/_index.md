---
title: Définition des couleurs automatiques des tranches de graphique à secteurs dans les diapositives Java
linktitle: Définition des couleurs automatiques des tranches de graphique à secteurs dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment créer des diagrammes circulaires dynamiques avec des couleurs de tranche automatiques dans des présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec le code source.
type: docs
weight: 24
url: /fr/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Introduction à la définition automatique des couleurs des tranches de graphique à secteurs dans les diapositives Java

Dans ce didacticiel, nous allons explorer comment créer un graphique à secteurs dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java et définir les couleurs de tranche automatiques pour le graphique. Nous fournirons des conseils étape par étape ainsi que le code source.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque depuis le site Web d'Aspose :[Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

## Étape 1 : Importer les packages requis

Tout d’abord, vous devez importer les packages nécessaires depuis Aspose.Slides pour Java :

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Étape 2 : Créer une présentation PowerPoint

 Instancier le`Presentation` classe pour créer une nouvelle présentation PowerPoint :

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Étape 3 : ajouter une diapositive

Accédez à la première diapositive de la présentation et ajoutez-y un graphique avec les données par défaut :

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Étape 4 : Définir le titre du graphique

Définissez un titre pour le graphique :

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Étape 5 : Configurer les données du graphique

Définissez le graphique pour qu'il affiche les valeurs de la première série et configurez les données du graphique :

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Étape 6 : ajouter des catégories et des séries

Ajoutez de nouvelles catégories et séries au graphique :

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Étape 7 : Remplir les données de la série

Remplissez les données de série pour le graphique à secteurs :

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Étape 8 : Activer des couleurs de tranches variées

Activez des couleurs de tranche variées pour le graphique à secteurs :

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Étape 9 : Enregistrez la présentation

Enfin, enregistrez la présentation dans un fichier PowerPoint :

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir les couleurs automatiques des tranches de graphique à secteurs dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
try
{
	// Accéder à la première diapositive
	ISlide slides = presentation.getSlides().get_Item(0);
	// Ajouter un graphique avec les données par défaut
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Tableau de réglage Titre
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Définir la première série sur Afficher les valeurs
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Définition de l'index de la feuille de données du graphique
	int defaultWorksheetIndex = 0;
	//Obtenir la feuille de calcul des données du graphique
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Supprimer les séries et catégories générées par défaut
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Ajout de nouvelles catégories
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Ajout d'une nouvelle série
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Remplir maintenant les données de série
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Vous avez créé avec succès un diagramme circulaire dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java et l'avez configuré pour avoir des couleurs de tranche automatiques. Ce guide étape par étape vous fournit le code source nécessaire pour y parvenir. Vous pouvez personnaliser davantage le graphique et la présentation selon vos besoins.

## FAQ

### Comment puis-je personnaliser les couleurs des tranches individuelles dans le diagramme circulaire ?

 Pour personnaliser les couleurs des tranches individuelles du graphique à secteurs, vous pouvez utiliser l'option`getAutomaticSeriesColors`méthode pour récupérer le jeu de couleurs par défaut, puis modifier les couleurs si nécessaire. Voici un exemple :

```java
// Obtenez le jeu de couleurs par défaut
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modifier les couleurs selon vos besoins
colors.get_Item(0).setColor(Color.RED); // Définir la couleur de la première tranche sur rouge
colors.get_Item(1).setColor(Color.BLUE); // Définir la couleur de la deuxième tranche sur bleu
// Ajoutez plus de modifications de couleur si nécessaire
```

### Comment puis-je ajouter une légende au diagramme circulaire ?

 Pour ajouter une légende au diagramme circulaire, vous pouvez utiliser le`getLegend` et configurez-la comme suit :

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Définir la position de la légende
legend.setOverlay(true); // Afficher la légende sur le graphique
```

### Puis-je modifier la police et le style du titre ?

Oui, vous pouvez modifier la police et le style du titre. Utilisez le code suivant pour définir la police et le style du titre :

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Définir la taille de la police
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Mettre le titre en gras
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Mettre le titre en italique
```

Vous pouvez ajuster la taille de la police, le gras et le style italique selon vos besoins.
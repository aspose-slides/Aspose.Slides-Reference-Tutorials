---
"description": "Apprenez à créer des graphiques à secteurs dynamiques avec couleurs de tranches automatiques dans des présentations PowerPoint Java avec Aspose.Slides pour Java. Guide étape par étape avec code source."
"linktitle": "Définition automatique des couleurs des secteurs de graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définition automatique des couleurs des secteurs de graphiques dans les diapositives Java"
"url": "/fr/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définition automatique des couleurs des secteurs de graphiques dans les diapositives Java


## Introduction à la définition automatique des couleurs des secteurs de graphiques dans les diapositives Java

Dans ce tutoriel, nous découvrirons comment créer un graphique à secteurs dans une présentation PowerPoint avec Aspose.Slides pour Java et définir automatiquement les couleurs des tranches. Nous vous fournirons des instructions étape par étape ainsi que le code source.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez la télécharger sur le site web d'Aspose : [Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

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

Instancier le `Presentation` classe pour créer une nouvelle présentation PowerPoint :

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Étape 3 : Ajouter une diapositive

Accédez à la première diapositive de la présentation et ajoutez-y un graphique avec des données par défaut :

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Étape 4 : Définir le titre du graphique

Définir un titre pour le graphique :

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Étape 5 : Configurer les données du graphique

Définissez le graphique pour afficher les valeurs de la première série et configurez les données du graphique :

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Étape 6 : Ajouter des catégories et des séries

Ajoutez de nouvelles catégories et séries au graphique :

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Étape 7 : Remplir les données de la série

Renseignez les données de la série pour le graphique à secteurs :

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Étape 8 : Activer les couleurs de tranches variées

Activer différentes couleurs de tranches pour le graphique à secteurs :

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Étape 9 : Enregistrer la présentation

Enfin, enregistrez la présentation dans un fichier PowerPoint :

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Code source complet pour la définition automatique des couleurs des secteurs de diagramme dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
try
{
	// Accéder à la première diapositive
	ISlide slides = presentation.getSlides().get_Item(0);
	// Ajouter un graphique avec des données par défaut
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Titre du tableau de réglage
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Définir la première série sur Afficher les valeurs
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Définition de l'index de la feuille de données du graphique
	int defaultWorksheetIndex = 0;
	// Obtenir la feuille de calcul des données du graphique
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Supprimer les séries et catégories générées par défaut
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Ajout de nouvelles catégories
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Ajout de nouvelles séries
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Les données de la série sont maintenant en cours de remplissage
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

Vous avez créé avec succès un graphique à secteurs dans une présentation PowerPoint avec Aspose.Slides pour Java et l'avez configuré pour des couleurs de tranches automatiques. Ce guide étape par étape vous fournit le code source nécessaire pour y parvenir. Vous pouvez personnaliser davantage le graphique et la présentation selon vos besoins.

## FAQ

### Comment puis-je personnaliser les couleurs des tranches individuelles du graphique à secteurs ?

Pour personnaliser les couleurs des tranches individuelles du graphique à secteurs, vous pouvez utiliser le `getAutomaticSeriesColors` Méthode permettant de récupérer le jeu de couleurs par défaut et de modifier les couleurs selon les besoins. Voici un exemple :

```java
// Obtenir le schéma de couleurs par défaut
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Modifiez les couleurs selon vos besoins
colors.get_Item(0).setColor(Color.RED); // Définissez la couleur de la première tranche sur rouge
colors.get_Item(1).setColor(Color.BLUE); // Définissez la couleur de la deuxième tranche sur bleu
// Ajoutez d'autres modifications de couleur si nécessaire
```

### Comment puis-je ajouter une légende au graphique à secteurs ?

Pour ajouter une légende au graphique à secteurs, vous pouvez utiliser le `getLegend` méthode et configurez-la comme suit :

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

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
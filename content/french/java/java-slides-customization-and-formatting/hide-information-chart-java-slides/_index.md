---
title: Masquer les informations du graphique dans les diapositives Java
linktitle: Masquer les informations du graphique dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment masquer les éléments du graphique dans Java Slides avec Aspose.Slides pour Java. Personnalisez les présentations pour plus de clarté et d'esthétique avec des conseils étape par étape et le code source.
type: docs
weight: 13
url: /fr/java/customization-and-formatting/hide-information-chart-java-slides/
---

## Introduction pour masquer les informations du graphique dans les diapositives Java

Dans ce didacticiel, nous allons explorer comment masquer divers éléments d'un graphique dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Vous pouvez utiliser ce code pour personnaliser vos graphiques selon les besoins de vos présentations.

## Étape 1 : Configuration de l'environnement

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 2 : Créer une nouvelle présentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 3 : Ajout d'un graphique à la diapositive

Nous allons ajouter un graphique linéaire avec des marqueurs à une diapositive, puis masquer divers éléments du graphique.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Étape 4 : Masquer le titre du graphique

Vous pouvez masquer le titre du graphique comme suit :

```java
chart.setTitle(false);
```

## Étape 5 : Masquer l'axe des valeurs

Pour masquer l'axe des valeurs (axe vertical), utilisez le code suivant :

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Étape 6 : Masquer l’axe des catégories

Pour masquer l'axe des catégories (axe horizontal), utilisez ce code :

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Étape 7 : Masquer la légende

Vous pouvez masquer la légende du graphique comme ceci :

```java
chart.setLegend(false);
```

## Étape 8 : Masquer les principales lignes de la grille

Pour masquer les grandes lignes du quadrillage de l'axe horizontal, vous pouvez utiliser le code suivant :

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Étape 9 : Supprimer la série

Si vous souhaitez supprimer toutes les séries du graphique, vous pouvez utiliser une boucle comme celle-ci :

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Étape 10 : Personnaliser la série de graphiques

Vous pouvez personnaliser la série de graphiques selon vos besoins. Dans cet exemple, nous modifions le style du marqueur, la position de l'étiquette de données, la taille du marqueur, la couleur de la ligne et le style du tiret :

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Étape 11 : Enregistrez la présentation

Enfin, enregistrez la présentation dans un fichier :

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez réussi à masquer divers éléments d'un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser davantage vos graphiques et présentations selon vos besoins spécifiques.

## Code source complet pour masquer les informations du graphique dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Masquer le titre du graphique
	chart.setTitle(false);
	///Masquer l'axe des valeurs
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Visibilité de l'axe de catégorie
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Cacher la légende
	chart.setLegend(false);
	//Masquer les lignes MajorGrid
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Définition de la couleur des lignes de série
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Conclusion

Dans ce guide étape par étape, nous avons exploré comment masquer divers éléments d'un graphique dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Cela peut être incroyablement utile lorsque vous devez personnaliser vos graphiques pour des présentations et les rendre plus attrayants visuellement ou adaptés à vos besoins spécifiques.

## FAQ

### Comment puis-je personnaliser davantage l’apparence des éléments du graphique ?

Vous pouvez personnaliser diverses propriétés des éléments du graphique, telles que la couleur des lignes, la couleur de remplissage, le style des marqueurs, etc. en accédant aux propriétés correspondantes de la série de graphiques, des marqueurs, des étiquettes et du format.

### Puis-je masquer des points de données spécifiques dans le graphique ?

Oui, vous pouvez masquer des points de données spécifiques en manipulant les données de la série de graphiques. Vous pouvez supprimer des points de données ou définir leurs valeurs sur null pour les masquer.

### Comment puis-je ajouter des séries supplémentaires au graphique ?

 Vous pouvez ajouter d'autres séries au graphique en utilisant le`IChartData.getSeries().add` méthode et en spécifiant les points de données pour la nouvelle série.

### Est-il possible de changer le type de graphique de manière dynamique ?

Oui, vous pouvez modifier le type de graphique de manière dynamique en créant un nouveau graphique du type souhaité et en copiant les données de l'ancien graphique vers le nouveau.

### Comment puis-je modifier le titre et les étiquettes des axes du graphique par programmation ?

Vous pouvez définir le titre et les étiquettes du graphique et des axes en accédant à leurs propriétés respectives et en définissant le texte et le formatage souhaités.
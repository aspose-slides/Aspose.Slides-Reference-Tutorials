---
title: Ajouter une erreur personnalisée dans les diapositives Java
linktitle: Ajouter une erreur personnalisée dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des barres d'erreur personnalisées aux graphiques PowerPoint dans Java Slides à l'aide d'Aspose.Slides. Guide étape par étape avec code source pour une visualisation précise des données.
type: docs
weight: 11
url: /fr/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Introduction à l'ajout de barres d'erreur personnalisées dans les diapositives Java à l'aide d'Aspose.Slides

Dans ce didacticiel, vous apprendrez à ajouter des barres d'erreur personnalisées à un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Les barres d'erreur sont utiles pour afficher la variabilité ou l'incertitude des points de données sur un graphique.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée et configurée dans votre projet.
- Un environnement de développement Java mis en place.

## Étape 1 : Créer une présentation vide

Tout d’abord, créez une présentation PowerPoint vide.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une présentation vide
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter un graphique à bulles

Ensuite, nous ajouterons un graphique à bulles à la présentation.

```java
// Créer un graphique à bulles
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Étape 3 : ajouter des barres d'erreur personnalisées

Ajoutons maintenant des barres d'erreur personnalisées à la série de graphiques.

```java
// Ajout de barres d'erreur personnalisées et définition de leur format
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Étape 4 : Définir les données des barres d'erreur

Au cours de cette étape, nous accéderons aux points de données de la série de graphiques et définirons les valeurs des barres d'erreur personnalisées pour chaque point.

```java
// Accès aux points de données des séries de graphiques et définition des valeurs des barres d'erreur pour des points individuels
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Définition des barres d'erreur pour les points des séries de graphiques
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Étape 5 : Enregistrez la présentation

Enfin, enregistrez la présentation avec les barres d'erreur personnalisées.

```java
// Enregistrement de la présentation
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez ajouté avec succès des barres d'erreur personnalisées à un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java.

## Code source complet pour ajouter une erreur personnalisée dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une présentation vide
Presentation presentation = new Presentation();
try
{
	// Créer un graphique à bulles
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//Ajout de barres d'erreur personnalisées et définition de son format
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Accès aux points de données des séries de graphiques et définition des valeurs des barres d'erreur pour un point individuel
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Définition des barres d'erreur pour les points des séries de graphiques
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Enregistrement de la présentation
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel complet, vous avez appris à améliorer vos présentations PowerPoint en ajoutant des barres d'erreur personnalisées aux graphiques à l'aide d'Aspose.Slides pour Java. Les barres d'erreur fournissent des informations précieuses sur la variabilité et l'incertitude des données, rendant vos graphiques plus informatifs et visuellement attrayants.

## FAQ

### Comment personnaliser l’apparence des barres d’erreur ?

 Vous pouvez personnaliser l'apparence des barres d'erreur en modifiant les propriétés du`IErrorBarsFormat` objet, tel que le style de ligne, la couleur de ligne et la largeur de la barre d'erreur.

### Puis-je ajouter des barres d’erreur à d’autres types de graphiques ?

Oui, vous pouvez ajouter des barres d'erreur à différents types de graphiques pris en charge par Aspose.Slides pour Java, notamment les graphiques à barres, les graphiques linéaires et les graphiques à nuages de points.

### Comment définir différentes valeurs de barre d'erreur pour chaque point de données ?

Vous pouvez parcourir les points de données et définir des valeurs de barre d'erreur personnalisées pour chaque point, comme indiqué dans le code ci-dessus.

### Est-il possible de masquer les barres d’erreur pour des points de données spécifiques ?

 Oui, vous pouvez contrôler la visibilité des barres d'erreur pour des points de données individuels en définissant l'option`setVisible` propriété du`IErrorBarsFormat` objet.
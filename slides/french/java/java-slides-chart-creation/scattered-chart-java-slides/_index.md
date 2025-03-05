---
title: Graphique dispersé dans les diapositives Java
linktitle: Graphique dispersé dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer des graphiques à nuages de points en Java à l'aide d'Aspose.Slides. Guide étape par étape avec le code source Java pour la visualisation des données dans les présentations.
type: docs
weight: 11
url: /fr/java/chart-creation/scattered-chart-java-slides/
---

## Introduction au diagramme dispersé dans Aspose.Slides pour Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un graphique à nuages de points à l'aide d'Aspose.Slides pour Java. Les nuages de points sont utiles pour visualiser des points de données sur un plan bidimensionnel. Nous fournirons des instructions étape par étape et inclurons le code source Java pour votre commodité.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. [Aspose.Slides pour Java](https://products.aspose.com/slides/java) installée.
2. Un environnement de développement Java mis en place.

## Étape 1 : initialiser la présentation

Tout d’abord, importez les bibliothèques nécessaires et créez une nouvelle présentation.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Créer une nouvelle présentation
Presentation pres = new Presentation();
```

## Étape 2 : ajouter une diapositive et créer le graphique à nuages de points

 Ensuite, ajoutez une diapositive et créez le graphique à nuages de points dessus. Nous utiliserons le`ScatterWithSmoothLines`type de graphique dans cet exemple.

```java
// Obtenez la première diapositive
ISlide slide = pres.getSlides().get_Item(0);

// Création du nuage de points
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Étape 3 : préparer les données du graphique

Maintenant, préparons les données pour notre graphique à nuages de points. Nous ajouterons deux séries, chacune avec plusieurs points de données.

```java
// Obtention de l'index de la feuille de calcul des données graphiques par défaut
int defaultWorksheetIndex = 0;

// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Supprimer la série de démonstration
chart.getChartData().getSeries().clear();

// Ajouter la première série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Ajouter des points de données à la première série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Modifier le type de série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Changer la taille du marqueur
series.getMarker().setSymbol(MarkerStyleType.Star); // Changer le symbole du marqueur

// Prenez la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);

// Ajouter des points de données à la deuxième série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Changer le style de marqueur pour la deuxième série
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Étape 4 : Enregistrez la présentation

Enfin, enregistrez la présentation avec le nuage de points dans un fichier PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez créé avec succès un graphique à nuages de points à l'aide d'Aspose.Slides pour Java. Vous pouvez désormais personnaliser davantage cet exemple pour l'adapter à vos exigences spécifiques en matière de données et de conception.

## Code source complet pour les graphiques dispersés dans les diapositives Java
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Création du graphique par défaut
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Obtention de l'index de la feuille de calcul des données graphiques par défaut
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Supprimer la série de démonstration
chart.getChartData().getSeries().clear();
// Ajouter une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Prendre la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ajoutez-y un nouveau point (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Ajouter un nouveau point (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Modifier le type de série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Changer le marqueur de série de graphiques
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Ajoutez-y un nouveau point (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Ajouter un nouveau point (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Ajouter un nouveau point (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Ajouter un nouveau point (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Changer le marqueur de série de graphiques
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous vous avons expliqué le processus de création d'un graphique à nuages de points à l'aide d'Aspose.Slides pour Java. Les diagrammes à nuages de points sont des outils puissants pour visualiser des points de données dans un espace bidimensionnel, facilitant ainsi l'analyse et la compréhension des relations complexes entre les données.

## FAQ

### Comment puis-je changer le type de graphique ?

 Pour modifier le type de graphique, utilisez le`setType` méthode sur la série de graphiques et fournissez le type de graphique souhaité. Par exemple,`series.setType(ChartType.Line)` changerait la série en un graphique linéaire.

### Comment puis-je personnaliser la taille et le style du marqueur ?

 Vous pouvez modifier la taille et le style du marqueur à l'aide du bouton`getMarker` méthode sur la série, puis définissez les propriétés de taille et de symbole. Par exemple:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

N'hésitez pas à explorer davantage d'options de personnalisation dans la documentation Aspose.Slides pour Java.

 N'oubliez pas de remplacer`"Your Document Directory"` avec le chemin réel où vous souhaitez enregistrer la présentation.
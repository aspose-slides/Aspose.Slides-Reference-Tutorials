---
"description": "Apprenez à créer des graphiques en nuage de points en Java avec Aspose.Slides. Guide étape par étape avec code source Java pour la visualisation de données dans les présentations."
"linktitle": "Graphique dispersé dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Graphique dispersé dans les diapositives Java"
"url": "/fr/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Graphique dispersé dans les diapositives Java


## Introduction aux graphiques dispersés dans Aspose.Slides pour Java

Dans ce tutoriel, nous vous guiderons dans la création d'un graphique en nuage de points avec Aspose.Slides pour Java. Les graphiques en nuage de points permettent de visualiser des points de données sur un plan bidimensionnel. Nous vous fournirons des instructions étape par étape et inclurons le code source Java pour vous faciliter la tâche.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. [Aspose.Slides pour Java](https://products.aspose.com/slides/java) installé.
2. Un environnement de développement Java mis en place.

## Étape 1 : Initialiser la présentation

Tout d’abord, importez les bibliothèques nécessaires et créez une nouvelle présentation.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Créer une nouvelle présentation
Presentation pres = new Presentation();
```

## Étape 2 : ajouter une diapositive et créer le graphique en nuage de points

Ensuite, ajoutez une diapositive et créez le graphique en nuage de points. Nous utiliserons `ScatterWithSmoothLines` type de graphique dans cet exemple.

```java
// Obtenez la première diapositive
ISlide slide = pres.getSlides().get_Item(0);

// Création du graphique en nuage de points
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Étape 3 : préparer les données du graphique

Préparons maintenant les données pour notre nuage de points. Nous allons ajouter deux séries, chacune comportant plusieurs points de données.

```java
// Obtenir l'index de la feuille de calcul des données du graphique par défaut
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
series.getMarker().setSize(10); // Modifier la taille du marqueur
series.getMarker().setSymbol(MarkerStyleType.Star); // Changer le symbole du marqueur

// Prenez la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);

// Ajouter des points de données à la deuxième série
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Modifier le style du marqueur pour la deuxième série
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique en nuage de points dans un fichier PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez créé un graphique en nuage de points avec Aspose.Slides pour Java. Vous pouvez maintenant personnaliser cet exemple pour l'adapter à vos besoins spécifiques en matière de données et de conception.

## Code source complet pour un graphique dispersé en Java (diapositives)
```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Création du graphique par défaut
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Obtenir l'index de la feuille de calcul des données du graphique par défaut
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Supprimer la série de démonstration
chart.getChartData().getSeries().clear();
// Ajouter une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ajoutez un nouveau point (1:3) ici.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Ajouter un nouveau point (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Modifier le type de série
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Modification du marqueur de série de graphiques
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Ajoutez un nouveau point (5:2) ici.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Ajouter un nouveau point (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Ajouter un nouveau point (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Ajouter un nouveau point (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Modification du marqueur de série de graphiques
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce tutoriel, nous vous avons expliqué comment créer un graphique en nuage de points avec Aspose.Slides pour Java. Les graphiques en nuage de points sont des outils puissants pour visualiser des points de données dans un espace bidimensionnel, facilitant ainsi l'analyse et la compréhension de relations de données complexes.

## FAQ

### Comment puis-je changer le type de graphique ?

Pour changer le type de graphique, utilisez le `setType` méthode sur la série de graphiques et indiquez le type de graphique souhaité. Par exemple, `series.setType(ChartType.Line)` changerait la série en un graphique linéaire.

### Comment personnaliser la taille et le style du marqueur ?

Vous pouvez modifier la taille et le style du marqueur à l'aide du `getMarker` sur la série, puis définissez les propriétés de taille et de symbole. Par exemple :

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

N'hésitez pas à explorer davantage d'options de personnalisation dans la documentation Aspose.Slides pour Java.

N'oubliez pas de remplacer `"Your Document Directory"` avec le chemin réel où vous souhaitez enregistrer la présentation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Options de deuxième tracé pour les graphiques dans les diapositives Java
linktitle: Options de deuxième tracé pour les graphiques dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment personnaliser des graphiques dans Java Slides à l'aide d'Aspose.Slides pour Java. Explorez les options de deuxième intrigue et améliorez vos présentations.
type: docs
weight: 12
url: /fr/java/chart-creation/second-plot-options-charts-java-slides/
---

## Introduction aux options de deuxième tracé pour les graphiques dans les diapositives Java

Dans ce didacticiel, nous explorerons comment ajouter des deuxièmes options de tracé aux graphiques à l'aide d'Aspose.Slides pour Java. Les options du deuxième tracé vous permettent de personnaliser l'apparence et le comportement des graphiques, en particulier dans des scénarios tels que les diagrammes à secteurs. Nous fournirons des instructions étape par étape et des exemples de code source pour y parvenir. 

## Conditions préalables
Avant de commencer, assurez-vous que Aspose.Slides pour Java est installé et configuré dans votre projet Java.

## Étape 1 : Créer une présentation
Commençons par créer une nouvelle présentation :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter un graphique à une diapositive
Ensuite, nous ajouterons un graphique à une diapositive. Dans cet exemple, nous allons créer un graphique à secteurs :

```java
// Ajouter un graphique sur la diapositive
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Étape 3 : Personnaliser les propriétés du graphique
Maintenant, définissons différentes propriétés pour le graphique, y compris les options du deuxième tracé :

```java
// Afficher les étiquettes de données pour la première série
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Définir la taille du deuxième gâteau (en pourcentage)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Divisez le gâteau en pourcentage
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Définir la position de la division
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Étape 4 : Enregistrez la présentation
Enfin, enregistrez la présentation avec les options de graphique et de deuxième tracé :

```java
// Écrire la présentation sur le disque
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour les options du deuxième tracé

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
// Ajouter un graphique sur la diapositive
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Définir différentes propriétés
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Écrire la présentation sur le disque
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter des options de deuxième tracé aux graphiques dans Java Slides à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser diverses propriétés pour améliorer l'apparence et les fonctionnalités de vos graphiques, rendant ainsi vos présentations plus informatives et visuellement attrayantes.

## FAQ

### Comment puis-je modifier la taille du deuxième secteur dans un graphique à secteurs ?

 Pour modifier la taille du deuxième secteur d'un graphique à secteurs, utilisez l'option`setSecondPieSize` méthode comme indiqué dans l’exemple de code ci-dessus. Ajustez la valeur pour spécifier la taille en pourcentage.

###  Qu'est-ce que`PieSplitBy` control in a Pie of Pie chart?

 Le`PieSplitBy`La propriété contrôle la façon dont le diagramme circulaire est divisé. Vous pouvez le définir soit`PieSplitType.ByPercentage` ou`PieSplitType.ByValue` pour diviser le graphique par pourcentage ou par une valeur spécifique, respectivement.

### Comment définir la position de la division dans un graphique à secteurs ?

 Vous pouvez définir la position de la division dans un graphique à secteurs à l'aide de l'option`setPieSplitPosition` méthode. Ajustez la valeur pour spécifier la position souhaitée.
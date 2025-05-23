---
"description": "Apprenez à personnaliser les graphiques dans Java Slides avec Aspose.Slides pour Java. Explorez les options de second tracé et améliorez vos présentations."
"linktitle": "Deuxième option de tracé pour les graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Deuxième option de tracé pour les graphiques dans les diapositives Java"
"url": "/fr/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Deuxième option de tracé pour les graphiques dans les diapositives Java


## Introduction aux options de tracé secondaire pour les graphiques en Java (diapositives)

Dans ce tutoriel, nous découvrirons comment ajouter des options de second tracé aux graphiques à l'aide d'Aspose.Slides pour Java. Ces options permettent de personnaliser l'apparence et le comportement des graphiques, notamment dans des scénarios comme les graphiques à secteurs. Nous fournirons des instructions pas à pas et des exemples de code source pour y parvenir. 

## Prérequis
Avant de commencer, assurez-vous qu’Aspose.Slides pour Java est installé et configuré dans votre projet Java.

## Étape 1 : Créer une présentation
Commençons par créer une nouvelle présentation :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Presentation
Presentation presentation = new Presentation();
```

## Étape 2 : Ajouter un graphique à une diapositive
Nous allons maintenant ajouter un graphique à une diapositive. Dans cet exemple, nous allons créer un graphique à secteurs :

```java
// Ajouter un graphique sur la diapositive
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Étape 3 : Personnaliser les propriétés du graphique
Maintenant, définissons différentes propriétés pour le graphique, y compris les options du deuxième tracé :

```java
// Afficher les étiquettes de données pour la première série
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Définir la taille du deuxième graphique (en pourcentage)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Diviser le gâteau en pourcentage
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Définir la position de la division
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Étape 4 : Enregistrer la présentation
Enfin, enregistrez la présentation avec les options de graphique et de deuxième tracé :

```java
// Écrire la présentation sur le disque
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour les options du deuxième tracé

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Presentation
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

Dans ce tutoriel, nous avons appris à ajouter des options de tracé secondaire aux graphiques dans Java Slides à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser diverses propriétés pour améliorer l'apparence et les fonctionnalités de vos graphiques, rendant ainsi vos présentations plus informatives et visuellement plus attrayantes.

## FAQ

### Comment puis-je modifier la taille du deuxième graphique à secteurs dans un graphique à secteurs ?

Pour modifier la taille du deuxième secteur dans un graphique à secteurs, utilisez le `setSecondPieSize` Méthode comme illustré dans l'exemple de code ci-dessus. Ajustez la valeur pour spécifier la taille en pourcentage.

### Qu'est-ce que `PieSplitBy` contrôle dans un graphique à secteurs ?

Le `PieSplitBy` La propriété contrôle la façon dont le graphique à secteurs est divisé. Vous pouvez la définir sur `PieSplitType.ByPercentage` ou `PieSplitType.ByValue` pour diviser le graphique en pourcentage ou en fonction d'une valeur spécifique, respectivement.

### Comment définir la position de la division dans un graphique à secteurs ?

Vous pouvez définir la position de la division dans un graphique à secteurs à l'aide de l'icône `setPieSplitPosition` méthode. Ajustez la valeur pour spécifier la position souhaitée.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
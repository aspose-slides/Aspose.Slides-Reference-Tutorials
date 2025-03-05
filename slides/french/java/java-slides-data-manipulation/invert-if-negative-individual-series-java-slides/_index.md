---
title: Inverser si négatif pour les séries individuelles dans les diapositives Java
linktitle: Inverser si négatif pour les séries individuelles dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment utiliser la fonctionnalité Inverser si négatif dans Aspose.Slides pour Java pour améliorer les visuels des graphiques dans les présentations PowerPoint.
type: docs
weight: 11
url: /fr/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## Introduction à Inverser si négatif pour des séries individuelles dans les diapositives Java

Aspose.Slides pour Java fournit des outils puissants pour travailler avec des présentations, et une fonctionnalité intéressante est la possibilité de contrôler la façon dont les séries de données sont affichées sur les graphiques. Dans cet article, nous explorerons comment utiliser la fonctionnalité « Inverser si négatif » pour des séries individuelles dans Java Slides. Cette fonctionnalité vous permet de distinguer visuellement les points de données négatifs dans un graphique, rendant ainsi vos présentations plus informatives et plus attrayantes.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Mise en place de votre projet

Pour commencer, créez un nouveau projet Java dans votre environnement de développement intégré (IDE) préféré. Une fois votre projet configuré, suivez ces étapes pour implémenter la fonctionnalité « Inverser si négatif » pour des séries individuelles dans Java Slides.

## Étape 1 : Inclure la bibliothèque Aspose.Slides

Tout d’abord, vous devez inclure la bibliothèque Aspose.Slides dans votre projet. Vous pouvez le faire en ajoutant le fichier JAR de la bibliothèque au chemin de classe de votre projet. Cette étape garantit que vous pouvez accéder à toutes les classes et méthodes nécessaires pour travailler avec des présentations PowerPoint.

```java
import com.aspose.slides.*;
```

## Étape 2 : Créer une présentation

 Créons maintenant une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides. Vous pouvez définir le répertoire dans lequel vous souhaitez enregistrer la présentation à l'aide du`dataDir` variable.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 3 : ajouter un graphique

Dans cette étape, nous ajouterons un graphique à la présentation. Nous utiliserons un histogramme groupé comme exemple. Vous pouvez choisir différents types de graphiques en fonction de vos besoins.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Étape 4 : Configurer la série de données graphiques

Ensuite, nous allons configurer la série de données du graphique. Pour illustrer la fonctionnalité « Inverser si négatif », nous allons créer un exemple d'ensemble de données avec des valeurs positives et négatives.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Ajout de points de données à la série
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Étape 5 : Appliquer « Inverser si négatif »

Nous allons maintenant appliquer la fonctionnalité « Inverser si négatif » à l'un des points de données. Cela inversera visuellement la couleur de ce point de données spécifique lorsqu'il est négatif.

```java
series.get_Item(0).setInvertIfNegative(false); // Ne pas inverser par défaut
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Inverser la couleur du troisième point de données
```

## Étape 6 : Enregistrez la présentation

Enfin, enregistrez la présentation dans le répertoire spécifié.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Code source complet pour inverser si négatif pour les séries individuelles dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser la fonctionnalité « Inverser si négatif » pour des séries individuelles dans Java Slides à l'aide d'Aspose.Slides pour Java. Cette fonctionnalité vous permet de mettre en évidence les points de données négatifs dans vos graphiques, rendant ainsi vos présentations plus attrayantes et informatives.

## FAQ

### Quel est le but de la fonctionnalité « Inverser si négatif » dans Aspose.Slides pour Java ?

La fonctionnalité « Inverser si négatif » dans Aspose.Slides pour Java vous permet de distinguer visuellement les points de données négatifs dans les graphiques. Il contribue à rendre vos présentations plus informatives et plus attrayantes en mettant en évidence des points de données spécifiques.

### Comment puis-je inclure la bibliothèque Aspose.Slides dans mon projet Java ?

Pour inclure la bibliothèque Aspose.Slides dans votre projet Java, vous devez ajouter le fichier JAR de la bibliothèque au chemin de classe de votre projet. Cela vous permet d'accéder à toutes les classes et méthodes nécessaires pour travailler avec des présentations PowerPoint.

### Puis-je utiliser différents types de graphiques avec la fonctionnalité « Inverser si négatif » ?

Oui, vous pouvez utiliser différents types de graphiques avec la fonctionnalité « Inverser si négatif ». Dans ce didacticiel, nous avons utilisé un histogramme groupé comme exemple, mais vous pouvez appliquer la fonctionnalité à différents types de graphiques en fonction de vos besoins.

### Est-il possible de personnaliser l'apparence des points de données inversés ?

Oui, vous pouvez personnaliser l'apparence des points de données inversés. Aspose.Slides pour Java fournit des options pour contrôler la couleur et le style des points de données lorsqu'ils sont inversés en raison du paramètre « Inverser si négatif ».

### Où puis-je accéder à la documentation Aspose.Slides pour Java ?

Vous pouvez accéder à la documentation d'Aspose.Slides pour Java à l'adresse[ici](https://reference.aspose.com/slides/java/).
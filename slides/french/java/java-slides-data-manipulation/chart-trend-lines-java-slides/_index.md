---
title: Graphique des lignes de tendance dans les diapositives Java
linktitle: Graphique des lignes de tendance dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter diverses lignes de tendance aux diapositives Java à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec des exemples de code pour une visualisation efficace des données.
weight: 15
url: /fr/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Graphique des lignes de tendance dans les diapositives Java


## Introduction aux lignes de tendance des graphiques dans les diapositives Java : un guide étape par étape

Dans ce guide complet, nous explorerons comment créer des lignes de tendance de graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Les courbes de tendance des graphiques peuvent constituer un ajout précieux à vos présentations, en aidant à visualiser et à analyser efficacement les tendances des données. Nous vous guiderons tout au long du processus avec des explications claires et des exemples de code.

## Conditions préalables

Avant de nous lancer dans la création de lignes de tendance de graphique, assurez-vous que les conditions préalables suivantes sont en place :

- Environnement de développement Java
- Aspose.Slides pour la bibliothèque Java
- Un éditeur de code de votre choix

## Étape 1 : Démarrage

Commençons par mettre en place l'environnement nécessaire et créer une nouvelle présentation :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Création d'une présentation vide
Presentation pres = new Presentation();
```

Nous avons initialisé notre présentation et nous sommes maintenant prêts à ajouter un histogramme groupé :

```java
// Création d'un histogramme groupé
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Étape 2 : Ajout d'une ligne de tendance exponentielle

Commençons par ajouter une ligne de tendance exponentielle à notre série de graphiques :

```java
// Ajout d'une ligne de tendance exponentielle pour la série de graphiques 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Étape 3 : Ajout d'une ligne de tendance linéaire

Ensuite, nous ajouterons une ligne de tendance linéaire à notre série de graphiques :

```java
// Ajout d'une ligne de tendance linéaire pour la série de graphiques 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Étape 4 : Ajout d'une ligne de tendance logarithmique

Maintenant, ajoutons une ligne de tendance logarithmique à une autre série de graphiques :

```java
// Ajout d'une ligne de tendance logarithmique pour la série de graphiques 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Étape 5 : Ajout d'une ligne de tendance moyenne mobile

Nous pouvons également ajouter une ligne de tendance moyenne mobile :

```java
// Ajout d'une ligne de tendance de moyenne mobile pour la série de graphiques 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Étape 6 : Ajout d'une ligne de tendance polynomiale

Ajout d'une ligne de tendance polynomiale :

```java
// Ajout d'une ligne de tendance polynomiale pour la série de graphiques 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Étape 7 : Ajout d'une ligne de tendance de puissance

Enfin, ajoutons une ligne de tendance de puissance :

```java
// Ajout d'une ligne de tendance de puissance pour la série de graphiques 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Étape 8 : Sauvegarde de la présentation

Maintenant que nous avons ajouté diverses lignes de tendance à notre graphique, sauvegardons la présentation :

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Toutes nos félicitations! Vous avez créé avec succès une présentation avec différents types de lignes de tendance dans Java Slides à l'aide d'Aspose.Slides pour Java.

## Code source complet pour les lignes de tendance des graphiques dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Création d'une présentation vide
Presentation pres = new Presentation();
// Création d'un histogramme groupé
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Ajout d'une ligne de tendance ponentielle pour la série de graphiques 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Ajout d'une ligne de tendance linéaire pour la série de graphiques 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Ajout d'une ligne de tendance logarithmique pour la série de graphiques 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Ajout de la ligne de tendance MovingAverage pour la série de graphiques 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Ajout d'une ligne de tendance polynomiale pour la série de graphiques 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Ajout d'une ligne de tendance Power pour la série de graphiques 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Enregistrement de la présentation
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter différents types de lignes de tendance aux graphiques dans Java Slides à l'aide de la bibliothèque Aspose.Slides pour Java. Que vous travailliez sur l'analyse de données ou créiez des présentations informatives, la capacité de visualiser les tendances peut être un outil puissant.

## FAQ

### Comment changer la couleur d’une ligne de tendance dans Aspose.Slides pour Java ?

 Pour changer la couleur d'une ligne de tendance, vous pouvez utiliser le`getSolidFillColor().setColor(Color)` méthode, comme le montre l’exemple d’ajout d’une ligne de tendance linéaire.

### Puis-je ajouter plusieurs lignes de tendance à une seule série de graphiques ?

Oui, vous pouvez ajouter plusieurs lignes de tendance à une seule série de graphiques. Appelez simplement le`getTrendLines().add()` méthode pour chaque ligne de tendance que vous souhaitez ajouter.

### Comment supprimer une ligne de tendance d’un graphique dans Aspose.Slides pour Java ?

 Pour supprimer une ligne de tendance d'un graphique, vous pouvez utiliser l'outil`removeAt(int index)` méthode, en spécifiant l’index de la ligne de tendance que vous souhaitez supprimer.

### Est-il possible de personnaliser l’affichage de l’équation de la ligne de tendance ?

 Oui, vous pouvez personnaliser l'affichage de l'équation de la ligne de tendance à l'aide de l'option`setDisplayEquation(boolean)` méthode, comme le montre l’exemple.

### Comment puis-je accéder à plus de ressources et d’exemples pour Aspose.Slides pour Java ?

 Vous pouvez accéder à des ressources, de la documentation et des exemples supplémentaires pour Aspose.Slides for Java sur le[Site Aspose](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

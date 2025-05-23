---
"description": "Apprenez à ajouter différentes courbes de tendance à vos diapositives Java avec Aspose.Slides pour Java. Guide étape par étape avec exemples de code pour une visualisation efficace des données."
"linktitle": "Lignes de tendance des graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Lignes de tendance des graphiques dans les diapositives Java"
"url": "/fr/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lignes de tendance des graphiques dans les diapositives Java


## Introduction aux courbes de tendance des graphiques en Java : un guide étape par étape

Dans ce guide complet, nous allons découvrir comment créer des courbes de tendance graphiques dans Java Slides avec Aspose.Slides pour Java. Les courbes de tendance graphiques peuvent être un atout précieux pour vos présentations, car elles permettent de visualiser et d'analyser efficacement les tendances des données. Nous vous guiderons pas à pas avec des explications claires et des exemples de code.

## Prérequis

Avant de nous plonger dans la création de lignes de tendance de graphique, assurez-vous de disposer des conditions préalables suivantes :

- Environnement de développement Java
- Bibliothèque Aspose.Slides pour Java
- Un éditeur de code de votre choix

## Étape 1 : Démarrage

Commençons par configurer l’environnement nécessaire et créer une nouvelle présentation :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Créer une présentation vide
Presentation pres = new Presentation();
```

Nous avons initialisé notre présentation et nous sommes maintenant prêts à ajouter un graphique à colonnes groupées :

```java
// Création d'un graphique à colonnes groupées
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Étape 2 : Ajout d'une ligne de tendance exponentielle

Commençons par ajouter une ligne de tendance exponentielle à notre série de graphiques :

```java
// Ajout d'une ligne de tendance exponentielle pour la série de graphiques 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Étape 3 : Ajout d'une ligne de tendance linéaire

Ensuite, nous allons ajouter une ligne de tendance linéaire à notre série de graphiques :

```java
// Ajout d'une ligne de tendance linéaire pour la série de graphiques 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Étape 4 : Ajout d'une ligne de tendance logarithmique

Maintenant, ajoutons une ligne de tendance logarithmique à une série de graphiques différente :

```java
// Ajout d'une ligne de tendance logarithmique pour la série de graphiques 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Étape 5 : Ajout d'une ligne de tendance moyenne mobile

Nous pouvons également ajouter une ligne de tendance moyenne mobile :

```java
// Ajout d'une ligne de tendance moyenne mobile pour la série de graphiques 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Étape 6 : Ajout d'une ligne de tendance polynomiale

Ajout d'une ligne de tendance polynomiale :

```java
// Ajout d'une ligne de tendance polynomiale pour la série de graphiques 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Étape 7 : Ajout d'une ligne de tendance de puissance

Enfin, ajoutons une ligne de tendance de puissance :

```java
// Ajout d'une ligne de tendance de puissance pour la série de graphiques 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Étape 8 : Enregistrer la présentation

Maintenant que nous avons ajouté différentes lignes de tendance à notre graphique, enregistrons la présentation :

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Félicitations ! Vous avez créé avec succès une présentation avec différents types de courbes de tendance dans Java Slides avec Aspose.Slides pour Java.

## Code source complet pour les courbes de tendance des graphiques en Java (diapositives)

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Créer une présentation vide
Presentation pres = new Presentation();
// Création d'un graphique à colonnes groupées
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Ajout d'une ligne de tendance potentielle pour la série de graphiques 1
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
// Ajout d'une ligne de tendance de moyenne mobile pour la série de graphiques 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Ajout d'une ligne de tendance polynomiale pour la série de graphiques 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Ajout d'une ligne de tendance de puissance pour la série de graphiques 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Sauvegarde de la présentation
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce tutoriel, nous avons appris à ajouter différents types de courbes de tendance aux graphiques dans Java Slides grâce à la bibliothèque Aspose.Slides pour Java. Que vous travailliez sur l'analyse de données ou que vous créiez des présentations informatives, la visualisation des tendances peut s'avérer un outil puissant.

## FAQ

### Comment changer la couleur d'une ligne de tendance dans Aspose.Slides pour Java ?

Pour changer la couleur d'une ligne de tendance, vous pouvez utiliser le `getSolidFillColor().setColor(Color)` méthode, comme illustré dans l'exemple pour ajouter une ligne de tendance linéaire.

### Puis-je ajouter plusieurs lignes de tendance à une seule série de graphiques ?

Oui, vous pouvez ajouter plusieurs lignes de tendance à une même série de graphiques. Il vous suffit d'appeler le `getTrendLines().add()` méthode pour chaque ligne de tendance que vous souhaitez ajouter.

### Comment supprimer une ligne de tendance d'un graphique dans Aspose.Slides pour Java ?

Pour supprimer une ligne de tendance d’un graphique, vous pouvez utiliser le `removeAt(int index)` méthode, spécifiant l'index de la ligne de tendance que vous souhaitez supprimer.

### Est-il possible de personnaliser l'affichage de l'équation de la ligne de tendance ?

Oui, vous pouvez personnaliser l'affichage de l'équation de la ligne de tendance à l'aide du `setDisplayEquation(boolean)` méthode, comme démontré dans l'exemple.

### Comment puis-je accéder à plus de ressources et d’exemples pour Aspose.Slides pour Java ?

Vous pouvez accéder à des ressources supplémentaires, à de la documentation et à des exemples pour Aspose.Slides pour Java sur le [Site Web d'Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Apprenez à récupérer les dimensions des zones de tracé d'un graphique dans Java Slides avec Aspose.Slides pour Java. Améliorez vos compétences en automatisation PowerPoint."
"linktitle": "Obtenir la largeur et la hauteur de la zone de tracé du graphique dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Obtenir la largeur et la hauteur de la zone de tracé du graphique dans les diapositives Java"
"url": "/fr/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir la largeur et la hauteur de la zone de tracé du graphique dans les diapositives Java


## Introduction

Les graphiques sont un moyen efficace de visualiser les données dans les présentations PowerPoint. Il peut être nécessaire de connaître les dimensions de la zone de tracé d'un graphique pour diverses raisons, comme le redimensionnement ou le repositionnement d'éléments. Ce guide explique comment obtenir la largeur et la hauteur de la zone de tracé avec Java et Aspose.Slides pour Java.

## Prérequis

Avant de nous plonger dans le code, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez la télécharger sur le site web d'Aspose. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configuration de l'environnement

Assurez-vous d'avoir ajouté la bibliothèque Aspose.Slides pour Java à votre projet Java. Vous pouvez le faire en l'incluant dans les dépendances de votre projet ou en ajoutant manuellement le fichier JAR.

## Étape 2 : Créer une présentation PowerPoint

Commençons par créer une présentation PowerPoint et y ajouter une diapositive. Celle-ci servira de conteneur pour notre graphique.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Remplacer `"Your Document Directory"` avec le chemin vers votre répertoire de documents.

## Étape 3 : Ajout d'un graphique

Ajoutons maintenant un graphique à colonnes groupées à la diapositive. Nous validerons également la mise en page du graphique.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Ce code crée un graphique à colonnes groupées à la position (100, 100) avec des dimensions (500, 350).

## Étape 4 : Obtenir les dimensions de la zone de parcelle

Pour récupérer la largeur et la hauteur de la zone de tracé du graphique, nous pouvons utiliser le code suivant :

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Maintenant, les variables `x`, `y`, `w`, et `h` contiennent les valeurs respectives de la coordonnée X, de la coordonnée Y, de la largeur et de la hauteur de la zone de tracé.

## Étape 5 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Assurez-vous de remplacer `"Chart_out.pptx"` avec le nom de fichier de sortie souhaité.

## Code source complet pour obtenir la largeur et la hauteur d'une zone de tracé de graphique dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Enregistrer la présentation avec le graphique
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans cet article, nous avons expliqué comment obtenir la largeur et la hauteur de la zone de tracé d'un graphique dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Ces informations peuvent s'avérer précieuses pour ajuster dynamiquement la mise en page de vos graphiques dans des présentations PowerPoint.

## FAQ

### Comment puis-je modifier le type de graphique en autre chose que des colonnes groupées ?

Vous pouvez modifier le type de graphique en remplaçant `ChartType.ClusteredColumn` avec l'énumération du type de graphique souhaité, tel que `ChartType.Line` ou `ChartType.Pie`.

### Puis-je modifier d’autres propriétés du graphique ?

Oui, vous pouvez modifier diverses propriétés du graphique, telles que les données, les étiquettes et la mise en forme, grâce à l'API Aspose.Slides pour Java. Consultez la documentation pour plus de détails.

### Aspose.Slides pour Java est-il adapté à l'automatisation professionnelle de PowerPoint ?

Oui, Aspose.Slides pour Java est une bibliothèque puissante permettant d'automatiser les tâches PowerPoint dans les applications Java. Elle offre des fonctionnalités complètes pour travailler avec des présentations, des diapositives, des formes, des graphiques, etc.

### Comment puis-je en savoir plus sur Aspose.Slides pour Java ?

Vous trouverez une documentation complète et des exemples sur la page de documentation d'Aspose.Slides pour Java. [ici](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
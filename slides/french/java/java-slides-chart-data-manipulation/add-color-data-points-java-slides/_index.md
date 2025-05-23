---
"description": "Découvrez comment ajouter de la couleur aux points de données dans les diapositives Java à l’aide d’Aspose.Slides pour Java."
"linktitle": "Ajouter de la couleur aux points de données dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter de la couleur aux points de données dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter de la couleur aux points de données dans les diapositives Java


## Introduction à l'ajout de couleur aux points de données dans les diapositives Java

Dans ce tutoriel, nous vous montrerons comment ajouter de la couleur aux points de données dans des diapositives Java avec Aspose.Slides pour Java. Ce guide étape par étape inclut des exemples de code source pour vous aider à réaliser cette tâche.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Environnement de développement Java
- Bibliothèque Aspose.Slides pour Java

## Étape 1 : Créer une nouvelle présentation

Nous allons d'abord créer une nouvelle présentation avec Aspose.Slides pour Java. Cette présentation servira de conteneur pour notre graphique.

```java
Presentation pres = new Presentation();
```

## Étape 2 : Ajouter un graphique Sunburst

Ajoutons maintenant un graphique en forme de soleil à la présentation. Nous spécifions le type, la position et la taille du graphique.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Étape 3 : Accéder aux points de données

Pour modifier les points de données dans le graphique, nous devons accéder à la `IChartDataPointCollection` objet.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Étape 4 : Personnaliser les points de données

Dans cette étape, nous allons personnaliser des points de données spécifiques. Nous allons modifier la couleur des points de données et configurer les paramètres d'étiquette.

```java
// Personnaliser le point de données 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Personnaliser le point de données 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Étape 5 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique personnalisé.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez ajouté de la couleur à des points de données spécifiques dans une diapositive Java avec Aspose.Slides pour Java.

## Code source complet pour ajouter de la couleur aux points de données dans les diapositives Java

```java
Presentation pres = new Presentation();
try
{
	// Le chemin vers le répertoire des documents.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//FAIRE
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce tutoriel, vous avez appris à ajouter de la couleur aux points de données dans les diapositives Java avec Aspose.Slides pour Java. Vous pouvez personnaliser davantage vos graphiques et présentations selon vos besoins spécifiques.

## FAQ

### Comment puis-je changer la couleur d’autres points de données ?

Pour modifier la couleur d’autres points de données, vous pouvez suivre une approche similaire à celle indiquée à l’étape 4. Accédez au point de données que vous souhaitez personnaliser et modifiez ses paramètres de couleur et d’étiquette.

### Puis-je personnaliser d’autres aspects du graphique ?

Oui, vous pouvez personnaliser divers aspects du graphique, notamment les polices, les libellés, les titres, etc. Consultez la section [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/) pour des options de personnalisation détaillées.

### Où puis-je trouver plus d'exemples et de documentation ?

Vous pouvez trouver plus d'exemples et une documentation détaillée sur l'utilisation d'Aspose.Slides pour Java sur le [Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) site web.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Apprenez à définir les modes de mise en page des diapositives Java avec Aspose.Slides. Personnalisez le positionnement et la taille des graphiques grâce à ce guide étape par étape avec code source."
"linktitle": "Définir le mode de mise en page dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir le mode de mise en page dans les diapositives Java"
"url": "/fr/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir le mode de mise en page dans les diapositives Java


## Introduction à la définition du mode de mise en page dans les diapositives Java

Dans ce tutoriel, nous allons apprendre à définir le mode de mise en page d'un graphique dans des diapositives Java à l'aide d'Aspose.Slides pour Java. Le mode de mise en page détermine le positionnement et la taille du graphique dans la diapositive.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une présentation

Tout d’abord, nous devons créer une nouvelle présentation.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter une diapositive et un graphique

Nous allons ensuite ajouter une diapositive et un graphique. Dans cet exemple, nous allons créer un graphique à colonnes groupées.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Étape 3 : Définir la disposition du graphique

Définissons maintenant la mise en page du graphique. Nous allons ajuster sa position et sa taille dans la diapositive à l'aide de l'icône `setX`, `setY`, `setWidth`, `setHeight` méthodes. De plus, nous définirons les `LayoutTargetType` pour déterminer le mode de mise en page.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Dans cet exemple, nous avons défini le type de cible de mise en page du graphique sur « Intérieur », ce qui signifie qu'il sera positionné et dimensionné par rapport à la zone intérieure de la diapositive.

## Étape 4 : Enregistrer la présentation

Enfin, enregistrons la présentation avec les paramètres de mise en page du graphique.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir le mode de mise en page dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce tutoriel, nous avons appris à définir le mode de mise en page d'un graphique dans les diapositives Java à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser la position et la taille du graphique selon vos besoins en ajustant les valeurs dans le champ. `setX`, `setY`, `setWidth`, `setHeight`, et `setLayoutTargetType` méthodes. Cela vous permet de contrôler le placement des graphiques dans vos diapositives.

## FAQ

### Comment modifier le mode de mise en page d'un graphique dans Aspose.Slides pour Java ?

Pour modifier le mode de mise en page d'un graphique dans Aspose.Slides pour Java, vous pouvez utiliser le `setLayoutTargetType` sur la zone de tracé du graphique. Vous pouvez la définir sur `LayoutTargetType.Inner` ou `LayoutTargetType.Outer` en fonction de la disposition souhaitée.

### Puis-je personnaliser la position et la taille du graphique dans la diapositive ?

Oui, vous pouvez personnaliser la position et la taille du graphique dans la diapositive en utilisant le `setX`, `setY`, `setWidth`, et `setHeight` Méthodes sur la zone de tracé du graphique. Ajustez ces valeurs pour positionner et dimensionner le graphique selon vos besoins.

### Où puis-je trouver plus d'informations sur Aspose.Slides pour Java ?

Vous pouvez trouver plus d'informations sur Aspose.Slides pour Java dans le [documentation](https://reference.aspose.com/slides/java/)Il comprend des références API détaillées et des exemples pour vous aider à travailler efficacement avec des diapositives et des graphiques en Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
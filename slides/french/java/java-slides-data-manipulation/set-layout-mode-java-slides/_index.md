---
title: Définir le mode de mise en page dans les diapositives Java
linktitle: Définir le mode de mise en page dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir les modes de mise en page pour les diapositives Java à l'aide d'Aspose.Slides. Personnalisez le positionnement et le dimensionnement des graphiques dans ce guide étape par étape avec le code source.
type: docs
weight: 23
url: /fr/java/data-manipulation/set-layout-mode-java-slides/
---

## Introduction à la définition du mode de mise en page dans les diapositives Java

Dans ce didacticiel, nous apprendrons comment définir le mode de mise en page d'un graphique dans des diapositives Java à l'aide d'Aspose.Slides pour Java. Le mode de mise en page détermine le positionnement et la taille du graphique dans la diapositive.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une présentation

Tout d’abord, nous devons créer une nouvelle présentation.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter une diapositive et un graphique

Ensuite, nous y ajouterons une diapositive et un graphique. Dans cet exemple, nous allons créer un histogramme groupé.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Étape 3 : Définir la disposition du graphique

 Maintenant, définissons la mise en page du graphique. Nous ajusterons la position et la taille du graphique dans la diapositive à l'aide du`setX`, `setY`, `setWidth`, `setHeight` méthodes. De plus, nous définirons le`LayoutTargetType` pour déterminer le mode de mise en page.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Dans cet exemple, nous avons défini le type de cible de mise en page du graphique sur « Intérieur », ce qui signifie qu'il sera positionné et dimensionné par rapport à la zone intérieure de la diapositive.

## Étape 4 : Enregistrez la présentation

Enfin, sauvegardons la présentation avec les paramètres de mise en page du graphique.

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

 Dans ce didacticiel, nous avons appris à définir le mode de mise en page d'un graphique dans des diapositives Java à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser la position et la taille du graphique en fonction de vos besoins spécifiques en ajustant les valeurs dans le`setX`, `setY`, `setWidth`, `setHeight` , et`setLayoutTargetType`méthodes. Cela vous permet de contrôler le placement des graphiques dans vos diapositives.

## FAQ

### Comment modifier le mode de mise en page d'un graphique dans Aspose.Slides pour Java ?

 Pour modifier le mode de mise en page d'un graphique dans Aspose.Slides pour Java, vous pouvez utiliser l'outil`setLayoutTargetType` méthode sur la zone de tracé du graphique. Vous pouvez le définir soit`LayoutTargetType.Inner` ou`LayoutTargetType.Outer` en fonction de la disposition souhaitée.

### Puis-je personnaliser la position et la taille du graphique dans la diapositive ?

 Oui, vous pouvez personnaliser la position et la taille du graphique dans la diapositive en utilisant l'option`setX`, `setY`, `setWidth` , et`setHeight` méthodes sur la zone de tracé du graphique. Ajustez ces valeurs pour positionner et dimensionner le graphique en fonction de vos besoins.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour Java ?

 Vous pouvez trouver plus d’informations sur Aspose.Slides pour Java dans le[Documentation](https://reference.aspose.com/slides/java/). Il comprend des références API détaillées et des exemples pour vous aider à travailler efficacement avec des diapositives et des graphiques en Java.
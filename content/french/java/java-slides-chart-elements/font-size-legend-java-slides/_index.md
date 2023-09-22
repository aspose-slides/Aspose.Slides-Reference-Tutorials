---
title: Légende de la taille de police dans les diapositives Java
linktitle: Légende de la taille de police dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez les présentations PowerPoint avec Aspose.Slides pour Java. Découvrez comment personnaliser les tailles de police des légendes et bien plus encore dans notre guide étape par étape.
type: docs
weight: 13
url: /fr/java/chart-elements/font-size-legend-java-slides/
---

## Introduction à la légende de la taille de police dans les diapositives Java

Dans ce didacticiel, vous apprendrez à personnaliser la taille de la police de la légende dans une diapositive PowerPoint à l'aide d'Aspose.Slides pour Java. Nous fournirons des instructions étape par étape et le code source pour réaliser cette tâche.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : initialiser la présentation

Tout d’abord, importez les classes nécessaires et initialisez votre présentation PowerPoint.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Remplacer`"Your Document Directory"` avec le chemin réel de votre fichier PowerPoint.

## Étape 2 : ajouter un graphique

Ensuite, nous ajouterons un graphique à la diapositive et définirons la taille de la police de la légende.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Dans ce code, nous créons un histogramme groupé sur la première diapositive et définissons la taille de police du texte de la légende sur 20 points. Vous pouvez ajuster le`setFontHeight` valeur pour modifier la taille de la police selon vos besoins.

## Étape 3 : Personnaliser les valeurs des axes

Maintenant, personnalisons les valeurs de l'axe vertical du graphique.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ici, nous définissons les valeurs minimales et maximales pour l'axe vertical. Vous pouvez modifier les valeurs selon vos besoins en données.

## Étape 4 : Enregistrez la présentation

Enfin, enregistrez la présentation modifiée dans un nouveau fichier.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Ce code enregistre la présentation modifiée sous "output.pptx" dans le répertoire spécifié.

## Code source complet pour la légende de la taille de police dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Vous avez personnalisé avec succès la taille de la police de la légende dans une diapositive Java PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez explorer davantage les capacités d'Aspose.Slides pour créer des présentations interactives et visuellement attrayantes.

## FAQ

### Comment modifier la taille de la police du texte de légende dans un graphique ?

Pour modifier la taille de la police du texte de la légende dans un graphique, vous pouvez utiliser le code suivant :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Dans ce code, nous créons un graphique et définissons la taille de police du texte de la légende sur 20 points. Vous pouvez ajuster le`setFontHeight` valeur pour modifier la taille de la police.

### Puis-je personnaliser d’autres propriétés de la légende dans un graphique ?

Oui, vous pouvez personnaliser diverses propriétés de la légende dans un graphique à l'aide d'Aspose.Slides. Certaines des propriétés courantes que vous pouvez personnaliser incluent le formatage du texte, la position, la visibilité, etc. Par exemple, pour changer la position de la légende, vous pouvez utiliser :

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ce code définit la légende pour qu'elle apparaisse au bas du graphique. Explorez la documentation Aspose.Slides pour plus d'options de personnalisation.

### Comment définir les valeurs minimales et maximales de l'axe vertical dans un graphique ?

Pour définir les valeurs minimales et maximales de l'axe vertical dans un graphique, vous pouvez utiliser le code suivant :

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ici, nous désactivons la mise à l'échelle automatique de l'axe et spécifions les valeurs minimales et maximales pour l'axe vertical. Ajustez les valeurs selon vos besoins pour les données de votre graphique.

### Où puis-je trouver plus d’informations et de documentation sur Aspose.Slides ?

 Vous pouvez trouver une documentation complète et des références API pour Aspose.Slides pour Java sur le site Web de documentation Aspose. Visite[ici](https://reference.aspose.com/slides/java/) pour des informations détaillées sur l’utilisation de la bibliothèque.
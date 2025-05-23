---
"description": "Améliorez vos présentations PowerPoint avec Aspose.Slides pour Java. Découvrez comment personnaliser la taille des polices des légendes et bien plus encore grâce à notre guide étape par étape."
"linktitle": "Légende de la taille de police dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Légende de la taille de police dans les diapositives Java"
"url": "/fr/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Légende de la taille de police dans les diapositives Java


## Introduction à la légende de taille de police dans les diapositives Java

Dans ce tutoriel, vous apprendrez à personnaliser la taille de police de la légende d'une diapositive PowerPoint avec Aspose.Slides pour Java. Nous vous fournirons des instructions étape par étape et le code source pour réaliser cette tâche.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Initialiser la présentation

Tout d’abord, importez les classes nécessaires et initialisez votre présentation PowerPoint.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Remplacer `"Your Document Directory"` avec le chemin réel vers votre fichier PowerPoint.

## Étape 2 : Ajouter un graphique

Ensuite, nous allons ajouter un graphique à la diapositive et définir la taille de police de la légende.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Dans ce code, nous créons un histogramme groupé sur la première diapositive et définissons la taille de police du texte de la légende à 20 points. Vous pouvez ajuster la taille. `setFontHeight` valeur pour modifier la taille de la police selon les besoins.

## Étape 3 : Personnaliser les valeurs de l’axe

Maintenant, personnalisons les valeurs de l’axe vertical du graphique.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ici, nous définissons les valeurs minimales et maximales pour l'axe vertical. Vous pouvez modifier ces valeurs selon vos besoins en données.

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez la présentation modifiée dans un nouveau fichier.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Ce code enregistre la présentation modifiée sous le nom « output.pptx » dans le répertoire spécifié.

## Code source complet de la légende de taille de police dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
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

Vous avez personnalisé la taille de police de la légende d'une diapositive PowerPoint Java avec Aspose.Slides pour Java. Vous pouvez explorer davantage les fonctionnalités d'Aspose.Slides pour créer des présentations interactives et visuellement attrayantes.

## FAQ

### Comment modifier la taille de la police du texte de la légende dans un graphique ?

Pour modifier la taille de la police du texte de la légende dans un graphique, vous pouvez utiliser le code suivant :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Dans ce code, nous créons un graphique et définissons la taille de police du texte de la légende à 20 points. Vous pouvez ajuster la taille. `setFontHeight` valeur pour changer la taille de la police.

### Puis-je personnaliser d’autres propriétés de la légende dans un graphique ?

Oui, vous pouvez personnaliser diverses propriétés de la légende d'un graphique avec Aspose.Slides. Parmi les propriétés courantes personnalisables, on trouve la mise en forme du texte, sa position, sa visibilité, etc. Par exemple, pour modifier la position de la légende, vous pouvez utiliser :

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ce code définit la légende pour qu'elle apparaisse en bas du graphique. Consultez la documentation d'Aspose.Slides pour plus d'options de personnalisation.

### Comment définir les valeurs minimales et maximales de l’axe vertical dans un graphique ?

Pour définir les valeurs minimales et maximales de l’axe vertical d’un graphique, vous pouvez utiliser le code suivant :

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Ici, nous désactivons la mise à l'échelle automatique des axes et spécifions les valeurs minimale et maximale de l'axe vertical. Ajustez les valeurs selon vos besoins pour les données de votre graphique.

### Où puis-je trouver plus d'informations et de documentation sur Aspose.Slides ?

Vous trouverez une documentation complète et des références API pour Aspose.Slides pour Java sur le site web de documentation d'Aspose. Visitez [ici](https://reference.aspose.com/slides/java/) pour des informations détaillées sur l'utilisation de la bibliothèque.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Propriétés de police pour le graphique dans les diapositives Java
linktitle: Propriétés de police pour le graphique dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez les propriétés de police du graphique dans les diapositives Java avec Aspose.Slides pour Java. Personnalisez la taille, le style et la couleur de la police pour des présentations percutantes.
weight: 11
url: /fr/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés de police pour le graphique dans les diapositives Java


## Introduction aux propriétés de police du graphique dans les diapositives Java

Ce guide vous guidera dans la définition des propriétés de police d'un graphique dans Java Slides à l'aide d'Aspose.Slides. Vous pouvez personnaliser la taille de la police et l'apparence du texte du graphique pour améliorer l'attrait visuel de vos présentations.

## Conditions préalables

 Avant de commencer, assurez-vous que l'API Aspose.Slides pour Java est intégrée à votre projet. Si ce n'est pas déjà fait, vous pouvez le télécharger depuis[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## Étape 1 : Créer une présentation

Tout d’abord, créez une nouvelle présentation en utilisant le code suivant :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique

Maintenant, ajoutons un histogramme groupé à votre présentation :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Ici, nous ajoutons un histogramme groupé à la première diapositive aux coordonnées (100, 100) avec une largeur de 500 unités et une hauteur de 400 unités.

## Étape 3 : Personnaliser les propriétés de la police

Ensuite, nous personnaliserons les propriétés de police du graphique. Dans cet exemple, nous définissons la taille de police sur 20 pour tout le texte du graphique :

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ce code définit la taille de police à 20 points pour tout le texte du graphique.

## Étape 4 : Afficher les étiquettes de données

Vous pouvez également afficher des étiquettes de données sur le graphique à l'aide du code suivant :

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Cette ligne de code active les étiquettes de données pour la première série du graphique, affichant les valeurs sur les colonnes du graphique.

## Étape 5 : Enregistrez la présentation

Enfin, enregistrez la présentation avec les propriétés de police de votre graphique personnalisées :

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ce code enregistrera la présentation dans le répertoire spécifié avec le nom de fichier « FontPropertiesForChart.pptx ».

## Code source complet pour les propriétés de police du graphique dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à personnaliser les propriétés de police d'un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Vous pouvez appliquer ces techniques pour améliorer l'apparence de vos graphiques et présentations. Explorez plus d'options dans le[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## FAQ

### Comment puis-je changer la couleur de la police ?

 Pour modifier la couleur de la police du texte du graphique, utilisez`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , remplaçant`Color.RED` avec la couleur désirée.

### Puis-je modifier le style de police (gras, italique, etc.) ?

 Oui, vous pouvez modifier le style de police. Utiliser`chart.getTextFormat().getPortionFormat().setFontBold(true);` pour rendre la police en gras. De la même manière, vous pouvez utiliser`setFontItalic(true)` pour le mettre en italique.

### Comment personnaliser les propriétés de police pour des éléments spécifiques du graphique ?

Pour personnaliser les propriétés de police d'éléments de graphique spécifiques, tels que les étiquettes d'axe ou le texte de légende, vous pouvez accéder à ces éléments et définir leurs propriétés de police à l'aide de méthodes similaires à celles indiquées ci-dessus.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

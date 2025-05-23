---
"description": "Améliorez les propriétés de police des graphiques dans les diapositives Java avec Aspose.Slides pour Java. Personnalisez la taille, le style et la couleur des polices pour des présentations percutantes."
"linktitle": "Propriétés de police pour les graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Propriétés de police pour les graphiques dans les diapositives Java"
"url": "/fr/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés de police pour les graphiques dans les diapositives Java


## Introduction aux propriétés de police pour les graphiques dans les diapositives Java

Ce guide vous explique comment définir les propriétés de police d'un graphique dans Java Slides avec Aspose.Slides. Vous pouvez personnaliser la taille de police et l'apparence du texte du graphique pour améliorer l'attrait visuel de vos présentations.

## Prérequis

Avant de commencer, assurez-vous que l'API Aspose.Slides pour Java est intégrée à votre projet. Si ce n'est pas déjà fait, vous pouvez la télécharger depuis le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## Étape 1 : Créer une présentation

Tout d’abord, créez une nouvelle présentation en utilisant le code suivant :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : Ajouter un graphique

Maintenant, ajoutons un graphique à colonnes groupées à votre présentation :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Ici, nous ajoutons un graphique à colonnes groupées à la première diapositive aux coordonnées (100, 100) avec une largeur de 500 unités et une hauteur de 400 unités.

## Étape 3 : Personnaliser les propriétés de la police

Nous allons ensuite personnaliser les propriétés de police du graphique. Dans cet exemple, nous définissons la taille de police à 20 pour tout le texte du graphique :

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ce code définit la taille de la police à 20 points pour tout le texte du graphique.

## Étape 4 : Afficher les étiquettes de données

Vous pouvez également afficher les étiquettes de données sur le graphique à l’aide du code suivant :

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Cette ligne de code active les étiquettes de données pour la première série du graphique, affichant les valeurs sur les colonnes du graphique.

## Étape 5 : Enregistrer la présentation

Enfin, enregistrez la présentation avec vos propriétés de police de graphique personnalisées :

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ce code enregistrera la présentation dans le répertoire spécifié avec le nom de fichier « FontPropertiesForChart.pptx ».

## Code source complet des propriétés de police pour les graphiques dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
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

Dans ce tutoriel, vous avez appris à personnaliser les propriétés de police d'un graphique dans Java Slides avec Aspose.Slides pour Java. Vous pouvez appliquer ces techniques pour améliorer l'apparence de vos graphiques et présentations. Explorez d'autres options dans la section [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## FAQ

### Comment puis-je changer la couleur de la police ?

Pour modifier la couleur de police du texte du graphique, utilisez `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, remplaçant `Color.RED` avec la couleur désirée.

### Puis-je changer le style de police (gras, italique, etc.) ?

Oui, vous pouvez modifier le style de police. Utilisez `chart.getTextFormat().getPortionFormat().setFontBold(true);` pour mettre la police en gras. De même, vous pouvez utiliser `setFontItalic(true)` pour le mettre en italique.

### Comment personnaliser les propriétés de police pour des éléments de graphique spécifiques ?

Pour personnaliser les propriétés de police d'éléments de graphique spécifiques, tels que les étiquettes d'axe ou le texte de légende, vous pouvez accéder à ces éléments et définir leurs propriétés de police à l'aide de méthodes similaires à celles indiquées ci-dessus.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
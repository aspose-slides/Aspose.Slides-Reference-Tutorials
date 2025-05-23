---
"description": "Améliorez vos graphiques avec Aspose.Slides pour Java. Apprenez à définir l'axe de position dans les diapositives Java, à créer des présentations époustouflantes et à personnaliser facilement la mise en page de vos graphiques."
"linktitle": "Définition de l'axe de position dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définition de l'axe de position dans les diapositives Java"
"url": "/fr/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définition de l'axe de position dans les diapositives Java


## Introduction à la définition de l'axe de position dans Aspose.Slides pour Java

Dans ce tutoriel, nous allons apprendre à définir l'axe des ordonnées dans un graphique avec Aspose.Slides pour Java. Le positionnement de l'axe peut être utile pour personnaliser l'apparence et la mise en page de votre graphique. Nous allons créer un histogramme groupé et ajuster la position de l'axe horizontal entre les catégories.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une présentation

Commençons par créer une nouvelle présentation avec laquelle travailler :

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Assurez-vous de remplacer `"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

## Étape 2 : Ajout d'un graphique

Nous allons ensuite ajouter un histogramme groupé à la diapositive. Nous en préciserons le type, la position (coordonnées x et y) et les dimensions (largeur et hauteur) :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Ici, nous avons ajouté un graphique à colonnes groupées à la position (50, 50) avec une largeur de 450 et une hauteur de 300. Vous pouvez ajuster ces valeurs selon vos besoins.

## Étape 3 : Définition de l'axe de position

Pour définir l'axe de position entre les catégories, vous pouvez utiliser le code suivant :

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Ce code définit l'axe horizontal à afficher entre les catégories, ce qui peut être utile pour certaines mises en page de graphiques.

## Étape 4 : Enregistrer la présentation

Enfin, sauvegardons la présentation avec le graphique :

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Remplacer `"AsposeClusteredColumnChart.pptx"` avec le nom de fichier souhaité.

Et voilà ! Vous avez créé avec succès un graphique à colonnes groupées et défini l'axe de positionnement entre les catégories avec Aspose.Slides pour Java.

## Code source complet
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce tutoriel, nous avons découvert comment définir l'axe des ordonnées dans un graphique avec Aspose.Slides pour Java. En suivant les étapes décrites dans ce guide, vous avez appris à créer un histogramme groupé et à personnaliser son apparence en positionnant l'axe horizontal entre les catégories. Aspose.Slides pour Java offre de puissantes fonctionnalités pour travailler avec des graphiques et des présentations, ce qui en fait un outil précieux pour les développeurs Java.

## FAQ

### Comment personnaliser davantage le graphique ?

Vous pouvez personnaliser divers aspects du graphique, notamment les séries de données, le titre du graphique, les légendes, etc. Consultez la section [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/) pour des instructions détaillées et des exemples.

### Puis-je changer le type de graphique ?

Oui, vous pouvez modifier le type de graphique en modifiant le `ChartType` Paramètre lors de l'ajout du graphique. Aspose.Slides pour Java prend en charge différents types de graphiques, comme les graphiques à barres, les graphiques linéaires, etc.

### Où puis-je trouver plus d'exemples et de documentation ?

Vous trouverez une documentation complète et plus d'exemples sur le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/) page.

N'oubliez pas de supprimer l'objet de présentation lorsque vous avez terminé de l'utiliser pour libérer les ressources système :

```java
if (pres != null) pres.dispose();
```

Voilà pour ce tutoriel. Vous avez appris à définir l'axe des positions dans un graphique avec Aspose.Slides pour Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Ajouter des barres d'erreur dans les diapositives Java
linktitle: Ajouter des barres d'erreur dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des barres d'erreur aux graphiques PowerPoint en Java à l'aide d'Aspose.Slides. Guide étape par étape avec code source pour personnaliser les barres d'erreur.
weight: 13
url: /fr/java/chart-data-manipulation/add-error-bars-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à l'ajout de barres d'erreur dans les diapositives Java à l'aide d'Aspose.Slides

Dans ce didacticiel, nous montrerons comment ajouter des barres d'erreur à un graphique dans une diapositive PowerPoint à l'aide d'Aspose.Slides pour Java. Les barres d'erreur fournissent des informations précieuses sur la variabilité ou l'incertitude des points de données dans un graphique. Nous allons créer un graphique à bulles et y ajouter des barres d’erreur. Commençons!

## Conditions préalables

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque à partir du[Site Aspose](https://downloads.aspose.com/slides/java).

## Étape 1 : Créer une présentation vide

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une présentation vide
Presentation presentation = new Presentation();
```

Dans cette étape, nous créons une présentation vide dans laquelle nous ajouterons notre graphique avec des barres d'erreur.

## Étape 2 : Créer un graphique à bulles

```java
// Créer un graphique à bulles
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Ici, nous créons un graphique à bulles et spécifions sa position et ses dimensions sur la diapositive.

## Étape 3 : ajout de barres d'erreur et définition du format

```java
// Ajout de barres d'erreur et définition de son format
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Dans cette étape, nous ajoutons des barres d'erreur au graphique et définissons leur format. Vous pouvez personnaliser les barres d'erreur en modifiant les valeurs, les types et d'autres propriétés.

- `errBarX` représente les barres d'erreur le long de l'axe X.
- `errBarY` représente les barres d'erreur le long de l'axe Y.
- Nous rendons visibles les barres d’erreur X et Y.
- `setValueType` spécifie le type de valeur pour les barres d'erreur (par exemple, Fixe ou Pourcentage).
- `setValue` définit la valeur des barres d'erreur.
- `setType` définit le type de barres d'erreur (par exemple, Plus ou Moins).
-  Nous définissons la largeur des lignes de la barre d'erreur en utilisant`getFormat().getLine().setWidth(2)`.
- `setEndCap`spécifie s'il faut inclure des embouts sur les barres d'erreur.

## Étape 4 : Enregistrez la présentation

```java
// Enregistrement de la présentation
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec les barres d'erreur ajoutées à un emplacement spécifié.

C'est ça! Vous avez ajouté avec succès des barres d'erreur à un graphique dans une diapositive PowerPoint à l'aide d'Aspose.Slides pour Java.

## Code source complet pour ajouter des barres d'erreur dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une présentation vide
Presentation presentation = new Presentation();
try
{
	// Créer un graphique à bulles
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Ajout de barres d'erreur et définition de son format
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Enregistrement de la présentation
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment améliorer vos présentations PowerPoint en ajoutant des barres d'erreur aux graphiques à l'aide d'Aspose.Slides pour Java. Les barres d'erreur fournissent des informations précieuses sur la variabilité et les incertitudes des données, rendant vos présentations plus informatives et visuellement attrayantes.

## FAQ

### Comment puis-je personnaliser davantage l’apparence des barres d’erreur ?

Vous pouvez personnaliser les barres d'erreur en modifiant leurs propriétés, telles que le style de ligne, la couleur et la largeur, comme illustré à l'étape 3.

### Puis-je ajouter des barres d’erreur à différents types de graphiques ?

Oui, vous pouvez ajouter des barres d'erreur à différents types de graphiques pris en charge par Aspose.Slides pour Java. Créez simplement le type de graphique souhaité et suivez les mêmes étapes de personnalisation de la barre d'erreur.

### Comment puis-je ajuster la position et la taille du graphique sur la diapositive ?

 Vous pouvez contrôler la position et les dimensions du graphique en ajustant les paramètres dans le`addChart` méthode, comme indiqué à l’étape 2.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour Java ?

 Vous pouvez vous référer au[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/) pour des informations détaillées sur l’utilisation de la bibliothèque.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

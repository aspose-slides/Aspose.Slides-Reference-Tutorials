---
title: Trou de graphique en beignet dans les diapositives Java
linktitle: Trou de graphique en beignet dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Créez des graphiques en anneau avec des tailles de trous personnalisées dans les diapositives Java à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec code source pour la personnalisation des graphiques.
weight: 11
url: /fr/java/chart-elements/doughnut-chart-hole-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction au graphique en anneau avec un trou dans les diapositives Java

Dans ce didacticiel, nous vous guiderons dans la création d'un graphique en anneau avec un trou à l'aide d'Aspose.Slides pour Java. Ce guide étape par étape vous guidera tout au long du processus avec des exemples de code source.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet Java. Vous pouvez le télécharger depuis le[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## Étape 1 : Importer les bibliothèques requises

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Étape 2 : initialiser la présentation

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
```

## Étape 3 : Créer le graphique en beignet

```java
try {
    // Créez un graphique en anneau sur la première diapositive
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Définir la taille du trou dans le graphique en anneau (en pourcentage)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Enregistrez la présentation sur le disque
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Supprimer l'objet de présentation
    if (presentation != null) presentation.dispose();
}
```

## Étape 4 : Exécutez le code

 Exécutez le code Java dans votre IDE ou éditeur de texte pour créer un graphique en anneau avec une taille de trou spécifiée. Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel où vous souhaitez enregistrer la présentation.

## Code source complet pour le trou du graphique en beignet dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Écrire la présentation sur le disque
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

 Dans ce didacticiel, vous avez appris à créer un graphique en anneau avec un trou à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser la taille du trou en ajustant le`setDoughnutHoleSize` paramètre de méthode.

## FAQ

### Comment puis-je changer la couleur des segments du graphique ?

 Pour changer la couleur des segments du graphique, vous pouvez utiliser le`setDataPointsInLegend` méthode sur le`IChart` objet et définissez la couleur souhaitée pour chaque point de données.

### Puis-je ajouter des étiquettes aux segments du graphique en anneau ?

 Oui, vous pouvez ajouter des étiquettes aux segments du graphique en anneau à l'aide de l'outil`setDataPointsLabelValue` méthode sur le`IChart` objet.

### Est-il possible d'ajouter un titre au graphique ?

 Certainement! Vous pouvez ajouter un titre au graphique en utilisant le`setTitle` méthode sur le`IChart` objet et en fournissant le texte du titre souhaité.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

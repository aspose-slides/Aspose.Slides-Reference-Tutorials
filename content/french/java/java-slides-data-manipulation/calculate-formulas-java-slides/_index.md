---
title: Calculer des formules dans les diapositives Java
linktitle: Calculer des formules dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment calculer des formules dans Java Slides à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec code source pour les présentations PowerPoint dynamiques.
type: docs
weight: 10
url: /fr/java/data-manipulation/calculate-formulas-java-slides/
---

## Introduction au calcul de formules dans Java Slides à l'aide d'Aspose.Slides

Dans ce guide, nous montrerons comment calculer des formules dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante pour travailler avec des présentations PowerPoint et fournit des fonctionnalités permettant de manipuler des graphiques et d'effectuer des calculs de formules dans les diapositives.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Environnement de développement Java
-  Bibliothèque Aspose.Slides pour Java (vous pouvez la télécharger depuis[ici](https://releases.aspose.com/slides/java/)
- Connaissance de base de la programmation Java

## Étape 1 : Créer une nouvelle présentation

Tout d’abord, créons une nouvelle présentation PowerPoint et ajoutons-y une diapositive. Nous travaillerons avec une seule diapositive dans cet exemple.

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter un graphique à la diapositive

Maintenant, ajoutons un histogramme groupé à la diapositive. Nous utiliserons ce tableau pour démontrer les calculs de formules.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Étape 3 : définir les formules et les valeurs

Ensuite, nous définirons les formules et les valeurs pour les cellules de données du graphique à l'aide de l'API Aspose.Slides. Nous allons calculer les formules pour ces cellules.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Définir la formule pour la cellule A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Définir la valeur pour la cellule A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Définir la formule pour la cellule B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Définir la formule pour la cellule C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Définir à nouveau la formule pour la cellule A1
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Étape 4 : Enregistrez la présentation

Enfin, sauvons la présentation modifiée avec les formules calculées.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Code source complet pour calculer des formules dans les diapositives Java

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce guide, nous avons appris à calculer des formules dans Java Slides à l'aide d'Aspose.Slides pour Java. Nous avons créé une nouvelle présentation, y avons ajouté un graphique, défini des formules et des valeurs pour les cellules de données du graphique et enregistré la présentation avec les formules calculées.

## FAQ

### Comment définir des formules pour les cellules de données d’un graphique ?

 Vous pouvez définir des formules pour les cellules de données du graphique à l'aide de l'outil`setFormula` méthode de`IChartDataCell` dans Aspose.Slides.

### Comment définir les valeurs des cellules de données du graphique ?

 Vous pouvez définir des valeurs pour les cellules de données du graphique à l'aide de l'outil`setValue` méthode de`IChartDataCell` dans Aspose.Slides.

### Comment calculer des formules dans un classeur ?

 Vous pouvez calculer des formules dans un classeur à l'aide de l'outil`calculateFormulas` méthode de`IChartDataWorkbook` dans Aspose.Slides.

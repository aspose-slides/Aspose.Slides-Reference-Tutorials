---
"description": "Apprenez à définir des formules pour les cellules de données de graphiques dans des présentations PowerPoint Java avec Aspose.Slides pour Java. Créez des graphiques dynamiques avec des formules."
"linktitle": "Formules de cellules de données de graphique dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Formules de cellules de données de graphique dans les diapositives Java"
"url": "/fr/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formules de cellules de données de graphique dans les diapositives Java


## Introduction aux formules de cellules de données de graphique dans Aspose.Slides pour Java

Dans ce tutoriel, nous découvrirons comment utiliser les formules des cellules de données de graphiques avec Aspose.Slides pour Java. Avec Aspose.Slides, vous pouvez créer et manipuler des graphiques dans des présentations PowerPoint, y compris définir des formules pour les cellules de données.

## Prérequis

Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une présentation PowerPoint

Commençons par créer une nouvelle présentation PowerPoint et ajoutons-y un graphique.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Ajouter un graphique à la première diapositive
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Obtenez le classeur pour les données graphiques
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Continuer avec les opérations sur les cellules de données
    // ...
    
    // Enregistrer la présentation
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Étape 2 : Définir des formules pour les cellules de données

Définissons maintenant des formules pour des cellules de données spécifiques du graphique. Dans cet exemple, nous allons définir des formules pour deux cellules différentes.

### Cellule 1 : Utilisation de la notation A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Dans le code ci-dessus, nous définissons une formule pour la cellule B2 en notation A1. La formule calcule la somme des cellules F2 à H5 et ajoute 1 au résultat.

### Cellule 2 : Utilisation de la notation R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Ici, nous définissons une formule pour la cellule C2 en utilisant la notation L1C1. La formule calcule la valeur maximale comprise entre L2C6 et L5C8, puis la divise par 3.

## Étape 3 : Calculer les formules

Après avoir défini les formules, il est essentiel de les calculer à l'aide du code suivant :

```java
workbook.calculateFormulas();
```

Cette étape garantit que le graphique reflète les valeurs mises à jour en fonction des formules.

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez la présentation modifiée dans un fichier.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Code source complet des formules de cellules de données de graphique dans les diapositives Java

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce tutoriel, nous avons exploré l'utilisation des formules de cellules de données de graphiques dans Aspose.Slides pour Java. Nous avons abordé la création d'une présentation PowerPoint, l'ajout d'un graphique, la définition de formules pour les cellules de données, le calcul de ces formules et l'enregistrement de la présentation. Vous pouvez désormais exploiter ces fonctionnalités pour créer des graphiques dynamiques et basés sur les données dans vos présentations.

## FAQ

### Comment ajouter un graphique à une diapositive spécifique ?

Pour ajouter un graphique à une diapositive spécifique, vous pouvez utiliser le `getSlides().get_Item(slideIndex)` méthode pour accéder à la diapositive souhaitée, puis utilisez le `addChart` méthode pour ajouter le graphique.

### Puis-je utiliser différents types de formules dans les cellules de données ?

Oui, vous pouvez utiliser différents types de formules, notamment des opérations mathématiques, des fonctions et des références à d’autres cellules, dans les formules de cellules de données.

### Comment puis-je changer le type de graphique ?

Vous pouvez modifier le type de graphique en utilisant le `setChartType` méthode sur le `IChart` objet et en spécifiant l'objet souhaité `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
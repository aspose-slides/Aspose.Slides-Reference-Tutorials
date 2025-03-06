---
title: Définir un classeur externe dans les diapositives Java
linktitle: Définir un classeur externe dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des classeurs externes dans Java Slides à l'aide d'Aspose.Slides pour Java. Créez des présentations dynamiques avec l'intégration de données Excel.
weight: 19
url: /fr/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir un classeur externe dans les diapositives Java


## Introduction à la définition d'un classeur externe dans les diapositives Java

Dans ce didacticiel, nous allons explorer comment définir un classeur externe dans Java Slides à l'aide d'Aspose.Slides. Vous apprendrez à créer une présentation PowerPoint avec un graphique faisant référence aux données d'un classeur Excel externe. À la fin de ce guide, vous comprendrez clairement comment intégrer des données externes dans vos présentations Java Slides.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous de disposer des conditions préalables suivantes :

- Kit de développement Java (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java ajoutée à votre projet.
- Un classeur Excel avec les données que vous souhaitez référencer dans votre présentation.

## Étape 1 : Créer une nouvelle présentation

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Nous commençons par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides.

## Étape 2 : ajouter un graphique

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Ensuite, nous insérons un diagramme circulaire dans la présentation. Vous pouvez personnaliser le type et la position du graphique selon vos besoins.

## Étape 3 : accéder au classeur externe

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Pour accéder au classeur externe, nous utilisons le`setExternalWorkbook` et fournissez le chemin d’accès au classeur Excel contenant les données.

## Étape 4 : lier les données du graphique

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Nous lions le graphique aux données du classeur externe en spécifiant les références de cellules pour les séries et les catégories.

## Étape 5 : Enregistrez la présentation

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec la référence du classeur externe sous forme de fichier PowerPoint.

## Code source complet pour définir un classeur externe dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à définir un classeur externe dans Java Slides à l'aide d'Aspose.Slides. Vous pouvez désormais créer des présentations qui référencent dynamiquement les données des classeurs Excel, améliorant ainsi la flexibilité et l'interactivité de vos diapositives.

## FAQ

### Comment installer Aspose.Slides pour Java ?

Aspose.Slides pour Java peut être installé en ajoutant la bibliothèque à votre projet Java. Vous pouvez télécharger la bibliothèque depuis le site Web Aspose et suivre les instructions d'installation fournies dans la documentation.

### Puis-je utiliser différents types de graphiques avec des classeurs externes ?

Oui, vous pouvez utiliser différents types de graphiques pris en charge par Aspose.Slides et les lier aux données de classeurs externes. Le processus peut varier légèrement selon le type de graphique que vous choisissez.

### Que se passe-t-il si la structure des données de mon classeur externe change ?

Si la structure des données de votre classeur externe change, vous devrez peut-être mettre à jour les références de cellules dans votre code Java pour garantir que les données du graphique restent exactes.

### Aspose.Slides est-il compatible avec les dernières versions de Java ?

Aspose.Slides for Java est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions de Java. Assurez-vous de vérifier les mises à jour et d'utiliser la dernière version de la bibliothèque pour des performances et une compatibilité optimales.

### Puis-je ajouter plusieurs graphiques faisant référence au même classeur externe ?

Oui, vous pouvez ajouter plusieurs graphiques à votre présentation, faisant tous référence au même classeur externe. Répétez simplement les étapes décrites dans ce didacticiel pour chaque graphique que vous souhaitez créer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

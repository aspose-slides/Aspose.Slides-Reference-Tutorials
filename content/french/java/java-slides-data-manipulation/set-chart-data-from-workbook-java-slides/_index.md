---
title: Définir les données du graphique à partir du classeur dans les diapositives Java
linktitle: Définir les données du graphique à partir du classeur dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir les données d'un graphique à partir d'un classeur Excel dans Java Slides à l'aide d'Aspose.Slides. Guide étape par étape avec des exemples de code pour des présentations dynamiques.
type: docs
weight: 15
url: /fr/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Introduction à la définition des données de graphique à partir d'un classeur dans des diapositives Java

Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programme. Il fournit des fonctionnalités étendues pour créer, manipuler et gérer des diapositives PowerPoint. Une exigence courante lorsque l'on travaille avec des présentations consiste à définir dynamiquement les données du graphique à partir d'une source de données externe, telle qu'un classeur Excel. Dans ce didacticiel, nous montrerons comment y parvenir en utilisant Java.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous de disposer des conditions préalables suivantes :

- Kit de développement Java (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java ajoutée à votre projet.
- Un classeur Excel contenant les données que vous souhaitez utiliser pour le graphique.

## Étape 1 : Créer une présentation

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Nous commençons par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides pour Java.

## Étape 2 : ajouter un graphique

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Ensuite, nous ajoutons un graphique à l'une des diapositives de la présentation. Dans cet exemple, nous ajoutons un graphique circulaire, mais vous pouvez choisir le type de graphique qui correspond à vos besoins.

## Étape 3 : Effacer les données du graphique

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Nous effaçons toutes les données existantes du graphique pour le préparer aux nouvelles données du classeur Excel.

## Étape 4 : Charger le classeur Excel

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Nous chargeons le classeur Excel contenant les données que nous souhaitons utiliser pour le graphique. Remplacer`"book1.xlsx"` avec le chemin d'accès à votre fichier Excel.

## Étape 5 : Écrire un flux de classeur pour tracer des données

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Nous convertissons les données du classeur Excel en flux et les écrivons dans les données du graphique.

## Étape 6 : Définir la plage de données du graphique

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Nous spécifions la plage de cellules du classeur Excel qui doit être utilisée comme données pour le graphique. Ajustez la plage selon vos besoins.

## Étape 7 : Personnaliser la série de graphiques

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Vous pouvez personnaliser diverses propriétés de la série de graphiques pour répondre à vos besoins. Dans cet exemple, nous activons des couleurs variées pour la série de graphiques.

## Étape 8 : Enregistrez la présentation

```java
pres.save(outPath, SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec les données du graphique mises à jour dans le chemin de sortie spécifié.

## Code source complet pour définir les données du graphique à partir du classeur dans les diapositives Java

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à définir les données d'un graphique à partir d'un classeur Excel dans Java Slides à l'aide de la bibliothèque Aspose.Slides pour Java. En suivant le guide étape par étape et en utilisant les exemples de code source fournis, vous pouvez facilement intégrer des données de graphiques dynamiques dans vos présentations PowerPoint.

## FAQ

### Comment puis-je personnaliser l’apparence du graphique dans ma présentation ?

Vous pouvez personnaliser l'apparence du graphique en modifiant les propriétés telles que les couleurs, les polices, les étiquettes, etc. Reportez-vous à la documentation Aspose.Slides pour Java pour des informations détaillées sur les options de personnalisation des graphiques.

### Puis-je utiliser les données d’un autre fichier Excel pour le graphique ?

Oui, vous pouvez utiliser les données de n'importe quel fichier Excel en spécifiant le chemin de fichier correct lors du chargement du classeur dans le code.

### Quels autres types de graphiques puis-je créer avec Aspose.Slides pour Java ?

Aspose.Slides pour Java prend en charge différents types de graphiques, notamment les graphiques à barres, les graphiques linéaires, les graphiques à nuages de points, etc. Vous pouvez choisir le type de graphique qui correspond le mieux à vos besoins en matière de représentation des données.

### Est-il possible de mettre à jour les données du graphique de manière dynamique dans une présentation en cours ?

Oui, vous pouvez mettre à jour les données du graphique de manière dynamique dans une présentation en modifiant le classeur sous-jacent, puis en actualisant les données du graphique.

### Où puis-je trouver plus d’exemples et de ressources pour travailler avec Aspose.Slides pour Java ?

 Vous pouvez explorer des exemples et des ressources supplémentaires sur le[Site Aspose](https://www.aspose.com/). De plus, la documentation Aspose.Slides pour Java fournit des conseils complets sur l'utilisation de la bibliothèque.
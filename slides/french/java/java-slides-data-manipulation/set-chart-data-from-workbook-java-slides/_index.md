---
"description": "Apprenez à définir les données d'un graphique à partir d'un classeur Excel dans Java Slides avec Aspose.Slides. Guide étape par étape avec exemples de code pour des présentations dynamiques."
"linktitle": "Définir les données du graphique à partir du classeur dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir les données du graphique à partir du classeur dans les diapositives Java"
"url": "/fr/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir les données du graphique à partir du classeur dans les diapositives Java


## Introduction à la définition des données d'un graphique à partir d'un classeur dans Java (diapositives)

Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programmation. Elle offre des fonctionnalités complètes pour la création, la manipulation et la gestion de diapositives PowerPoint. L'une des exigences courantes des présentations est de définir dynamiquement les données d'un graphique à partir d'une source de données externe, comme un classeur Excel. Dans ce tutoriel, nous vous montrerons comment y parvenir avec Java.

## Prérequis

Avant de nous plonger dans la mise en œuvre, assurez-vous de disposer des prérequis suivants :

- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java ajoutée à votre projet.
- Un classeur Excel contenant les données que vous souhaitez utiliser pour le graphique.

## Étape 1 : Créer une présentation

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Nous commençons par créer une nouvelle présentation PowerPoint en utilisant Aspose.Slides pour Java.

## Étape 2 : Ajouter un graphique

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Ensuite, nous ajoutons un graphique à l'une des diapositives de la présentation. Dans cet exemple, nous ajoutons un graphique à secteurs, mais vous pouvez choisir le type de graphique qui vous convient.

## Étape 3 : Effacer les données du graphique

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Nous effaçons toutes les données existantes du graphique pour le préparer aux nouvelles données du classeur Excel.

## Étape 4 : Charger le classeur Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Nous chargeons le classeur Excel contenant les données que nous souhaitons utiliser pour le graphique. Remplacer `"book1.xlsx"` avec le chemin vers votre fichier Excel.

## Étape 5 : Écrire le flux du classeur dans les données du graphique

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Nous convertissons les données du classeur Excel en un flux et les écrivons dans les données du graphique.

## Étape 6 : Définir la plage de données du graphique

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Nous spécifions la plage de cellules du classeur Excel à utiliser comme données pour le graphique. Ajustez la plage selon vos besoins.

## Étape 7 : Personnaliser la série de graphiques

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Vous pouvez personnaliser différentes propriétés de la série de graphiques selon vos besoins. Dans cet exemple, nous activons différentes couleurs pour la série de graphiques.

## Étape 8 : Enregistrer la présentation

```java
pres.save(outPath, SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec les données du graphique mises à jour dans le chemin de sortie spécifié.

## Code source complet pour définir les données du graphique à partir du classeur dans les diapositives Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
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

Dans ce tutoriel, nous avons appris à définir des données graphiques à partir d'un classeur Excel dans Java Slides grâce à la bibliothèque Aspose.Slides pour Java. En suivant le guide étape par étape et en utilisant les exemples de code source fournis, vous pourrez facilement intégrer des données graphiques dynamiques à vos présentations PowerPoint.

## FAQ

### Comment puis-je personnaliser l’apparence du graphique dans ma présentation ?

Vous pouvez personnaliser l'apparence du graphique en modifiant des propriétés telles que les couleurs, les polices, les libellés, etc. Consultez la documentation d'Aspose.Slides pour Java pour plus d'informations sur les options de personnalisation des graphiques.

### Puis-je utiliser des données provenant d’un autre fichier Excel pour le graphique ?

Oui, vous pouvez utiliser les données de n’importe quel fichier Excel en spécifiant le chemin de fichier correct lors du chargement du classeur dans le code.

### Quels autres types de graphiques puis-je créer avec Aspose.Slides pour Java ?

Aspose.Slides pour Java prend en charge différents types de graphiques, notamment les graphiques à barres, les graphiques en courbes, les graphiques en nuage de points, etc. Vous pouvez choisir le type de graphique le mieux adapté à vos besoins de représentation de données.

### Est-il possible de mettre à jour les données du graphique de manière dynamique dans une présentation en cours d'exécution ?

Oui, vous pouvez mettre à jour les données du graphique de manière dynamique dans une présentation en modifiant le classeur sous-jacent, puis en actualisant les données du graphique.

### Où puis-je trouver plus d’exemples et de ressources pour travailler avec Aspose.Slides pour Java ?

Vous pouvez explorer des exemples et des ressources supplémentaires sur le [Site Web d'Aspose](https://www.aspose.com/)De plus, la documentation Aspose.Slides pour Java fournit des conseils complets sur l'utilisation de la bibliothèque.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Couleur automatique des séries de graphiques dans les diapositives Java
linktitle: Couleur automatique des séries de graphiques dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment créer des graphiques dynamiques avec des couleurs de série automatiques dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Améliorez vos visualisations de données sans effort.
weight: 14
url: /fr/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Couleur automatique des séries de graphiques dans les diapositives Java


## Introduction à la couleur automatique des séries de graphiques dans Aspose.Slides pour Java

Dans ce didacticiel, nous allons explorer comment créer une présentation PowerPoint avec un graphique à l'aide d'Aspose.Slides pour Java et définir les couleurs de remplissage automatiques pour les séries de graphiques. Les couleurs de remplissage automatiques peuvent rendre vos graphiques plus attrayants visuellement et vous faire gagner du temps en laissant la bibliothèque choisir les couleurs pour vous.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Créer une nouvelle présentation

Tout d’abord, nous allons créer une nouvelle présentation PowerPoint et y ajouter une diapositive.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
```

## Étape 2 : ajouter un graphique à la diapositive

Ensuite, nous ajouterons un histogramme groupé à la diapositive. Nous définirons également la première série pour afficher les valeurs.

```java
// Accéder à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
// Ajouter un graphique avec les données par défaut
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Définir la première série sur Afficher les valeurs
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Étape 3 : Remplir les données du graphique

Nous allons maintenant remplir le graphique avec des données. Nous commencerons par supprimer les séries et catégories générées par défaut, puis ajouterons de nouvelles séries et catégories.

```java
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Supprimer les séries et catégories générées par défaut
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Ajout d'une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Ajout de nouvelles catégories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Étape 4 : Remplir les données de la série

Nous remplirons les données de série pour les séries 1 et 2.

```java
// Prendre la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Étape 5 : Définir la couleur de remplissage automatique pour les séries

Maintenant, définissons les couleurs de remplissage automatiques pour la série de graphiques. Cela obligera la bibliothèque à choisir les couleurs pour nous.

```java
// Définition de la couleur de remplissage automatique pour les séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Étape 6 : Enregistrez la présentation

Enfin, nous enregistrerons la présentation avec le graphique dans un fichier PowerPoint.

```java
// Enregistrer la présentation avec le graphique
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour la couleur automatique des séries de graphiques dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
try
{
	// Accéder à la première diapositive
	ISlide slide = presentation.getSlides().get_Item(0);
	// Ajouter un graphique avec les données par défaut
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Définir la première série sur Afficher les valeurs
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Définition de l'index de la feuille de données du graphique
	int defaultWorksheetIndex = 0;
	// Obtenir la feuille de calcul des données du graphique
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Supprimer les séries et catégories générées par défaut
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Ajout d'une nouvelle série
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Ajout de nouvelles catégories
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Prendre la première série de graphiques
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Remplir maintenant les données de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Définition de la couleur de remplissage automatique pour les séries
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Prendre la deuxième série de graphiques
	series = chart.getChartData().getSeries().get_Item(1);
	// Remplir maintenant les données de série
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Définition de la couleur de remplissage pour les séries
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Enregistrer la présentation avec le graphique
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer une présentation PowerPoint avec un graphique à l'aide d'Aspose.Slides pour Java et à définir les couleurs de remplissage automatiques pour les séries de graphiques. Les couleurs automatiques peuvent améliorer l'attrait visuel de vos graphiques et rendre vos présentations plus attrayantes. Vous pouvez personnaliser davantage le graphique selon vos besoins spécifiques.

## FAQ

### Comment définir les couleurs de remplissage automatiques pour les séries de graphiques dans Aspose.Slides pour Java ?

Pour définir les couleurs de remplissage automatiques pour les séries de graphiques dans Aspose.Slides pour Java, utilisez le code suivant :

```java
// Définition de la couleur de remplissage automatique pour les séries
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Ce code permettra à la bibliothèque de choisir automatiquement les couleurs pour la série de graphiques.

### Puis-je personnaliser les couleurs du graphique si nécessaire ?

 Oui, vous pouvez personnaliser les couleurs du graphique selon vos besoins. Dans l'exemple fourni, nous avons utilisé des couleurs de remplissage automatiques, mais vous pouvez définir des couleurs spécifiques en modifiant le`FillType` et`SolidFillColor` propriétés du format de la série.

### Comment puis-je ajouter des séries ou des catégories supplémentaires au graphique ?

 Pour ajouter des séries ou des catégories supplémentaires au graphique, utilisez le`getSeries()` et`getCategories()` méthodes du graphique`ChartData` objet. Vous pouvez ajouter de nouvelles séries et catégories en spécifiant leurs données et étiquettes.

### Est-il possible de formater davantage le graphique et les étiquettes ?

Oui, vous pouvez formater davantage le graphique, la série et les étiquettes selon vos besoins. Aspose.Slides pour Java fournit des options de formatage étendues pour les graphiques, notamment les polices, les couleurs, les styles, etc. Vous pouvez explorer la documentation pour plus de détails sur les options de formatage.

### Où puis-je trouver plus d’informations sur l’utilisation d’Aspose.Slides pour Java ?

 Pour plus d'informations et une documentation détaillée sur Aspose.Slides pour Java, vous pouvez visiter la documentation de référence[ici](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

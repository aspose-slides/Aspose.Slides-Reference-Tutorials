---
title: Graphiques normaux dans les diapositives Java
linktitle: Graphiques normaux dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Créez des graphiques normaux dans des diapositives Java avec Aspose.Slides pour Java. Guide étape par étape et code source pour créer, personnaliser et enregistrer des graphiques dans des présentations PowerPoint.
type: docs
weight: 21
url: /fr/java/chart-data-manipulation/normal-charts-java-slides/
---

## Introduction aux graphiques normaux dans les diapositives Java

Dans ce didacticiel, nous allons parcourir le processus de création de graphiques normaux dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Nous utiliserons des instructions étape par étape ainsi que le code source pour montrer comment créer un histogramme groupé dans une présentation PowerPoint.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Aspose.Slides pour l'API Java installée.
2. Un environnement de développement Java mis en place.
3. Connaissance de base de la programmation Java.

## Étape 1 : Mise en place du projet

Assurez-vous d'avoir un répertoire pour votre projet. Appelons-le « Votre répertoire de documents » comme mentionné dans le code. Vous pouvez le remplacer par le chemin réel d'accès à votre répertoire de projet.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Étape 2 : Créer une présentation

Créons maintenant une présentation PowerPoint et accédons à sa première diapositive.

```java
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation();
// Accéder à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
```

## Étape 3 : Ajout d'un graphique

Nous ajouterons un histogramme groupé à la diapositive et définirons son titre.

```java
// Ajouter un graphique avec les données par défaut
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Tableau de réglage Titre
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Étape 4 : Définition des données du graphique

Ensuite, nous définirons les données du graphique en définissant des séries et des catégories.

```java
// Définir la première série sur Afficher les valeurs
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;

//Obtenir la feuille de calcul des données du graphique
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

## Étape 5 : Remplir les données de la série

Maintenant, remplissons les points de données de la série pour le graphique.

```java
// Prendre la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Remplir les données des séries
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Définition de la couleur de remplissage pour les séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);

// Remplir les données des séries
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Définition de la couleur de remplissage pour les séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Étape 6 : personnalisation des étiquettes

Personnalisons les étiquettes de données pour la série de graphiques.

```java
// La première étiquette affichera le nom de la catégorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Afficher la valeur de la troisième étiquette avec le nom de la série et le séparateur
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Étape 7 : Sauvegarde de la présentation

Enfin, enregistrez la présentation avec le graphique dans le répertoire de votre projet.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez créé avec succès un histogramme groupé dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser davantage ce graphique en fonction de vos besoins.

## Code source complet pour les graphiques normaux dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation();
// Accéder à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
// Ajouter un graphique avec les données par défaut
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Tableau de réglage Titre
// Chart.getChartTitle().getTextFrameForOverriding().setText("Sample Title");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Définir la première série sur Afficher les valeurs
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
//Obtenir la feuille de calcul des données du graphique
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
// Définition de la couleur de remplissage pour les séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Définition de la couleur de remplissage pour les séries
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//Le premier libellé affichera le nom de la catégorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Afficher la valeur du troisième libellé
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Enregistrer la présentation avec le graphique
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusion

Dans ce didacticiel, nous avons appris à créer des graphiques normaux dans Java Slides à l'aide de l'API Aspose.Slides for Java. Nous avons parcouru un guide étape par étape avec le code source pour créer un histogramme groupé dans une présentation PowerPoint.

## FAQ

### Comment puis-je changer le type de graphique ?

 Pour changer le type de graphique, modifiez le`ChartType` paramètre lors de l'ajout du graphique à l'aide de`sld.getShapes().addChart()`. Vous pouvez choisir parmi différents types de graphiques disponibles dans Aspose.Slides.

### Puis-je changer les couleurs de la série de graphiques ?

 Oui, vous pouvez modifier les couleurs de la série de graphiques en définissant la couleur de remplissage de chaque série à l'aide de`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Comment puis-je ajouter plus de catégories ou de séries au graphique ?

 Vous pouvez ajouter plus de catégories ou de séries au graphique en ajoutant de nouveaux points de données et étiquettes à l'aide de l'icône`chart.getChartData().getCategories().add()` et`chart.getChartData().getSeries().add()` méthodes.

### Comment puis-je personnaliser davantage le titre du graphique ?

 Vous pouvez personnaliser davantage le titre du graphique en modifiant les propriétés de`chart.getChartTitle()` tels que l'alignement du texte, la taille de la police et la couleur.

### Comment puis-je enregistrer le graphique dans un format de fichier différent ?

Pour enregistrer le graphique dans un format de fichier différent, modifiez le`SaveFormat` paramètre dans le`pres.save()` méthode au format souhaité (par exemple, PDF, PNG, JPEG).
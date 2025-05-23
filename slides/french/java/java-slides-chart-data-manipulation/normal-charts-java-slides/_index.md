---
"description": "Créez des graphiques normaux dans des diapositives Java avec Aspose.Slides pour Java. Guide étape par étape et code source pour créer, personnaliser et enregistrer des graphiques dans des présentations PowerPoint."
"linktitle": "Diagrammes normaux dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagrammes normaux dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagrammes normaux dans les diapositives Java


## Introduction aux graphiques normaux en Java (diapositives)

Dans ce tutoriel, nous allons vous expliquer comment créer des graphiques classiques dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Des instructions détaillées et du code source vous montreront comment créer un histogramme groupé dans une présentation PowerPoint.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. Aspose.Slides pour l'API Java installée.
2. Un environnement de développement Java mis en place.
3. Connaissances de base de la programmation Java.

## Étape 1 : Configuration du projet

Assurez-vous d'avoir un répertoire pour votre projet. Appelons-le « Répertoire de vos documents », comme indiqué dans le code. Vous pouvez le remplacer par le chemin d'accès réel au répertoire de votre projet.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Étape 2 : Créer une présentation

Maintenant, créons une présentation PowerPoint et accédons à sa première diapositive.

```java
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation();
// Accéder à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
```

## Étape 3 : Ajout d'un graphique

Nous allons ajouter un graphique à colonnes groupées à la diapositive et définir son titre.

```java
// Ajouter un graphique avec des données par défaut
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titre du tableau de réglage
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Étape 4 : Définition des données du graphique

Ensuite, nous allons définir les données du graphique en définissant des séries et des catégories.

```java
// Définir la première série sur Afficher les valeurs
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;

// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Supprimer les séries et catégories générées par défaut
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Ajout de nouvelles séries
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Ajout de nouvelles catégories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Étape 5 : Remplissage des données de la série

Maintenant, remplissons les points de données de la série pour le graphique.

```java
// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Remplissage des données de la série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Définition de la couleur de remplissage pour la série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);

// Remplissage des données de la série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Définition de la couleur de remplissage pour la série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Étape 6 : Personnalisation des étiquettes

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

## Étape 7 : Enregistrer la présentation

Enfin, enregistrez la présentation avec le graphique dans le répertoire de votre projet.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez créé avec succès un histogramme groupé dans une présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez personnaliser ce graphique selon vos besoins.

## Code source complet pour les graphiques normaux en Java (diapositives)

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation();
// Accéder à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
// Ajouter un graphique avec des données par défaut
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Titre du tableau de réglage
// Chart.getChartTitle().getTextFrameForOverriding().setText("Exemple de titre");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
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
// Ajout de nouvelles séries
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Ajout de nouvelles catégories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Les données de la série sont maintenant en cours de remplissage
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Définition de la couleur de remplissage pour la série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Les données de la série sont maintenant en cours de remplissage
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Définition de la couleur de remplissage pour la série
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// La première étiquette affichera le nom de la catégorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Afficher la valeur pour la troisième étiquette
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Enregistrer la présentation avec le graphique
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Conclusion

Dans ce tutoriel, nous avons appris à créer des graphiques normaux dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Nous avons suivi un guide étape par étape avec le code source pour créer un histogramme groupé dans une présentation PowerPoint.

## FAQ

### Comment puis-je changer le type de graphique ?

Pour changer le type de graphique, modifiez le `ChartType` paramètre lors de l'ajout du graphique à l'aide de `sld.getShapes().addChart()`Vous pouvez choisir parmi différents types de graphiques disponibles dans Aspose.Slides.

### Puis-je modifier les couleurs de la série de graphiques ?

Oui, vous pouvez modifier les couleurs de la série de graphiques en définissant la couleur de remplissage de chaque série à l'aide de `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Comment ajouter plus de catégories ou de séries au graphique ?

Vous pouvez ajouter davantage de catégories ou de séries au graphique en ajoutant de nouveaux points de données et étiquettes à l'aide de l' `chart.getChartData().getCategories().add()` et `chart.getChartData().getSeries().add()` méthodes.

### Comment puis-je personnaliser davantage le titre du graphique ?

Vous pouvez personnaliser davantage le titre du graphique en modifiant les propriétés de `chart.getChartTitle()` tels que l'alignement du texte, la taille de la police et la couleur.

### Comment enregistrer le graphique dans un format de fichier différent ?

Pour enregistrer le graphique dans un format de fichier différent, modifiez le `SaveFormat` paramètre dans le `pres.save()` méthode au format souhaité (par exemple, PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
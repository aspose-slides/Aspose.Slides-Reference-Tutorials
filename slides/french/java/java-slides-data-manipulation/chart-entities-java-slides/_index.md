---
"description": "Apprenez à créer et personnaliser des graphiques Java Slides avec Aspose.Slides. Améliorez vos présentations grâce à de puissantes entités graphiques."
"linktitle": "Diagrammes d'entités dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagrammes d'entités dans les diapositives Java"
"url": "/fr/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagrammes d'entités dans les diapositives Java


## Introduction aux entités graphiques en Java (diapositives)

Les graphiques sont des outils puissants pour visualiser les données dans les présentations. Que vous créiez des rapports commerciaux, des présentations académiques ou tout autre type de contenu, les graphiques contribuent à transmettre efficacement l'information. Aspose.Slides pour Java offre des fonctionnalités performantes pour travailler avec des graphiques, ce qui en fait un choix incontournable pour les développeurs Java.

## Prérequis

Avant de plonger dans le monde des entités graphiques, assurez-vous de disposer des prérequis suivants :

- Kit de développement Java (JDK) installé
- Bibliothèque Aspose.Slides pour Java téléchargée et ajoutée à votre projet
- Connaissances de base de la programmation Java

Commençons maintenant par créer et personnaliser des graphiques à l’aide d’Aspose.Slides pour Java.

## Étape 1 : Créer une présentation

La première étape consiste à créer une nouvelle présentation dans laquelle vous ajouterez votre graphique. Voici un extrait de code pour créer une présentation :

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : Ajout d'un graphique

Une fois votre présentation prête, il est temps d'ajouter un graphique. Dans cet exemple, nous allons ajouter un graphique linéaire simple avec des marqueurs. Voici comment procéder :

```java
// Accéder à la première diapositive
ISlide slide = pres.getSlides().get_Item(0);

// Ajout du graphique d'échantillon
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Étape 3 : Personnalisation du titre du graphique

Un graphique bien défini doit avoir un titre. Définissons-en un :

```java
// Titre du tableau de réglage
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Étape 4 : Formatage des lignes de la grille

Vous pouvez formater les lignes principales et secondaires de votre graphique. Définissons maintenant le formatage des lignes de l'axe vertical :

```java
// Définition du format des lignes principales de la grille pour l'axe des valeurs
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Définition du format des lignes de grille mineures pour l'axe des valeurs
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Étape 5 : Personnalisation de l'axe des valeurs

Vous pouvez contrôler le format des nombres, ainsi que les valeurs maximales et minimales de l'axe des valeurs. Voici comment le personnaliser :

```java
// Format du numéro de l'axe des valeurs de réglage
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Tableau de réglage des valeurs maximales et minimales
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Étape 6 : Ajout du titre de l'axe de valeur

Pour rendre votre graphique plus informatif, vous pouvez ajouter un titre à l'axe des valeurs :

```java
// Définition du titre de l'axe des valeurs
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Étape 7 : Formatage de l'axe des catégories

L'axe des catégories, qui représente généralement les catégories de données, peut également être personnalisé :

```java
// Définition du format des lignes de grille principales pour l'axe des catégories
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Définition du format des lignes de grille mineures pour l'axe des catégories
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Étape 8 : Ajout de légendes

Les légendes expliquent les séries de données de votre graphique. Personnalisons-les :

```java
// Définition des propriétés du texte des légendes
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Définir l'affichage des légendes du graphique sans chevauchement du graphique
chart.getLegend().setOverlay(true);
```

## Étape 9 : Enregistrer la présentation

Enfin, enregistrez votre présentation avec le graphique :

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Diapositives sur le code source complet des entités graphiques en Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Instanciation de la présentation // Instanciation de la présentation
Presentation pres = new Presentation();
try
{
	// Accéder à la première diapositive
	ISlide slide = pres.getSlides().get_Item(0);
	// Ajout du graphique d'échantillon
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Titre du tableau de réglage
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Définition du format des lignes principales de la grille pour l'axe des valeurs
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Définition du format des lignes de grille mineures pour l'axe des valeurs
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Format du numéro de l'axe des valeurs de réglage
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Tableau de réglage des valeurs maximales et minimales
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Définition des propriétés du texte de l'axe des valeurs
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Définition du titre de l'axe des valeurs
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Paramètre de format de ligne d'axe de valeur : désormais obsolète
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Définition du format des lignes de grille principales pour l'axe des catégories
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Définition du format des lignes de grille mineures pour l'axe des catégories
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Définition des propriétés du texte de l'axe des catégories
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Titre de la catégorie de réglage
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Définition de la position de l'étiquette de l'axe des catégories
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Définition de l'angle de rotation de l'étiquette de l'axe de catégorie
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Définition des propriétés du texte des légendes
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Définir l'affichage des légendes du graphique sans chevauchement du graphique
	chart.getLegend().setOverlay(true);
	// Tracé de la première série sur l'axe des valeurs secondaires
	// Graphique.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Tableau de réglage de la couleur du mur arrière
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Définition de la couleur de la zone de tracé
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Enregistrer la présentation
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans cet article, nous avons exploré l'univers des entités graphiques dans Java Slides avec Aspose.Slides pour Java. Vous avez appris à créer, personnaliser et manipuler des graphiques pour améliorer vos présentations. Les graphiques rendent vos données visuellement attrayantes et aident également votre public à comprendre plus facilement des informations complexes.

## FAQ

### Comment puis-je changer le type de graphique ?

Pour changer le type de graphique, utilisez le `chart.setType()` méthode et spécifiez le type de graphique souhaité.

### Puis-je ajouter plusieurs séries de données à un graphique ?

Oui, vous pouvez ajouter plusieurs séries de données à un graphique à l'aide de l' `chart.getChartData().getSeries().addSeries()` méthode.

### Comment personnaliser les couleurs du graphique ?

Vous pouvez personnaliser les couleurs du graphique en définissant le format de remplissage de divers éléments du graphique, tels que les lignes de grille, le titre et les légendes.

### Puis-je créer des graphiques 3D ?

Oui, Aspose.Slides pour Java prend en charge la création de graphiques 3D. Vous pouvez définir `ChartType` vers un type de graphique 3D pour en créer un.

### Aspose.Slides pour Java est-il compatible avec les dernières versions de Java ?

Oui, Aspose.Slides pour Java est régulièrement mis à jour pour prendre en charge les dernières versions de Java et offre une compatibilité avec une large gamme d'environnements Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
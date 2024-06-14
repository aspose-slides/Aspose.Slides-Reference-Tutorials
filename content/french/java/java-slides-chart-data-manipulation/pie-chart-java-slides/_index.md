---
title: Graphique circulaire dans les diapositives Java
linktitle: Graphique circulaire dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer de superbes diagrammes circulaires dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec code source pour les développeurs Java.
type: docs
weight: 23
url: /fr/java/chart-data-manipulation/pie-chart-java-slides/
---

## Introduction à la création d'un diagramme circulaire dans Java Slides à l'aide d'Aspose.Slides

Dans ce didacticiel, nous montrerons comment créer un diagramme circulaire dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Nous vous fournirons des instructions étape par étape et du code source Java pour vous aider à démarrer. Ce guide suppose que vous avez déjà configuré votre environnement de développement avec Aspose.Slides pour Java.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Importer les bibliothèques requises

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Assurez-vous d'importer les classes nécessaires depuis la bibliothèque Aspose.Slides.

## Étape 2 : initialiser la présentation

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
```

 Créez un nouvel objet Présentation pour représenter votre fichier PowerPoint. Remplacer`"Your Document Directory"` avec le chemin réel où vous souhaitez enregistrer la présentation.

## Étape 3 : ajouter une diapositive

```java
// Accédez à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```

Obtenez la première diapositive de la présentation dans laquelle vous souhaitez ajouter le graphique à secteurs.

## Étape 4 : Ajouter un graphique à secteurs

```java
// Ajouter un diagramme circulaire avec les données par défaut
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Ajoutez un diagramme circulaire à la diapositive à la position et à la taille spécifiées.

## Étape 5 : Définir le titre du graphique

```java
// Définir le titre du graphique
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Définissez un titre pour le graphique à secteurs. Vous pouvez personnaliser le titre selon vos besoins.

## Étape 6 : Personnaliser les données du graphique

```java
//Définir la première série pour afficher les valeurs
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;

// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Supprimer les séries et catégories générées par défaut
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Ajout de nouvelles catégories
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Ajout d'une nouvelle série
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Remplir les données des séries
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personnalisez les données du graphique en ajoutant des catégories et des séries et en définissant leurs valeurs. Dans cet exemple, nous avons trois catégories et une série avec les points de données correspondants.

## Étape 7 : Personnaliser les secteurs du graphique à secteurs

```java
// Définir les couleurs du secteur
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personnalisez l'apparence de chaque secteur
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Personnaliser la bordure du secteur
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Personnalisez d’autres secteurs de la même manière
```

Personnalisez l'apparence de chaque secteur dans le diagramme circulaire. Vous pouvez modifier les couleurs, les styles de bordure et d'autres propriétés visuelles.

## Étape 8 : Personnaliser les étiquettes de données

```java
// Personnaliser les étiquettes de données
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personnalisez les étiquettes de données pour d'autres points de données de la même manière
```

Personnalisez les étiquettes de données pour chaque point de données dans le graphique à secteurs. Vous pouvez contrôler les valeurs affichées sur le graphique.

## Étape 9 : Afficher les lignes de repère

```java
// Afficher les lignes de repère pour le graphique
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Permettez aux lignes de repère de connecter les étiquettes de données à leurs secteurs correspondants.

## Étape 10 : Définir l'angle de rotation du graphique à secteurs

```java
// Définir l'angle de rotation des secteurs du graphique à secteurs
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Définissez l'angle de rotation des secteurs du graphique à secteurs. Dans cet exemple, nous l'avons réglé à 180 degrés.

## Étape 11 : Enregistrez la présentation

```java
// Enregistrez la présentation avec le diagramme circulaire
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Enregistrez la présentation avec le diagramme circulaire dans le répertoire spécifié.

## Code source complet pour le graphique à secteurs dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
// Accéder à la première diapositive
ISlide slides = presentation.getSlides().get_Item(0);
// Ajouter un graphique avec les données par défaut
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Tableau de réglage Titre
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
// Ajout de nouvelles catégories
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Ajout d'une nouvelle série
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ne fonctionne pas dans la nouvelle version
// Ajout de nouveaux points et définition de la couleur du secteur
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Définition de la frontière du secteur
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Définition de la frontière du secteur
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Définition de la frontière du secteur
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Créez des étiquettes personnalisées pour chacune des catégories des nouvelles séries
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Affichage des lignes de repère pour le graphique
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Définition de l'angle de rotation pour les secteurs du graphique à secteurs
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Enregistrer la présentation avec le graphique
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Vous avez créé avec succès un diagramme circulaire dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser l'apparence du graphique et les étiquettes de données en fonction de vos besoins spécifiques. Ce didacticiel fournit un exemple de base et vous pouvez améliorer et personnaliser davantage vos graphiques selon vos besoins.

## FAQ

### Comment puis-je modifier les couleurs de secteurs individuels dans le diagramme circulaire ?

 Pour modifier les couleurs de secteurs individuels dans le graphique à secteurs, vous pouvez personnaliser la couleur de remplissage pour chaque point de données. Dans l'exemple de code fourni, nous avons montré comment définir la couleur de remplissage pour chaque secteur à l'aide du`getSolidFillColor().setColor()` méthode. Vous pouvez modifier les valeurs de couleur pour obtenir l'apparence souhaitée.

### Puis-je ajouter plus de catégories et de séries de données au graphique circulaire ?

 Oui, vous pouvez ajouter des catégories et des séries de données supplémentaires au graphique à secteurs. Pour ce faire, vous pouvez utiliser le`getChartData().getCategories().add()` et`getChartData().getSeries().add()` méthodes, comme le montre l’exemple. Fournissez simplement les données et les étiquettes appropriées pour les nouvelles catégories et séries afin d'élargir votre graphique.

### Comment personnaliser l’apparence des étiquettes de données ?

 Vous pouvez personnaliser l'apparence des étiquettes de données à l'aide de l'outil`getDataLabelFormat()` méthode sur l’étiquette de chaque point de données. Dans l'exemple, nous avons montré comment afficher la valeur sur les étiquettes de données en utilisant`getDataLabelFormat().setShowValue(true)`. Vous pouvez personnaliser davantage les étiquettes de données en contrôlant les valeurs affichées, en affichant les clés de légende et en ajustant d'autres options de formatage.

### Puis-je changer le titre du diagramme circulaire ?

 Oui, vous pouvez modifier le titre du diagramme circulaire. Dans le code fourni, nous définissons le titre du graphique en utilisant`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Vous pouvez remplacer`"Sample Title"` avec le texte de titre souhaité.

### Comment enregistrer la présentation générée avec le camembert ?

 Pour enregistrer la présentation avec le diagramme circulaire, utilisez le`presentation.save()` méthode. Fournissez le chemin et le nom du fichier souhaité ainsi que le format dans lequel vous souhaitez enregistrer la présentation. Par exemple:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Assurez-vous de spécifier le chemin et le format du fichier corrects.

### Puis-je créer d’autres types de graphiques à l’aide d’Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java prend en charge différents types de graphiques, notamment les graphiques à barres, les graphiques linéaires, etc. Vous pouvez créer différents types de graphiques en modifiant le`ChartType` lors de l'ajout d'un graphique. Reportez-vous à la documentation Aspose.Slides pour plus de détails sur la création de différents types de graphiques.

### Comment puis-je trouver plus d’informations et d’exemples pour travailler avec Aspose.Slides pour Java ?

 Pour plus d'informations, une documentation détaillée et des exemples supplémentaires, vous pouvez visiter le[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/). Il fournit des ressources complètes pour vous aider à utiliser efficacement la bibliothèque.
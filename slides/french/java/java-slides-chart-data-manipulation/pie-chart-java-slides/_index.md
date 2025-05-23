---
"description": "Apprenez à créer de superbes graphiques à secteurs dans vos présentations PowerPoint avec Aspose.Slides pour Java. Guide étape par étape avec code source pour les développeurs Java."
"linktitle": "Diagramme à secteurs dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagramme à secteurs dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramme à secteurs dans les diapositives Java


## Introduction à la création d'un graphique à secteurs dans Java Slides avec Aspose.Slides

Dans ce tutoriel, nous vous montrerons comment créer un graphique à secteurs dans une présentation PowerPoint avec Aspose.Slides pour Java. Nous vous fournirons des instructions étape par étape et le code source Java pour vous aider à démarrer. Ce guide suppose que vous avez déjà configuré votre environnement de développement avec Aspose.Slides pour Java.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Importer les bibliothèques requises

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Assurez-vous d'importer les classes nécessaires depuis la bibliothèque Aspose.Slides.

## Étape 2 : Initialiser la présentation

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
```

Créez un nouvel objet Présentation pour représenter votre fichier PowerPoint. Remplacez `"Your Document Directory"` avec le chemin réel où vous souhaitez enregistrer la présentation.

## Étape 3 : Ajouter une diapositive

```java
// Accéder à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```

Obtenez la première diapositive de la présentation où vous souhaitez ajouter le graphique à secteurs.

## Étape 4 : Ajouter un graphique à secteurs

```java
// Ajouter un graphique à secteurs avec des données par défaut
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Ajoutez un graphique à secteurs à la diapositive à la position et à la taille spécifiées.

## Étape 5 : Définir le titre du graphique

```java
// Définir le titre du graphique
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Définissez un titre pour le graphique à secteurs. Vous pouvez le personnaliser selon vos besoins.

## Étape 6 : Personnaliser les données du graphique

```java
// Définir la première série pour afficher les valeurs
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

// Ajout de nouvelles séries
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Remplissage des données de la série
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Personnalisez les données du graphique en ajoutant des catégories et des séries, et en définissant leurs valeurs. Dans cet exemple, nous avons trois catégories et une série avec les points de données correspondants.

## Étape 7 : Personnaliser les secteurs du graphique à secteurs

```java
// Définir les couleurs des secteurs
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Personnaliser l'apparence de chaque secteur
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

Personnalisez l'apparence de chaque secteur du graphique à secteurs. Vous pouvez modifier les couleurs, les styles de bordure et d'autres propriétés visuelles.

## Étape 8 : Personnaliser les étiquettes de données

```java
// Personnaliser les étiquettes de données
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Personnalisez les étiquettes de données pour d’autres points de données de la même manière
```

Personnalisez les étiquettes de données pour chaque point du graphique à secteurs. Vous pouvez contrôler les valeurs affichées sur le graphique.

## Étape 9 : Afficher les lignes de repère

```java
// Afficher les lignes de repère pour le graphique
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Activez les lignes de repère pour connecter les étiquettes de données à leurs secteurs correspondants.

## Étape 10 : Définir l'angle de rotation du graphique à secteurs

```java
// Définir l'angle de rotation des secteurs du graphique à secteurs
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Définissez l'angle de rotation des secteurs du graphique à secteurs. Dans cet exemple, nous le définissons à 180 degrés.

## Étape 11 : Enregistrer la présentation

```java
// Enregistrez la présentation avec le graphique à secteurs
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Enregistrez la présentation avec le graphique à secteurs dans le répertoire spécifié.

## Code source complet pour les diapositives de diagramme à secteurs en Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
// Accéder à la première diapositive
ISlide slides = presentation.getSlides().get_Item(0);
// Ajouter un graphique avec des données par défaut
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Titre du tableau de réglage
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
// Ajout de nouvelles séries
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Les données de la série sont maintenant en cours de remplissage
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ne fonctionne pas dans la nouvelle version
// Ajout de nouveaux points et définition de la couleur du secteur
// série.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Définition de la bordure du secteur
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Définition de la bordure du secteur
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Définition de la bordure du secteur
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Créez des étiquettes personnalisées pour chacune des catégories pour les nouvelles séries
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
// Définition de l'angle de rotation des secteurs du graphique à secteurs
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Enregistrer la présentation avec le graphique
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Vous avez créé avec succès un graphique à secteurs dans une présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez personnaliser l'apparence et les libellés des données du graphique selon vos besoins. Ce tutoriel fournit un exemple de base, et vous pouvez améliorer et personnaliser vos graphiques selon vos besoins.

## FAQ

### Comment puis-je modifier les couleurs des secteurs individuels dans le graphique à secteurs ?

Pour modifier la couleur des secteurs individuels du graphique à secteurs, vous pouvez personnaliser la couleur de remplissage de chaque point de données. Dans l'exemple de code fourni, nous avons montré comment définir la couleur de remplissage de chaque secteur à l'aide de l'option `getSolidFillColor().setColor()` méthode. Vous pouvez modifier les valeurs de couleur pour obtenir l'apparence souhaitée.

### Puis-je ajouter plus de catégories et de séries de données au graphique à secteurs ?

Oui, vous pouvez ajouter des catégories et des séries de données supplémentaires au graphique à secteurs. Pour ce faire, utilisez l'outil `getChartData().getCategories().add()` et `getChartData().getSeries().add()` Méthodes, comme illustré dans l'exemple. Fournissez simplement les données et les libellés appropriés pour les nouvelles catégories et séries afin de développer votre graphique.

### Comment personnaliser l’apparence des étiquettes de données ?

Vous pouvez personnaliser l’apparence des étiquettes de données à l’aide de l’ `getDataLabelFormat()` sur l'étiquette de chaque point de données. Dans cet exemple, nous avons montré comment afficher la valeur sur les étiquettes de données à l'aide de `getDataLabelFormat().setShowValue(true)`Vous pouvez personnaliser davantage les étiquettes de données en contrôlant les valeurs affichées, en affichant les clés de légende et en ajustant d'autres options de formatage.

### Puis-je changer le titre du graphique à secteurs ?

Oui, vous pouvez modifier le titre du graphique à secteurs. Dans le code fourni, nous définissons le titre du graphique avec `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Vous pouvez remplacer `"Sample Title"` avec le texte du titre souhaité.

### Comment enregistrer la présentation générée avec le graphique à secteurs ?

Pour enregistrer la présentation avec le graphique à secteurs, utilisez le `presentation.save()` Méthode. Indiquez le chemin et le nom du fichier souhaités, ainsi que le format d'enregistrement de la présentation. Par exemple :
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Assurez-vous de spécifier le chemin de fichier et le format corrects.

### Puis-je créer d’autres types de graphiques à l’aide d’Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java prend en charge différents types de graphiques, notamment les graphiques à barres, les graphiques linéaires, etc. Vous pouvez créer différents types de graphiques en modifiant le `ChartType` lors de l'ajout d'un graphique. Consultez la documentation d'Aspose.Slides pour plus de détails sur la création de différents types de graphiques.

### Comment puis-je trouver plus d’informations et d’exemples pour travailler avec Aspose.Slides pour Java ?

Pour plus d'informations, une documentation détaillée et des exemples supplémentaires, vous pouvez visiter le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/)Il fournit des ressources complètes pour vous aider à utiliser la bibliothèque efficacement.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
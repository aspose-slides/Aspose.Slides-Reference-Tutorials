---
"description": "Optimisez vos diapositives Java avec des options de marqueurs de graphique personnalisés. Apprenez à améliorer visuellement vos points de données avec Aspose.Slides pour Java. Découvrez des instructions étape par étape et une FAQ."
"linktitle": "Options de marqueur de graphique sur les points de données dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Options de marqueur de graphique sur les points de données dans les diapositives Java"
"url": "/fr/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Options de marqueur de graphique sur les points de données dans les diapositives Java


## Introduction aux options de marqueur de graphique sur les points de données dans les diapositives Java

Pour créer des présentations percutantes, la possibilité de personnaliser et de manipuler les marqueurs de graphique sur les points de données peut faire toute la différence. Avec Aspose.Slides pour Java, vous avez la possibilité de transformer vos graphiques en éléments dynamiques et visuellement attrayants.

## Prérequis

Avant de nous plonger dans la partie codage, assurez-vous que vous disposez des prérequis suivants :

- Environnement de développement Java
- Bibliothèque Aspose.Slides pour Java
- Un environnement de développement intégré Java (IDE)
- Exemple de document de présentation (par exemple, « Test.pptx »)

## Étape 1 : Configuration de l'environnement

Tout d'abord, assurez-vous que les outils nécessaires sont installés et prêts. Créez un projet Java dans votre IDE et importez la bibliothèque Aspose.Slides pour Java.

## Étape 2 : Chargement de la présentation

Pour commencer, chargez votre exemple de présentation. Dans le code fourni, nous supposons que le document s'appelle « Test.pptx ».

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Étape 3 : Création d'un graphique

Créons maintenant un graphique dans la présentation. Dans cet exemple, nous utiliserons un graphique linéaire avec marqueurs.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Étape 4 : Travailler avec les données du graphique

Pour manipuler les données du graphique, nous devons accéder au classeur de données du graphique et préparer les séries de données. Nous allons effacer les séries par défaut et ajouter nos données personnalisées.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Étape 5 : Ajout de marqueurs personnalisés

Voici la partie intéressante : la personnalisation des marqueurs sur les points de données. Dans cet exemple, nous utiliserons des images comme marqueurs.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Ajout de marqueurs personnalisés aux points de données
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Répétez l’opération pour d’autres points de données
// ...

// Modification de la taille du marqueur de la série de graphiques
series.getMarker().setSize(15);
```

## Étape 6 : Enregistrer la présentation

Une fois que vous avez personnalisé vos marqueurs de graphique, enregistrez la présentation pour voir les modifications en action.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Code source complet des options de marqueur de graphique sur les points de données dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Création du graphique par défaut
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Obtenir l'index de la feuille de calcul des données du graphique par défaut
int defaultWorksheetIndex = 0;
//Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Supprimer la série de démonstration
chart.getChartData().getSeries().clear();
//Ajouter une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Définir l'image
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Définir l'image
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Ajoutez un nouveau point (1:3) ici.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Modification du marqueur de série de graphiques
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusion

Avec Aspose.Slides pour Java, vous pouvez améliorer vos présentations en personnalisant les marqueurs de graphique sur les points de données. Vous pouvez ainsi créer des diapositives visuellement percutantes et informatives qui captiveront votre public.

## FAQ

### Comment puis-je modifier la taille du marqueur pour les points de données ?

Pour modifier la taille du marqueur pour les points de données, utilisez le `series.getMarker().setSize()` méthode et fournir la taille souhaitée comme argument.

### Puis-je utiliser des images comme marqueurs personnalisés ?

Oui, vous pouvez utiliser des images comme marqueurs personnalisés pour les points de données. Définissez le type de remplissage sur `FillType.Picture` et fournissez l'image que vous souhaitez utiliser.

### Aspose.Slides pour Java est-il adapté à la création de graphiques dynamiques ?

Absolument ! Aspose.Slides pour Java offre de nombreuses fonctionnalités pour créer des graphiques dynamiques et interactifs dans vos présentations.

### Puis-je personnaliser d’autres aspects du graphique à l’aide d’Aspose.Slides ?

Oui, vous pouvez personnaliser divers aspects du graphique, notamment les titres, les axes, les étiquettes de données, etc., à l'aide d'Aspose.Slides pour Java.

### Où puis-je accéder à la documentation et aux téléchargements d'Aspose.Slides pour Java ?

Vous pouvez trouver la documentation sur [ici](https://reference.aspose.com/slides/java/) et téléchargez la bibliothèque sur [ici](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
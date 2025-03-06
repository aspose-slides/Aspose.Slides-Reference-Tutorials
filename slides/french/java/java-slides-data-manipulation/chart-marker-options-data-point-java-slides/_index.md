---
title: Options de marqueur de graphique sur le point de données dans les diapositives Java
linktitle: Options de marqueur de graphique sur le point de données dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Optimisez vos diapositives Java avec les options de marqueurs de graphique personnalisés. Apprenez à améliorer visuellement les points de données à l'aide d'Aspose.Slides pour Java. Découvrez les conseils étape par étape et les FAQ.
weight: 14
url: /fr/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Options de marqueur de graphique sur le point de données dans les diapositives Java


## Introduction aux options de marqueur de graphique sur les points de données dans les diapositives Java

Lorsqu'il s'agit de créer des présentations percutantes, la possibilité de personnaliser et de manipuler des marqueurs de graphique sur des points de données peut faire toute la différence. Avec Aspose.Slides pour Java, vous avez le pouvoir de transformer vos graphiques en éléments dynamiques et visuellement attrayants.

## Conditions préalables

Avant de plonger dans la partie codage, assurez-vous que les conditions préalables suivantes sont en place :

- Environnement de développement Java
- Aspose.Slides pour la bibliothèque Java
- Un environnement de développement intégré (IDE) Java
- Exemple de document de présentation (par exemple, "Test.pptx")

## Étape 1 : Configuration de l'environnement

Tout d’abord, assurez-vous que les outils nécessaires sont installés et prêts. Créez un projet Java dans votre IDE et importez la bibliothèque Aspose.Slides pour Java.

## Étape 2 : chargement de la présentation

Pour commencer, chargez votre exemple de document de présentation. Dans le code fourni, nous supposons que le document s'appelle "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Étape 3 : Création d'un graphique

Maintenant, créons un graphique dans la présentation. Nous utiliserons un graphique linéaire avec des marqueurs dans cet exemple.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Étape 4 : Travailler avec des données graphiques

Pour manipuler les données du graphique, nous devons accéder au classeur de données du graphique et préparer la série de données. Nous effacerons la série par défaut et ajouterons nos données personnalisées.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Étape 5 : Ajout de marqueurs personnalisés

Voici la partie passionnante : personnaliser les marqueurs sur les points de données. Nous utiliserons des images comme marqueurs dans cet exemple.

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

// Répétez l'opération pour d'autres points de données
// ...

// Modification de la taille du marqueur de série de graphiques
series.getMarker().setSize(15);
```

## Étape 6 : Sauvegarde de la présentation

Une fois que vous avez personnalisé vos marqueurs de graphique, enregistrez la présentation pour voir les modifications en action.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Code source complet pour les options de marqueur de graphique sur le point de données dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Création du graphique par défaut
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Obtention de l'index de la feuille de calcul des données graphiques par défaut
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
//Prendre la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Ajoutez-y un nouveau point (1:3).
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
//Changer le marqueur de série de graphiques
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusion

Avec Aspose.Slides pour Java, vous pouvez améliorer vos présentations en personnalisant les marqueurs de graphique sur les points de données. Cela vous permet de créer des diapositives visuellement époustouflantes et informatives qui captivent votre public.

## FAQ

### Comment puis-je modifier la taille du marqueur pour les points de données ?

 Pour modifier la taille du marqueur pour les points de données, utilisez le`series.getMarker().setSize()` et fournissez la taille souhaitée comme argument.

### Puis-je utiliser des images comme marqueurs personnalisés ?

 Oui, vous pouvez utiliser des images comme marqueurs personnalisés pour les points de données. Définissez le type de remplissage sur`FillType.Picture` et fournissez l’image que vous souhaitez utiliser.

### Aspose.Slides for Java est-il adapté à la création de graphiques dynamiques ?

Absolument! Aspose.Slides pour Java offre des fonctionnalités étendues pour créer des graphiques dynamiques et interactifs dans vos présentations.

### Puis-je personnaliser d’autres aspects du graphique à l’aide d’Aspose.Slides ?

Oui, vous pouvez personnaliser divers aspects du graphique, notamment les titres, les axes, les étiquettes de données, etc., à l'aide d'Aspose.Slides pour Java.

### Où puis-je accéder à la documentation et aux téléchargements d'Aspose.Slides pour Java ?

 Vous pouvez trouver la documentation sur[ici](https://reference.aspose.com/slides/java/) et téléchargez la bibliothèque sur[ici](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

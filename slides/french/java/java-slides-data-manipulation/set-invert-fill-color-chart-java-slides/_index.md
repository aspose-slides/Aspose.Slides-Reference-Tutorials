---
title: Définir le nuancier de couleurs de remplissage inversé dans les diapositives Java
linktitle: Définir le nuancier de couleurs de remplissage inversé dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des couleurs de remplissage inversées pour les graphiques Java Slides à l'aide d'Aspose.Slides. Améliorez vos visualisations de graphiques avec ce guide étape par étape et ce code source.
weight: 22
url: /fr/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir le nuancier de couleurs de remplissage inversé dans les diapositives Java


## Introduction à la définition du nuancier de couleurs de remplissage inversé dans les diapositives Java

Dans ce didacticiel, nous montrerons comment définir la couleur de remplissage inversée pour un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. L'inversion de la couleur de remplissage est une fonctionnalité utile lorsque vous souhaitez mettre en évidence des valeurs négatives dans un graphique avec une couleur spécifique. Nous fournirons des instructions étape par étape et le code source pour y parvenir.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Aspose.Slides pour la bibliothèque Java installée.
2. Environnement de développement Java mis en place.

## Étape 1 : Créer une présentation

Tout d’abord, nous devons créer une présentation à laquelle ajouter notre graphique. Vous pouvez utiliser le code suivant pour créer une présentation :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique

Ensuite, nous ajouterons un histogramme groupé à la présentation. Voici comment procéder :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Étape 3 : Configurer les données du graphique

Maintenant, configurons les données du graphique, y compris les séries et les catégories :

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Ajout de nouvelles séries et catégories
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Étape 4 : Remplir les données de la série

Maintenant, remplissons les données de série pour le graphique :

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Étape 5 : Définir la couleur de remplissage inversée

Pour définir la couleur de remplissage inversée de la série de graphiques, vous pouvez utiliser le code suivant :

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Dans le code ci-dessus, nous définissons la série pour inverser la couleur de remplissage pour les valeurs négatives et spécifions la couleur du remplissage inversé.

## Étape 6 : Enregistrez la présentation

Enfin, enregistrez la présentation avec le graphique :

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir le nuancier de remplissage inversé dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Ajout de nouvelles séries et catégories
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Prenez la première série de graphiques et remplissez les données de la série.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous vous avons montré comment définir la couleur de remplissage inversée pour un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Cette fonctionnalité vous permet de mettre en évidence les valeurs négatives dans vos graphiques avec une couleur spécifique, rendant ainsi vos données plus informatives visuellement.

## FAQ

Dans cette section, nous aborderons quelques questions courantes liées à la définition de la couleur de remplissage inversée pour un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java.

### Comment installer Aspose.Slides pour Java ?

 Vous pouvez installer Aspose.Slides pour Java en incluant les fichiers JAR Aspose.Slides dans votre projet Java. Vous pouvez télécharger la bibliothèque à partir du[Page de téléchargement d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/). Suivez les instructions d'installation fournies dans la documentation de votre environnement de développement spécifique.

### Puis-je personnaliser la couleur du remplissage inversé dans la série de graphiques ?

Oui, vous pouvez personnaliser la couleur du remplissage inversé dans la série de graphiques. Dans l'exemple de code fourni, le`series.getInvertedSolidFillColor().setColor(Color.RED)` La ligne définit la couleur sur rouge pour le remplissage inversé. Vous pouvez remplacer`Color.RED` avec toute autre couleur de votre choix.

### Comment puis-je modifier le type de graphique dans Aspose.Slides pour Java ?

 Vous pouvez modifier le type de graphique en changeant le`ChartType` paramètre lors de l’ajout d’un graphique à la présentation. Dans l'exemple de code, nous avons utilisé`ChartType.ClusteredColumn` . Vous pouvez explorer d'autres types de graphiques, tels que des graphiques linéaires, des graphiques à barres, des diagrammes circulaires, etc., en spécifiant le paramètre approprié.`ChartType` valeur enum.

### Comment ajouter plusieurs séries de données à un graphique ?

 Pour ajouter plusieurs séries de données à un graphique, vous pouvez utiliser l'outil`chart.getChartData().getSeries().add(...)` méthode pour chaque série que vous souhaitez ajouter. Assurez-vous de fournir les points de données et les étiquettes appropriés pour chaque série afin de remplir votre graphique avec plusieurs séries.

### Existe-t-il un moyen de personnaliser d’autres aspects de l’apparence du graphique ?

Oui, vous pouvez personnaliser divers aspects de l'apparence du graphique, notamment les étiquettes des axes, les titres, les légendes, etc. à l'aide d'Aspose.Slides pour Java. Reportez-vous à la documentation pour obtenir des conseils détaillés sur la personnalisation des éléments et de l'apparence du graphique.

### Puis-je enregistrer le graphique dans différents formats ?

 Oui, vous pouvez enregistrer le graphique dans différents formats à l'aide d'Aspose.Slides pour Java. Dans l'exemple de code fourni, nous avons enregistré la présentation sous forme de fichier PPTX. Vous pouvez utiliser différents`SaveFormat` options pour l'enregistrer dans d'autres formats comme PDF, PNG ou SVG, en fonction de vos besoins.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

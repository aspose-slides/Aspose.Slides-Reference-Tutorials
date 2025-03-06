---
title: Graphique en entonnoir dans les diapositives Java
linktitle: Graphique en entonnoir dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer des graphiques en entonnoir dans des présentations PowerPoint avec Aspose.Slides pour Java. Guide étape par étape avec code source pour une visualisation efficace des données.
weight: 18
url: /fr/java/chart-data-manipulation/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Graphique en entonnoir dans les diapositives Java


## Introduction à la création d'un graphique en entonnoir dans Aspose.Slides pour Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un graphique en entonnoir dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Les graphiques en entonnoir sont utiles pour visualiser des données qui se rétrécissent progressivement ou « entonnoirs » à travers différentes étapes ou catégories. Nous fournirons des instructions étape par étape ainsi que le code source pour vous aider à y parvenir.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée et configurée dans votre projet.
- Un fichier de présentation PowerPoint (PPTX) dans lequel vous souhaitez insérer le graphique en entonnoir.

## Étape 1 : Importer Aspose.Slides pour Java

Tout d’abord, vous devez importer la bibliothèque Aspose.Slides pour Java dans votre projet Java. Assurez-vous d'avoir ajouté les dépendances nécessaires à votre configuration de build.

```java
import com.aspose.slides.*;
```

## Étape 2 : initialiser la présentation et le graphique

Dans cette étape, nous initialisons une présentation et ajoutons un graphique en entonnoir à une diapositive.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    //Ajoutez un graphique en entonnoir à la première diapositive aux coordonnées (50, 50) et aux dimensions (500, 400).
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Étape 3 : Définir les données du graphique

Ensuite, nous définissons les données de notre graphique en entonnoir. Vous pouvez personnaliser les catégories et les points de données en fonction de vos besoins.

```java
// Effacez les données graphiques existantes.
wb.clear(0);

// Définissez des catégories pour le graphique.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Ajoutez des points de données pour la série Funnel Chart.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Étape 4 : Enregistrez la présentation

Enfin, nous enregistrons la présentation avec le Funnel Chart dans un fichier spécifié.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez réussi à créer un graphique en entonnoir à l'aide d'Aspose.Slides pour Java et à l'insérer dans une présentation PowerPoint.

## Code source complet pour le graphique en entonnoir dans les diapositives Java

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusion

Dans ce guide étape par étape, nous avons montré comment créer un graphique en entonnoir dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Les graphiques en entonnoir sont un outil précieux pour visualiser les données qui suivent un modèle de progression ou de rétrécissement, ce qui facilite la transmission efficace des informations. 

## FAQ

### Comment puis-je personnaliser l'apparence du graphique en entonnoir ?

Vous pouvez personnaliser l'apparence du graphique en entonnoir en modifiant diverses propriétés du graphique telles que les couleurs, les étiquettes et les styles. Reportez-vous à la documentation Aspose.Slides pour des informations détaillées sur les options de personnalisation des graphiques.

### Puis-je ajouter plus de points de données ou de catégories au graphique en entonnoir ?

Oui, vous pouvez ajouter des points de données et des catégories supplémentaires au graphique en entonnoir en étendant le code fourni à l'étape 3. Ajoutez simplement plus d'étiquettes de catégorie et de points de données si nécessaire.

### Comment puis-je modifier la position et la taille du graphique en entonnoir sur la diapositive ?

Vous pouvez ajuster la position et la taille du graphique en entonnoir en modifiant les coordonnées et les dimensions fournies lors de l'ajout du graphique à la diapositive à l'étape 2. Mettez à jour les valeurs (50, 50, 500, 400) en conséquence.

### Puis-je exporter le graphique vers différents formats, tels que PDF ou image ?

Oui, Aspose.Slides pour Java vous permet d'exporter la présentation avec le Funnel Chart vers différents formats, notamment PDF, formats d'image, etc. Vous pouvez utiliser le`SaveFormat` options pour spécifier le format de sortie souhaité lors de l’enregistrement de la présentation.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

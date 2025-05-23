---
"description": "Apprenez à créer des graphiques en entonnoir dans des présentations PowerPoint avec Aspose.Slides pour Java. Guide étape par étape avec code source pour une visualisation efficace des données."
"linktitle": "Diagramme en entonnoir dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diagramme en entonnoir dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramme en entonnoir dans les diapositives Java


## Introduction à la création d'un graphique en entonnoir dans Aspose.Slides pour Java

Dans ce tutoriel, nous vous guiderons dans la création d'un graphique en entonnoir dans une présentation PowerPoint avec Aspose.Slides pour Java. Les graphiques en entonnoir permettent de visualiser des données progressivement affinées, ou « entonnoirs », à travers différentes étapes ou catégories. Nous vous fournirons des instructions étape par étape ainsi que le code source pour vous aider à y parvenir.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée et configurée dans votre projet.
- Un fichier de présentation PowerPoint (PPTX) dans lequel vous souhaitez insérer le graphique en entonnoir.

## Étape 1 : Importer Aspose.Slides pour Java

Tout d'abord, vous devez importer la bibliothèque Aspose.Slides pour Java dans votre projet Java. Assurez-vous d'avoir ajouté les dépendances nécessaires à votre configuration de build.

```java
import com.aspose.slides.*;
```

## Étape 2 : Initialiser la présentation et le graphique

Dans cette étape, nous initialisons une présentation et ajoutons un graphique en entonnoir à une diapositive.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // Ajoutez un graphique en entonnoir à la première diapositive aux coordonnées (50, 50) avec les dimensions (500, 400).
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

Ensuite, nous définissons les données de notre graphique en entonnoir. Vous pouvez personnaliser les catégories et les points de données selon vos besoins.

```java
// Effacer les données du graphique existant.
wb.clear(0);

// Définir des catégories pour le graphique.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// Ajoutez des points de données pour la série de graphiques en entonnoir.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## Étape 4 : Enregistrer la présentation

Enfin, nous enregistrons la présentation avec le graphique en entonnoir dans un fichier spécifié.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez créé avec succès un graphique en entonnoir avec Aspose.Slides pour Java et l'avez inséré dans une présentation PowerPoint.

## Code source complet pour le graphique en entonnoir en Java (diapositives)

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

Dans ce guide étape par étape, nous vous expliquons comment créer un graphique en entonnoir dans une présentation PowerPoint avec Aspose.Slides pour Java. Les graphiques en entonnoir sont un outil précieux pour visualiser des données suivant une progression ou un rétrécissement, facilitant ainsi la transmission efficace de l'information. 

## FAQ

### Comment puis-je personnaliser l’apparence du graphique en entonnoir ?

Vous pouvez personnaliser l'apparence du graphique en entonnoir en modifiant diverses propriétés, telles que les couleurs, les libellés et les styles. Consultez la documentation d'Aspose.Slides pour plus d'informations sur les options de personnalisation des graphiques.

### Puis-je ajouter plus de points de données ou de catégories au graphique en entonnoir ?

Oui, vous pouvez ajouter des points de données et des catégories supplémentaires au graphique en entonnoir en étendant le code fourni à l'étape 3. Ajoutez simplement plus d'étiquettes de catégorie et de points de données selon vos besoins.

### Comment puis-je modifier la position et la taille du graphique en entonnoir sur la diapositive ?

Vous pouvez ajuster la position et la taille du graphique en entonnoir en modifiant les coordonnées et les dimensions fournies lors de l'ajout du graphique à la diapositive à l'étape 2. Mettez à jour les valeurs (50, 50, 500, 400) en conséquence.

### Puis-je exporter le graphique vers différents formats, tels que PDF ou image ?

Oui, Aspose.Slides pour Java vous permet d'exporter la présentation avec le graphique en entonnoir vers différents formats, notamment PDF, image, etc. Vous pouvez utiliser l'outil `SaveFormat` options permettant de spécifier le format de sortie souhaité lors de l'enregistrement de la présentation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
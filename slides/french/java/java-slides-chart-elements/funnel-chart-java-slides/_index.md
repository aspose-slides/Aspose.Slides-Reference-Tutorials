---
title: Graphique en entonnoir dans les diapositives Java
linktitle: Graphique en entonnoir dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Explorez Aspose.Slides pour Java avec des didacticiels étape par étape. Créez de superbes graphiques en entonnoir et bien plus encore.
weight: 14
url: /fr/java/chart-elements/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Graphique en entonnoir dans les diapositives Java


## Introduction au graphique en entonnoir dans les diapositives Java

Dans ce didacticiel, nous montrerons comment créer un graphique en entonnoir à l'aide d'Aspose.Slides pour Java. Les graphiques en entonnoir sont utiles pour visualiser un processus séquentiel avec des étapes qui se rétrécissent progressivement, telles que les conversions de ventes ou l'acquisition de clients.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides est ajoutée à votre projet Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : initialiser la présentation

Tout d’abord, initialisons une présentation et ajoutons-y une diapositive où nous placerons notre graphique en entonnoir.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel vers le répertoire de votre projet.

## Étape 2 : Créer le graphique en entonnoir

Créons maintenant le graphique en entonnoir et définissons ses dimensions sur la diapositive.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Dans le code ci-dessus, nous ajoutons un graphique en entonnoir à la première diapositive aux coordonnées (50, 50) avec une largeur de 500 et une hauteur de 400 pixels.

## Étape 3 : Définir les données du graphique

Ensuite, nous définirons les données de notre graphique en entonnoir. Nous définirons les catégories et les séries du graphique.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

Ici, nous effaçons toutes les données existantes, ajoutons des catégories (dans ce cas, les étapes de l'entonnoir) et définissons leurs étiquettes.

## Étape 4 : ajouter des points de données

Maintenant, ajoutons des points de données à notre série de graphiques en entonnoir.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

Dans cette étape, nous créons une série pour notre graphique en entonnoir et ajoutons des points de données représentant les valeurs à chaque étape de l'entonnoir.

## Étape 5 : Enregistrez la présentation

Enfin, nous enregistrons la présentation avec le graphique en entonnoir dans un fichier PowerPoint.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Assurez-vous de remplacer`"Your Document Directory"` avec l'emplacement de sauvegarde souhaité.

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

Dans ce didacticiel, nous vous avons montré comment créer un graphique en entonnoir dans Java Slides à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser davantage le graphique en ajustant les couleurs, les étiquettes et d'autres propriétés pour répondre à vos besoins spécifiques.

## FAQ

### Comment puis-je personnaliser l’apparence du graphique en entonnoir ?

Vous pouvez personnaliser l'apparence du graphique en entonnoir en modifiant les propriétés du graphique, des séries et des points de données. Reportez-vous à la documentation Aspose.Slides pour les options de personnalisation détaillées.

### Puis-je ajouter plus de catégories ou de points de données au graphique en entonnoir ?

Oui, vous pouvez ajouter plus de catégories et de points de données au graphique en entonnoir en étendant le code aux étapes 3 et 4 en conséquence.

### Est-il possible de changer le type de graphique en autre chose qu'un entonnoir ?

 Oui, Aspose.Slides prend en charge différents types de graphiques. Vous pouvez modifier le type de graphique en remplaçant`ChartType.Funnel` avec le type de graphique souhaité à l’étape 2.

### Comment gérer les erreurs ou les exceptions lorsque je travaille avec Aspose.Slides ?

Vous pouvez gérer les erreurs et les exceptions à l'aide des mécanismes de gestion des exceptions Java standard. Assurez-vous que votre code gère correctement les erreurs pour gérer les situations inattendues avec élégance.

### Où puis-je trouver plus d’exemples et de documentation pour Aspose.Slides pour Java ?

 Vous pouvez trouver plus d'exemples et une Documentation détaillée sur l'utilisation d'Aspose.Slides pour Java dans le[documentation](https://docs.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

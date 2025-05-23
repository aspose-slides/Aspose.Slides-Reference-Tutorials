---
"description": "Apprenez à définir un format de date pour l'axe des catégories dans un graphique PowerPoint avec Aspose.Slides pour Java. Guide étape par étape avec code source."
"linktitle": "Définition du format de date pour l'axe des catégories dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définition du format de date pour l'axe des catégories dans les diapositives Java"
"url": "/fr/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définition du format de date pour l'axe des catégories dans les diapositives Java


## Introduction à la définition du format de date pour l'axe des catégories dans les diapositives Java

Dans ce tutoriel, nous allons apprendre à définir un format de date pour l'axe des catégories d'un graphique PowerPoint à l'aide d'Aspose.Slides pour Java. Aspose.Slides pour Java est une bibliothèque puissante qui vous permet de créer, manipuler et gérer des présentations PowerPoint par programmation.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

1. Bibliothèque Aspose.Slides pour Java (vous pouvez la télécharger à partir de [ici](https://releases.aspose.com/slides/java/).
2. Configuration de l'environnement de développement Java.

## Étape 1 : Créer une présentation PowerPoint

Tout d'abord, nous devons créer une présentation PowerPoint dans laquelle nous ajouterons un graphique. Assurez-vous d'avoir importé les classes Aspose.Slides nécessaires.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique à la diapositive

Ajoutons maintenant un graphique à la diapositive PowerPoint. Dans cet exemple, nous utiliserons un graphique en aires.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Étape 3 : préparer les données du graphique

Nous allons configurer les données et les catégories du graphique. Dans cet exemple, nous utiliserons des catégories de dates.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Ajout de catégories de dates
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Ajout de séries de données
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Étape 4 : Personnaliser l’axe des catégories
Maintenant, personnalisons l'axe des catégories pour afficher les dates dans un format spécifique (par exemple, aaaa).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Étape 5 : Enregistrer la présentation
Enfin, enregistrez la présentation PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez défini avec succès un format de date pour l'axe des catégories dans un graphique PowerPoint avec Aspose.Slides pour Java.

## Code source complet pour définir le format de date de l'axe des catégories dans les diapositives Java

```java
	// Le chemin vers le répertoire des documents.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Conclusion

Vous avez personnalisé avec succès le format de date de l'axe des catégories dans un graphique Java Slides avec Aspose.Slides pour Java. Cela vous permet de présenter les valeurs de date au format souhaité sur vos graphiques. N'hésitez pas à explorer d'autres options de personnalisation en fonction de vos besoins spécifiques.

## FAQ

### Comment modifier le format de date pour l'axe des catégories ?

Pour modifier le format de date de l'axe des catégories, utilisez le `setNumberFormat` sur l'axe des catégories et indiquez le format de date souhaité, par exemple « aaaa-MM-jj » ou « MM/aaaa ». Assurez-vous de définir `setNumberFormatLinkedToSource(false)` pour remplacer le format par défaut.

### Puis-je utiliser différents formats de date pour différents graphiques dans la même présentation ?

Oui, vous pouvez définir différents formats de date pour les axes de catégories de différents graphiques au sein d'une même présentation. Personnalisez simplement l'axe de catégories de chaque graphique selon vos besoins.

### Comment ajouter plus de points de données au graphique ?

Pour ajouter plus de points de données au graphique, utilisez le `getDataPoints().addDataPointForLineSeries` méthode sur la série de données et fournir les valeurs des données.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
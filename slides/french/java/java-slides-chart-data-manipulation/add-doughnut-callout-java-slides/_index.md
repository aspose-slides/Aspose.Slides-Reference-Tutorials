---
"description": "Apprenez à ajouter des légendes en anneau dans vos diapositives Java avec Aspose.Slides pour Java. Guide étape par étape avec code source pour des présentations optimisées."
"linktitle": "Ajouter une légende en forme de beignet dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter une légende en forme de beignet dans les diapositives Java"
"url": "/fr/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une légende en forme de beignet dans les diapositives Java


## Introduction à l'ajout d'une légende en anneau dans les diapositives Java à l'aide d'Aspose.Slides pour Java

Dans ce tutoriel, nous vous expliquerons comment ajouter une légende en anneau à une diapositive en Java avec Aspose.Slides pour Java. Une légende en anneau est un élément de graphique permettant de mettre en évidence des points de données spécifiques dans un graphique en anneau. Nous vous fournirons des instructions étape par étape et le code source complet pour vous faciliter la tâche.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. Environnement de développement Java
2. Bibliothèque Aspose.Slides pour Java
3. Environnement de développement intégré (IDE) comme Eclipse ou IntelliJ IDEA
4. Une présentation PowerPoint dans laquelle vous souhaitez ajouter la légende en forme de beignet

## Étape 1 : Configurez votre projet Java

1. Créez un nouveau projet Java dans l’IDE de votre choix.
2. Ajoutez la bibliothèque Aspose.Slides pour Java à votre projet en tant que dépendance.

## Étape 2 : Initialiser la présentation

Pour commencer, vous devez initialiser une présentation PowerPoint et créer une diapositive dans laquelle vous souhaitez ajouter la légende en anneau. Voici le code pour y parvenir :

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Assurez-vous de remplacer `"Your Document Directory"` avec le chemin réel vers votre fichier de présentation PowerPoint.

## Étape 3 : Créer un graphique en anneau

Ensuite, vous allez créer un graphique en anneau sur la diapositive. Vous pouvez personnaliser sa position et sa taille selon vos besoins. Voici le code pour ajouter un graphique en anneau :

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Étape 4 : Personnaliser le graphique en anneau

Il est maintenant temps de personnaliser le graphique en anneau. Nous allons définir diverses propriétés, comme la suppression de la légende, la configuration de la taille des trous et l'ajustement de l'angle de la première tranche. Voici le code :

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Cet extrait de code définit les propriétés du graphique en anneau. Vous pouvez ajuster les valeurs selon vos besoins.

## Étape 5 : Ajouter des données au graphique en anneau

Ajoutons maintenant des données au graphique en anneau. Nous allons également personnaliser l'apparence des points de données. Voici le code pour y parvenir :

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Personnalisez l'apparence des points de données ici
        i++;
    }
    categoryIndex++;
}
```

Dans ce code, nous ajoutons des catégories et des points de données au graphique en anneau. Vous pouvez personnaliser l'apparence des points de données selon vos besoins.

## Étape 6 : Enregistrer la présentation

Enfin, n'oubliez pas d'enregistrer votre présentation après avoir ajouté la légende en anneau. Voici le code pour enregistrer la présentation :

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Assurez-vous de remplacer `"chart.pptx"` avec le nom de fichier souhaité.

Félicitations ! Vous avez ajouté avec succès une légende en anneau à une diapositive Java avec Aspose.Slides pour Java. Vous pouvez maintenant exécuter votre application Java pour générer la présentation PowerPoint avec le graphique en anneau et la légende.

## Code source complet pour l'ajout d'un anneau dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce tutoriel, nous avons abordé le processus d'ajout d'une légende en anneau à une diapositive Java avec Aspose.Slides pour Java. Vous avez appris à créer un graphique en anneau, à personnaliser son apparence et à ajouter des points de données. N'hésitez pas à enrichir vos présentations grâce à cette puissante bibliothèque et à explorer d'autres options de création de graphiques.

## FAQ

### Comment puis-je modifier l'apparence de la légende en forme de beignet ?

Vous pouvez personnaliser l'apparence de la légende en anneau en modifiant les propriétés des points de données du graphique. Le code fourni montre comment définir la couleur de remplissage, la couleur de trait, le style de police et d'autres attributs des points de données.

### Puis-je ajouter plus de points de données au graphique en anneau ?

Oui, vous pouvez ajouter autant de points de données que nécessaire au graphique en anneau. Il suffit d'étendre les boucles du code où sont ajoutées les catégories et les points de données, et de fournir les données et le formatage appropriés.

### Comment puis-je ajuster la position et la taille du graphique en anneau sur la diapositive ?

Vous pouvez modifier la position et la taille du graphique en anneau en modifiant les paramètres dans le `addChart` méthode. Les quatre nombres de cette méthode correspondent respectivement aux coordonnées X et Y du coin supérieur gauche du graphique et à sa largeur et sa hauteur.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
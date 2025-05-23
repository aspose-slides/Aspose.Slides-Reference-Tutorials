---
"description": "Apprenez à créer des graphiques époustouflants et à gérer les propriétés de vos diapositives Java avec Aspose.Slides. Guide étape par étape avec code source pour des présentations percutantes."
"linktitle": "Gérer les propriétés des graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Gérer les propriétés des graphiques dans les diapositives Java"
"url": "/fr/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les propriétés des graphiques dans les diapositives Java


## Introduction à la gestion des propriétés et des graphiques dans les diapositives Java avec Aspose.Slides

Dans ce tutoriel, nous découvrirons comment gérer les propriétés et créer des graphiques dans des diapositives Java avec Aspose.Slides. Aspose.Slides est une puissante API Java pour travailler avec des présentations PowerPoint. Nous vous expliquerons la procédure étape par étape, avec des exemples de code source.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Ajouter un graphique à une diapositive

Pour ajouter un graphique à une diapositive, suivez ces étapes :

1. Importez les classes nécessaires et créez une instance de la classe Présentation.

```java
// Créer une instance de la classe Presentation
Presentation presentation = new Presentation();
```

2. Accédez à la diapositive où vous souhaitez ajouter le graphique. Dans cet exemple, nous accédons à la première diapositive.

```java
// Accéder à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Ajoutez un graphique avec des données par défaut. Dans ce cas, nous ajoutons un graphique StackedColumn3D.

```java
// Ajouter un graphique avec des données par défaut
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Définition des données du graphique

Pour définir les données du graphique, nous devons créer un classeur de données et ajouter des séries et des catégories. Suivez ces étapes :

4. Définir l'index de la feuille de données du graphique.

```java
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
```

5. Obtenez le classeur de données graphiques.

```java
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Ajoutez des séries au graphique. Dans cet exemple, nous ajoutons deux séries nommées « Série 1 » et « Série 2 ».

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Ajoutez des catégories au graphique. Ici, nous ajoutons trois catégories.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Définition des propriétés de rotation 3D

Maintenant, définissons les propriétés de rotation 3D pour le graphique :

8. Définissez les axes d'angle droit.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Définissez les angles de rotation des axes X et Y. Dans cet exemple, nous faisons pivoter X de 40 degrés et Y de 270 degrés.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Définissez le pourcentage de profondeur sur 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Remplissage des données de la série

11. Prenez la deuxième série de graphiques et remplissez-la avec des points de données.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Remplir les données de la série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Réglage du chevauchement

12. Définissez la valeur de chevauchement des séries. Par exemple, vous pouvez la définir sur 100 pour aucun chevauchement.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Enregistrer la présentation

Enfin, enregistrez la présentation sur le disque.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez créé avec succès un graphique à colonnes empilées 3D avec des propriétés personnalisées à l'aide d'Aspose.Slides en Java.

## Code source complet pour gérer les propriétés des graphiques dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Presentation
Presentation presentation = new Presentation();
// Accéder à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
// Ajouter un graphique avec des données par défaut
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Ajouter une série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Ajouter des catégories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Définir les propriétés de Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Prendre la deuxième série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Les données de la série sont maintenant en cours de remplissage
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Définir la valeur de chevauchement
series.getParentSeriesGroup().setOverlap((byte) 100);
// Écrire la présentation sur le disque
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce tutoriel, nous avons abordé la gestion des propriétés et la création de graphiques dans des diapositives Java avec Aspose.Slides. Aspose.Slides est une API Java robuste qui permet aux développeurs de travailler efficacement avec des présentations PowerPoint. Nous avons abordé les étapes essentielles et fourni des exemples de code source pour vous guider tout au long du processus.

## FAQ

### Comment puis-je changer le type de graphique ?

Vous pouvez modifier le type de graphique en modifiant le `ChartType` Paramètre lors de l'ajout du graphique. Consultez la documentation d'Aspose.Slides pour connaître les types de graphiques disponibles.

### Puis-je personnaliser les couleurs du graphique ?

Oui, vous pouvez personnaliser les couleurs du graphique en définissant les propriétés de remplissage des points de données ou des catégories de la série.

### Comment ajouter plus de points de données à une série ?

Vous pouvez ajouter plus de points de données à une série en utilisant le `series.getDataPoints().addDataPointForBarSeries()` méthode et spécifiant la cellule contenant la valeur des données.

### Comment puis-je définir un angle de rotation différent ?

Pour définir un angle de rotation différent pour les axes X et Y, utilisez `chart.getRotation3D().setRotationX()` et `chart.getRotation3D().setRotationY()` avec les valeurs d'angle souhaitées.

### Quelles autres propriétés 3D puis-je personnaliser ?

Vous pouvez explorer d'autres propriétés 3D du graphique, telles que la profondeur, la perspective et l'éclairage, en vous référant à la documentation Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
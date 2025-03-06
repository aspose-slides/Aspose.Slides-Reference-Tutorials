---
title: Graphique existant dans les diapositives Java
linktitle: Graphique existant dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez vos présentations PowerPoint avec Aspose.Slides pour Java. Apprenez à modifier les graphiques existants par programmation. Guide étape par étape avec code source pour la personnalisation des graphiques.
weight: 12
url: /fr/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction au graphique existant dans Java Slides à l'aide d'Aspose.Slides pour Java

Dans ce didacticiel, nous montrerons comment modifier un graphique existant dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Nous passerons en revue les étapes permettant de modifier les données du graphique, les noms de catégories, les noms de séries et d'ajouter une nouvelle série au graphique. Assurez-vous que Aspose.Slides pour Java est configuré dans votre projet.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Bibliothèque Aspose.Slides pour Java incluse dans votre projet.
2. Une présentation PowerPoint existante avec un graphique que vous souhaitez modifier.
3. Environnement de développement Java mis en place.

## Étape 1 : Charger la présentation

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Étape 2 : accéder à la diapositive et au graphique

```java
// Accédez à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);

// Accédez au graphique sur la diapositive
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Étape 3 : Modifier les données du graphique et les noms de catégories

```java
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;

// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Modifier les noms des catégories de graphiques
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Étape 4 : Mettre à jour la première série de graphiques

```java
// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Mettre à jour le nom de la série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Mettre à jour les données de la série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Étape 5 : Mettre à jour la deuxième série de graphiques

```java
// Prenez la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);

// Mettre à jour le nom de la série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Mettre à jour les données de la série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Étape 6 : ajouter une nouvelle série au graphique

```java
// Ajouter une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Prenez la troisième série de graphiques
series = chart.getChartData().getSeries().get_Item(2);

// Remplir les données de la série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Étape 7 : Modifier le type de graphique

```java
//Changez le type de graphique en Cylindre clusterisé
chart.setType(ChartType.ClusteredCylinder);
```

## Étape 8 : Enregistrez la présentation modifiée

```java
// Enregistrez la présentation avec le graphique modifié
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Toutes nos félicitations! Vous avez modifié avec succès un graphique existant dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez désormais utiliser ce code pour personnaliser par programme les graphiques de vos présentations PowerPoint.

## Code source complet pour le graphique existant dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Classe de présentation instanciée qui représente le fichier PPTX // Classe de présentation instanciée qui représente le fichier PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Accéder au premier slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Ajouter un graphique avec les données par défaut
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Modification du nom de la catégorie du graphique
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Prendre la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Mise à jour actuelle des données de série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modification du nom de la série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Prendre la deuxième série de graphiques
series = chart.getChartData().getSeries().get_Item(1);
// Mise à jour actuelle des données de série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modification du nom de la série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Maintenant, ajout d'une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Prenez la 3ème série de graphiques
series = chart.getChartData().getSeries().get_Item(2);
// Remplir maintenant les données de série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Enregistrer la présentation avec le graphique
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusion

Dans ce didacticiel complet, nous avons appris à modifier un graphique existant dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant le guide étape par étape et en utilisant des exemples de code source, vous pouvez facilement personnaliser et mettre à jour les graphiques pour répondre à vos besoins spécifiques. Voici un récapitulatif de ce que nous avons couvert :

## FAQ

### Comment puis-je changer le type de graphique ?

 Vous pouvez modifier le type de graphique en utilisant le`chart.setType(ChartType.ChartTypeHere)` méthode. Remplacer`ChartTypeHere` avec le type de graphique souhaité, tel que`ChartType.ClusteredCylinder` dans notre exemple.

### Puis-je ajouter plus de points de données à une série ?

 Oui, vous pouvez ajouter plus de points de données à une série à l'aide de l'outil`series.getDataPoints().addDataPointForBarSeries(cell)` méthode. Assurez-vous de fournir les données de cellule appropriées.

### Comment mettre à jour les noms des catégories ?

 Vous pouvez mettre à jour les noms de catégories en utilisant`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pour définir les nouveaux noms de catégories.

### Comment modifier les noms de séries ?

 Pour modifier les noms de séries, utilisez`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pour définir les nouveaux noms de séries.

### Existe-t-il un moyen de supprimer une série du graphique ?

 Oui, vous pouvez supprimer une série du graphique en utilisant le`chart.getChartData().getSeries().removeAt(index)` méthode, où`index`est l'index de la série que vous souhaitez supprimer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

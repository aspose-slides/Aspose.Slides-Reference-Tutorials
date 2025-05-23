---
"description": "Améliorez vos présentations PowerPoint avec Aspose.Slides pour Java. Apprenez à modifier vos graphiques existants par programmation. Guide étape par étape avec code source pour la personnalisation de vos graphiques."
"linktitle": "Graphique existant dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Graphique existant dans les diapositives Java"
"url": "/fr/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Graphique existant dans les diapositives Java


## Introduction aux diapositives de diagrammes existants dans Java avec Aspose.Slides pour Java

Dans ce tutoriel, nous vous montrerons comment modifier un graphique existant dans une présentation PowerPoint avec Aspose.Slides pour Java. Nous détaillerons les étapes à suivre pour modifier les données du graphique, les noms de catégories et de séries, ainsi que pour ajouter une nouvelle série au graphique. Assurez-vous d'avoir configuré Aspose.Slides pour Java dans votre projet.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :

1. Bibliothèque Aspose.Slides pour Java incluse dans votre projet.
2. Une présentation PowerPoint existante avec un graphique que vous souhaitez modifier.
3. Configuration de l'environnement de développement Java.

## Étape 1 : Charger la présentation

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Instancier la classe de présentation qui représente le fichier PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Étape 2 : Accéder à la diapositive et au graphique

```java
// Accéder à la première diapositive
ISlide sld = pres.getSlides().get_Item(0);

// Accéder au graphique sur la diapositive
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Étape 3 : Modifier les données du graphique et les noms des catégories

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

## Étape 6 : Ajouter une nouvelle série au graphique

```java
// Ajout d'une nouvelle série
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
// Changer le type de graphique en Cylindre groupé
chart.setType(ChartType.ClusteredCylinder);
```

## Étape 8 : Enregistrer la présentation modifiée

```java
// Enregistrer la présentation avec le graphique modifié
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Félicitations ! Vous avez réussi à modifier un graphique existant dans une présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez désormais utiliser ce code pour personnaliser les graphiques de vos présentations PowerPoint par programmation.

## Code source complet du graphique existant dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Instanciez la classe Presentation qui représente le fichier PPTX // Instanciez la classe Presentation qui représente le fichier PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Accéder au premier slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Ajouter un graphique avec des données par défaut
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Définition de l'index de la feuille de données du graphique
int defaultWorksheetIndex = 0;
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Modification du nom de la catégorie du graphique
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Prenez la première série de graphiques
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Mise à jour des données de la série en cours
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Modification du nom de la série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Série de graphiques Take Second
series = chart.getChartData().getSeries().get_Item(1);
// Mise à jour des données de la série en cours
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Modification du nom de la série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Maintenant, ajout d'une nouvelle série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Prenez la 3ème série de graphiques
series = chart.getChartData().getSeries().get_Item(2);
// Les données de la série sont maintenant en cours de remplissage
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Enregistrer la présentation avec le graphique
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Conclusion

Dans ce tutoriel complet, nous avons appris à modifier un graphique existant dans une présentation PowerPoint avec Aspose.Slides pour Java. En suivant le guide étape par étape et en utilisant des exemples de code source, vous pouvez facilement personnaliser et mettre à jour vos graphiques pour répondre à vos besoins spécifiques. Voici un récapitulatif des points abordés :

## FAQ

### Comment puis-je changer le type de graphique ?

Vous pouvez modifier le type de graphique en utilisant le `chart.setType(ChartType.ChartTypeHere)` méthode. Remplacer `ChartTypeHere` avec le type de graphique souhaité, tel que `ChartType.ClusteredCylinder` dans notre exemple.

### Puis-je ajouter plus de points de données à une série ?

Oui, vous pouvez ajouter plus de points de données à une série en utilisant le `series.getDataPoints().addDataPointForBarSeries(cell)` méthode. Assurez-vous de fournir les données de cellule appropriées.

### Comment mettre à jour les noms des catégories ?

Vous pouvez mettre à jour les noms de catégories en utilisant `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pour définir les nouveaux noms de catégories.

### Comment modifier les noms des séries ?

Pour modifier les noms des séries, utilisez `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pour définir les nouveaux noms de séries.

### Existe-t-il un moyen de supprimer une série du graphique ?

Oui, vous pouvez supprimer une série du graphique en utilisant le `chart.getChartData().getSeries().removeAt(index)` méthode, où `index` est l'index de la série que vous souhaitez supprimer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
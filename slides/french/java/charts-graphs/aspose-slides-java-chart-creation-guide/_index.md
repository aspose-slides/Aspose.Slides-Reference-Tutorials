---
date: '2026-06-03'
description: Apprenez comment créer un graphique à colonnes groupées en Java en utilisant
  Aspose.Slides. Ce guide couvre la dépendance Maven, les étapes de création du graphique
  et la gestion des données.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Créer un graphique à colonnes groupées en Java avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un graphique à colonnes groupées en Java avec Aspose.Slides

## Comment créer un graphique en Java : Introduction
Créer des présentations dynamiques implique souvent de visualiser des données à l’aide de graphiques. Avec **Aspose.Slides for Java**, vous pouvez facilement **créer des graphiques à colonnes groupées** , améliorer la clarté et avoir un impact plus fort sur votre public. Ce tutoriel vous guide à travers la configuration de la bibliothèque, l’ajout d’un graphique à colonnes groupées, la gestion des séries et l’inversion conditionnelle des points de données négatifs.

**Ce que vous apprendrez**
- Comment configurer Aspose.Slides pour Java.
- Étapes pour **créer un graphique à colonnes groupées** dans votre présentation.
- Techniques pour gérer les séries du graphique et les points de données.
- Méthodes pour inverser conditionnellement les points de données négatifs afin d’améliorer la visualisation.
- Comment enregistrer la présentation en toute sécurité.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Slides for Java.  
- **Quel type de graphique est démontré ?** Graphique à colonnes groupées.  
- **Puis‑je inverser les valeurs négatives ?** Oui, en utilisant `invertIfNegative`.  
- **Quelle version de Java est requise ?** JDK 16 ou ultérieure.  
- **Une licence est‑elle nécessaire pour la production ?** Oui, une licence Aspose valide.

## Qu’est‑ce qu’un graphique à colonnes groupées ?
Un graphique à colonnes groupées est une représentation visuelle qui place plusieurs séries de données côte à côte pour chaque catégorie, permettant une comparaison rapide entre les groupes. Il est parfait pour les rapports financiers, les tableaux de bord de ventes et tout scénario où vous devez contraster plusieurs indicateurs simultanément.

## Pourquoi utiliser Aspose.Slides pour la création de graphiques ?
Aspose.Slides vous permet de générer et de personnaliser entièrement les graphiques par programme, éliminant ainsi le besoin d’éditer manuellement PowerPoint. Il prend en charge **plus de 70 formats d’entrée et de sortie** et peut traiter des présentations contenant **jusqu’à 10 000 diapositives** sans charger le fichier complet en mémoire, garantissant des performances élevées pour les rapports à grande échelle.

## Prérequis
1. **Bibliothèques requises**  
   - Aspose.Slides for Java (version 25.4 ou ultérieure).  

2. **Environnement**  
   - JDK 16 ou plus récent.  
   - Maven ou Gradle pour la gestion des dépendances.  

3. **Connaissances**  
   - Programmation Java de base.  
   - Familiarité avec les outils de construction (Maven/Gradle).  

## Configuration d’Aspose.Slides pour Java
### Installation avec Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installation avec Gradle
Ajoutez la ligne suivante à votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Alternativement, téléchargez la dernière version depuis [versions d’Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Obtention de licence
- **Essai gratuit :** Explorez les fonctionnalités sans licence.  
- **Licence temporaire :** Utilisez‑la pendant l’évaluation.  
- **Licence complète :** Achetez‑la pour les déploiements en production.

### Initialisation de base
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Comment ajouter un graphique à colonnes groupées à une diapositive ?
`Presentation` est la classe principale représentant un fichier PowerPoint. Chargez une nouvelle `Presentation`, ajoutez une diapositive et appelez `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Cet appel unique crée un graphique à colonnes groupées pleinement fonctionnel positionné aux coordonnées spécifiées. Vous pouvez ensuite accéder à l’objet graphique pour modifier les séries, les points de données et les styles visuels.

## Guide étape par étape

### Étape 1 : Créer une présentation et ajouter un graphique à colonnes groupées
La classe `Presentation` représente un document PowerPoint et permet de créer des diapositives.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Étape 2 : Gérer les séries du graphique
Nous allons maintenant supprimer les séries par défaut, en ajouter une nouvelle et la remplir avec des valeurs à la fois positives et négatives.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Étape 3 : Inverser conditionnellement les points de données négatifs
La méthode `invertIfNegative` permet d’inverser les valeurs négatives dans une série de graphique.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Pièges courants et conseils
- **Vous avez oublié de libérer l’objet `Presentation` ?** Appelez toujours `dispose()` dans un bloc `finally` pour libérer les ressources natives.  
- **Les valeurs négatives ne s’affichent pas inversées ?** Assurez‑vous d’appeler `invertIfNegative(true)` **après** avoir ajouté le point de données.  
- **Problèmes de taille du graphique :** Les coordonnées (X, Y) et les dimensions (largeur, hauteur) sont en points ; ajustez‑les pour correspondre à la mise en page de votre diapositive.  

## Questions fréquemment posées

**Q :** Puis‑je créer d’autres types de graphiques avec la même approche ?  
**R :** Oui, remplacez simplement `ChartType.ClusteredColumn` par n’importe quelle autre valeur de l’énumération `ChartType` (par ex., `Line`, `Pie`).  

**Q :** Une licence est‑elle nécessaire pour les builds de développement ?  
**R :** Une licence temporaire ou d’évaluation est requise pour un accès complet aux fonctionnalités ; sinon, la bibliothèque fonctionne en mode essai avec des limitations de filigrane.  

**Q :** Comment exporter la présentation en PDF après avoir ajouté des graphiques ?  
`SaveFormat.Pdf` spécifie le PDF comme format de sortie pour l’enregistrement d’une présentation. Utilisez `pres.save("output.pdf", SaveFormat.Pdf);` après avoir terminé la manipulation du graphique.  

**Q :** Est‑il possible de styliser des colonnes individuelles (couleur, bordure) ?  
`IChartDataPoint` représente un point de données unique dans un graphique et permet le formatage. Chaque `IChartDataPoint` offre des options telles que `getFillFormat().setFillType(FillType.Solid)` et `getLineFormat()`.  

**Q :** Que faire si je dois mettre à jour les données du graphique après avoir enregistré la présentation ?  
**R :** Chargez à nouveau la présentation avec `new Presentation("file.pptx")`, modifiez les données du graphique et ré‑enregistrez.

---

**Dernière mise à jour :** 2026-06-03  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un graphique à colonnes empilées en Java avec Aspose.Slides – Guide complet](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Comment créer un graphique en Java avec Aspose.Slides – Maîtriser la création et la validation de graphiques](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Créer et formater des graphiques en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
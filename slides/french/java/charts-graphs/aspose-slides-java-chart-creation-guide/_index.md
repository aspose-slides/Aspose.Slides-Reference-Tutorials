---
date: '2026-01-14'
description: Apprenez à créer un diagramme à colonnes groupées en Java avec Aspose.Slides.
  Guide étape par étape couvrant la présentation vide, l’ajout du diagramme à la présentation
  et la gestion des séries.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Comment créer un graphique à colonnes groupées en Java avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la création de graphiques en Java avec Aspose.Slides

## Comment créer et gérer des graphiques avec Aspose.Slides pour Java

### Introduction
Créer des présentations dynamiques implique souvent de visualiser des données à l'aide de graphiques. Avec **Aspose.Slides for Java**, vous pouvez facilement **créer un graphique à colonnes groupées** et gérer divers types de graphiques, améliorant à la fois la clarté et l'impact. Ce tutoriel vous guidera à travers la création d'une présentation vide, l'ajout d'un graphique à colonnes groupées, la gestion des séries et la personnalisation de l'inversion des points de données — le tout avec Aspose.Slides for Java.

**Ce que vous apprendrez :**
- Comment configurer Aspose.Slides pour Java.
- Étapes pour **créer une présentation vide** et ajouter un graphique à la présentation.
- Techniques pour gérer efficacement les séries de graphiques et les points de données.
- Méthodes pour inverser conditionnellement les points de données négatifs afin d'améliorer la visualisation.
- Comment enregistrer la présentation en toute sécurité.

Plongeons dans les prérequis avant de commencer.

## Quick Answers
- **Quelle est la classe principale pour commencer ?** `Presentation` de `com.aspose.slides`.
- **Quel type de graphique crée un graphique à colonnes groupées ?** `ChartType.ClusteredColumn`.
- **Comment ajouter un graphique à une diapositive ?** Utilisez `addChart()` sur la collection de formes de la diapositive.
- **Pouvez‑vous inverser les valeurs négatives ?** Oui, avec `invertIfNegative(true)` sur un point de données.
- **Quelle version est requise ?** Aspose.Slides for Java 25.4 ou ultérieure.

## Qu'est‑ce qu'un graphique à colonnes groupées ?
Un graphique à colonnes groupées affiche plusieurs séries de données côte à côte pour chaque catégorie, ce qui le rend idéal pour comparer des valeurs entre différents groupes. Aspose.Slides vous permet de générer ce graphique de manière programmatique sans ouvrir PowerPoint.

## Pourquoi utiliser Aspose.Slides pour Java pour ajouter un graphique à une présentation ?
- **Contrôle complet** sur les données du graphique, son apparence et sa mise en page.
- **Aucune installation d'Office** requise sur le serveur.
- **Prend en charge tous les principaux types de graphiques**, y compris les graphiques à colonnes groupées.
- **Intégration facile** avec les builds Maven/Gradle.

## Prérequis
Avant de commencer, assurez‑vous d'avoir les éléments suivants :

1. **Bibliothèques requises :**
   - Aspose.Slides for Java (version 25.4 ou ultérieure).

2. **Exigences de configuration de l'environnement :**
   - Une version JDK compatible (par ex., JDK 16).
   - Maven ou Gradle installés si vous préférez la gestion des dépendances.

3. **Prérequis de connaissances :**
   - Compréhension de base de la programmation Java.
   - Familiarité avec la gestion des dépendances dans votre environnement de développement.

## Configuration d'Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, suivez ces étapes :

**Maven Installation:**  
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle Installation:**  
Ajoutez la ligne suivante à votre `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct:**  
Vous pouvez également télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtention de licence
- **Essai gratuit :** Vous pouvez commencer avec un essai gratuit pour explorer les fonctionnalités.  
- **Licence temporaire :** Obtenez une licence temporaire pour un accès complet pendant votre période d'évaluation.  
- **Achat :** Envisagez d'acheter si cela correspond à vos besoins à long terme.

### Initialisation de base
Voici le code minimal nécessaire pour créer une nouvelle instance de présentation :

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guide de mise en œuvre
Maintenant, décomposons chaque fonctionnalité en étapes gérables.

### Création d'une présentation avec un graphique à colonnes groupées
#### Vue d'ensemble
Cette section montre comment **créer une présentation vide**, ajouter un **graphique à colonnes groupées**, et le positionner sur la première diapositive.

**Étapes :**
1. **Initialiser l'objet Presentation** – créer une nouvelle `Presentation`.
2. **Ajouter un graphique à colonnes groupées** – appeler `addChart()` avec le type et les dimensions appropriés.

**Exemple de code :**
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

### Gestion des séries du graphique
#### Vue d'ensemble
Apprenez à effacer les séries par défaut, ajouter une nouvelle série et la remplir avec des valeurs positives et négatives.

**Étapes :**
1. **Effacer les séries existantes** – supprimer toutes les données pré‑remplies.
2. **Ajouter une nouvelle série** – utiliser la cellule du classeur comme nom de série.
3. **Insérer des points de données** – ajouter des valeurs, y compris négatives, pour illustrer l'inversion ultérieure.

**Exemple de code :**
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

### Inversion des points de données de la série selon des conditions
#### Vue d'ensemble
Par défaut, Aspose.Slides peut inverser les valeurs négatives. Vous pouvez contrôler ce comportement globalement et par point de données.

**Étapes :**
1. **Définir l'inversion globale** – désactiver l'inversion automatique pour toute la série.
2. **Appliquer l'inversion conditionnelle** – activer l'inversion uniquement pour des points négatifs spécifiques.

**Exemple de code :**
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

### Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| Le graphique apparaît vide | Assurez‑vous que l'index de la diapositive (`0`) existe et que les dimensions du graphique sont dans les limites de la diapositive. |
| Les valeurs négatives ne sont pas inversées | Vérifiez que `invertIfNegative(false)` est défini sur la série et `invertIfNegative(true)` sur le point de données spécifique. |
| Exception de licence | Appliquez une licence Aspose valide avant de créer l'objet `Presentation`. |

## Questions fréquentes

**Q : Puis‑je ajouter d'autres types de graphiques en plus des colonnes groupées ?**  
R : Oui, Aspose.Slides prend en charge les graphiques en ligne, en secteurs, en barres, en aires, et bien d'autres types.

**Q : Ai‑je besoin d'une licence pour le développement ?**  
R : Un essai gratuit suffit pour l'évaluation, mais une licence commerciale est requise pour une utilisation en production.

**Q : Comment exporter le graphique en tant qu'image ?**  
R : Utilisez `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` après le rendu.

**Q : Est‑il possible de styliser le graphique (couleurs, polices) ?**  
R : Absolument. Chaque `IChartSeries` et `IChartDataPoint` offre des propriétés de style.

**Q : Et si je veux ajouter un graphique à un fichier PPTX existant ?**  
R : Chargez le fichier avec `new Presentation("existing.pptx")`, puis ajoutez le graphique à la diapositive souhaitée.

## Conclusion
Dans ce tutoriel, vous avez appris comment **créer un graphique à colonnes groupées** en Java, gérer les séries et inverser conditionnellement les points de données négatifs à l'aide d'Aspose.Slides. Armé de ces techniques, vous pouvez créer des présentations percutantes et axées sur les données de manière programmatique.

**Étapes suivantes :**
- Expérimentez d'autres types de graphiques proposés par Aspose.Slides pour Java.  
- Explorez les options de style avancées comme les couleurs personnalisées, les étiquettes de données et le formatage des axes.  
- Intégrez la génération de graphiques dans vos pipelines de reporting ou d'analyse.

---

**Dernière mise à jour :** 2026-01-14  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
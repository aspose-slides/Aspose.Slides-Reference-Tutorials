---
date: '2026-02-12'
description: Apprenez à créer des graphiques et à les gérer avec Aspose.Slides pour
  Java. Ce tutoriel montre comment créer un graphique à colonnes groupées, gérer les
  séries de données et personnaliser la visualisation.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Comment créer un graphique en Java avec Aspose.Slides : guide complet'
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique en Java avec Aspose.Slides

## Comment créer un graphique en Java : Introduction
Créer des présentations dynamiques implique souvent de visualiser des données à l’aide de graphiques. Avec **Aspose.Slides for Java**, vous pouvez facilement **how to create chart** des objets, améliorer la clarté et avoir un impact plus fort sur votre public. Ce tutoriel vous guide à travers la configuration de la bibliothèque, l’ajout d’un **create clustered column chart**, la gestion des séries et l’inversion conditionnelle des points de données négatifs.

**Ce que vous apprendrez**
- Comment configurer Aspose.Slides for Java.
- Étapes pour **create clustered column chart** dans votre présentation.
- Techniques pour gérer les séries de graphiques et les points de données.
- Méthodes pour inverser conditionnellement les points de données négatifs afin d’améliorer la visualisation.
- Comment enregistrer la présentation en toute sécurité.

### Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Slides for Java.
- **Quel type de graphique est démontré ?** Clustered column chart.
- **Puis‑je inverser les valeurs négatives ?** Oui, en utilisant `invertIfNegative`.
- **Quelle version de Java est requise ?** JDK 16 ou ultérieure.
- **Une licence est‑elle nécessaire pour la production ?** Oui, une licence Aspose valide.

## Qu’est‑ce qu’un graphique à colonnes groupées ?
Un graphique à colonnes groupées affiche plusieurs séries de données côte à côte pour chaque catégorie, ce qui facilite la comparaison des valeurs entre les groupes. Il est idéal pour les rapports financiers, les tableaux de bord de ventes et tout scénario où vous devez comparer plusieurs indicateurs.

## Pourquoi utiliser Aspose.Slides pour la création de graphiques ?
- **Contrôle total** de l’apparence du graphique sans dépendre de l’interface PowerPoint.
- **Génération programmatique** permet des pipelines de reporting automatisés.
- **Support multiplateforme** garantit que votre code s’exécute sur tout système compatible Java.
- **API riche** pour une personnalisation fine (couleurs, libellés de données, inversion, etc.).

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
### Installation Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installation Gradle
Ajoutez la ligne suivante à votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence
- **Essai gratuit :** Explorez les fonctionnalités sans licence.
- **Licence temporaire :** Utilisez pendant l’évaluation.
- **Licence complète :** Achetez pour les déploiements en production.

### Initialisation de base
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guide étape par étape

### Étape 1 : Créer une présentation et ajouter un graphique à colonnes groupées
Dans cette étape, nous **how to create chart** des objets et plaçons un **create clustered column chart** sur la première diapositive.

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

### Étape 2 : Gérer les séries du graphique
Nous allons maintenant supprimer toute série par défaut, en ajouter une nouvelle et la remplir avec des valeurs positives et négatives.

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

### Étape 3 : Inverser conditionnellement les points de données négatifs
Par défaut, Aspose.Slides n’inverse pas les valeurs négatives. Nous activerons l’inversion uniquement pour les points qui en ont besoin.

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

### Pièges courants et conseils
- **Vous avez oublié de libérer l’objet `Presentation` ?** Appelez toujours `dispose()` dans un bloc `finally` pour libérer les ressources natives.
- **Les valeurs négatives ne s’affichent pas inversées ?** Assurez‑vous d’appeler `invertIfNegative(true)` **après** avoir ajouté le point de données.
- **Problèmes de taille du graphique :** Les coordonnées (X, Y) et les dimensions (largeur, hauteur) sont en points ; ajustez‑les pour correspondre à la mise en page de votre diapositive.

## Questions fréquemment posées

**Q : Puis‑je créer d’autres types de graphiques avec la même approche ?**  
**R :** Oui, remplacez simplement `ChartType.ClusteredColumn` par toute autre valeur d’énumération `ChartType` (par ex., `Line`, `Pie`).

**Q : Une licence est‑elle nécessaire pour les versions de développement ?**  
**R :** Une licence temporaire ou d’évaluation est requise pour un accès complet aux fonctionnalités ; sinon, la bibliothèque fonctionne en mode d’essai avec des limitations de filigrane.

**Q : Comment exporter la présentation en PDF après avoir ajouté des graphiques ?**  
**R :** Utilisez `pres.save("output.pdf", SaveFormat.Pdf);` après avoir terminé la manipulation du graphique.

**Q : Est‑il possible de styliser des colonnes individuelles (couleur, bordure) ?**  
**R :** Oui, chaque `IChartDataPoint` offre des options de formatage telles que `getFillFormat().setFillType(FillType.Solid)` et `getLineFormat()`.

**Q : Et si je dois mettre à jour les données du graphique après que la présentation a été enregistrée ?**  
**R :** Chargez à nouveau la présentation avec `new Presentation("file.pptx")`, modifiez les données du graphique, puis ré‑enregistrez.

---

**Dernière mise à jour :** 2026-02-12  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
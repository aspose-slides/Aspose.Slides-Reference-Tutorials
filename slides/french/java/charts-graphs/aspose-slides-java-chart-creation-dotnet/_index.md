---
date: '2026-06-03'
description: Apprenez à créer des graphiques dans des présentations .NET et à ajouter
  un graphique à une diapositive avec Aspose.Slides for Java. Suivez ce guide étape
  par étape pour la visualisation des données.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Créer des graphiques en .NET avec Aspose.Slides for Java
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques dans .NET avec Aspose.Slides pour Java

## Introduction
Créer des présentations percutantes implique souvent d’intégrer des représentations visuelles de données comme des graphiques afin d’améliorer la compréhension et l’engagement du public. **Si vous souhaitez créer des graphiques dans .NET**, Aspose.Slides pour Java vous offre une API puissante, indépendante du langage, qui fonctionne sans problème à l’intérieur des applications .NET. Dans ce tutoriel, vous apprendrez comment initialiser une présentation, ajouter divers types de graphiques, gérer le classeur de données du graphique et formater les données de séries — y compris la prise en charge des valeurs négatives. À la fin, vous serez capable de générer des graphiques dans des fichiers de présentation de façon programmatique et d’ajouter un graphique à une diapositive en quelques lignes de code seulement.

## Réponses rapides
- **Quel est l’objectif principal ?** Créer des graphiques dans des présentations .NET en utilisant Aspose.Slides pour Java.  
- **Quelle version de la bibliothèque est requise ?** Aspose.Slides pour Java 25.4 ou ultérieure.  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je utiliser Maven ou Gradle ?** Oui — les deux systèmes de construction sont pris en charge.  
- **Quels types de graphiques sont disponibles ?** Colonnes groupées, lignes, secteurs, barres, aires, et bien plus.

## Comment créer des graphiques dans des présentations .NET avec Aspose.Slides pour Java ?
La classe `Presentation` représente un fichier PowerPoint et fournit des méthodes pour manipuler ses diapositives. Chargez un nouvel objet `Presentation`, appelez `slides.addEmptySlide()` pour obtenir une diapositive, puis utilisez `slide.getShapes().addChart()` pour insérer le type de graphique souhaité aux coordonnées que vous spécifiez. Après l’ajout du graphique, remplissez son classeur de données avec des séries et des catégories, appliquez le formatage souhaité (par exemple les couleurs pour les valeurs négatives), puis enregistrez la présentation dans un fichier .pptx. Ce flux vous permet de **créer des graphiques dans .NET** avec un ensemble concis d’appels d’API.

## Qu’est‑ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une API multiplateforme qui permet aux développeurs de créer, modifier et rendre des fichiers PowerPoint sans Microsoft Office. Elle prend en charge **plus de 50 formats d’entrée et de sortie** et peut traiter des présentations contenant des milliers de diapositives tout en maintenant une utilisation mémoire inférieure à 200 Mo.

## Pourquoi utiliser Aspose.Slides pour Java dans un projet .NET ?
Aspose.Slides pour Java s’exécute sur la machine virtuelle Java et peut être appelé depuis .NET via un wrapper natif, offrant ainsi aux développeurs .NET un moteur de graphiques mature, un traitement haute performance de grands ensembles de données et une compatibilité totale avec le code Java existant sans réécriture de la logique.

## Prérequis
Avant de plonger dans la création de graphiques avec Aspose.Slides pour Java, voici ce dont vous avez besoin :

### Bibliothèques requises et versions
- **Aspose.Slides pour Java** : Version 25.4 ou ultérieure.

### Exigences de configuration de l’environnement
- Un environnement de développement prenant en charge les applications .NET.  
- Une compréhension de base des concepts de programmation Java.

### Prérequis de connaissances
- Familiarité avec la création de présentations dans le contexte d’une application .NET.  
- Compréhension des dépendances Java et de leur gestion (Maven/Gradle).

## Configuration d'Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, vous devez l’inclure comme dépendance dans votre projet. Voici comment procéder :

### Maven
Le fragment de dépendance Maven ajoute Aspose.Slides pour Java à votre projet.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez cette ligne dans votre fichier `build.gradle` pour récupérer la bibliothèque depuis Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d'obtention de licence
- **Essai gratuit** : Commencez avec une licence temporaire pour explorer les fonctionnalités.  
- **Achat** : Achetez une licence pour une utilisation en production sans restriction.

#### Initialisation et configuration de base
L'initialisation de `Slides` nécessite de définir la licence et de créer une instance `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Cette configuration garantit une gestion efficace des ressources.

## Guide de mise en œuvre
Nous vous guiderons pas à pas dans la mise en œuvre des fonctionnalités.

### Initialisation de la présentation
**Vue d'ensemble :**  
Créer une instance de présentation prépare le terrain pour toutes les opérations suivantes. Cette fonctionnalité montre comment démarrer de zéro avec Aspose.Slides.

#### Étape 1 : Importer les packages nécessaires
`Presentation` et les classes associées font partie de l’espace de noms `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Étape 2 : Créer un nouvel objet Presentation
Instanciez un objet `Presentation` et encapsulez‑le dans un bloc try‑with‑resources afin de garantir sa libération.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Cela assure que l’objet présentation est correctement libéré après utilisation, évitant ainsi les fuites de mémoire.*

### Ajout d'un graphique à la diapositive
**Vue d'ensemble :**  
Ajouter un graphique à votre diapositive peut rendre la visualisation des données plus efficace et engageante.

#### Étape 1 : Importer les packages nécessaires
La classe `Chart` représente une forme de graphique qui peut être placée sur une diapositive et personnalisée.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Étape 2 : Initialiser la présentation et ajouter le graphique
Créez une diapositive, puis appelez `addChart` avec `ChartType.ClusteredColumn` et les coordonnées ainsi que la taille souhaitées.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Ici, nous ajoutons un graphique à colonnes groupées à la première diapositive aux coordonnées et dimensions spécifiées.*

### Gestion du classeur de données du graphique
**Vue d'ensemble :**  
Gérer efficacement le classeur de données de votre graphique vous permet de manipuler les séries et les catégories sans effort.

#### Étape 1 : Importer les packages nécessaires
`IChartDataWorkbook` donne accès au classeur de type Excel sous‑jacent utilisé par les graphiques.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Étape 2 : Accéder et nettoyer le classeur de données
Récupérez le classeur depuis le graphique et effacez toutes les données existantes pour repartir à zéro.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Nettoyer le classeur est essentiel pour commencer avec une base propre lors de l’ajout de nouvelles séries et catégories.*

### Ajout de séries et de catégories au graphique
**Vue d'ensemble :**  
Cette fonctionnalité montre comment ajouter des points de données pertinents en gérant les séries et les catégories.

#### Étape 1 : Ajouter des séries et des catégories
Utilisez `chart.getChartData().getSeries().add()` et `chart.getChartData().getCategories().add()` pour définir la structure.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*L’ajout de séries et de catégories permet une présentation des données plus organisée.*

### Remplissage des données de séries et mise en forme
**Vue d'ensemble :**  
Alimentez votre graphique avec des points de données et formatez son apparence pour améliorer la lisibilité, notamment lorsqu’il s’agit de valeurs négatives.

#### Étape 1 : Remplir les données de séries
Attribuez des valeurs numériques à chaque cellule du classeur et appliquez un remplissage rouge pour les nombres négatifs.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Cette section montre comment remplir les données et appliquer un format de couleur pour une meilleure visualisation.*

## Problèmes courants et solutions
- **LicenseNotFoundException** – Vérifiez que le chemin du fichier de licence est correct et que le fichier est accessible à l’exécution.  
- **NullPointerException on chart data** – Nettoyez toujours le classeur avant d’ajouter de nouvelles séries afin d’éviter les données résiduelles.  
- **Chart not rendering in .NET** – Assurez‑vous d’utiliser la version compatible .NET du JAR Aspose.Slides et que le runtime Java est correctement configuré dans votre projet .NET.

## Questions fréquentes

**Q : Puis‑je générer un graphique dans des fichiers de présentation sans interface graphique ?**  
R : Oui, Aspose.Slides pour Java fonctionne entièrement en mode headless et s’exécute sur des serveurs sans aucun composant graphique.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : .NET Framework 4.5+, .NET Core 3.1+, .NET 5 et .NET 6 sont toutes prises en charge.

**Q : Combien de types de graphiques puis‑je ajouter ?**  
R : Plus de 20 types de graphiques sont disponibles, y compris les colonnes, lignes, secteurs, aires et graphiques radar.

**Q : Est‑il possible de styliser des points de données individuels ?**  
R : Absolument — vous pouvez définir les couleurs de remplissage, les bordures et les marqueurs pour chaque point de données via l’API `IDataPoint`.

**Q : Dois‑je convertir manuellement les objets Java en types .NET ?**  
R : Non, le wrapper .NET d’Aspose.Slides pour Java gère automatiquement la conversion des types.

---

**Dernière mise à jour :** 2026-06-03  
**Testé avec :** Aspose.Slides pour Java 25.4  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment intégrer des graphiques dans des présentations .NET avec Aspose.Slides pour une visualisation efficace des données](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Comment récupérer le type de source de données d’un graphique avec Aspose.Slides pour .NET - Graphiques & Diagrammes](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Maîtriser la création et la manipulation de séries de graphiques avec Aspose.Slides .NET pour une visualisation efficace des données](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
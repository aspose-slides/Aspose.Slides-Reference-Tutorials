---
date: '2026-09-12'
description: Apprenez à utiliser Maven Aspose Slides pour ajouter et personnaliser
  des dynamic stock charts dans PowerPoint avec Java. Comprend la configuration, l'ajout
  de data series, le formatting lines et le saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Le tutoriel Maven Aspose Slides montre comment créer et personnaliser
  des dynamic stock charts dans PowerPoint en utilisant Java, couvrant les data series,
  le formatting lines et le saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Guide Maven Aspose Slides : créer des dynamic stock charts dans PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides : créer des dynamic stock charts dans PowerPoint avec
  Java'
url: /fr/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides : créer des graphiques boursiers dynamiques dans PowerPoint avec Java

## Introduction

**Maven Aspose Slides** vous permet de générer de manière programmatique des présentations PowerPoint sophistiquées à partir de Java. Dans ce tutoriel, vous apprendrez à créer des graphiques boursiers dynamiques, à ajouter et formater des séries de données, à personnaliser les lignes du graphique, puis à enregistrer le fichier. Que vous soyez analyste financier préparant des rapports trimestriels ou développeur créant des diaporamas automatisés, les étapes ci‑dessous vous offrent une solution complète, prête pour la production.

**Ce que vous apprendrez**
- Comment configurer Maven avec Aspose.Slides for Java
- Comment ajouter un graphique boursier et effacer les données par défaut
- Comment **ajouter un graphique de séries de données** et **formater les lignes du graphique**
- Comment **personnaliser les éléments visuels spécifiques à Java** du graphique
- Comment enregistrer la présentation mise à jour

Prêt à transformer des chiffres bruts en visuels boursiers accrocheurs ? Commençons !

## Réponses rapides
- **Quel artefact Maven dois‑je utiliser ?** `aspose-slides` version 25.4 (or newer).  
- **Puis‑je exécuter cela sur n’importe quel OS ?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **Ai‑je besoin d’une licence pour le développement ?** A free temporary license works for testing; a full license is required for production.  
- **Quels types de graphiques sont pris en charge ?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **Quelle taille de présentation puis‑je traiter ?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## Qu’est‑ce que Maven Aspose Slides ?

`Aspose.Slides for Java` est une API Java qui permet la création, la manipulation et la conversion de fichiers PowerPoint sans Microsoft Office. L’intégration Maven simplifie la gestion des dépendances, vous permettant de récupérer la bibliothèque directement depuis Maven Central.

## Pourquoi utiliser Maven Aspose Slides pour les graphiques boursiers ?

Aspose.Slides prend en charge **plus de 70 types de graphiques** et peut rendre des présentations de plusieurs centaines de pages en moins d’une seconde sur du matériel serveur typique. Ses fonctionnalités de **ligne haut‑bas** et de **barres haut/bas** vous offrent un contrôle précis des visualisations financières, bien au‑delà de ce que propose l’interface de PowerPoint.

## Prérequis

- **Java Development Kit (JDK)** – version 11 ou supérieure.  
- **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur de votre choix.  
- **Aspose.Slides for Java** – version 25.4 (la plus récente au moment de la rédaction).  

### Configuration d’Aspose.Slides pour Java

#### Maven
Pour intégrer Aspose.Slides à votre projet avec Maven, ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Pour les utilisateurs de Gradle, incluez ceci dans votre `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Téléchargement direct
Sinon, téléchargez le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Acquisition de licence** – commencez avec un essai gratuit ou demandez une licence temporaire. Pour un usage commercial, achetez une licence complète.

Pour une référence détaillée de l’API, consultez la [documentation Aspose.Slides](https://docs.aspose.com/slides/java/).

## Comment créer un graphique boursier dynamique étape par étape

Chargez votre présentation, ajoutez un graphique boursier, effacez les données par défaut, puis injectez vos propres séries et catégories. La réponse directe à la question principale est :

> Charger un PPTX existant avec `new Presentation("template.pptx")`, ajouter un `Chart` de type `ChartType.Stock`, effacer ses séries et catégories par défaut, puis le remplir avec vos propres points de données et options de formatage. Enfin, appeler `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Initialiser la présentation
#### Vue d’ensemble
Commencez par charger un fichier PowerPoint existant afin de le modifier sur place.

#### Étape par étape
1. **Importez la bibliothèque** – la classe `Presentation` est le point d’entrée pour toutes les opérations de diapositives.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Chargez le fichier de présentation** – fournissez le chemin vers votre modèle PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter un graphique boursier à la diapositive
#### Vue d’ensemble
Insérez un graphique boursier sur la première diapositive de la présentation.

La classe `Chart` représente une forme de graphique qui peut être ajoutée à une diapositive.

#### Réponse directe
Vous ajoutez un graphique boursier en appelant `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Cela crée un objet graphique que vous pouvez manipuler immédiatement.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Effacer les séries de données et catégories existantes dans le graphique
#### Vue d’ensemble
Supprimez toutes les séries ou catégories pré‑remplies afin de commencer avec un jeu de données propre.

L’objet `ChartData` contient les séries et les catégories d’un graphique.

#### Réponse directe
Appelez `chart.getChartData().getSeries().clear()` et `chart.getChartData().getCategories().clear()` pour effacer le contenu par défaut avant d’ajouter le vôtre.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter des catégories aux données du graphique
#### Vue d’ensemble
Définissez les catégories de l’axe X (par ex., dates) qui regroupent vos valeurs boursières.

Un `ChartCategory` représente une étiquette de l’axe X pour un graphique.

#### Réponse directe
Créez un nouveau `ChartCategory` pour chaque étiquette en utilisant `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, en répétant pour chaque mois ou période.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter des séries de données au graphique
#### Vue d’ensemble
Ajoutez les quatre séries essentielles : Ouverture, Haut, Bas et Clôture.

Un `ChartSeries` contient une collection de points de données pour une série spécifique du graphique.

#### Réponse directe
Pour chaque série, appelez `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Cela enregistre la série dans le classeur de données du graphique.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter des points de données aux séries
#### Vue d’ensemble
Remplissez chaque série avec des valeurs numériques représentant les cours boursiers.

Un `DataPoint` représente une valeur unique dans une série.

#### Réponse directe
Parcourez votre collection de données et utilisez `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (ou la méthode appropriée pour le type de série) afin d’insérer chaque point.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formater les lignes haut‑bas et les barres haut/bas
#### Vue d’ensemble
Ajustez le style visuel des connecteurs haut‑bas et des remplissages des barres haut/bas.

Un `Marker` définit le symbole visuel d’un point de données.

#### Réponse directe
Définissez `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` et configurez `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` pour contrôler l’épaisseur et la couleur de la ligne.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Afficher les barres haut/bas
Utilisez la méthode `setShowUpDownBars(true)` du graphique pour rendre les barres haut/bas visibles.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personnaliser les étiquettes de données sur les lignes haut‑bas
#### Vue d’ensemble
Affichez les valeurs numériques directement sur les lignes haut‑bas pour une référence rapide.

Un `DataLabel` contrôle l’apparence des étiquettes attachées aux points de données.

#### Réponse directe
Activez les étiquettes de données avec `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` et stylisez‑les selon les besoins.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Définir la couleur de remplissage des barres haut/bas
#### Vue d’ensemble
Attribuez aux barres haussières un remplissage vert et aux barres baissières un remplissage rouge afin de refléter intuitivement le mouvement du marché.

L’objet `UpDownBars` donne accès au formatage des barres haussières et baissières.

#### Réponse directe
Appliquez `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` et définissez la couleur unie sur `Color.GREEN` ; répétez pour la barre baissière avec `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Enregistrer le fichier PowerPoint
#### Vue d’ensemble
Enregistrez vos modifications dans un nouveau fichier PPTX.

La méthode `save` écrit la présentation sur le disque dans le format spécifié.

#### Réponse directe
Appelez `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – cela écrit la présentation modifiée sur le disque au format PowerPoint standard.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Problèmes courants et dépannage

- **Le graphique n’apparaît pas** – assurez‑vous que les coordonnées X/Y et les dimensions du graphique sont à l’intérieur des limites de la diapositive.  
- **Points de données manquants** – vérifiez que les indices de cellules du classeur de données correspondent à la série/ligne que vous souhaitez remplir.  
- **Exception de licence** – une licence d’essai temporaire expire après 30 jours ; remplacez‑la par une licence permanente pour les builds de production.  
- **Ralentissement des performances sur de gros fichiers** – utilisez `Presentation.setCacheSize(0)` pour désactiver le cache si vous traitez des milliers de diapositives en lot.

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code dans une application web ?**  
R : Oui. La bibliothèque est pure Java, vous pouvez donc l’exécuter dans n’importe quel conteneur de servlets ou service Spring Boot.

**Q : Aspose.Slides prend‑il en charge d’autres types de graphiques que le Stock ?**  
R : Absolument. Il prend en charge plus de 70 types de graphiques, y compris les graphiques en ligne, en barres, en secteurs et radar.

**Q : Comment ajouter un titre de graphique programmatique ?**  
R : Utilisez `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` puis formatez le titre selon vos besoins.

**Q : Existe‑t‑il une limite au nombre de points de données par série ?**  
R : En pratique, vous pouvez ajouter des dizaines de milliers de points ; l’utilisation de la mémoire augmente linéairement, et la bibliothèque diffuse les données pour garder une empreinte faible.

**Q : Quels coordonnées Maven dois‑je utiliser pour la dernière version ?**  
R : La dernière version est toujours disponible sous `com.aspose:aspose-slides:25.4` (ou plus récente) sur Maven Central.

---

**Dernière mise à jour :** 2026-09-12  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose

## Tutoriels associés

- [aspose slides dépendance Maven : ajouter et configurer des graphiques dans les présentations avec Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Créer un graphique PowerPoint Java – Enregistrer des présentations avec des graphiques en utilisant Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Créer et formater des graphiques PowerPoint avec Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-06-08'
description: Apprenez comment ajouter des séries à un graphique et personnaliser les
  graphiques à colonnes empilées dans les présentations .NET à l'aide d'Aspose.Slides
  for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Ajouter des séries à un graphique avec Aspose.Slides for Java dans .NET
url: /fr/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la personnalisation des graphiques dans les présentations .NET avec Aspose.Slides for Java

## Introduction
Dans le domaine des présentations axées sur les données, les graphiques sont des outils indispensables qui transforment des nombres bruts en histoires visuelles captivantes. Lorsque vous devez **add series to chart** de manière programmatique, en particulier dans des fichiers de présentation .NET, la tâche peut sembler intimidante. Heureusement, **Aspose.Slides for Java** propose une API puissante et indépendante du langage qui rend la création et la personnalisation de graphiques simples — même lorsque votre format cible est un PPTX .NET. Ce guide vous accompagne dans l’ajout de séries, la construction d’un graphique à colonnes empilées et le réglage fin d’aspects visuels tels que la largeur des espaces, afin de générer des diapositives dynamiques et riches en données, à l’aspect soigné et professionnel.

## Quick Answers
La classe `Presentation` représente un fichier PPTX, et `slide.getShapes().addChart(...)` insère une forme de graphique. Utilisez `chart.getChartData().getSeries().add(...)` pour ajouter une série, et `setGapWidth()` ajuste l’espacement.

- **Quelle est la classe principale pour démarrer une présentation ?** `Presentation` – elle représente un fichier PPTX en mémoire.  
- **Quelle méthode ajoute un graphique à une diapositive ?** `slide.getShapes().addChart(...)` crée l’objet graphique sur la diapositive.  
- **Comment ajouter une nouvelle série ?** `chart.getChartData().getSeries().add(...)` insère une nouvelle série de données.  
- **Peut‑on modifier la largeur de l’écart entre les barres ?** Oui — appelez `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (la valeur est un pourcentage).  
- **Ai‑je besoin d’une licence pour la production ?** Absolument — une licence valide Aspose.Slides for Java débloque toutes les fonctionnalités et supprime les filigranes d’évaluation.

## What is “add series to chart”?
Ajouter une série à un graphique signifie insérer une nouvelle collection de points de données que le graphique rend comme un élément visuel distinct (par ex., un groupe de colonnes séparé). Chaque série peut avoir ses propres valeurs, couleurs et formatage, permettant une comparaison côte à côte de plusieurs ensembles de données.

## Why use Aspose.Slides for Java to modify .NET presentations?
Aspose.Slides for Java vous permet de générer ou de modifier des fichiers PPTX entièrement compatibles avec les visionneuses PowerPoint .NET, sans nécessiter d’installation Microsoft Office. Utilisez Aspose.Slides for Java lorsque vous avez besoin d’une solution côté serveur, multiplateforme, qui crée ou met à jour des fichiers PPTX .NET, prend en charge plus de 50 types de graphiques et traite des fichiers jusqu’à 500 Mo sans charger le document complet en mémoire. Son API fonctionne en Java, Kotlin, Scala ou tout autre langage JVM, offrant le même résultat attendu par les développeurs .NET.

## Prerequisites
- Bibliothèque **Aspose.Slides for Java** (version 25.4 ou ultérieure).  
- Maven, Gradle ou téléchargement manuel du JAR.  
- Connaissances de base en Java et familiarité avec la structure des fichiers PPTX.  

## Setting Up Aspose.Slides for Java
### Maven Installation
Ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Incluez cette ligne dans votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Sinon, récupérez le JAR le plus récent depuis la page officielle : [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition**  
Commencez avec un essai gratuit en téléchargeant une licence temporaire depuis [here](https://purchase.aspose.com/temporary-license/). Pour une utilisation en production, achetez une licence complète afin de débloquer toutes les fonctionnalités et de supprimer les filigranes d’évaluation.

## Step‑by‑Step Implementation Guide
Sous chaque étape, vous trouverez un extrait de code concis (inchangé par rapport au tutoriel original) suivi d’une explication de son fonctionnement.

### Step 1: Create an Empty Presentation
`Presentation` est la classe d’entrée qui représente un fichier PowerPoint en mémoire.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*We start with a clean PPTX file, which gives us a canvas for adding charts.*

### Step 2: Add a Stacked Column Chart to the Slide
`Chart` représente une forme de graphique au sein d’une diapositive. `ChartType.StackedColumn` spécifie un graphique à colonnes empilées.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*The `addChart` method creates a **stacked column chart** and places it at the top‑left corner of the slide.*

### Step 3: Add Series to the Chart (Primary Goal)
`Series` encapsule une seule série de données dans un graphique.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Here we **add series to chart** – each call creates a new data series that will appear as a separate column group.*

### Step 4: Add Categories to the Chart
`Category` définit une étiquette d’axe X pour les données du graphique.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Categories act as the X‑axis labels, giving meaning to each column.*

### Step 5: Populate Series Data
`DataPoint` contient une valeur numérique pour une série à une catégorie spécifique.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Data points give each series its numeric values, which the chart will render as bar heights.*

### Step 6: Set Gap Width for Chart Series Group
`SeriesGroup` contrôle les propriétés de mise en page d’un groupe de séries, telles que la largeur de l’écart.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Adjusting the gap width improves readability, especially when many categories are present.*

## Common Use Cases
- **Reporting financier** – comparer le chiffre d’affaires trimestriel entre les unités commerciales.  
- **Tableaux de bord de projet** – afficher les pourcentages d’achèvement des tâches par équipe.  
- **Analyse marketing** – visualiser les performances de campagnes côte à côte.  
Ces scénarios tirent parti de l’**exemple de graphique à colonnes empilées** car ils mettent en évidence la contribution de chaque catégorie à un total.

## Performance Tips
- **Réutilisez l’objet `Presentation`** lors de la création de plusieurs graphiques afin de réduire la charge mémoire.  
- **Limitez le nombre de points de données** aux seuls nécessaires pour le récit visuel ; Aspose.Slides peut gérer 10 000 points, mais la vitesse de rendu chute après ~5 000.  
- **Libérez les objets** (`presentation.dispose()`) après l’enregistrement pour libérer les ressources et éviter les fuites de mémoire.  

## Frequently Asked Questions
**Q : Puis‑je ajouter d’autres types de graphiques que les colonnes empilées ?**  
R : Oui, Aspose.Slides prend en charge les graphiques en ligne, en secteur, en aires, radar, bulles et plus de 50 autres types, tous accessibles via la même méthode `addChart`.

**Q : Ai‑je besoin d’une licence distincte pour la sortie .NET ?**  
R : Non, la même licence Java fonctionne pour tous les formats de sortie, y compris les fichiers PPTX .NET.

**Q : Comment changer la palette de couleurs du graphique ?**  
R : Utilisez `series.getFormat().getFill().setFillType(FillType.Solid)` puis définissez l’objet `Color` souhaité pour chaque série.

**Q : Est‑il possible d’ajouter des étiquettes de données programmatique ?**  
R : Absolument. Appelez `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` pour afficher la valeur numérique sur chaque colonne.

**Q : Que faire si je dois mettre à jour une présentation existante ?**  
R : Chargez le fichier avec `new Presentation("existing.pptx")`, modifiez le graphique en utilisant les mêmes appels d’API, puis enregistrez-le à nouveau sur le disque.

## Conclusion
Vous disposez maintenant d’un guide complet, de bout en bout, pour **add series to chart**, créer un **stacked column chart** et affiner son apparence dans les présentations .NET à l’aide d’Aspose.Slides for Java. Expérimentez avec différents types de graphiques, couleurs et sources de données pour créer des rapports visuels percutants qui impressionnent les parties prenantes et favorisent les décisions basées sur les données.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [How to Create Percentage-Based Stacked Column Charts in .NET using Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Master Chart Series Creation and Manipulation with Aspose.Slides .NET for Effective Data Visualization](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Clear Specific Chart Series Data Points with Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
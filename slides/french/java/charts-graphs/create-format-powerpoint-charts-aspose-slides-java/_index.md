---
date: '2026-03-15'
description: Apprenez à ajouter un graphique à colonnes groupées à une diapositive
  PowerPoint à l'aide d'Aspose.Slides pour Java, en couvrant les étapes pour ajouter
  le graphique à la diapositive et créer efficacement une diapositive PowerPoint en
  Java.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Ajouter un diagramme à colonnes groupées à PPT avec Aspose.Slides Java
url: /fr/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter un graphique à colonnes groupées à PPT avec Aspose.Slides Java

## Introduction
Dans ce guide, vous **ajouterez un graphique à colonnes groupées** à une présentation PowerPoint de manière programmatique avec Aspose.Slides for Java. Que vous créiez des rapports d'entreprise, des présentations éducatives ou des présentations marketing, l'automatisation de la création de graphiques fait gagner du temps et garantit la cohérence. Nous parcourrons la configuration de la bibliothèque, la création d'une diapositive, l'ajout du graphique, l'application de styles de ligne et de coins arrondis, et enfin l'enregistrement du fichier. À la fin, vous serez à l'aise avec le flux complet pour **ajouter un graphique à une diapositive** et même **create PowerPoint slide Java**‑based solutions.

### Quick Answers
- **Quelle est la classe principale pour commencer ?** `Presentation`
- **Quel type de graphique est utilisé ?** `ChartType.ClusteredColumn`
- **Comment activer les coins arrondis ?** `chart.setRoundedCorners(true);`
- **Quel format est recommandé pour l'enregistrement ?** `SaveFormat.Pptx`
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit fonctionne pour les tests ; une licence achetée est requise pour la production.

## Qu’est‑ce qu’un graphique à colonnes groupées ?
Un graphique à colonnes groupées regroupe plusieurs séries de données côte à côte pour chaque catégorie, ce qui le rend idéal pour comparer des valeurs entre différents groupes. Aspose.Slides vous permet de générer ce type de graphique entièrement en code sans ouvrir PowerPoint.

## Pourquoi utiliser Aspose.Slides for Java pour ajouter un graphique à colonnes groupées ?
- **Automatisation complète** – aucune interaction manuelle avec l'interface requise.  
- **Multiplateforme** – fonctionne sur tout OS supportant Java.  
- **Mise en forme riche** – contrôle des styles de ligne, remplissages, coins arrondis, etc.  
- **Pas de dépendances COM** – contrairement à Office Interop, il s'exécute en toute sécurité sur les serveurs.

## Prérequis
- **Aspose.Slides for Java** (v25.4 ou plus récent)  
- **JDK 16** (ou version ultérieure)  
- Un IDE tel qu'IntelliJ IDEA, Eclipse ou NetBeans  

## Installation d’Aspose.Slides for Java
Vous pouvez ajouter la bibliothèque via Maven, Gradle ou un téléchargement direct.

### Using Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Using Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Essai gratuit** – testez toutes les fonctionnalités sans limite de temps.  
- **Licence temporaire** – demandez‑en une sur le portail Aspose pour une évaluation complète.  
- **Achat** – obtenez une licence permanente pour la production.

## Implementation Guide

### Creating a Presentation and Adding a Slide
#### Overview
First, we create a new `Presentation` object and grab the default slide that ships with a fresh file.

#### Step‑by‑Step
**1. Initialize the Presentation Object**
```java
Presentation presentation = new Presentation();
```

**2. Access the First Slide**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Dispose of Resources**
```java
if (presentation != null) presentation.dispose();
```

### Adding a Chart to a Slide
#### Overview
Now we embed a **clustered column chart** into the slide we just prepared.

#### Step‑by‑Step
**1. Initialize the Presentation Object**
```java
Presentation presentation = new Presentation();
```

**2. Access the First Slide**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Add a Clustered Column Chart**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Dispose of Resources**
```java
if (presentation != null) presentation.dispose();
```

### Formatting Chart Line Style and Setting Rounded Corners
#### Overview
Enhance the visual appeal by applying a solid line fill, a single line style, and rounded corners.

#### Step‑by‑Step
**1. Initialize the Presentation Object**
```java
Presentation presentation = new Presentation();
```

**2. Access the First Slide**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Add a Clustered Column Chart**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Set Line Format to Solid Fill Type**
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Apply Single Line Style**
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Enable Rounded Corners for Chart Area**
```java
chart.setRoundedCorners(true);
```

**7. Dispose of Resources**
```java
if (presentation != null) presentation.dispose();
```

### Saving a Presentation
#### Overview
Finally, we write the presentation to disk in PPTX format.

#### Step‑by‑Step
**1. Initialize the Presentation Object**
```java
Presentation presentation = new Presentation();
```

**2. Define Output Directory and File Name**
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Save the Presentation in PPTX Format**
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Dispose of Resources**
```java
if (presentation != null) presentation.dispose();
```

## Practical Applications
- **Rapports d'entreprise** – automatisez les présentations financières trimestrielles avec des graphiques dynamiques.  
- **Contenu éducatif** – générez des diapositives de cours qui récupèrent les données d'une base de données.  
- **Présentations marketing** – visualisez les tendances produit avec des graphiques soignés.

## Performance Considerations
- **Gestion des ressources** – appelez toujours `dispose()` ou utilisez try‑with‑resources.  
- **Optimisation de la mémoire** – traitez les grands ensembles de données par lots plus petits.  
- **Bonnes pratiques** – privilégiez les structures de données immuables pour les séries de graphiques lorsque c'est possible.

## Common Issues and Solutions
| Problème | Solution |
|----------|----------|
| **`NullPointerException` on `getSlides()`** | Assurez‑vous que l'objet `Presentation` est correctement instancié avant d'accéder aux diapositives. |
| **Chart not appearing** | Vérifiez que les dimensions du graphique (x, y, largeur, hauteur) sont à l'intérieur des limites de la diapositive. |
| **License not applied** | Chargez votre fichier de licence avant de créer l'objet `Presentation` : `License license = new License(); license.setLicense("path/to/license.xml");` |

## Frequently Asked Questions

**Q : Comment ajouter différents types de graphiques avec Aspose.Slides ?**  
A : Remplacez `ChartType.ClusteredColumn` par toute autre valeur d'énumération telle que `ChartType.Pie`, `ChartType.Line` ou `ChartType.Bar`.

**Q : Que faire si je rencontre des erreurs de compilation ?**  
A : Vérifiez que vous utilisez JDK 16 ou une version plus récente et que la dépendance Maven/Gradle correspond à la version indiquée ci‑dessus.

**Q : Puis‑je alimenter le graphique avec des données provenant d’une base de données ?**  
A : Oui. Accédez à la collection `getChartData()` du graphique, créez des séries et des catégories, puis remplissez‑les avec les valeurs récupérées à l'exécution.

**Q : Comment améliorer les performances pour des présentations très volumineuses ?**  
A : Divisez le travail en plusieurs instances `Presentation`, réutilisez des modèles de graphiques et libérez toujours les objets rapidement.

## Conclusion
Vous disposez maintenant d’une recette complète, de bout en bout, pour **ajouter un graphique à colonnes groupées** à une diapositive PowerPoint avec Aspose.Slides for Java. Expérimentez avec d’autres types de graphiques, liez des sources de données en temps réel et intégrez cette logique dans des pipelines de reporting plus larges afin d’automatiser votre flux de travail de présentation.

---

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 for Java (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
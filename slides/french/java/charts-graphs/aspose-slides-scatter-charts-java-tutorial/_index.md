---
date: '2026-07-27'
description: Comment personnaliser un graphique avec Aspose.Slides for Java. Apprenez
  à créer un graphique PowerPoint, à styliser les séries de dispersion et à enregistrer
  les présentations efficacement.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Comment personnaliser un graphique avec Aspose.Slides for Java. Ce
  guide montre comment créer un graphique PowerPoint, styliser les points de dispersion
  et exporter les présentations.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Comment personnaliser un graphique : Graphique de dispersion Aspose en
  Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Comment personnaliser un graphique : Graphique de dispersion Aspose en Java'
url: /fr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personnaliser le diagramme de dispersion Aspose en Java

Dans ce tutoriel, vous découvrirez **comment personnaliser un graphique** — plus précisément un diagramme de dispersion — en utilisant la puissante bibliothèque Aspose.Slides for Java. Nous parcourrons la configuration du projet, la création d’un diagramme de dispersion, l’ajustement des types de séries et des marqueurs, puis l’enregistrement de la présentation. À la fin, vous serez capable de générer des diagrammes de dispersion d’aspect professionnel de manière programmatique et d’ajuster chaque détail visuel pour correspondre à votre marque ou à vos besoins de reporting.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.Slides for Java (v25.4+).  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieur.  
- **Puis‑je changer les formes des marqueurs ?** Oui – utilisez `MarkerStyleType` pour choisir des étoiles, des cercles, etc.  
- **Comment enregistrer le fichier ?** Appelez `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Une licence est‑elle requise ?** Un essai gratuit suffit pour le développement ; une licence commerciale est nécessaire pour la production.

## Comment personnaliser un graphique en Java avec Aspose.Slides ?
`Presentation` est la classe Aspose.Slides qui représente un fichier PowerPoint complet en mémoire. Chargez une nouvelle `Presentation`, ajoutez un diagramme de dispersion sur la première diapositive, configurez les séries et les styles de marqueurs, puis appelez `save`. Ce flux de travail unique crée un graphique entièrement stylisé en quelques lignes de code Java, prêt à être intégré dans n’importe quelle présentation PowerPoint.

## Qu’est‑ce que « personnaliser un diagramme de dispersion Aspose » ?
Personnaliser un diagramme de dispersion avec Aspose signifie définir de manière programmatique les données, l’apparence et le comportement du graphique — tout, des coordonnées des points aux symboles des marqueurs — sans ouvrir PowerPoint manuellement. Cette approche est idéale pour les rapports automatisés, les présentations basées sur les données, ou tout scénario nécessitant des visualisations répétables et de haute qualité.

## Pourquoi personnaliser les diagrammes de dispersion avec Aspose.Slides ?
Aspose.Slides offre aux développeurs un contrôle programmatique complet sur l’apparence des graphiques, permettant la création automatisée de visualisations de haute qualité, une intégration fluide dans les pipelines de reporting, et la possibilité de personnaliser chaque élément visuel sans ouvrir PowerPoint manuellement, ce qui fait gagner du temps et assure la cohérence des présentations.

- **Contrôle total** – modifiez les types de séries, les styles de marqueurs, les couleurs, et plus via le code Java.  
- **Automatisation** – générez des dizaines de graphiques à la volée pour les tableaux de bord ou les rapports par lots.  
- **Cross‑platform** – fonctionne sur tout OS supportant Java, aucune installation d’Office requise.  
- **Performance** – API légère qui traite **plus de 150 types de graphiques** et gère des présentations de plusieurs centaines de pages sans charger le fichier complet en mémoire.

## Prérequis
Pour suivre, assurez‑vous d’avoir :
- **Aspose.Slides for Java** (v25.4 ou ultérieure).  
- **Java Development Kit (JDK)** 8 + installé.  
- Maven ou Gradle pour la gestion des dépendances (ou vous pouvez télécharger le JAR manuellement).  
- Connaissances de base en Java et familiarité avec l’outil de construction de votre choix.

## Configuration d’Aspose.Slides pour Java
Intégrez la bibliothèque dans votre projet en utilisant l’une des méthodes ci‑dessous.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ou récupérez la dernière version depuis [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- **Essai gratuit** – évaluation de 30 jours.  
- **Licence temporaire** – période de test prolongée.  
- **Licence complète** – utilisation en production avec support premium.

## Guide étape par étape pour personnaliser le diagramme de dispersion Aspose

### 1️⃣ Préparer un dossier pour vos fichiers de présentation
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Pourquoi c’est important :* S’assurer que le dossier de sortie existe évite `FileNotFoundException` lors de l’enregistrement ultérieur du PPTX.

### 2️⃣ Créer une nouvelle présentation et récupérer la première diapositive
`Presentation` représente un document PowerPoint et donne accès aux diapositives et aux formes. La classe `Presentation` représente un fichier PowerPoint complet en mémoire.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Ajouter un diagramme de dispersion avec des lignes lisses
`ChartType.ScatterWithSmoothLines` crée un diagramme de dispersion où les points sont reliés par des lignes lisses.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Effacer les séries par défaut et ajouter les vôtres
`IChartSeries` représente une série de données au sein d’un graphique.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Remplir la première série avec des points de données
`addDataPointForScatterSeries` ajoute un point X‑Y unique à une série de dispersion.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Personnaliser le type de série et l’apparence des marqueurs
`Marker` contrôle le symbole visuel utilisé pour chaque point de données dans une série de graphique.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Enregistrer la présentation
`save` écrit la présentation dans un fichier au format spécifié.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Cas d’utilisation courants pour les diagrammes de dispersion personnalisés
- **Tableaux de bord financiers** – tracer le cours de l’action vs. le volume.  
- **Recherche scientifique** – afficher les mesures expérimentales avec des marqueurs d’erreur.  
- **Gestion de projet** – comparer l’effort prévu vs. réel sur les tâches.  

## Conseils de performance
- Appelez `pres.dispose()` après l’enregistrement pour libérer la mémoire native.  
- Pour les grands ensembles de données, remplissez d’abord le classeur puis liez la série afin d’éviter des rafraîchissements UI répétés.  
- Réutilisez une seule instance `IChartDataWorkbook` lors de l’ajout de nombreuses séries pour maintenir une faible consommation de mémoire.

## Questions fréquemment posées

**Q : Comment changer la couleur des marqueurs ?**  
A: Utilisez `series.getMarker().getFillFormat().setFillColor(Color)` où `Color` est une instance `java.awt.Color` comme `Color.RED`.

**Q : Puis‑je ajouter plus de deux séries à un diagramme de dispersion ?**  
A: Oui. Appelez `chart.getChartData().getSeries().add(...)` pour chaque série supplémentaire et remplissez ses points en conséquence.

**Q : Est‑il possible de définir une légende personnalisée pour chaque série ?**  
A: Absolument. Après avoir créé une série, invoquez `series.getLegend().setText("Your Legend Text")` pour remplacer le nom par défaut.

**Q : Comment exporter le graphique en image au lieu d’un PPTX ?**  
A: Appelez `chart.getImage().save("chart.png", ImageFormat.Png)` après avoir configuré le graphique. Cela produit un fichier PNG autonome.

**Q : Et si je dois animer les points de dispersion ?**  
A: Aspose.Slides prend en charge les effets d’animation. Utilisez `chart.getTimeline().getMainSequence().addEffect(...)` pour ajouter des animations d’entrée ou d’accentuation au graphique ou aux séries individuelles.

---

**Dernière mise à jour :** 2026-07-27  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer et personnaliser des graphiques PowerPoint en Java avec Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Comment créer un diagramme à bulles dans PowerPoint avec Aspose.Slides for Java (Tutoriel)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Créer et personnaliser des graphiques avec des lignes de tendance dans Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
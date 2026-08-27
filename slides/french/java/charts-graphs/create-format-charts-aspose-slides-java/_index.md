---
date: '2026-08-27'
description: Apprenez comment ajouter des grid lines à un chart en Java avec Aspose.Slides,
  formater les axes, les titres, et exporter un PowerPoint line chart soigné.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Apprenez comment ajouter des grid lines à un chart en Java avec Aspose.Slides,
  formater les axes, les titres, et exporter un PowerPoint line chart soigné.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Comment ajouter des grid lines à un chart avec Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Comment ajouter des grid lines à un chart avec Aspose.Slides for Java
url: /fr/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des lignes de grille à un graphique avec Aspose.Slides pour Java

## Introduction
Si vous devez **ajouter des lignes de grille au graphique** dans une présentation PowerPoint de manière programmatique, Aspose.Slides pour Java vous fournit une API propre et entièrement fonctionnelle. Que vous prépariez un compte‑rendu commercial trimestriel, une conférence académique ou une présentation de ventes axée sur les données, vous pouvez générer un graphique en courbes, personnaliser chaque élément visuel et enregistrer le résultat en quelques secondes — le tout sans ouvrir PowerPoint manuellement.

## Réponses rapides
- **Quelle bibliothèque crée des graphiques en Java ?** Aspose.Slides for Java.
- **Quel type de graphique ce guide couvre-t-il ?** A line chart with markers and grid lines.
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** A free temporary license works for evaluation; a commercial license is required for production.
- **Quel IDE puis‑je utiliser ?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
- **Comment les éléments du graphique sont‑ils formatés ?** Using fluent API calls for titles, axes, grid lines, legends, and background colors.

## Comment ajouter des lignes de grille au graphique en Java avec Aspose.Slides
Chargez une nouvelle `Presentation`, insérez une diapositive, ajoutez un graphique en courbes, puis activez les lignes de grille majeures sur l’axe vertical – le tout en moins de dix lignes de code. Cette réponse directe montre la séquence exacte dont vous avez besoin, afin que vous puissiez copier‑coller et voir immédiatement un graphique entièrement formaté.

### Ancre de définition
`Presentation` est la classe principale d’Aspose.Slides qui représente un fichier PowerPoint en mémoire ; toutes les opérations au niveau des diapositives commencent à partir de cet objet.

## Qu’est‑ce qu’un graphique en courbes et pourquoi utiliser Aspose.Slides ?
Un graphique en courbes trace une série de points de données reliés par des lignes droites, rendant les tendances au fil du temps immédiatement visibles. Aspose.Slides prend en charge **plus de 50 types de graphiques** et peut gérer **jusqu’à 10 000 points de données par série** sans ralentissement notable, vous offrant des performances de niveau entreprise pour de grands ensembles de données.

### Ancre de définition
`Chart` est l’objet de haut niveau d’Aspose.Slides pour tout graphique ; il stocke les séries, les catégories et les informations de formatage.

## Prérequis
- **Java Development Kit (JDK) 8+** installé.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, etc.).
- **Aspose.Slides for Java** bibliothèque ajoutée via Maven ou Gradle (voir la section *aspose.slides maven dependency* ci‑dessous).

### Dépendance Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dépendance Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Sinon, téléchargez le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## Acquisition de licence (appliquer la licence Aspose)
- Obtenez une **licence d'essai gratuite** depuis la page [free trial license](https://purchase.aspose.com/temporary-license/) pour les tests.
- Achetez une licence complète sur le [site officiel d'Aspose](https://purchase.aspose.com/buy) pour les déploiements en production.

## Configuration d’Aspose.Slides pour Java
1. Ajoutez la dépendance Maven ou Gradle affichée ci‑dessus à votre projet.
2. Chargez le fichier de licence **avant** de créer tout objet `Presentation` afin que toutes les fonctionnalités soient débloquées.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Implémentation étape par étape

### Étape 1 : créer le répertoire de sortie (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Pourquoi c’est important :* S’assurer que le dossier existe empêche `FileNotFoundException` lors de l’enregistrement ultérieur de la présentation.

### Étape 2 : ajouter une diapositive et insérer un graphique en courbes
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Explication :* Cela crée une nouvelle diapositive et place un **graphique en courbes avec marqueurs** aux coordonnées spécifiées.

### Étape 3 : ajouter le titre du graphique (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*Conseil :* Utiliser un titre gras et gris rend le graphique immédiatement reconnaissable.

### Étape 4 : formater les axes et ajouter des lignes de grille (add grid lines)
#### Formatage de l'axe vertical
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Pourquoi c’est important :* Des lignes de grille claires et des étiquettes pivotées améliorent la lisibilité, surtout lorsque les points de données sont denses.

#### Formatage de l'axe horizontal
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Étape 5 : personnaliser la légende (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Étape 6 : définir les couleurs d'arrière‑plan (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Étape 7 : enregistrer la présentation
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Résultat :* Vous avez maintenant un fichier PowerPoint (`FormattedChart_out.pptx`) contenant un graphique en courbes entièrement formaté.

## Applications pratiques (générer un graphique en courbes PowerPoint)
- **Rapports d’entreprise :** Afficher les tendances de revenu trimestriel avec des lignes de grille nettes.
- **Conférences académiques :** Visualiser les données expérimentales sur plusieurs sessions.
- **Propositions de projet :** Mettre en évidence la progression des jalons et les courbes de prévision.
- **Analyse marketing :** Présenter les tendances du ROI de la campagne côte à côte avec les données des concurrents.
- **Intégration de tableau de bord :** Exporter les analyses en temps réel vers PowerPoint pour les réunions avec les parties prenantes.

## Considérations de performance
- **Gestion de la mémoire :** Appelez `presentation.dispose()` après l’enregistrement pour libérer rapidement les ressources natives.
- **Grands ensembles de données :** Aspose.Slides traite les graphiques contenant des milliers de points en utilisant le streaming, maintenant l’utilisation de la mémoire sous 100 Mo sur un serveur typique.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Licence non appliquée** | Chargez la licence d’essai ou complète **avant** toute création d’objets `Presentation`. |
| **Le graphique apparaît vide** | Vérifiez que la diapositive contient au moins une série de données ; ajoutez des séries via `chart.getChartData().getSeries().add(...)` si nécessaire. |
| **Fichier non enregistré** | Assurez‑vous que le répertoire de sortie existe (voir Étape 1). |
| **Couleurs non appliquées** | Utilisez les constantes `java.awt.Color` ou l’énumération `PresetColor` pour un rendu fiable des couleurs. |

## Questions fréquemment posées

**Q : Puis‑je créer d’autres types de graphiques en plus des graphiques en courbes ?**  
R : Oui, Aspose.Slides prend en charge les graphiques à barres, secteurs, nuages de points, radar, et plus de 50 types de graphiques supplémentaires.

**Q : Comment ajouter plusieurs séries de données au graphique en courbes ?**  
R : Utilisez `chart.getChartData().getSeries().add(...)` pour insérer des séries supplémentaires avant d’appliquer le formatage.

**Q : Est‑il possible d’exporter le graphique en tant qu’image ?**  
R : Absolument. Rendu de la diapositive en PNG, JPEG ou SVG avec `presentation.save("slide.png", SaveFormat.Png)`.

**Q : Ai‑je besoin d’une licence payante pour le développement ?**  
R : Une licence temporaire gratuite suffit pour l’évaluation ; une licence commerciale est requise pour une utilisation en production.

**Q : Quelles versions de Java sont prises en charge ?**  
R : La bibliothèque fonctionne avec JDK 8 à JDK 22 ; choisissez le classificateur approprié (par ex., `jdk16`) lors de l’ajout de la dépendance Maven/Gradle.

---

**Dernière mise à jour :** 2026-08-27  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Tutoriels associés

- [dépendance maven aspose slides : ajouter et configurer des graphiques dans les présentations avec Aspose.Slides pour Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Créer et personnaliser les lignes de tendance des graphiques Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
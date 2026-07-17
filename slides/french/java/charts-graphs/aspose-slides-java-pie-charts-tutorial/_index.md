---
date: '2026-07-17'
description: Apprenez à faire pivoter le Pie Chart, personnaliser les couleurs du
  Pie Chart et exporter la diapositive au format PDF à l'aide d'Aspose.Slides for
  Java – un guide complet de visualisation de données.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Faites pivoter le Pie Chart et personnalisez les couleurs du Pie Chart
  avec Aspose.Slides for Java. Apprenez à exporter la diapositive au format PDF et
  à travailler avec le chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Faire pivoter le Pie Chart et personnaliser les couleurs en Java – Guide
  Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Comment faire pivoter le Pie Chart et personnaliser les couleurs en Java avec
  Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques circulaires avec Aspose.Slides pour Java : un tutoriel complet

## Introduction
Dans ce guide, vous apprendrez à **rotate pie chart** les éléments, à personnaliser la couleur de chaque tranche et à exporter la diapositive finale au format PDF — le tout avec Aspose.Slides pour Java. Que vous construisiez un tableau de bord commercial, un rapport financier ou toute présentation basée sur des données, maîtriser ces techniques vous permet de fournir des visuels clairs et accrocheurs sans dépendre de Microsoft Office. Préparons les outils et plongeons‑y.

## Réponses rapides
- **Quelle classe démarre une nouvelle présentation ?** `Presentation` from `com.aspose.slides`.
- **Quel appel d'API ajoute un graphique circulaire ?** `slide.addChart(ChartType.Pie, …)`.
- **Comment donner à chaque tranche une couleur unique ?** Appelez `series.setColorVaried(true)` et définissez des remplissages solides pour chaque point de données.
- **Quelle méthode fait pivoter le graphique ?** `chart.setRotationAngle(double)` – utilisez des degrés de 0 à 360.
- **La diapositive peut‑elle être exportée en PDF ?** Oui, invoquez `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Qu’est‑ce que « customize pie chart colors » ?
Personnaliser les couleurs d’un graphique circulaire signifie attribuer des couleurs de remplissage distinctes à chaque tranche du cercle, améliorant la lisibilité et l’impact visuel. Dans Aspose.Slides, vous y parvenez en activant les couleurs variées puis en définissant des couleurs de remplissage solides pour chaque point de données. Cette approche garantit que chaque segment de données se démarque clairement dans la présentation.

## Pourquoi utiliser Aspose.Slides pour Java pour créer des graphiques circulaires ?
Aspose.Slides prend en charge **plus de 150 types de graphiques** et peut rendre une présentation de 300 pages en moins de **5 secondes** sur un serveur type, le tout sans nécessiter l’installation de Microsoft Office. La bibliothèque fonctionne sous Windows, Linux et macOS, vous offrant une flexibilité multiplateforme pour tout projet de visualisation de données basé sur Java.

## Prérequis
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 ou version plus récente
- IDE tel que IntelliJ IDEA, Eclipse ou NetBeans
- Connaissances de base en Java et familiarité avec Maven ou Gradle

## Configuration d’Aspose.Slides pour Java
Ajoutez la bibliothèque à votre configuration de build.

**Maven**  
Ajoutez cet extrait à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Incluez ce qui suit dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Si vous préférez une approche manuelle, téléchargez le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – prolongez les limites de l’essai pendant une courte période.  
- **Achat** – obtenez une licence permanente pour une utilisation en production.

**Initialisation et configuration de base**  
La classe `Presentation` représente un fichier PowerPoint en mémoire et fournit des méthodes pour manipuler les diapositives.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guide d’implémentation
Voici un guide étape par étape qui couvre tout, de la création d’une diapositive à la rotation du graphique circulaire final.

### Initialiser la présentation et la diapositive
Créez une nouvelle instance `Presentation` et récupérez la première diapositive pour servir de toile au graphique.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Ajouter un graphique circulaire à la diapositive
`addChart` ajoute une forme de graphique du type spécifié à la diapositive aux coordonnées données.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Définir le titre du graphique
`setTitle` attribue un titre texte au graphique et le positionne au centre.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurer les étiquettes de données pour la série
`setShowValue(true)` active les étiquettes de valeurs numériques sur chaque point de données de la série.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Préparer la feuille de données du graphique
`ChartDataWorkbook` stocke le tableau de données sous‑jacent qui alimente les séries et catégories du graphique.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Ajouter des catégories au graphique
`addCategory` crée une nouvelle étiquette de catégorie pour les séries de données du graphique.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Ajouter une série et remplir les points de données
`addSeries` crée une série de données, et `addDataPointForBarSeries` insère des valeurs numériques pour chaque catégorie.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personnaliser les couleurs et bordures de la série
`setColorVaried(true)` active les couleurs par tranche, et `setFillFormat` attribue un remplissage solide à chaque point de données.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurer des étiquettes de données personnalisées
`setDataLabelFormat` personnalise l’apparence, la position et la police des étiquettes pour des annotations de graphique plus claires.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Définir l’angle de rotation et enregistrer la présentation
`setRotationAngle` fait pivoter le graphique circulaire complet, et `save` écrit la présentation dans un fichier.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Comment faire pivoter un graphique circulaire ?
Chargez l’objet du graphique, appelez `chart.setRotationAngle(45.0)` (ou toute valeur en degrés), puis enregistrez la présentation. Faire pivoter un graphique circulaire décale l’angle de départ, vous permettant de mettre en avant un segment particulier sans modifier les données. Cet appel de méthode unique fonctionne pour toute instance `Chart` dans Aspose.Slides. Vous pouvez également combiner la rotation avec des couleurs de tranche variées pour attirer l’attention sur le point de données le plus important.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Toutes les tranches ont la même couleur** | `setColorVaried(true)` non appelé | Assurez‑vous d’activer les couleurs variées sur le groupe de séries. |
| **Les étiquettes de données ne s’affichent pas** | drapeau `showValue` désactivé | Appelez `setShowValue(true)` sur le format d’étiquette. |
| **La rotation n’a aucun effet** | Utilisation d’une version plus ancienne d’Aspose.Slides | Mettez à jour vers la version 25.4 ou ultérieure. |
| **Exception de licence à l’exécution** | Fichier de licence manquant ou invalide | Chargez votre licence avec `License license = new License(); license.setLicense("Aspose.Slides.lic");` avant de créer le `Presentation`. |

## Questions fréquentes

**Q : Comment obtenir une licence Aspose.Slides pour Java ?**  
R : Demandez un essai gratuit sur le site Aspose, puis achetez une licence permanente. Chargez‑la à l’exécution comme indiqué dans le tableau des problèmes courants.

**Q : Puis‑je utiliser ce code avec d’anciennes versions du JDK ?**  
R : L’API nécessite JDK 16 ou supérieur ; les versions antérieures ne sont pas prises en charge.

**Q : Est‑il possible d’exporter le graphique sous forme d’image plutôt qu’en PPTX ?**  
R : Oui — après le rendu, appelez `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q : Que faire si j’ai besoin de plus d’une série dans un graphique circulaire ?**  
R : Les graphiques circulaires sont conçus pour une seule série de données ; pour plusieurs séries, envisagez d’utiliser un graphique en anneau.

**Q : Aspose.Slides fonctionne‑t‑il sur des serveurs Linux ?**  
R : Absolument — Aspose.Slides pour Java est indépendant de la plateforme et fonctionne sur tout système d’exploitation avec un JDK compatible.

---

**Dernière mise à jour :** 2026-07-17  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer des graphiques circulaires dans des présentations Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Maîtriser les graphiques circulaires en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Faire pivoter les textes de graphique en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-07-08'
description: Apprenez comment utiliser Aspose pour créer un doughnut chart dans PowerPoint
  avec Java. Ce guide étape par étape montre comment ajouter des chart data points
  programmatiquement, personnaliser les labels et enregistrer le PPTX avec une haute
  fidélité.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Comment utiliser Aspose vous permet de créer un doughnut chart dans
  PowerPoint avec Java. Suivez ce tutoriel pour ajouter des data points, personnaliser
  les labels et enregistrer le PPTX avec une haute fidélité.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Comment utiliser Aspose : créer un doughnut chart dans PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Comment utiliser Aspose pour créer un doughnut chart dans PowerPoint (Java)
url: /fr/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment utiliser Aspose pour créer un graphique en anneau dans PowerPoint (Java)

## Introduction
Créer des présentations percutantes nécessite souvent plus que du texte et des images ; les graphiques peuvent améliorer considérablement la narration en visualisant les données efficacement. **Comment utiliser Aspose** pour la génération de graphiques vous donne un contrôle programmatique sans jamais ouvrir PowerPoint. Ce tutoriel vous guide dans la création d’un graphique en anneau, la configuration de ses points de données et l’enregistrement d’un PPTX haute fidélité. Vous n’avez besoin que de connaissances de base en Java et de quelques minutes de configuration.

`Aspose.Slides for Java` est une bibliothèque Java qui permet la création, la manipulation et la conversion de fichiers PowerPoint sans Microsoft Office.

## Réponses rapides
- **Quelle bibliothèque crée un graphique en anneau PowerPoint ?** Aspose.Slides for Java  
- **Puis-je ajouter des points de données au graphique programmatique ?** Oui, en utilisant l’API du graphique  
- **Ai-je besoin d’une licence pour la production ?** Une licence valide d’Aspose.Slides est requise  
- **Quelles versions de Java sont prises en charge ?** Java 8 et ultérieures (classificateur JDK 16 indiqué)  
- **Combien de séries puis-je ajouter ?** L’exemple ajoute jusqu’à 15 séries, mais vous pouvez ajuster selon vos besoins  

## Qu’est‑ce qu’un graphique en anneau dans PowerPoint ?
Un graphique en anneau est un graphique circulaire similaire à un graphique en secteurs mais avec un centre creux, permettant d’afficher plusieurs séries simultanément. Il met en avant les relations partie‑à‑tout tout en conservant une mise en page visuelle compacte et facile à lire.

## Pourquoi utiliser Aspose.Slides for Java pour créer des graphiques en anneau ?
Aspose.Slides for Java gère plus de 50 formats d’entrée et de sortie et peut générer des présentations jusqu’à 500 Mo sans charger le fichier complet en mémoire. Il offre un contrôle programmatique complet sur l’apparence, les données et la mise en page du graphique sur n’importe quelle plateforme Java, élimine l’interopérabilité COM, et peut rendre 100 diapositives riches en graphiques en moins de deux secondes sur un serveur type.

## Prérequis
- Connaissances de base en programmation Java.  
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.  
- Maven ou Gradle pour la gestion des dépendances.  
- Une licence valide d’Aspose.Slides for Java (essai gratuit disponible).

## Configuration d’Aspose.Slides for Java
Choisissez le gestionnaire de dépendances qui convient à votre projet.

**Maven**  
Ajoutez la dépendance suivante à votre `pom.xml` (remplacez la version par la dernière publication) :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Ajoutez cette ligne à votre `build.gradle` :

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Si vous préférez télécharger directement, visitez la page [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) .

### Acquisition de licence
Vous pouvez commencer avec un essai gratuit pour explorer les fonctionnalités d’Aspose.Slides. Pour une utilisation prolongée, achetez une licence ou demandez une licence temporaire depuis le [site d’Aspose](https://purchase.aspose.com/temporary-license/). Suivez les instructions fournies pour configurer votre environnement et initialiser Aspose.Slides dans votre application.

## Comment créer un graphique en anneau PowerPoint avec Aspose.Slides for Java
Pour créer un graphique en anneau, commencez par charger ou créer une `Presentation`, ajoutez une forme de graphique de type `ChartType.Doughnut`, supprimez les séries par défaut, définissez la taille du trou, puis remplissez le classeur du graphique avec les noms de catégories et les valeurs numériques. Enfin, ajustez le formatage des libellés et enregistrez le PPTX.

### Étape 1 : Initialiser la présentation
Créez une nouvelle présentation ou ouvrez un fichier existant pour obtenir une collection de diapositives.

`Presentation` est la classe principale qui représente un fichier PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Étape 2 : Ajouter un graphique en anneau à la diapositive
Insérez une forme de graphique, supprimez les séries/catégories par défaut, et configurez les paramètres visuels de base comme la taille du trou de l’anneau.

`Chart` (ou forme de graphique) représente un objet graphique placé sur une diapositive.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Étape 3 : Ajouter des points de données au graphique et personnaliser les libellés
Remplissez les noms de catégories, ajoutez des points de données pour chaque série, et peaufinez le formatage des libellés (police, couleur, position). Cette étape montre la capacité « ajouter des points de données au graphique ».

`Workbook` fournit l’accès aux données de feuille de calcul sous‑jacentes du graphique où les cellules sont remplies.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Étape 4 : Enregistrer la présentation mise à jour
Enregistrez les modifications dans un nouveau fichier PPTX sur le disque.

`save` écrit la présentation dans un fichier au format choisi.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Applications pratiques
- **Rapports financiers :** Visualisation des allocations budgétaires ou de la répartition des dépenses.  
- **Analyse du marché :** Affichage de la répartition des parts de marché parmi les concurrents.  
- **Résultats d’enquête :** Présentation des données d’enquête catégoriques sous forme compacte.  
- **Génération de tableaux de bord :** Combinaison avec des requêtes de base de données pour produire des diapositives mises à jour en temps réel.

## Considérations de performance
- **Libérer les ressources :** Appelez `pres.dispose()` après l’enregistrement pour libérer la mémoire native.  
- **Limiter le nombre de graphiques :** Ajouter des centaines de graphiques peut augmenter l’utilisation de mémoire ; traitez par lots si nécessaire.  
- **Utiliser le streaming :** Pour des ensembles de données massifs, remplissez le classeur directement à partir de flux au lieu de tableaux en mémoire.  

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Le graphique apparaît vide** | Les cellules de données ne sont pas correctement remplies | Vérifiez que `workBook.getCell(...)` fait référence aux bons indices de ligne/colonne. |
| **Les libellés se chevauchent** | Trop de catégories dans un espace limité | Augmentez `DoughnutHoleSize` ou ajustez `FirstSliceAngle`. |
| **OutOfMemoryError** | Présentations volumineuses sans libération | Appelez `pres.dispose()` après l’enregistrement et envisagez d’augmenter la taille du tas JVM. |

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.Slides for Java dans des applications commerciales ?**  
R : Oui, mais vous avez besoin d’une licence commerciale valide. Un essai gratuit est disponible pour l’évaluation.

**Q : Comment ajouter plus de 15 séries ?**  
R : Augmentez la limite de boucle dans l’étape « Add Doughnut Chart » et assurez‑vous que votre classeur de données contient suffisamment de lignes.

**Q : Est‑il possible de modifier la taille du trou de l’anneau après la création ?**  
R : Oui, appelez `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` avant l’enregistrement.

**Q : Puis‑je exporter le graphique sous forme d’image au lieu d’un PPTX ?**  
R : Absolument. Utilisez `chart.getImage()` et enregistrez le `java.awt.image.BufferedImage` retourné dans le format de votre choix.

**Q : Aspose.Slides prend‑il en charge les graphiques animés ?**  
R : L’animation peut être ajoutée via l’API `ISlide.getTimeline()`, bien que cela dépasse le cadre de ce tutoriel.

## Conclusion
Vous disposez maintenant d’une méthode complète et prête pour la production afin de **créer des fichiers PowerPoint avec des graphiques en anneau** grâce à Aspose.Slides for Java, y compris comment **ajouter des points de données au graphique**, personnaliser les libellés et gérer les considérations de performance. Expérimentez avec différentes couleurs, sources de données et types de graphiques pour que vos présentations se démarquent réellement.

---

**Dernière mise à jour :** 2026-07-08  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur JDK 16)  
**Auteur :** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Tutoriels associés

- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides for Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Comment modifier les données d’un graphique PowerPoint avec Aspose.Slides for Java : guide complet](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animer les graphiques PowerPoint avec Aspose.Slides for Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
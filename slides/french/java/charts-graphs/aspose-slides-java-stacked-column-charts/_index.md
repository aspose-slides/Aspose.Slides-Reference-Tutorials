---
date: '2026-07-22'
description: Découvrez l'Aspose Slides Maven Dependency pour créer un graphique à
  colonnes empilées en Java, ajouter des étiquettes de données, modifier le format
  numérique de l'axe vertical et exporter le résultat sous forme de fichier PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency vous permet de créer un graphique à
  colonnes empilées en Java, de personnaliser les étiquettes de données, d'ajuster
  le format de l'axe vertical et d'enregistrer en PPTX – le tout avec un code concis
  et prêt pour la production.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency : graphique à colonnes empilées en Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency : graphique à colonnes empilées en Java'
url: /fr/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Diagramme à colonnes empilées en Java

## Introduction

Élevez vos présentations en incorporant des visualisations de données perspicaces grâce à la puissance d'**Aspose.Slides for Java**. Dans ce guide, vous allez **créer un diagramme à colonnes empilées** qui a l'air professionnel, que vous prépariez des rapports d'affaires ou présentiez des statistiques de projet. À la fin de ce tutoriel, vous serez capable de :

- Configurer votre environnement avec la **dépendance Aspose Slides Maven**
- Créer une présentation à partir de zéro
- **Ajouter un diagramme à colonnes empilées en pourcentage** et personnaliser son apparence
- **Formater les étiquettes de données du diagramme** et **modifier le format numérique de l'axe vertical**
- **Enregistrer la présentation au format PPTX** avec une seule ligne de code

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Ajoutez la dépendance Maven/Gradle `aspose-slides` (voir « Aspose Slides Maven Dependency » ci‑dessous).  
- **Quel type de diagramme crée une vue empilée ?** Utilisez `ChartType.PercentsStackedColumn` pour un diagramme à colonnes empilées en pourcentage.  
- **Comment changer le format numérique de l'axe ?** Appelez `IAxis.setNumberFormat()` et définissez `setNumberFormatLinkedToSource(false)`.  
- **Puis‑je personnaliser les étiquettes de données ?** Oui – parcourez chaque `IChartDataPoint` et attribuez un `ITextFrame` personnalisé.  
- **Comment enregistrer le fichier ?** Appelez `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Qu'est‑ce qu'un diagramme à colonnes empilées ?
Un diagramme à colonnes empilées visualise plusieurs séries de données empilées verticalement dans chaque colonne de catégorie, la variante **empilée en pourcentage** normalisant chaque colonne à 100 % pour une comparaison de proportions facile. Ce format permet aux spectateurs d'évaluer rapidement comment chaque composant contribue à l'ensemble selon les différentes catégories, rendant les tendances et les tailles relatives immédiatement claires.

## Pourquoi utiliser Aspose.Slides pour Java ?
Aspose.Slides pour Java vous permet de générer, modifier et convertir des fichiers PowerPoint **sans nécessiter Microsoft Office** et prend en charge **plus de 50 formats de sortie** sous Windows, Linux et macOS. La bibliothèque s'exécute entièrement sur une JRE, permettant l'automatisation côté serveur et la génération de rapports à haut débit. Elle offre également un contrôle granulaire sur les objets de diagramme, les mises en page des diapositives et les propriétés du document, ce qui la rend idéale pour la génération de présentations de niveau entreprise.

## Prérequis
- **Java Development Kit (JDK) :** 8 ou supérieur  
- **IDE :** IntelliJ IDEA, Eclipse ou tout éditeur compatible Java  
- **Outil de construction :** Maven ou Gradle (facultatif mais recommandé)  
- **Connaissances de base en Java** – vous devez être à l'aise avec les classes et les méthodes  

## Configuration d'Aspose.Slides pour Java
Pour commencer, ajoutez la bibliothèque Aspose.Slides à votre projet.

### Dépendance Aspose Slides Maven
Ajoutez ce qui suit à votre `pom.xml` (c’est la **aspose slides maven dependency** dont vous avez besoin) :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternative Gradle
Si vous préférez Gradle, incluez cette ligne dans `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence
Vous pouvez commencer avec un essai gratuit pour explorer les fonctionnalités d'Aspose.Slides. Pour supprimer les limitations d'évaluation, envisagez d'obtenir une licence temporaire ou achetée.

- **Essai gratuit :** Accédez à des fonctionnalités limitées sans frais immédiats.  
- **Licence temporaire :** Demandez‑la via le [site d'Aspose](https://purchase.aspose.com/temporary-license/).  
- **Achat :** Visitez la page d'achat pour un accès complet.

### Initialisation de base
`Presentation` est la classe centrale d'Aspose.Slides représentant un fichier PowerPoint en mémoire. L'extrait minimal suivant montre comment créer un objet `Presentation` :

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guide de mise en œuvre

### Création d'une présentation et ajout d'une diapositive
**Vue d'ensemble :**  
Nous allons d'abord créer une présentation vierge et vérifier qu'une diapositive existe.

#### Étape 1 : Initialiser l'objet Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Étape 2 : Enregistrer la présentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Ajout d'un diagramme à colonnes empilées en pourcentage à une diapositive
**Vue d'ensemble :**  
Nous allons maintenant placer un **diagramme empilé en pourcentage** sur la première diapositive.

`ChartType.PercentsStackedColumn` spécifie un type de diagramme à colonnes empilées en pourcentage.

#### Étape 1 : Initialiser et accéder à la diapositive
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Étape 2 : Ajouter le diagramme à la diapositive
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personnalisation du format numérique de l'axe du diagramme
**Vue d'ensemble :**  
Pour une meilleure lisibilité, nous allons **modifier le format de l'axe vertical** afin d'afficher des pourcentages.

`IAxis` est l'interface représentant un axe de diagramme, permettant des ajustements de format et d'échelle.

#### Étape 1 : Ajouter et accéder au diagramme
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Étape 2 : Définir le format numérique personnalisé
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Ajout de séries et de points de données au diagramme
**Vue d'ensemble :**  
Nous allons remplir le diagramme avec des séries de données d'exemple.

#### Étape 1 : Initialiser la présentation et le diagramme
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Étape 2 : Ajouter des séries de données
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatage de la couleur de remplissage des séries
**Vue d'ensemble :**  
Donnez à chaque série une couleur distincte pour rendre le diagramme plus lisible.

#### Étape 1 : Initialiser et accéder au diagramme
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Étape 2 : Définir les couleurs de remplissage
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatage des étiquettes de données
**Vue d'ensemble :**  
Nous allons maintenant **formater les étiquettes de données du diagramme** afin qu'elles affichent un texte personnalisé.

`IChartDataPoint` représente un point de données individuel au sein d'une série de diagramme, et `ITextFrame` contient le texte de l'étiquette.

#### Étape 1 : Accéder aux séries et points de données du diagramme
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Étape 2 : Personnaliser les étiquettes de données
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Problèmes courants et solutions
- **Le diagramme apparaît vide :** Assurez‑vous d'avoir ajouté au moins une série de données et un point de données avant d'enregistrer.  
- **Les nombres de l'axe n'affichent pas les pourcentages :** N'oubliez pas de définir `verticalAxis.setNumberFormatLinkedToSource(false)` ; sinon le format personnalisé est ignoré.  
- **Message d'évaluation de licence :** Appliquez un fichier de licence valide avant de créer l'objet `Presentation` pour supprimer la bannière d'évaluation.

## Questions fréquentes

**Q : Puis‑je utiliser ce code avec Java 11 ou une version plus récente ?**  
R : Oui. La bibliothèque prend en charge JDK 8+ ; utilisez simplement le classificateur approprié (par ex., `jdk16` pour JDK 16 ou supérieur).

**Q : Comment exporter le diagramme en image au lieu d'un PPTX ?**  
R : Utilisez `chart.getImage().save("chart.png", ImageFormat.Png);` après avoir ajouté le diagramme à la diapositive.

**Q : Est‑il possible d'ajouter une légende au diagramme à colonnes empilées ?**  
R : Absolument. Appelez `chart.getChartTitle().addTextFrameForOverriding("My Chart");` et configurez `chart.getLegend()` selon vos besoins.

**Q : Que faire si je dois mettre à jour les données après la génération de la présentation ?**  
R : Vous pouvez modifier les cellules du `ChartDataWorkbook` puis appeler `chart.refresh();` pour refléter les changements.

**Q : Aspose.Slides fonctionne‑t‑il sur des serveurs Linux ?**  
R : Oui. La bibliothèque est pure Java et s'exécute sur tout OS disposant d'une JRE compatible.

## Conclusion
En suivant ce guide, vous avez appris à **créer un diagramme à colonnes empilées** en Java en utilisant la **dépendance Aspose Slides Maven**, depuis la configuration de l'environnement jusqu'à la personnalisation visuelle fine. Expérimentez avec différents ensembles de données, couleurs et formats d'étiquettes pour que vos rapports se démarquent réellement.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer un diagramme à colonnes groupées en Java avec Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Comment définir les formats numériques dans les points de données du diagramme avec Aspose.Slides pour Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Comment ajouter et configurer des diagrammes dans les présentations avec Aspose.Slides pour Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
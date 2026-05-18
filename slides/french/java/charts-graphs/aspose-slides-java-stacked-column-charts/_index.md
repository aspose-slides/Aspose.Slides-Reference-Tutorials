---
date: '2026-02-22'
description: Apprenez à créer un graphique à colonnes empilées en Java avec Aspose.Slides.
  Ce tutoriel couvre la dépendance Maven d'Aspose Slides, l'ajout d'un graphique empilé
  en pourcentage, le formatage des étiquettes de données du graphique et l'enregistrement
  de la présentation au format PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Comment créer un graphique à colonnes empilées en Java avec Aspose.Slides –
  Guide complet
url: /fr/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique à colonnes empilées en Java avec Aspose.Slides – Guide complet

## Introduction

Élevez vos présentations en intégrant des visualisations de données perspicaces grâce à la puissance d’Aspose.Slides pour Java. Dans ce guide, vous **créerez des diapositives avec un graphique à colonnes empilées** au rendu professionnel, que vous prépariez des rapports d’entreprise ou présentiez des statistiques de projet. À la fin de ce tutoriel, vous serez capable de :

- Configurer votre environnement avec la dépendance Maven Aspose Slides
- Créer une présentation à partir de zéro
- **Ajouter un graphique à colonnes empilées en pourcentage** et personnaliser son apparence
- **Formater les étiquettes de données du graphique** et **modifier le format de l’axe vertical**
- **Enregistrer la présentation au format PPTX** en une seule ligne de code

Parcourons chaque étape afin que vous puissiez commencer à créer des présentations percutantes immédiatement.

## Quick Answers
- **Quelle bibliothèque faut‑il ?** dépendance Maven/Gradle `aspose-slides` (voir « aspose slides maven dependency » ci‑dessous)  
- **Quel type de graphique est utilisé ?** `ChartType.PercentsStackedColumn` pour un graphique à colonnes empilées en pourcentage  
- **Comment changer le format numérique de l’axe ?** Utilisez `IAxis.setNumberFormat()` et désactivez le lien avec la source  
- **Puis‑je personnaliser les étiquettes de données ?** Oui – parcourez les objets `IChartDataPoint` et définissez un `ITextFrame` personnalisé  
- **Comment enregistrer le fichier ?** Appelez `presentation.save("output.pptx", SaveFormat.Pptx)`

## What is a stacked column chart?
Un graphique à colonnes empilées visualise plusieurs séries de données superposées les unes sur les autres dans des colonnes verticales. Lorsque vous utilisez la variante **empilée en pourcentage**, chaque colonne totalise toujours 100 %, ce qui facilite la comparaison des contributions proportionnelles entre les catégories.

## Why use Aspose.Slides for Java?
Aspose.Slides fournit une API pure Java qui fonctionne sur n’importe quelle plateforme sans nécessiter Microsoft Office. Elle offre un contrôle fin sur les objets graphiques, prend en charge un large éventail de formats et vous permet de générer des présentations de façon programmatique—idéal pour les rapports automatisés ou la génération de documents côté serveur.

## Prerequisites
- **Java Development Kit (JDK) :** 8 ou supérieur  
- **IDE :** IntelliJ IDEA, Eclipse ou tout éditeur compatible Java  
- **Outil de construction :** Maven ou Gradle (optionnel mais recommandé)  
- **Connaissances de base en Java** – vous devez être à l’aise avec les classes et les méthodes  

## Setting Up Aspose.Slides for Java
Pour commencer, ajoutez la bibliothèque Aspose.Slides à votre projet.

### Aspose Slides Maven Dependency
Ajoutez ce qui suit à votre `pom.xml` (c’est la **aspose slides maven dependency** dont vous avez besoin) :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternative
Si vous préférez Gradle, incluez cette ligne dans `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Sinon, téléchargez le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
Vous pouvez commencer avec une version d’essai gratuite pour explorer les fonctionnalités d’Aspose.Slides. Pour lever les limitations d’évaluation, envisagez d’obtenir une licence temporaire ou achetée.

- **Essai gratuit :** Accès à des fonctionnalités limitées sans frais immédiats.  
- **Licence temporaire :** Demandez‑la via le [site d’Aspose](https://purchase.aspose.com/temporary-license/).  
- **Achat :** Visitez la page d’achat pour un accès complet.

### Basic Initialization
Voici un extrait minimal montrant comment créer un objet `Presentation` :

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

## Implementation Guide

### Creating a Presentation and Adding a Slide
**Overview :**  
Tout d’abord, nous créerons une présentation vierge et vérifierons qu’une diapositive existe.

#### Step 1: Initialize Presentation Object
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

#### Step 2: Save the Presentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview :**  
Nous placerons maintenant un **graphique empilé en pourcentage** sur la première diapositive.

#### Step 1: Initialize and Access Slide
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

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview :**  
Pour une meilleure lisibilité, nous **modifierons le format de l’axe vertical** afin d’afficher des pourcentages.

#### Step 1: Add and Access Chart
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

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview :**  
Nous remplirons le graphique avec des séries de données d’exemple.

#### Step 1: Initialize Presentation and Chart
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

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview :**  
Attribuez à chaque série une couleur distincte pour rendre le graphique plus lisible.

#### Step 1: Initialize and Access Chart
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

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview :**  
Nous **formaterons les étiquettes de données du graphique** afin qu’elles affichent un texte personnalisé.

#### Step 1: Access Chart Series and Data Points
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

#### Step 2: Customize Data Labels
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

## Common Issues and Solutions
- **Le graphique apparaît vide :** Assurez‑vous d’avoir ajouté au moins une série de données et un point de données avant l’enregistrement.  
- **Les nombres de l’axe n’affichent pas de pourcentages :** N’oubliez pas de définir `verticalAxis.setNumberFormatLinkedToSource(false)` ; sinon le format personnalisé est ignoré.  
- **Message d’évaluation de licence :** Appliquez un fichier de licence valide avant de créer l’objet `Presentation` pour supprimer la bannière d’évaluation.

## Frequently Asked Questions

**Q : Puis‑je utiliser ce code avec Java 11 ou une version plus récente ?**  
R : Oui. La bibliothèque prend en charge JDK 8+ ; utilisez simplement le classificateur approprié (par ex., `jdk16` pour JDK 16 ou supérieur).

**Q : Comment exporter le graphique sous forme d’image plutôt qu’en PPTX ?**  
R : Utilisez `chart.getImage().save("chart.png", ImageFormat.Png);` après avoir ajouté le graphique à la diapositive.

**Q : Est‑il possible d’ajouter une légende au graphique à colonnes empilées ?**  
R : Absolument. Appelez `chart.getChartTitle().addTextFrameForOverriding("My Chart");` et configurez `chart.getLegend()` selon vos besoins.

**Q : Que faire si je dois mettre à jour les données après la génération de la présentation ?**  
R : Vous pouvez modifier les cellules du `ChartDataWorkbook` puis appeler `chart.refresh();` pour refléter les changements.

**Q : Aspose.Slides fonctionne‑t‑il sur des serveurs Linux ?**  
R : Oui. La bibliothèque est pure Java et s’exécute sur tout OS disposant d’une JRE compatible.

## Conclusion
En suivant ce guide, vous avez appris à **créer des présentations avec un graphique à colonnes empilées** à l’aide d’Aspose.Slides pour Java, depuis la configuration de l’environnement jusqu’à la personnalisation visuelle fine. Expérimentez avec différents ensembles de données, couleurs et formats d’étiquettes pour que vos rapports se démarquent réellement.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
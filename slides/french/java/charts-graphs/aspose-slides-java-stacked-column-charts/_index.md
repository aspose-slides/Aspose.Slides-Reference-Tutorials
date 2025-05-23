---
"date": "2025-04-17"
"description": "Apprenez à créer des présentations professionnelles avec Aspose.Slides pour Java. Ce guide explique comment configurer votre environnement, ajouter des graphiques à colonnes empilées et les personnaliser pour plus de clarté."
"title": "Maîtrisez les graphiques à colonnes empilées en Java avec Aspose.Slides &#58; un guide complet"
"url": "/fr/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser les graphiques à colonnes empilées en Java avec Aspose.Slides : un guide complet

## Introduction

Optimisez vos présentations en intégrant des visualisations de données perspicaces grâce à la puissance d'Aspose.Slides pour Java. Créer des diapositives professionnelles avec des graphiques à colonnes empilées est simple, que vous prépariez des rapports d'activité ou présentiez des statistiques de projet.

Dans ce tutoriel, nous découvrirons comment utiliser Aspose.Slides pour Java pour créer des présentations dynamiques et ajouter des histogrammes empilés attrayants. À la fin de ce guide, vous maîtriserez les compétences nécessaires pour :
- Configurez votre environnement pour utiliser Aspose.Slides
- Créer une présentation à partir de zéro
- Ajouter et personnaliser des graphiques à colonnes empilées en pourcentage
- Formater les axes du graphique et les étiquettes de données pour plus de clarté

Plongeons dans la création de présentations qui captivent votre public.

## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- **Kit de développement Java (JDK) :** Version 8 ou supérieure.
- **IDE:** Tout environnement de développement intégré comme IntelliJ IDEA ou Eclipse.
- **Maven/Gradle :** Pour gérer les dépendances (facultatif mais recommandé).
- **Connaissances de base en Java :** Connaissance des concepts de programmation Java.

## Configuration d'Aspose.Slides pour Java
Pour commencer, vous devez inclure la bibliothèque Aspose.Slides dans votre projet. Voici comment :

**Expert :**
Ajoutez cette dépendance à votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle :**
Incluez ceci dans votre `build.gradle` déposer:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct :**
Vous pouvez également télécharger le dernier JAR à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Acquisition de licence
Vous pouvez commencer par un essai gratuit pour explorer les fonctionnalités d'Aspose.Slides. Pour lever les restrictions d'évaluation, envisagez d'obtenir une licence temporaire ou payante.
- **Essai gratuit :** Accédez à des fonctionnalités limitées sans frais immédiats.
- **Licence temporaire :** Demande via [Le site d'Aspose](https://purchase.aspose.com/temporary-license/).
- **Achat:** Visitez la page d'achat pour un accès complet.

### Initialisation de base
Voici comment initialiser Aspose.Slides dans votre application Java :
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Créer une instance de la classe Presentation
        Presentation presentation = new Presentation();
        
        // Effectuer des opérations sur l'objet de présentation
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guide de mise en œuvre

### Créer une présentation et ajouter une diapositive
**Aperçu:**
Commencez par créer une présentation simple avec une diapositive initiale. Elle servira de base à vos améliorations ultérieures.

#### Étape 1 : Initialiser l'objet de présentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Créer une nouvelle instance de présentation
        Presentation presentation = new Presentation();
        
        // Référence à la première diapositive (créée automatiquement)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Étape 2 : Enregistrer la présentation
```java
// Enregistrer la présentation dans un fichier
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Ajout d'un graphique à colonnes empilées en pourcentage à une diapositive
**Aperçu:**
Améliorez votre diapositive en ajoutant un graphique à colonnes empilées en pourcentage, permettant une comparaison facile des données.

#### Étape 1 : Initialiser et accéder à la diapositive
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Procédez à l'ajout du graphique à l'étape suivante
    }
}
```

#### Étape 2 : Ajouter un graphique à la diapositive
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personnalisation du format des nombres des axes du graphique
**Aperçu:**
Personnalisez le format numérique de l'axe vertical de votre graphique pour une meilleure lisibilité.

#### Étape 1 : Ajouter et accéder au graphique
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

#### Étape 2 : définir un format numérique personnalisé
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Ajout de séries et de points de données au graphique
**Aperçu:**
Remplissez votre graphique avec des séries de données, le rendant informatif et visuellement attrayant.

#### Étape 1 : Initialiser la présentation et le graphique
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

#### Étape 2 : Ajouter une série de données
```java
// Effacer les séries existantes et en ajouter de nouvelles
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Ajoutez plus de points de données si nécessaire
```

### Couleur de remplissage de la série de formatage
**Aperçu:**
Améliorez l'esthétique de votre graphique en formatant la couleur de remplissage de chaque série.

#### Étape 1 : Initialiser et accéder au graphique
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

#### Étape 2 : définir les couleurs de remplissage
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Répétez l'opération pour d'autres séries avec des couleurs différentes
```

### Formatage des étiquettes de données
**Aperçu:**
Rendez vos étiquettes de données plus lisibles en personnalisant leur format.

#### Étape 1 : Accéder aux séries de graphiques et aux points de données
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

#### Étape 2 : Personnaliser les étiquettes de données
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

## Conclusion
En suivant ce guide, vous avez appris à configurer Aspose.Slides pour Java et à créer des présentations dynamiques avec des graphiques à colonnes empilées en pourcentage. Personnalisez davantage vos graphiques en ajustant les couleurs et les libellés selon vos besoins.

Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
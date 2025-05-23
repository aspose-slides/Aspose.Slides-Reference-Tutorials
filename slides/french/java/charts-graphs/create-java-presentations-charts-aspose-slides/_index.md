---
"date": "2025-04-17"
"description": "Apprenez à créer et configurer des présentations dynamiques avec des graphiques en Java avec Aspose.Slides. Maîtrisez l'ajout, la personnalisation et l'enregistrement efficaces de présentations."
"title": "Créer des présentations Java avec des graphiques à l'aide d'Aspose.Slides pour Java"
"url": "/fr/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et configurer une présentation avec un graphique à l'aide d'Aspose.Slides pour Java

## Introduction

Créer des présentations dynamiques qui transmettent efficacement les données est essentiel dans le contexte économique actuel, en constante évolution. Que vous prépariez un rapport financier ou présentiez les indicateurs d'un projet, l'ajout de graphiques peut considérablement améliorer l'impact de votre présentation. Ce tutoriel vous guide dans la création et la configuration d'une présentation avec un histogramme 3D empilé à l'aide d'Aspose.Slides pour Java, une puissante bibliothèque conçue pour gérer les présentations par programmation.

**Ce que vous apprendrez :**
- Comment créer une nouvelle présentation
- Ajouter et configurer des graphiques dans les diapositives
- Personnaliser les données et l'apparence du graphique
- Enregistrez efficacement votre présentation

Prêt à maîtriser la création de présentations visuellement attrayantes avec Java ? C'est parti !

## Prérequis

Avant de plonger dans le didacticiel, assurez-vous d’avoir couvert ces prérequis :

- **Bibliothèques et dépendances**:Aspose.Slides pour Java doit être installé.
- **Configuration de l'environnement**:Travailler dans un environnement Java (JDK 16 ou version ultérieure recommandé).
- **Base de connaissances**:Une connaissance des concepts de base de la programmation Java sera bénéfique.

## Configuration d'Aspose.Slides pour Java

### Installation

Pour intégrer Aspose.Slides dans votre projet, suivez ces étapes :

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct**:Vous pouvez également télécharger la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Acquisition de licence
- **Essai gratuit**: Commencez par un essai gratuit pour explorer les fonctionnalités.
- **Permis temporaire**:Obtenez une licence temporaire pour des tests prolongés.
- **Achat**: Acquérir une licence complète pour une utilisation commerciale.

Une fois installée, initialisez la bibliothèque dans votre environnement Java en créant une instance de la `Presentation` classe. Cela pose les bases de l'ajout de graphiques et d'autres éléments à votre présentation.

## Guide de mise en œuvre

### Créer et configurer une présentation avec un graphique

#### Aperçu
Créer une présentation de A à Z est simple avec Aspose.Slides. Dans cette section, nous allons ajouter un graphique à colonnes empilées 3D à la première diapositive de notre présentation.

**Mesures:**

1. **Initialiser l'objet de présentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialiser un nouvel objet de présentation
           Presentation presentation = new Presentation();
           
           // Accéder à la première diapositive de la présentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Ajoutez un graphique à colonnes empilées 3D à la diapositive à la position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Expliquer les paramètres**:
   - `ChartType.StackedColumn3D`: Spécifie le type de graphique.
   - Position et taille `(0, 0, 500, 500)`: Détermine où le graphique apparaît sur la diapositive.

### Configurer les données du graphique

#### Aperçu
Pour que votre graphique soit pertinent, configurez ses séries de données et ses catégories. Cette section explique comment ajouter des points de données spécifiques à votre graphique.

**Mesures:**

1. **Classeur de données d'Access Chart**

   ```java
   public static void configureChartData(IChart chart) {
       // Définir l'index de la feuille de calcul contenant les données du graphique
       int defaultWorksheetIndex = 0;
       
       // Accéder au classeur de données du graphique
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Ajouter deux séries avec des noms
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Ajouter trois catégories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Définir les propriétés Rotation3D pour le graphique

#### Aperçu
Améliorez l'attrait visuel de votre graphique grâce aux propriétés de rotation 3D. Cette personnalisation vous permet d'ajuster la perspective et la profondeur.

**Mesures:**

1. **Configurer les rotations 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Activer les axes à angle droit et configurer les rotations dans les directions X, Y et le pourcentage de profondeur
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Expliquer les paramètres**:
   - `setRightAngleAxes(true)`: Assure que les axes sont perpendiculaires.
   - Valeurs de rotation : ajuste l’angle et la profondeur de la vue 3D.

### Remplir les données de la série dans le graphique

#### Aperçu
Alimenter votre graphique avec des points de données est essentiel pour l'analyse. Ici, nous allons ajouter des valeurs spécifiques à une série de notre graphique.

**Mesures:**

1. **Ajouter des points de données**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Accéder à la deuxième série de graphiques
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Ajouter des points de données pour les séries de barres avec des valeurs spécifiées
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Ajuster le chevauchement des séries dans le graphique

#### Aperçu
Ajuster l'apparence de votre graphique peut améliorer sa lisibilité. Cette section explique comment ajuster la propriété de chevauchement pour une meilleure visualisation des données.

**Mesures:**

1. **Chevauchement des séries d'ensembles**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Obtenez la deuxième série du graphique et définissez son chevauchement à 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Enregistrer la présentation

#### Aperçu
Une fois votre présentation configurée, enregistrez-la sur disque au format souhaité. Cette étape garantit la conservation de toutes les modifications.

**Mesures:**

1. **Enregistrer la présentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Enregistrer la présentation modifiée dans un fichier
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Conclusion

Vous savez maintenant comment créer et configurer des présentations avec graphiques à l'aide d'Aspose.Slides pour Java. Ce guide aborde l'initialisation d'une présentation, l'ajout d'un histogramme 3D empilé, la configuration des séries de données et des catégories, la définition des propriétés de rotation, le remplissage des données des séries, l'ajustement du chevauchement des séries et l'enregistrement de la présentation finale.

Pour des fonctionnalités plus avancées et des options de personnalisation, reportez-vous à la [Documentation Aspose.Slides pour Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
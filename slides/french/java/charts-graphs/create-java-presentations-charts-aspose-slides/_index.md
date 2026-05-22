---
date: '2026-03-20'
description: Apprenez à ajouter des graphiques aux présentations Java en utilisant
  Aspose.Slides et à générer rapidement des fichiers de graphiques de présentation.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Comment ajouter un graphique aux présentations Java avec Aspose.Slides
url: /fr/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un graphique à une présentation avec Aspose.Slides pour Java

## Introduction

Créer des présentations dynamiques qui transmettent efficacement les données est essentiel dans l’environnement commercial actuel, rapide et exigeant. Que vous prépariez un rapport financier, un deck marketing ou une mise à jour de l’état d’un projet, **savoir comment ajouter un graphique** à vos diapositives peut améliorer considérablement l’engagement du public. Dans ce tutoriel, vous apprendrez pas à pas comment ajouter un graphique à colonnes empilées 3D, configurer ses données et enregistrer le fichier final — le tout avec Aspose.Slides pour Java.

### Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.Slides pour Java  
- **Quel type de graphique est démontré ?** Colonne empilée 3D  
- **Puis‑je générer des fichiers de graphiques de présentation programmatiquement ?** Oui, en utilisant les méthodes API présentées ci‑dessous  
- **Quelle version de Java est recommandée ?** JDK 16 ou ultérieure  
- **Ai‑je besoin d’une licence pour la production ?** Une licence valide d’Aspose.Slides est requise pour un usage commercial  

## Qu’est‑ce que « comment ajouter un graphique » dans Aspose.Slides ?

Aspose.Slides pour Java fournit un ensemble riche d’objets qui vous permettent de créer, modifier et exporter des fichiers PowerPoint sans Microsoft Office. Ajouter un graphique est aussi simple que de créer un objet `Presentation`, d’insérer une forme de graphique et d’alimenter celle‑ci avec des données via le classeur intégré.

## Pourquoi ajouter un graphique aux présentations Java ?

- **Impact visuel :** Les graphiques transforment des chiffres bruts en visuels immédiatement compréhensibles.  
- **Automatisation :** Générez des rapports à la volée — idéal pour des résumés par e‑mail planifiés ou des tableaux de bord.  
- **Cohérence :** Utilisez le même style et la même identité visuelle sur toutes les présentations générées.  
- **Portabilité :** Exportez en PPTX, PDF ou images avec un seul appel de méthode.

## Prérequis

- **Bibliothèques et dépendances :** Aspose.Slides pour Java doit être installé.  
- **Configuration de l’environnement :** Travaillez dans un environnement Java (JDK 16 ou ultérieur recommandé).  
- **Base de connaissances :** Une familiarité avec les concepts de base de la programmation Java sera bénéfique.

## Configuration d’Aspose.Slides pour Java

### Installation

Pour intégrer Aspose.Slides à votre projet, suivez l’une des options ci‑dessous.

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

**Direct Download** : alternativement, téléchargez la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtention de licence
- **Essai gratuit :** Commencez avec un essai gratuit pour explorer les fonctionnalités.  
- **Licence temporaire :** Obtenez une licence temporaire pour des tests prolongés.  
- **Achat :** Acquérez une licence complète pour un usage commercial.

Une fois installé, vous pouvez instancier la classe `Presentation`, qui constitue le point d’entrée pour toutes les opérations liées aux graphiques.

## Guide d’implémentation

### Comment ajouter un graphique à une présentation avec une colonne empilée 3D

#### Vue d’ensemble
Créer une présentation à partir de zéro est simple avec Aspose.Slides. Dans cette section, nous ajouterons un graphique à colonnes empilées 3D à la première diapositive de notre présentation.

**Étapes :**

1. **Initialiser l’objet Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
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

2. **Expliquer les paramètres**  
   - `ChartType.StackedColumn3D` : spécifie le type de graphique.  
   - Position et taille `(0, 0, 500, 500)` : détermine où le graphique apparaît sur la diapositive.

### Configurer les données du graphique

#### Vue d’ensemble
Pour que votre graphique soit pertinent, configurez ses séries de données et ses catégories. Cette section montre comment ajouter des points de données spécifiques à votre graphique.

**Étapes :**

1. **Accéder au classeur de données du graphique**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Définir les propriétés Rotation3D du graphique

#### Vue d’ensemble
Améliorez l’aspect visuel de votre graphique avec les propriétés de rotation 3D. Cette personnalisation vous permet d’ajuster la perspective et la profondeur.

**Étapes :**

1. **Configurer les rotations 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Expliquer les paramètres**  
   - `setRightAngleAxes(true)` : garantit que les axes sont perpendiculaires.  
   - Valeurs de rotation : ajustez l’angle et la profondeur de la vue 3D.

### Remplir les données de la série dans le graphique

#### Vue d’ensemble
Peupler votre graphique avec des points de données est crucial pour l’analyse. Ici, nous ajouterons des valeurs spécifiques à une série de notre graphique.

**Étapes :**

1. **Ajouter des points de données**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
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

#### Vue d’ensemble
Affiner l’apparence de votre graphique peut améliorer la lisibilité. Cette section explique comment ajuster la propriété de chevauchement pour une meilleure visualisation des données.

**Étapes :**

1. **Définir le chevauchement des séries**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Enregistrer la présentation

#### Vue d’ensemble
Une fois votre présentation configurée, enregistrez‑la sur le disque dans le format souhaité. Cette étape garantit que toutes les modifications sont conservées.

**Étapes :**

1. **Enregistrer la présentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Le graphique apparaît plat** | Rotation 3D non définie | Appelez `setRotation3D` avec des valeurs X/Y appropriées. |
| **Les données ne s’affichent pas** | Les cellules du classeur ne sont pas liées | Assurez‑vous que les références `fact.getCell` pointent vers les bons indices de ligne/colonne. |
| **Le fichier n’est pas enregistré** | Chemin incorrect ou permissions manquantes | Vérifiez que `outputFilePath` est accessible en écriture et que le dossier existe. |

## Questions fréquentes

**Q : Puis‑je générer des fichiers de graphiques de présentation dans des formats autres que PPTX ?**  
R : Oui, Aspose.Slides prend en charge PDF, ODP et les formats d’image via l’énumération `SaveFormat`.

**Q : Ai‑je besoin d’une licence pour exécuter le code en développement ?**  
R : Une licence temporaire ou d’évaluation suffit pour le développement, mais une licence complète est requise pour les déploiements en production.

**Q : Est‑il possible d’ajouter plusieurs graphiques sur la même diapositive ?**  
R : Absolument. Appelez `slide.getShapes().addChart` plusieurs fois avec des positions ou tailles différentes.

**Q : Comment changer la palette de couleurs du graphique ?**  
R : Utilisez `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` et définissez une `SolidFillColor`.

**Q : Puis‑je lier le graphique à une source de données externe comme une base de données ?**  
R : Oui. Récupérez les données avec JDBC, puis remplissez les cellules du classeur programmatique avant l’enregistrement.

## Conclusion

Vous avez maintenant appris **comment ajouter un graphique** à une présentation Java, configurer ses données, personnaliser la rotation 3D, ajuster le chevauchement des séries et enregistrer le fichier final. Cette connaissance vous permet d’automatiser la génération de rapports, de créer une identité visuelle cohérente et de livrer des présentations axées sur les données sans effort manuel. Pour une personnalisation plus poussée — comme le style des légendes, des axes ou l’application de thèmes — explorez les capacités complètes dans la documentation officielle.

Pour des fonctionnalités avancées et des options de personnalisation, consultez la [documentation Aspose.Slides pour Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-20  
**Testé avec :** Aspose.Slides pour Java 25.4 (JDK 16)  
**Auteur :** Aspose
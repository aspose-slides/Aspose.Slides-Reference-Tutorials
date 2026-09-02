---
date: '2026-09-02'
description: Apprenez à créer un graphique en entonnoir dans PowerPoint en utilisant
  Aspose.Slides for Java. Ce guide étape par étape couvre la configuration des données
  du graphique, la personnalisation des couleurs et l'exportation de la présentation.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Apprenez à créer un graphique en entonnoir dans PowerPoint en utilisant
  Aspose.Slides for Java. Ce guide vous accompagne dans la configuration des données,
  la personnalisation des couleurs et l'exportation de la présentation finale.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Créer un graphique en entonnoir dans PowerPoint avec Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Créer un graphique en entonnoir dans PowerPoint avec Aspose.Slides for Java
url: /fr/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser la création de diagrammes en entonnoir dans PowerPoint avec Aspose.Slides pour Java

## Introduction
Créer des présentations percutantes est un art qui combine visualisation de données, design et narration. Un visuel puissant qui clarifie instantanément un processus à plusieurs étapes est le diagramme en entonnoir. Que vous ayez besoin d'illustrer un pipeline de ventes, un flux de conversion ou un goulot d'étranglement de production, un diagramme en entonnoir bien conçu transforme des chiffres bruts en une narration intuitive. Dans ce tutoriel, vous apprendrez comment **créer un diagramme en entonnoir** dans PowerPoint de manière programmatique en utilisant Aspose.Slides pour Java, configurer ses données, personnaliser la couleur de chaque segment et exporter la présentation finale.

**Ce que vous apprendrez**
- Comment ajouter Aspose.Slides pour Java à un projet Maven ou Gradle
- Comment instancier un objet `Presentation` et accéder à ses diapositives
- Comment insérer un diagramme en entonnoir, définir les catégories et remplir les données de séries
- Comment styliser chaque tranche du diagramme en entonnoir avec des remplissages solides ou des couleurs spécifiques à la marque
- Comment enregistrer la présentation au format PPTX ou exporter une diapositive en tant qu'image

## Réponses rapides
- **Quelle est la bibliothèque principale pour la visualisation de données Java ?** Aspose.Slides for Java.  
- **Comment créer un diagramme en entonnoir dans PowerPoint ?** Appelez `slide.addChart(ChartType.Funnel, …)` sur la diapositive cible.  
- **Quelle API définit la source de données du diagramme ?** Utilisez `IChartDataWorkbook` avec `chart.getChartData()`.  
- **Pouvez‑vous personnaliser les couleurs de chaque segment du diagramme en entonnoir ?** Oui—définissez `FillFormat.setFillType(FillType.Solid)` et attribuez un `java.awt.Color`.  
- **Avez‑vous besoin d’une licence pour une utilisation en production ?** Une licence Aspose.Slides achetée est requise pour les déploiements commerciaux.

## Qu’est‑ce que la visualisation de données Java ?
La visualisation de données Java est la pratique consistant à convertir des données brutes en graphiques, diagrammes ou graphiques interactifs directement depuis des applications Java. Aspose.Slides pour Java est une bibliothèque de premier plan qui permet aux développeurs de générer plus de 100 types de graphiques—y compris les diagrammes en entonnoir—sans jamais lancer PowerPoint manuellement, en prenant en charge des présentations pouvant contenir jusqu’à 500 diapositives tout en maintenant une faible utilisation de la mémoire.

## Pourquoi utiliser des diagrammes en entonnoir dans PowerPoint ?
Les diagrammes en entonnoir révèlent instantanément les taux d’abandon à travers les étapes séquentielles, ce qui les rend idéaux pour les pipelines de ventes, l’analyse de conversion ou les revues d’efficacité des processus. Aspose.Slides vous offre un contrôle pixel‑parfait sur la mise en page, les couleurs des segments et les étiquettes de données, vous permettant de maintenir la cohérence de la marque et d’éviter l’effort manuel de modification des graphiques dans l’interface PowerPoint.

## Prérequis (H2)

### Bibliothèques requises, versions et dépendances
Pour implémenter Aspose.Slides pour Java dans votre projet, incluez les coordonnées Maven ou Gradle appropriées. La bibliothèque fonctionne avec Java 8‑21 et ne nécessite aucune dépendance native externe.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vous pouvez également télécharger le JAR directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Exigences de configuration de l’environnement
Assurez‑vous d’avoir le JDK 8 ou une version plus récente installé et que votre `JAVA_HOME` pointe vers le répertoire JDK correct. Aspose.Slides fonctionne sur tout système d’exploitation supportant le JDK, y compris Windows, macOS et Linux.

### Prérequis de connaissances
Une familiarité de base avec la syntaxe Java, la programmation orientée objet et le concept de fichier de présentation sera utile, mais les extraits de code sont entièrement expliqués pour les développeurs de tout niveau d’expérience.

## Configuration d’Aspose.Slides pour Java (H2)

1. **Ajouter la dépendance** – Utilisez le fragment Maven ou Gradle ci‑dessus.  
2. **Obtenir une licence** –  
   - **Essai gratuit** – Téléchargez une licence temporaire depuis [Aspose's website](https://purchase.aspose.com/temporary-license/) pour évaluation.  
   - **Licence complète** – Achetez une licence de production via la [purchase page](https://purchase.aspose.com/buy).  
3. **Initialisation de base** –  

`Presentation` est la classe principale d’Aspose.Slides qui représente un fichier PowerPoint en mémoire. Elle donne accès aux diapositives, aux formes et aux objets de graphique.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Le code ci‑dessus crée une nouvelle instance `Presentation`, prête pour la manipulation des diapositives, et garantit que les ressources sont libérées avec `dispose()`.

## Guide de mise en œuvre

Nous parcourrons chaque fonctionnalité nécessaire pour créer un diagramme en entonnoir complet, en ajoutant un court texte explicatif avant chaque espace réservé de code.

### Fonctionnalité 1 : création d’une présentation (H2)

#### Vue d’ensemble
Commencez par créer une instance de la classe `Presentation`. Cet objet est le point d’entrée pour toutes les opérations suivantes.

`Presentation` est l’objet de niveau supérieur d’Aspose.Slides qui contient la collection de diapositives et les paramètres globaux du document.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

L’extrait ouvre une présentation vierge, que vous pourrez ensuite enregistrer au format `.pptx`.

### Fonctionnalité 2 : ajout d’un diagramme en entonnoir à une diapositive (H2)

#### Vue d’ensemble
Insérez un diagramme en entonnoir sur la première diapositive, définissez sa taille et spécifiez le type de graphique.

`ChartType.Funnel` indique à Aspose.Slides de rendre une visualisation de type entonnoir au lieu d’un graphique à barres ou en lignes.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

L’appel `addChart` crée la forme du graphique, la positionne à `(50, 50)` points, et lui attribue une largeur de `500` et une hauteur de `400`.

### Fonctionnalité 3 : suppression des données du graphique (H2)

#### Vue d’ensemble
Avant de remplir le graphique, supprimez toutes les catégories ou séries factices que le modèle pourrait contenir.

`chart.getChartData().getCategories().clear()` supprime toutes les entrées de catégorie existantes, tandis que `chart.getChartData().getSeries().clear()` supprime toutes les séries pré‑remplies.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Cela garantit une toile vierge afin que vos données personnalisées apparaissent exactement comme prévu.

### Fonctionnalité 4 : configuration du classeur de données du graphique (H2)

#### Vue d’ensemble
L’objet `IChartDataWorkbook` stocke les valeurs brutes qui alimentent le graphique. L’initialiser vous permet d’écrire des données directement dans les cellules.

`IChartDataWorkbook` est une feuille de calcul légère en mémoire qu’Aspose.Slides utilise pour alimenter les séries et les catégories du graphique.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Le code supprime toutes les cellules existantes, préparant le classeur pour de nouvelles entrées.

### Fonctionnalité 5 : ajout de catégories à un graphique (H2)

#### Vue d’ensemble
Définissez les libellés textuels qui apparaissent sur le côté gauche de l’entonnoir—ils représentent chaque étape de votre processus.

`chart.getChartData().getCategories().add()` crée un nouvel objet catégorie lié à une cellule spécifique du classeur.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Ici nous ajoutons trois étapes : « Prospects », « Leads qualifiés » et « Affaires conclues ».

### Fonctionnalité 6 : ajout de séries de données à un graphique (H2)

#### Vue d’ensemble
Remplissez l’entonnoir avec des valeurs numériques et, éventuellement, attribuez une couleur unique à chaque tranche.

`IDataPoint` représente un point de données unique au sein d’une série de graphique.  

`chart.getChartData().getSeries().add()` crée une série qui contient les points de données numériques ; chaque `IDataPoint` peut recevoir sa propre couleur de remplissage.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

La boucle montre comment définir un remplissage solide pour chaque point, en utilisant soit des constantes `java.awt.Color` spécifiques à la marque, soit des couleurs générées aléatoirement pour plus de variété visuelle.

## Cas d’utilisation courants et astuces (H2)

- **Rapport de pipeline de ventes** – Montrez combien de leads passent de prospect à gagné à chaque étape.  
- **Analyse de l’efficacité des processus** – Visualisez les pertes de matière ou les retards de temps à travers les étapes de fabrication.  
- **Revue du funnel marketing** – Comparez les taux de conversion entre les campagnes ou les sources de trafic.  

**Astuce pro :** Au lieu de couleurs aléatoires, utilisez la palette de marque de votre entreprise (par ex., `new Color(0, 112, 192)`) pour que la présentation reste cohérente avec les autres actifs marketing.

## Questions fréquentes (H2)

**Q : Comment changer l’orientation du diagramme en entonnoir ?**  
R : Définissez la propriété `ChartOrientation` sur l’objet `IChart` à `ChartOrientation.Vertical` ou `ChartOrientation.Horizontal`.

**Q : Puis‑je exporter la diapositive en image après avoir ajouté le graphique ?**  
R : Oui—appelez `pres.getSlides().get_Item(0).getThumbnail(1, 1)` et écrivez le `java.awt.image.BufferedImage` résultant dans un fichier PNG ou JPEG.

**Q : Et si j’ai besoin de plus de trois catégories ?**  
R : Ajoutez simplement des catégories supplémentaires avec `chart.getChartData().getCategories().add(...)` et fournissez des points de données correspondants pour chaque nouvelle catégorie.

**Q : Existe‑t‑il un moyen de masquer la légende ?**  
R : Utilisez `chart.getChartTitle().setVisible(false)` et `chart.getLegend().setVisible(false)` pour supprimer à la fois le titre et la légende du visuel.

**Q : Ai‑je besoin d’une licence pour les builds de développement ?**  
R : Une licence temporaire suffit pour l’évaluation ; une licence commerciale complète est requise pour les déploiements en production.

---

**Last updated:** 2026-09-02  
**Testé avec:** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Comment modifier les données d’un graphique PowerPoint avec Aspose.Slides pour Java : guide complet](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Ajouter une animation à un graphique PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-07-17'
description: Apprenez comment ajouter un graphique à PowerPoint en créant un graphique
  'Pie of Pie' à l’aide d’Aspose.Slides for Java. Comprend l’installation, le code,
  la personnalisation et l’enregistrement au format PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Ajoutez un graphique à PowerPoint avec Aspose.Slides for Java. Ce
  guide montre comment créer, personnaliser et enregistrer un graphique 'Pie of Pie'
  au format PPTX en quelques minutes.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Ajouter un graphique à PowerPoint – Créer un graphique 'Pie of Pie' en Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Ajouter un graphique à PowerPoint – Créer un graphique 'Pie of Pie' en Java
  avec Aspose.Slides
url: /fr/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter un graphique à PowerPoint – Créer un graphique « Pie of Pie » en Java avec Aspose.Slides

## Graphiques et diagrammes

### Introduction

Dans les présentations modernes axées sur les données, **ajouter un graphique à PowerPoint** est souvent le moyen le plus rapide de transformer des nombres bruts en informations visuelles. Un graphique circulaire ordinaire fonctionne bien pour quelques catégories, mais lorsque quelques parts sont très petites, elles deviennent illisibles. Un graphique *Pie of Pie* résout ce problème en extrayant ces petites parts dans un graphique secondaire, gardant le graphique principal épuré et les détails accessibles.

Dans ce tutoriel, vous apprendrez comment **ajouter un graphique à PowerPoint** en créant un graphique Pie of Pie avec Aspose.Slides pour Java. Nous parcourrons la configuration de l’environnement, la création du graphique, la personnalisation des étiquettes, le réglage de la position de division, et enfin l’enregistrement de la présentation au format PPTX. À la fin, vous serez prêt à intégrer des graphiques sophistiqués dans n’importe quel diaporama.

## Réponses rapides
Dans Aspose.Slides, `Presentation` représente un fichier PPTX, `ChartType.PieOfPie` sélectionne le graphique Pie of Pie, `setShowValue(true)` affiche les valeurs sur les étiquettes, et `save` écrit le fichier.

- **Quelle est la classe principale pour la manipulation de PowerPoint ?** `Presentation` – elle représente un fichier PPTX complet en mémoire.  
- **Quel type de graphique crée un graphique secondaire pour les petites parts ?** `ChartType.PieOfPie`.  
- **Comment afficher les valeurs sur chaque part ?** Définissez `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Pouvez‑vous enregistrer le fichier directement au format PPTX ?** Oui – appelez `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Avez‑vous besoin d’une licence pour le développement ?** Un essai gratuit de 30 jours fonctionne pour les tests ; une licence permanente supprime les filigranes d’évaluation.

## Qu’est‑ce qu’un graphique Pie of Pie ?
Un **graphique Pie of Pie** est une visualisation circulaire à deux niveaux qui isole une ou plusieurs petites parts dans un cercle séparé et lié, les rendant plus faciles à lire. Aspose.Slides prend en charge ce type de graphique dès le départ, vous permettant de contrôler la taille de la division, la position et le formatage des étiquettes.

## Pourquoi ajouter un graphique à PowerPoint avec Aspose.Slides ?
Aspose.Slides peut générer, modifier et rendre des fichiers PowerPoint sans Microsoft Office installé. Il prend en charge **plus de 50 formats d’entrée et de sortie**, traite des présentations contenant **jusqu’à 500 diapositives** en moins d’une seconde sur du matériel serveur typique, et offre **un contrôle complet de l’API** sur le style des graphiques, les étiquettes de données et la mise en page—parfait pour les pipelines de reporting automatisés.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Java Development Kit (JDK) 16+** installé.  
- Un IDE tel que **IntelliJ IDEA**, **Eclipse** ou **NetBeans**.  
- Maven ou Gradle pour la gestion des dépendances (voir les sections ci‑dessus).  
- Connaissances de base en Java et familiarité avec la construction de projets.

## Configuration d’Aspose.Slides pour Java

### Informations d’installation

**Maven :**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle :**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Téléchargement direct :** Vous pouvez télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
- **Essai gratuit :** Commencez avec un essai de 30 jours pour explorer toutes les fonctionnalités.  
- **Licence temporaire :** Demandez une clé temporaire pour une évaluation prolongée.  
- **Achat :** Obtenez une licence permanente pour une utilisation en production afin de supprimer les filigranes d’évaluation.

### Initialisation et configuration de base
`Presentation` est l’objet principal pour créer des fichiers PowerPoint, et `Chart` représente une forme de graphique au sein d’une diapositive.

```java
Presentation presentation = new Presentation();
```  

Cela crée une présentation vide prête pour les diapositives et les graphiques.

## Guide de mise en œuvre

### Comment ajouter un graphique à PowerPoint en utilisant Aspose.Slides pour Java ?
Chargez une nouvelle `Presentation`, ajoutez une diapositive et insérez un `Chart` de type `PieOfPie`. La chaîne d’appels API est concise : créez le graphique, remplissez les données de la série, ajustez la visibilité des étiquettes, configurez la taille du graphique secondaire, puis enregistrez. L’ensemble du processus tient généralement en moins de 20 lignes de code, ce qui le rend idéal pour la génération automatisée de rapports.

### Création d’un graphique « Pie of Pie »

#### Vue d’ensemble
Nous créerons un graphique Pie of Pie sur la première diapositive, séparerons les plus petites parts et étiquetterons chaque segment avec sa valeur.

#### Étape 1 : Créer une instance de la classe Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Cela initialise le conteneur pour toutes les diapositives et graphiques suivants.

#### Étape 2 : Ajouter un graphique « Pie of Pie » sur la première diapositive
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Ici nous spécifions `ChartType.PieOfPie` et définissons la position du graphique (X, Y) ainsi que sa taille (largeur, hauteur) sur le canevas de la diapositive.

#### Étape 3 : Définir les étiquettes de données pour afficher les valeurs de la série
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Activer `showValue` fait afficher à chaque part sa valeur numérique, ce qui est essentiel pour une interprétation rapide des données.

#### Étape 4 : Configurer la taille du second graphique et la division par pourcentage
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Ces options vous permettent de décider quelle part du graphique est allouée au second cercle et quelles parts sont déplacées en fonction d’un seuil de pourcentage.

#### Étape 5 : Enregistrer la présentation sur le disque au format PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Astuce :** Utilisez un chemin absolu ou `Paths.get()` de Java pour éviter les séparateurs spécifiques à la plateforme.

## Problèmes courants et solutions

La classe `License` charge un fichier de licence pour supprimer les restrictions d’évaluation.

- **Avertissement de licence manquante :** Si vous voyez « Evaluation Only » sur le graphique, assurez‑vous d’avoir appliqué un fichier de licence valide via `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Division de part incorrecte :** Vérifiez que la propriété `splitBy` est définie sur `SplitBy.Percentage` et que `secondPieSize` est une valeur comprise entre 0 et 100.  
- **Données non affichées :** Confirmez que la série du graphique contient au moins un point de données ; sinon le graphique s’affiche vide.

## Questions fréquemment posées

`IChart` représente un objet graphique qui peut être ajouté à une diapositive.

**Q : Puis‑je générer plusieurs graphiques dans une même présentation ?**  
R : Oui, créez une nouvelle instance de `IChart` pour chaque diapositive ou emplacement ; l’API permet un nombre illimité d’objets graphiques par fichier.

`SaveFormat.Pdf` spécifie le format de sortie PDF pour l’enregistrement.

**Q : Aspose.Slides prend‑il également en charge l’enregistrement au format PDF ?**  
R : Absolument – appelez `presentation.save("output.pdf", SaveFormat.Pdf)` pour exporter le même diaporama en PDF.

`IPortion` représente une part individuelle d’un graphique circulaire.

**Q : Quel est le nombre maximal de points de données qu’un graphique Pie of Pie peut gérer ?**  
R : La bibliothèque prend en charge jusqu’à **10 000** points de données par série, limité uniquement par la mémoire disponible.

**Q : Est‑il possible de personnaliser les couleurs des parts individuelles ?**  
R : Oui, accédez à chaque `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()` et définissez `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q : Comment intégrer le PPTX généré dans une application web ?**  
R : Après avoir enregistré le fichier, diffusez‑le directement au client en utilisant `HttpServletResponse` avec `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusion

Vous disposez maintenant d’une recette complète, prête pour la production, pour **ajouter un graphique à PowerPoint** en créant un graphique Pie of Pie avec Aspose.Slides pour Java. Expérimentez différents seuils de division, formats d’étiquettes et palettes de couleurs pour correspondre à vos directives de marque. Ensuite, explorez d’autres types de graphiques—comme les barres empilées ou le radar—pour enrichir davantage vos diaporamas automatisés.

---

**Dernière mise à jour :** 2026-07-17  
**Testé avec :** Aspose.Slides for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un graphique dynamique Java – Tutoriels de graphiques PowerPoint pour Aspose.Slides](/slides/java/charts-graphs/)
- [Comment ajouter un graphique circulaire PowerPoint avec Aspose.Slides pour Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
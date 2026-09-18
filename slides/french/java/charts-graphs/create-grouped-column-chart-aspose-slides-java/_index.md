---
date: '2026-09-17'
description: Apprenez comment ajouter un clustered column chart à une présentation
  PowerPoint, personnaliser le graphique PowerPoint et insérer un graphique de data
  series en utilisant Aspose.Slides for Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Apprenez comment ajouter un clustered column chart à une présentation
  PowerPoint en utilisant Aspose.Slides for Java, y compris les étapes pour insérer
  des data series, personnaliser le grouping et enregistrer le fichier au format PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Ajouter un clustered column chart à PowerPoint avec Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Comment ajouter un clustered column chart dans PowerPoint en utilisant Aspose.Slides
  for Java
url: /fr/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un graphique à colonnes groupées dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Lorsque vous devez **ajouter un graphique à colonnes groupées** à une présentation PowerPoint, un visuel clair peut transformer des chiffres bruts en une histoire immédiatement compréhensible. Le faire manuellement dans PowerPoint peut être chronophage, surtout si vous devez générer de nombreuses diapositives de façon programmatique. **Aspose.Slides pour Java** élimine les frictions – il vous permet de créer, personnaliser un graphique PowerPoint et d’insérer une série de données avec seulement quelques lignes de code.

Dans ce tutoriel, vous apprendrez à :
- Initialiser une nouvelle présentation PowerPoint avec Aspose.Slides pour Java.  
- **Ajouter un graphique à la diapositive** et le configurer comme un graphique à colonnes groupées.  
- **Créer un graphique à colonnes groupées** en définissant des niveaux de regroupement pour les catégories.  
- **Insérer une série de données** afin que vos données soient affichées correctement.  
- Enregistrer la présentation finale au format PPTX.

## Réponses rapides
- **Quelle est la classe principale ?** `Presentation` de `com.aspose.slides`.  
- **Quel type de graphique est utilisé ?** `ChartType.ClusteredColumn`.  
- **Ai‑je besoin d’une licence pour les tests ?** Un essai gratuit fonctionne, mais une licence supprime les limites d’évaluation.  
- **Quelle version de Java est prise en charge ?** JDK 16 ou plus récent (l’exemple utilise JDK 16).  
- **Comment exécuter l’exemple ?** Ajoutez la dépendance Maven/Gradle, compilez et exécutez la méthode `main`.

## Qu’est‑ce que « ajouter un graphique à colonnes groupées » ?

Un graphique à colonnes groupées affiche plusieurs séries de données côte à côte pour chaque catégorie, vous permettant de comparer les valeurs entre groupes dans un même visuel. Il est idéal pour les ventes trimestrielles, les résultats d’enquêtes ou tout scénario où vous devez contraster plusieurs ensembles de données au sein de la même catégorie.

## Pourquoi utiliser Aspose.Slides pour ajouter un graphique à colonnes groupées ?

Vous pouvez générer des dizaines de diapositives automatiquement, personnaliser chaque élément visuel et exécuter le code sur n’importe quel OS supportant Java—sans besoin d’une installation Microsoft Office. Aspose.Slides prend en charge **plus de 50 types de graphiques** et peut traiter des présentations contenant **jusqu’à 500 diapositives** sans charger le fichier complet en mémoire, ce qui le rend adapté aux pipelines de reporting à grande échelle.

## Prérequis

- Bibliothèque **Aspose.Slides pour Java** (la dernière version recommandée).  
- JDK 16 ou ultérieur.  
- Outil de construction Maven ou Gradle (ou vous pouvez ajouter le JAR manuellement).  
- Un IDE ou éditeur de texte pour exécuter du code Java.

## Installation d’Aspose.Slides pour Java

Ajoutez la bibliothèque à votre projet en utilisant l’un des scripts de construction suivants.

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

Vous pouvez également télécharger directement la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence

Avant de déployer en production, obtenez une licence :
- **Essai gratuit** – explorez toutes les fonctionnalités sans achat.  
- **Licence temporaire** – évaluez les capacités étendues pendant une courte période.  
- **Licence complète** – débloquez l’utilisation illimitée. Obtenez‑la sur la [page d’achat d’Aspose](https://purchase.aspose.com/buy).

## Comment ajouter un graphique à colonnes groupées dans PowerPoint avec Aspose.Slides pour Java ?

Chargez une nouvelle `Presentation`, ajoutez une diapositive, insérez un `Chart` de type `ChartType.ClusteredColumn`, remplissez son classeur interne avec les catégories et les séries, puis enregistrez le fichier au format PPTX. Cette séquence crée un graphique à colonnes groupées pleinement fonctionnel avec seulement quelques appels d’API.

### Initialiser la présentation

`Presentation` est la classe qui représente un fichier PowerPoint en mémoire, vous permettant d’ajouter des diapositives, des formes et des graphiques de façon programmatique.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Ajouter le graphique à la diapositive

`ChartType.ClusteredColumn` indique à Aspose.Slides de rendre un graphique à colonnes groupées.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Préparer le classeur de données du graphique

Le graphique stocke ses données dans un classeur interne. Le nettoyer vous donne une toile vierge pour des données personnalisées.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Ajouter des catégories avec des niveaux de regroupement

Regrouper les catégories crée l’effet de graphique à colonnes groupées. Chaque catégorie peut appartenir à un groupe logique qui apparaît dans les libellés d’axe.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Ajouter des séries de données au graphique

Les objets `Series` représentent les colonnes individuelles du graphique. Ajouter plusieurs séries produit des colonnes côte à côte pour chaque catégorie.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Enregistrer la présentation avec le graphique

Enregistrer la `Presentation` crée un fichier PPTX standard qui peut être ouvert dans n’importe quel visualiseur PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Applications pratiques

- **Rapports d’entreprise** – comparer le chiffre d’affaires trimestriel selon les régions.  
- **Recherche académique** – présenter les résultats d’expériences regroupés par conditions de test.  
- **Gestion de projet** – visualiser les taux d’achèvement des tâches pour plusieurs équipes sur une même diapositive.

## Considérations de performance

- **Gestion de la mémoire** – libérez les classeurs volumineux après utilisation.  
- **Opérations par lots** – évitez de mettre à jour le graphique dans des boucles serrées ; collectez d’abord les données, puis appliquez‑les.  
- **Optimisations intégrées** – Aspose.Slides propose des méthodes comme `Presentation.optimize()` pour les gros fichiers, réduisant l’empreinte mémoire jusqu’à **30 %**.

## Pièges courants & astuces

- **Piège :** Oublier de nettoyer les séries/catégories existantes peut entraîner des doublons de données.  
  **Astuce :** Appelez toujours `clear()` avant de peupler de nouvelles données.  
- **Piège :** Utiliser une mauvaise adresse de cellule (par ex., `"c2"` au lieu de `"C2"`).  
  **Astuce :** Les références de cellules sont insensibles à la casse, mais gardez‑les cohérentes pour la lisibilité.  
- **Astuce :** Utilisez `setGroupingItem` pour créer des libellés de groupe pertinents ; ils apparaissent automatiquement dans la légende du graphique.

## Questions fréquentes

**Q1 : Comment ajouter plusieurs séries à mon graphique ?**  
R1 : Appelez `ch.getChartData().getSeries().add()` de façon répétée, en fournissant un nom unique et des points de données pour chaque série.

**Q2 : Quels sont les problèmes courants avec les graphiques Aspose.Slides ?**  
R2 : Les problèmes proviennent souvent de plages de données incohérentes ou de cellules manquantes dans le classeur. Vérifiez que chaque catégorie et chaque point de données possède une cellule correspondante.

**Q3 : Puis‑je utiliser Aspose.Slides avec d’autres langages de programmation ?**  
R3 : Oui, Aspose propose des bibliothèques équivalentes pour .NET, C++, Python, et plus encore.

**Q4 : Comment mettre à jour un graphique existant dans une présentation ?**  
R4 : Chargez la présentation, localisez le graphique via `slide.getShapes().get_Item(index)`, puis modifiez ses séries ou son formatage selon vos besoins.

**Q5 : Existe‑t‑il des limitations sur les types de graphiques avec Aspose.Slides ?**  
R5 : La bibliothèque prend en charge plus de **50 types de graphiques** et en ajoute continuellement de nouveaux ; consultez toujours la documentation la plus récente pour la liste à jour.

## Ressources

- **Documentation :** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Téléchargement :** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Achat :** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Essai gratuit :** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Licence temporaire :** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum de support :** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-09-17  
**Testé avec :** Aspose.Slides pour Java 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Create Chart Creation Guide in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
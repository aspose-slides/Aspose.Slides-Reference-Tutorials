---
date: '2026-07-17'
description: Apprenez à ajouter des graphiques Sunburst dans PowerPoint en utilisant
  Aspose Slides for Java. Ce guide étape par étape couvre la configuration, la création
  de graphiques, la personnalisation et des cas d’utilisation concrets.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Comment ajouter des graphiques Sunburst dans PowerPoint en utilisant
  Aspose Slides for Java. Suivez ce tutoriel pour configurer la bibliothèque, créer
  un graphique, personnaliser les points de données et l’appliquer à des projets réels.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Comment ajouter des graphiques Sunburst dans PowerPoint avec Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Comment ajouter des graphiques Sunburst dans PowerPoint avec Aspose (Java)
url: /fr/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter des graphiques Sunburst dans PowerPoint avec Aspose (Java)

## Introduction

Ajouter un graphique Sunburst à une présentation PowerPoint peut instantanément transformer un tableau de données plat en une hiérarchie visuelle attrayante. Dans ce tutoriel, vous apprendrez **comment ajouter des graphiques Sunburst** dans PowerPoint en utilisant Aspose.Slides pour Java, de la configuration de l'environnement à l'ajustement fin des couleurs et des libellés. Que vous construisiez un tableau de bord de ventes, une ventilation de projet‑tâche ou une présentation éducative, les étapes ci‑dessous vous fourniront une solution prête pour la production.

**Ce que vous apprendrez**
- Comment configurer Aspose.Slides dans un projet Maven ou Gradle
- Comment créer une nouvelle présentation et insérer un graphique Sunburst
- Comment personnaliser les points de données, les libellés et les couleurs de remplissage
- Scénarios réels où les graphiques Sunburst brillent

Commençons et voyons à quel point il est facile de transformer des données hiérarchiques brutes en un visuel PowerPoint soigné.

## Réponses rapides
- **Bibliothèque principale ?** Aspose.Slides for Java  
- **Type de graphique pris en charge ?** Sunburst (hiérarchique radial)  
- **Version minimale de Java ?** JDK 16  
- **Temps d'implémentation typique ?** 10‑15 minutes pour un graphique de base  
- **Licence nécessaire pour la production ?** Oui, une licence Aspose valide  

## Qu'est‑ce qu'un graphique Sunburst ?
Un graphique Sunburst est un diagramme radial qui visualise des données hiérarchiques en imbriquant des anneaux à partir d'un point central. Il est parfait pour montrer des relations à plusieurs niveaux telles que les structures organisationnelles, les catégories de produits ou les arborescences de systèmes de fichiers. Chaque anneau concentrique représente un niveau de la hiérarchie, et la taille de chaque segment reflète sa valeur quantitative, permettant aux spectateurs de saisir rapidement à la fois la structure et l'ampleur.

## Pourquoi utiliser Aspose.Slides pour Java ?
Aspose.Slides prend en charge **plus de 50 types de graphiques** et peut manipuler des présentations contenant **jusqu'à 10 000 diapositives** sans charger le fichier complet en mémoire, offrant ainsi des performances élevées pour les rapports à l'échelle de l'entreprise. Il fonctionne sur plusieurs plates‑formes, propose une couverture API étendue et inclut des options de licence robustes qui suppriment les limites d'évaluation, ce qui le rend idéal pour les environnements de production.

## Prérequis
- **Java Development Kit (JDK)** 16 ou plus récent
- **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur compatible Java
- Familiarité de base avec la syntaxe Java et les outils de construction Maven/Gradle

## Configuration d'Aspose.Slides pour Java

### Dépendance Maven
Ajoutez l'artifact Maven d'Aspose.Slides à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dépendance Gradle
Si vous préférez Gradle, incluez la ligne suivante dans `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger le JAR le plus récent directement depuis la page officielle des versions : [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Obtention de licence
Pour exécuter sans limites d'évaluation, obtenez une licence :
- **Essai gratuit** – licence temporaire pour une évaluation rapide.
- **Licence temporaire** – demandez‑en une sur le [site Web d'Aspose](https://purchase.aspose.com/temporary-license).
- **Achat complet** – achetez un abonnement pour une utilisation en production illimitée.

### Initialisation de base
La classe `Presentation` est le point d'entrée pour créer ou ouvrir des fichiers PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guide d'implémentation

### Comment ajouter un graphique Sunburst à une présentation PowerPoint en utilisant Aspose.Slides pour Java ?
Chargez une nouvelle `Presentation`, ajoutez une diapositive, insérez un `IChart` de type `ChartType.Sunburst`, puis appelez `save`. Ce schéma concis en trois étapes crée un graphique Sunburst entièrement fonctionnel, prêt à être personnalisé davantage.

#### Étape 1 : Initialiser la présentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Étape 2 : Ajouter le graphique Sunburst
L'interface `IChart` définit un objet graphique qui peut être placé sur n'importe quelle diapositive. Ici, nous ajoutons un graphique Sunburst aux coordonnées (100, 100) avec une taille de 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Étape 3 : Enregistrer la présentation
Enregistrez toujours vos modifications en appelant `save`. Vous pouvez choisir PPTX, PDF ou l'un des plus de 50 formats de sortie pris en charge.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modifier les points de données du graphique

#### Vue d'ensemble
Vous pouvez personnaliser chaque tranche du Sunburst — libellés, couleurs et visibilité — via la collection de points de données du graphique.

#### Étape 1 : Accéder à la collection de points de données
La première série du graphique contient une collection d'objets `IChartDataPoint` qui représentent chaque tranche.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Étape 2 : Afficher la valeur d'un point de données spécifique
Définissez `IsValueShown` sur `true` pour le point de données souhaité afin d'afficher sa valeur numérique directement sur la tranche.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Étape 3 : Modifier les formats de libellé
Ajustez la visibilité du libellé, la couleur de la police et l'arrière‑plan pour améliorer la lisibilité.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Étape 4 : Définir la couleur de remplissage des points de données
Personnalisez la couleur de remplissage des tranches individuelles pour correspondre à la palette de votre marque ou mettre en évidence des segments clés.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Étape 5 : Enregistrer la présentation modifiée
Conservez le graphique personnalisé en enregistrant à nouveau la présentation.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Applications pratiques

1. **Analyse commerciale** – Visualiser les ventes par région → gamme de produits → SKU dans une vue radiale unique.  
2. **Gestion de projet** – Montrer les structures de répartition du travail, en descendant des phases aux tâches puis aux sous‑tâches.  
3. **Éducation** – Cartographier les hiérarchies de programmes, telles que départements → cours → modules.  

## Considérations de performance

- **Efficacité mémoire :** Aspose.Slides diffuse les données, de sorte qu'un deck de 500 pages avec plusieurs graphiques reste sous 200 Mo de RAM.  
- **Collecte des déchets :** Libérez les objets diapositive (`slide.dispose()`) lorsqu'ils ne sont plus nécessaires afin d'éviter les fuites de mémoire.  

## Questions fréquemment posées

**Q : Qu'est‑ce qu'un graphique Sunburst ?**  
R : Un graphique Sunburst visualise des données hiérarchiques sous forme d'anneaux concentriques, chaque anneau représentant un niveau de la hiérarchie.

**Q : Comment installer Aspose.Slides pour Java avec Maven ?**  
R : Ajoutez la dépendance Maven indiquée dans la section « Dépendance Maven » à votre `pom.xml` et exécutez `mvn clean install`.

**Q : Puis‑je personnaliser d'autres types de graphiques avec Aspose.Slides ?**  
R : Oui, la bibliothèque prend en charge plus de 50 types de graphiques, y compris les graphiques en colonnes, en lignes, circulaires et radar.

**Q : Ma présentation ne s’enregistre pas — que dois‑je vérifier ?**  
R : Vérifiez que le chemin du fichier est correct, que le répertoire existe et que vous avez les permissions d’écriture. Assurez‑vous également que la méthode `Presentation.save()` est appelée.

**Q : Où puis‑je obtenir plus d'aide ou d'exemples ?**  
R : Consultez le [forum Aspose](https://forum.aspose.com/c/slides/11) ou la [référence officielle d'Aspose.Slides](https://reference.aspose.com/slides/java/).

## Ressources
- **Documentation :** [Référence Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Référence (minuscule) :** [référence Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Forum communautaire :** [Forum Aspose](https://forum.aspose.com/c/slides)  
- **Téléchargements :** [Téléchargements Aspose.Slides](https://releases.aspose.com/slides/java)  

---

**Dernière mise à jour :** 2026-07-17  
**Testé avec :** Aspose.Slides for Java 24.12  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animer des graphiques PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Créer un graphique en Java avec Aspose.Slides – ajouter et valider des graphiques](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
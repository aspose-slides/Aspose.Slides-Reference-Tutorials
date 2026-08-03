---
date: '2026-08-01'
description: Apprenez comment utiliser une licence Aspose Slides pour créer et personnaliser
  des pie charts dans des présentations Java. Suivez les instructions étape par étape
  pour configurer les données du pie chart et ajouter des chart slides efficacement.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Apprenez comment utiliser une licence Aspose Slides pour créer et
  personnaliser des pie charts dans des présentations Java. Suivez les instructions
  étape par étape pour configurer les données du pie chart et ajouter des chart slides
  efficacement.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Créer des pie charts en Java avec une licence Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Créer des pie charts en Java avec une licence Aspose Slides
url: /fr/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques circulaires dans les présentations Java à l'aide d'Aspose.Slides

## Introduction

Si vous devez produire des présentations d'aspect professionnel, **une licence Aspose Slides** vous donne le pouvoir de générer et de styliser des graphiques de façon programmatique. Dans ce guide, vous apprendrez comment créer un graphique circulaire, configurer ses données et l'intégrer dans un diaporama Java — le tout sans dépendre de Microsoft PowerPoint. Nous parcourrons la configuration, le flux du code et les meilleures pratiques afin que vous puissiez livrer des rapports visuels soignés en quelques minutes.

**Ce que vous apprendrez :**
- Configurer Aspose.Slides pour Java avec une licence valide
- Étapes pour créer et personnaliser un graphique circulaire
- Comment configurer les données du graphique circulaire et ajouter des diapositives de graphique
- Écueils courants et astuces de performance

Commençons par vérifier que votre environnement est prêt.

## Réponses rapides
- **Que permet la licence Aspose Slides ?** Création de graphiques complète, exportation en PDF/HTML et suppression des filigranes.
- **Quelle version de Java est requise ?** JDK 16 ou plus récent.
- **Ai‑je besoin de Maven ou Gradle ?** Les deux fonctionnent ; la bibliothèque est disponible via les deux.
- **Combien de points de données un graphique circulaire peut‑il contenir ?** Jusqu'à 10 000 points sans problème de mémoire.
- **Puis‑je exporter la diapositive en image ?** Oui – PNG, JPEG, SVG et plus sont pris en charge.

## Prérequis
Avant de commencer, vérifiez que vous disposez de :
- **Bibliothèques requises :** Aspose.Slides pour Java (version 25.4 ou ultérieure) – cette version prend en charge les derniers formats de fichiers et les optimisations de performance.
- **Configuration de l'environnement :** JDK 16+ installé et configuré dans votre IDE ou système de build.
- **Connaissances de base :** Familiarité avec Java, Maven ou Gradle, et les concepts de programmation orientée objet.

## Configuration d'Aspose.Slides pour Java
Pour utiliser Aspose.Slides pour Java, incluez‑le dans votre projet. Voici comment ajouter la dépendance avec les outils de build les plus courants :

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

**Téléchargement direct :** Vous pouvez également télécharger le JAR le plus récent depuis [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Acquisition de licence
Aspose propose un essai gratuit qui débloque toutes les fonctionnalités, mais une **licence Aspose Slides valide** est requise pour une utilisation en production afin de supprimer les filigranes d'évaluation et d'obtenir des avantages de performance. Les options d'achat sont répertoriées sur la [page d'achat](https://purchase.aspose.com/buy). Après avoir obtenu le fichier de licence, chargez‑le une fois au démarrage de l'application :

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Guide d'implémentation

### Créer et ajouter un graphique circulaire à la présentation

#### Vue d'ensemble
Cette section explique comment créer un graphique circulaire, configurer ses séries de données et intégrer le graphique dans une diapositive. Vous verrez le flux complet depuis l'initialisation de l'objet présentation jusqu'à l'enregistrement du fichier final.

#### Étape 1 : Initialiser la présentation  
`Presentation` is Aspose.Slides' top‑level object that represents a PowerPoint file in memory. Creating an instance gives you a blank slide deck ready for modification.

```java
demo.Presentation pres = new demo.Presentation();
```  
Cette ligne crée une nouvelle présentation où toutes les modifications ultérieures seront appliquées.

#### Étape 2 : Ajouter un graphique circulaire à la diapositive  
`Chart` is the class that encapsulates chart objects, including pie charts. Adding a chart to a slide is a single method call that specifies position and size.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` et `yPosition` définissent le coin supérieur gauche du graphique.  
- `width` et `height` définissent l'empreinte visuelle du graphique sur la diapositive.

#### Étape 3 : Configurer les données du graphique circulaire  
`ChartData` holds the data series for a chart.  
**How do I configure pie chart data?**  
Provide a concise answer first: Use the `ChartData` collection to add a series, then populate `ChartDataPoint` objects with numeric values and category names. This approach lets you display up to 10 000 slices while preserving label formatting. After setting the data, you can customize colors, legends, and data labels to match your corporate style guide.

Now, here’s the code that adds two categories and shows their labels:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
L'extrait crée une série de données, insère deux points et active les libellés de catégorie sur le graphique.

#### Étape 4 : Enregistrer la présentation  
Finally, persist the presentation to a file format of your choice (PPTX, PDF, or PNG). The `save` method respects the active license, ensuring no trial watermarks appear.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Problèmes courants et solutions
- **Erreur de licence manquante :** Assurez‑vous que le chemin du fichier de licence est correct et que l'objet `License` est instancié avant tout appel à Aspose.Slides.
- **Graphique vide :** Vérifiez que la série `ChartData` contient au moins un `ChartDataPoint`. Une série vide entraîne une zone de graphique vide.
- **Lenteur de performance avec de grands ensembles de données :** Utilisez `presentation.getSlides().removeAt(index)` pour supprimer les diapositives inutilisées et appelez `System.gc()` après un traitement intensif.

## Applications pratiques
- **Rapports d'entreprise :** Visualisez la part de marché ou la répartition des revenus par région avec un seul graphique circulaire.
- **Présentations académiques :** Affichez les résultats d'enquêtes ou d'expériences dans un format clair et digeste.
- **Tableaux de bord de projet :** Représentez les pourcentages d'achèvement des tâches ou l'allocation des ressources instantanément sur une diapositive.

Vous pouvez également combiner Aspose.Slides avec JDBC pour extraire des données en temps réel depuis une base de données, générant des graphiques à jour pour les briefings exécutifs hebdomadaires.

## Considérations de performance
Lors du traitement de présentations contenant de nombreuses images haute résolution ou de grands ensembles de données :
- Libérez les objets rapidement en utilisant `try‑with‑resources` ou des appels explicites à `dispose()`.
- Activez le chargement paresseux des ressources de diapositives pour maintenir une faible utilisation de la mémoire.
- Pour le traitement par lots, réutilisez une seule instance `Presentation` lorsque cela est possible afin de réduire la surcharge JVM.

## Conclusion
Vous disposez maintenant d’un flux de travail complet et prêt pour la production pour créer des graphiques circulaires en Java à l’aide d’une **licence Aspose Slides**. Expérimentez d’autres types de graphiques — barres, lignes ou anneaux — pour enrichir davantage vos diapositives. Ensuite, explorez les capacités d’exportation de l’API pour générer automatiquement des rapports PDF ou des images PNG.

## Questions fréquentes

**Q : Comment ajouter plusieurs graphiques à une même diapositive ?**  
R : Appelez `slide.getShapes().addChart()` pour chaque graphique, en fournissant des coordonnées et des dimensions uniques pour chaque instance.

**Q : Quelles sont les alternatives à Aspose.Slides pour Java ?**  
R : Apache POI et JFreeChart sont des alternatives courantes, mais elles ne disposent pas des options d’exportation complètes et du modèle de licence d’Aspose.

**Q : Puis‑je convertir ma présentation en d’autres formats avec Aspose.Slides ?**  
R : Oui — exportation en PDF, XPS, HTML, PNG, JPEG, SVG, et plus avec un seul appel `save`.

**Q : Comment gérer la licence pour une grande équipe de développement ?**  
R : Achetez une licence entreprise qui couvre plusieurs développeurs et serveurs ; contactez les ventes d’Aspose pour des remises sur volume.

**Q : Que faire si les données de mon graphique sont mises à jour fréquemment ?**  
R : Intégrez Aspose.Slides à une source de données (par ex., une requête SQL) et reconstruisez le graphique à l’exécution ; l’API prend en charge la liaison dynamique des données.

## Ressources
- **Documentation :** [Référence Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- **Téléchargement :** [Dernières versions](https://releases.aspose.com/slides/java/)
- **Achat :** [Acheter une licence](https://purchase.aspose.com/buy)
- **Essai gratuit :** [Essayer Aspose.Slides gratuitement](https://releases.aspose.com/slides/java/)
- **Licence temporaire :** [Obtenir une licence temporaire](https://purchase.aspose.com/temporary-license/)
- **Support :** [Forum Aspose](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-01  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Tutoriels associés

- [Comment ajouter et configurer des graphiques dans les présentations à l'aide d'Aspose.Slides pour Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Créer et personnaliser des graphiques dans les présentations Java à l'aide d'Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Comment créer et configurer des présentations avec Aspose.Slides Java : guide étape par étape](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
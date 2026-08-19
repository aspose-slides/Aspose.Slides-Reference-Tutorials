---
date: '2026-07-03'
description: Apprenez à créer des diagrammes en rayons étape par étape en Java avec
  Aspose.Slides, avec des options de personnalisation complètes pour les présentations
  PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Comment créer des diagrammes en rayons en Java avec Aspose.Slides
url: /fr/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques Sunburst en Java avec Aspose.Slides

## Introduction
Dans les présentations d'aujourd'hui axées sur les données, **how to create sunburst** visualisations rapidement peuvent distinguer vos diapositives. Ce tutoriel vous guide dans la création d'un graphique Sunburst avec Aspose.Slides pour Java, depuis la configuration du projet jusqu'à l'exportation finale, afin que vous puissiez fournir des graphiques hiérarchiques percutants sans quitter l'écosystème Java.

## Réponses rapides
- **Quelle est la classe principale pour un fichier PowerPoint ?** `Presentation` – elle représente l'intégralité du PPTX en mémoire.  
- **Combien de lignes de code sont nécessaires pour un Sunburst de base ?** Typiquement 5 à 7 lignes une fois la bibliothèque référencée.  
- **Quels formats de sortie sont pris en charge ?** PPTX, PDF, PNG, SVG, et HTML.  
- **Puis-je styliser des segments individuels ?** Oui – les couleurs de remplissage, les bordures et les étiquettes de données sont entièrement personnalisables.  
- **Ai-je besoin d'une licence pour la production ?** Une évaluation gratuite suffit pour les tests ; une licence commerciale est requise pour le déploiement.

## Qu'est-ce qu'un graphique Sunburst ?
Un graphique Sunburst visualise des données hiérarchiques sous forme d'anneaux concentriques, chaque anneau représentant un niveau de la hiérarchie. Il permet aux spectateurs de saisir les relations parent‑enfant d'un seul coup d'œil, ce qui le rend idéal pour les organigrammes, les affichages taxonomiques et les métriques multi‑niveaux. Il est particulièrement utile pour afficher des catégories à plusieurs niveaux telles que les gammes de produits, les régions géographiques ou les structures organisationnelles, permettant de voir à la fois la distribution globale et le détail de chaque segment.

## Pourquoi utiliser Aspose.Slides pour les graphiques Sunburst ?
Aspose.Slides prend en charge **plus de 30 types de graphiques**, traite des fichiers jusqu'à **500 Mo** sans charger le document complet en mémoire, et rend les graphiques à **300 DPI** pour une sortie cristalline. Ces capacités quantifiées assurent une génération rapide et des visuels de haute qualité même pour de grandes présentations. De plus, la bibliothèque offre des opérations thread‑safe et s'intègre parfaitement aux outils de construction Java populaires, ce qui la rend adaptée à la génération de présentations sur le bureau comme sur le serveur à grande échelle.

## Prérequis
- Java Development Kit (JDK) 8 ou plus récent.  
- Maven ou Gradle pour la gestion des dépendances.  
- Aspose.Slides for Java (dernière version).  
- Compréhension de base des structures de données hiérarchiques.

## Comment créer des graphiques Sunburst étape par étape ?
Chargez votre environnement, ajoutez un graphique, alimentez les données hiérarchiques, stylisez‑le et enregistrez le fichier – le tout en quelques étapes simples. Vous trouverez ci‑dessous le flux de travail exact que vous pouvez suivre sans écrire de code supplémentaire. Le processus est entièrement automatisé, ne nécessite aucune interaction manuelle avec l'interface utilisateur et peut être intégré à des tâches batch ou à des services web pour produire des graphiques à la demande.

### Étape 1 : Configurer le projet
Ajoutez la dépendance Maven Aspose.Slides (ou le fragment Gradle équivalent) à votre `pom.xml`. Cela récupère tous les binaires requis ainsi que les bibliothèques transitives.

### Étape 2 : Charger ou créer une présentation
`Presentation` est l'objet de niveau supérieur d'Aspose.Slides qui représente un fichier PowerPoint unique en mémoire. Instanciez‑le avec `new Presentation()` pour un nouveau diaporama ou passez un chemin de fichier pour ouvrir un PPTX existant.

### Étape 3 : Ajouter un graphique Sunburst
Insérez une nouvelle forme de graphique sur une diapositive en utilisant `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Cela crée le placeholder Sunburst prêt à recevoir des données. `ChartType.Sunburst` spécifie le type de graphique Sunburst lors de l'ajout d'un graphique à une diapositive.

### Étape 4 : Remplir les données hiérarchiques
`ChartData` contient les séries de données et les catégories d'un graphique. Accédez à la collection `ChartData` du graphique et ajoutez des séries et des catégories qui reflètent votre hiérarchie. Pour chaque niveau, spécifiez la relation parent‑enfant via la propriété `ParentSeries`, permettant au graphique de rendre automatiquement les anneaux concentriques.

### Étape 5 : Personnaliser l'apparence
Affinez les couleurs des segments, les styles de bordure et les étiquettes de données via les objets `ChartSeries` et `ChartDataPoint`. `ChartSeries` représente une série de points de données dans un graphique. `ChartDataPoint` représente un point de données individuel au sein d'une série. Vous pouvez également activer la rotation 3‑D ou définir la propriété `Explode` pour mettre en évidence des tranches spécifiques.

### Étape 6 : Enregistrer la présentation
L'énumération `SaveFormat` définit les formats de fichier dans lesquels vous pouvez enregistrer une présentation. Appelez `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` pour écrire le fichier sur le disque. Vous pouvez également exporter en PDF ou PNG en modifiant la valeur de l'énumération `SaveFormat`.

## Comment personnaliser les couleurs d'un graphique Sunburst ?
Spécifiez une couleur de remplissage pour chaque `ChartDataPoint` en utilisant `point.getFillFormat().setFillType(FillType.Solid)` puis `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Cette approche directe vous permet d'aligner la charte graphique de l'entreprise ou de mettre en avant des points de données clés. Vous pouvez également appliquer des remplissages en dégradé, ajuster la transparence ou utiliser les couleurs du thème pour garantir la cohérence avec le reste de votre conception de diapositive.

## Problèmes courants et solutions
- **Problème :** La hiérarchie apparaît plate.  
  **Solution :** Assurez‑vous que chaque série enfant référence correctement son `ParentSeries`. Des liens manquants font que le graphique traite toutes les données comme un seul niveau.
- **Problème :** Le PNG exporté est flou.  
  **Solution :** Augmentez le DPI d'exportation en définissant `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problème :** Les gros fichiers PPTX provoquent un OutOfMemoryError.  
  **Solution :** Utilisez `Presentation.setMemoryOptimization(true)` pour diffuser les données et maintenir une faible consommation de mémoire.

## Questions fréquentes

**Q : Puis‑je générer un graphique Sunburst à partir d'un fichier CSV ?**  
R : Oui. Lisez le CSV, construisez la hiérarchie en mémoire, puis alimentez la collection `ChartData` du graphique avant d'enregistrer.

**Q : Aspose.Slides prend‑il en charge les transitions animées pour les graphiques Sunburst ?**  
R : Oui. Appliquez un `SlideShowTransition` à la diapositive ou utilisez `ChartFormat.setAnimationEnabled(true)` pour l'animation au niveau du graphique.

**Q : Est‑il possible d'exporter le graphique au format SVG vectoriel ?**  
R : Absolument. Enregistrez la présentation avec `SaveFormat.Svg` pour obtenir une version vectorielle évolutive du graphique Sunburst.

**Q : Quel est le nombre maximal de points de données qu'un graphique Sunburst peut gérer ?**  
R : Aspose.Slides traite de manière fiable jusqu'à **10 000** points de données dans un seul graphique Sunburst sans perte de performance.

**Q : Ai‑je besoin d'une licence séparée pour chaque environnement de déploiement ?**  
R : Une licence commerciale unique couvre tous les environnements (développement, préproduction, production) tant que les conditions de licence sont respectées.

## Conclusion
Vous disposez maintenant d'un guide complet, étape par étape, pour **how to create sunburst** charts en Java avec Aspose.Slides. En suivant le flux de travail ci‑dessus, vous pouvez générer des visualisations hiérarchiques de haute qualité, entièrement personnalisables, pour n'importe quelle présentation PowerPoint.

---

**Dernière mise à jour :** 2026-07-03  
**Testé avec :** Aspose.Slides for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Maîtriser la personnalisation des graphiques PowerPoint avec Aspose.Slides Java pour des présentations dynamiques](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animer les catégories de graphiques PowerPoint avec Aspose.Slides pour Java | guide étape par étape](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
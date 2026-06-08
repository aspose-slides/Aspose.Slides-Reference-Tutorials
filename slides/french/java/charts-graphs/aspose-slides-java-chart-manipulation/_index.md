---
date: '2026-06-08'
description: Apprenez comment créer un graphique PowerPoint en Java avec Aspose.Slides,
  configurer la dépendance Maven, ajouter un graphique à colonnes groupées et enregistrer
  au format PPTX.
keywords:
- java create powerpoint chart
- maven dependency aspose slides
- chart manipulation in presentations
- java presentation library
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create powerpoint chart with Aspose.Slides, set up
    the Maven dependency, add a clustered column chart, and save as PPTX.
  headline: Java create powerpoint chart using Aspose.Slides
  type: TechArticle
- questions:
  - answer: Use the `ChartType` enum (e.g., `ChartType.Pie`, `ChartType.Line`) when
      calling `addChart`.
    question: How do I add other chart types?
  - answer: Yes, modify the series’ fill format or the chart’s palette via the `IChart`
      API.
    question: Can I customize chart colors?
  - answer: Verify that the output directory path is correct, exists, and is writable.
      Also ensure no other process holds a lock on the file.
    question: My presentation won’t save—what’s wrong?
  - answer: Process slides in batches, dispose of each `Presentation` after use, and
      consider increasing the JVM heap size if needed.
    question: How can I handle very large presentations efficiently?
  - answer: A free trial is available for evaluation, but a purchased license is required
      for commercial deployment.
    question: Is Aspose.Slides free for commercial projects?
  type: FAQPage
title: Créer un graphique PowerPoint en Java avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java créer un graphique PowerPoint avec Aspose.Slides

## Introduction
Dans ce guide, vous créerez **java create powerpoint chart** sans effort avec Aspose.Slides pour Java. Nous parcourrons l'installation du package Maven ou Gradle, l'initialisation d'une `Presentation`, l'insertion d'un graphique à colonnes groupées, le réglage fin de la zone de tracé, et enfin l'enregistrement du résultat sous forme de fichier PPTX. À la fin, vous disposerez d'un extrait prêt à l'emploi qui fonctionne dans n'importe quel projet Java, que vous construisiez un rapport d'affaires ou un générateur de diapositives automatisé.

**Ce que vous apprendrez**
- Comment ajouter la dépendance Maven pour Aspose.Slides  
- Comment **java create powerpoint chart** et insérer un graphique à colonnes groupées  
- Comment ajuster la zone de tracé (position, taille, cible de mise en page)  
- Comment **save presentation as pptx** avec un nettoyage approprié des ressources  

Prêt à transformer des données brutes en diapositives accrocheuses ? Commençons !

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.Slides for Java (available via Maven or Gradle).  
- **Quel type de graphique est démontré ?** Clustered column chart.  
- **Comment enregistrer le fichier ?** Call `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Ai‑je besoin d'une licence ?** A free trial works for development; a full license is required for production.  
- **Puis‑je modifier la zone de tracé ?** Yes – set X, Y, width, height and choose a layout target type.

## Qu'est-ce que java create powerpoint chart ?
`java create powerpoint chart` désigne la génération programmatique d'un objet graphique, son remplissage avec des données, et son insertion dans une diapositive PowerPoint à l'aide d'une bibliothèque Java. Aspose.Slides abstrait le format Open XML afin que vous puissiez vous concentrer sur la conception visuelle plutôt que sur les détails internes du fichier.

## Pourquoi ajouter un graphique à colonnes groupées avec Aspose.Slides ?
Un graphique à colonnes groupées est idéal pour comparer plusieurs séries de données côte à côte. Il est largement utilisé dans les rapports d'entreprise, les tableaux de bord et les présentations. Aspose.Slides vous offre un contrôle total sur les couleurs, les marqueurs, les axes et la mise en page sans ouvrir PowerPoint manuellement. Il vous permet de mettre en évidence les tendances entre les catégories, rendant les informations de données plus claires pour les parties prenantes. Avec Aspose.Slides, vous pouvez ajuster programmatique le formatage des séries, l'échelle des axes et les étiquettes de données, garantissant que le graphique correspond à votre identité visuelle d'entreprise et aux normes graphiques.

## Prérequis
- **Aspose.Slides for Java** (version 25.4 ou plus récente).  
- **JDK 16** ou ultérieur.  
- Un IDE tel que IntelliJ IDEA ou Eclipse.  
- Connaissances de base en Java.

## Configuration d'Aspose.Slides pour Java
### Maven
Ajoutez la dépendance à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```

### Gradle
Incluez la bibliothèque dans `build.gradle` :

```gradle
implementation 'com.aspose:aspose-slides:25.4'
```

### Téléchargement direct
Sinon, téléchargez la dernière version depuis [Aspose's official site](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
Utilisez un essai gratuit ou une licence temporaire pour les tests. Achetez une licence complète pour les déploiements en production.

## Initialisation et configuration de base
La classe `Presentation` est le point d'entrée pour créer et manipuler des fichiers PowerPoint. Créez une nouvelle classe Java et importez la classe principale :

```java
import com.aspose.slides.Presentation;
```

## Guide d'implémentation
Nous parcourrons chaque étape avec des explications claires.

### Initialisation de la présentation et manipulation des diapositives
#### Ancre de définition
`Presentation` est l'objet de niveau supérieur d'Aspose.Slides qui représente un fichier PowerPoint complet en mémoire.  

#### Vue d'ensemble
Tout d'abord, créez une nouvelle présentation et récupérez la première diapositive où le graphique sera placé.

**1. Créer et initialiser une présentation**

```java
Presentation presentation = new Presentation();
```

**2. Accéder à la première diapositive**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Ajouter un graphique à colonnes groupées**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **Astuce :** Enveloppez toujours l'utilisation de la présentation dans un bloc `try‑finally` et appelez `presentation.dispose()` dans le `finally` pour libérer les ressources natives.

### Configuration de la zone de tracé
#### Vue d'ensemble
Ajustez finement la zone de tracé du graphique pour contrôler où les données sont visualisées sur la diapositive.

**1. Définir la position et la taille**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Définir le type de cible de mise en page**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Enregistrement de la présentation
#### Vue d'ensemble
Après avoir personnalisé le graphique, enregistrez la présentation sous forme de fichier PPTX.

**1. Enregistrer dans un fichier**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Avertissement :** Assurez‑vous que le répertoire de sortie existe et que l'application possède les permissions d'écriture ; sinon, l'opération d'enregistrement échouera.

## Cas d'utilisation courants
- **Rapports d'affaires :** Intégrer les tendances de ventes et les indicateurs financiers.  
- **Diapositives éducatives :** Visualiser les résultats d'expériences ou les données statistiques.  
- **Propositions de projet :** Mettre en évidence les jalons et l'allocation des ressources.  
- **Présentations marketing :** Montrer la performance des campagnes avec des graphiques vivants.  
- **Planification d'événements :** Afficher la démographie des participants ou la répartition du planning.  

## Considérations de performance
- Libérez rapidement les objets `Presentation` pour éviter les fuites de mémoire.  
- Pour les grands ensembles de données, remplissez les séries du graphique de manière incrémentielle plutôt que de tout charger d'un coup.  
- Utilisez les outils de profilage intégrés de Java pour surveiller l'utilisation du tas lors de la génération du graphique.  

## Questions fréquentes

**Q : Comment ajouter d'autres types de graphiques ?**  
A: Utilisez l'énumération `ChartType` (par ex., `ChartType.Pie`, `ChartType.Line`) lors de l'appel à `addChart`.

**Q : Puis‑je personnaliser les couleurs du graphique ?**  
A: Oui, modifiez le format de remplissage des séries ou la palette du graphique via l'API `IChart`.

**Q : Ma présentation ne s'enregistre pas—quel est le problème ?**  
A: Vérifiez que le chemin du répertoire de sortie est correct, qu'il existe et qu'il est accessible en écriture. Assurez‑vous également qu'aucun autre processus ne verrouille le fichier.

**Q : Comment gérer efficacement des présentations très volumineuses ?**  
A: Traitez les diapositives par lots, libérez chaque `Presentation` après utilisation, et envisagez d'augmenter la taille du tas JVM si nécessaire.

**Q : Aspose.Slides est‑il gratuit pour les projets commerciaux ?**  
A: Un essai gratuit est disponible pour l'évaluation, mais une licence achetée est requise pour le déploiement commercial.

## Ressources
- [Documentation](https://reference.aspose.com/slides/java/)
- [Télécharger Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/java/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum de support](https://forum.aspose.com/c/slides/11)

Commencez dès aujourd'hui à créer des présentations visuellement époustouflantes avec Aspose.Slides pour Java !

**Dernière mise à jour :** 2026-06-08  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur :** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

## Tutoriels associés

- [Comment créer un graphique à colonnes groupées en Java avec Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Comment ajouter et configurer des graphiques dans les présentations avec Aspose.Slides pour Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Créer une présentation PowerPoint animée en Java – Animer les graphiques PowerPoint avec Aspose.Slides](/slides/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
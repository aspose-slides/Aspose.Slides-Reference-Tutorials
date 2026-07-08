---
date: '2026-07-08'
description: Apprenez comment ajouter des diagrammes circulaires PowerPoint à l'aide
  d'Aspose.Slides for Java. Suivez ce guide étape par étape pour créer et personnaliser
  des diagrammes circulaires professionnels.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Ajoutez un diagramme circulaire PowerPoint avec Aspose.Slides for
  Java. Ce tutoriel montre comment générer et personnaliser des diagrammes circulaires
  de manière programmatique, idéal pour les rapports automatisés.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Ajouter un diagramme circulaire PowerPoint avec Aspose.Slides for Java –
  Guide rapide
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Comment ajouter un diagramme circulaire PowerPoint avec Aspose.Slides for Java
url: /fr/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter un diagramme circulaire PowerPoint avec Aspose.Slides pour Java

## Introduction

Si vous devez **ajouter un diagramme circulaire PowerPoint** sans ouvrir manuellement PowerPoint, vous êtes au bon endroit. Dans ce guide, nous parcourrons la configuration d'Aspose.Slides pour Java, la création d'un diagramme circulaire et la personnalisation de chaque tranche — parfait pour les rapports automatisés, les tableaux de bord ou les présentations personnalisées. À la fin, vous disposerez d'un extrait Java réutilisable qui génère un fichier PowerPoint avec un diagramme circulaire soigné en quelques secondes.

### Réponses rapides
- **Quelle bibliothèque crée le graphique ?** Aspose.Slides for Java (dernière version).  
- **Puis-je l’exécuter en mode sans tête ?** Oui—aucune installation d'Office requise.  
- **Quelle version de Java est optimale ?** JDK 16+ pour les meilleures performances et les améliorations du ramasse-miettes.  
- **Comment exploser une tranche ?** Appelez `setExplosion` sur le `IDataPoint` et définissez un décalage en pixels.  
- **Ai-je besoin d’une licence pour la production ?** Un essai fonctionne pour le développement ; une licence permanente supprime toutes les limites d’évaluation.

## Pourquoi ajouter un diagramme circulaire PowerPoint avec Aspose.Slides pour Java ?

Vous pouvez générer des rapports visuels à jour directement depuis vos services back‑end, éliminant les erreurs de copier‑coller manuelles et garantissant un style cohérent avec la marque. Aspose.Slides prend en charge **plus de 70 types de graphiques** et peut traiter des présentations contenant **plus de 10 000 diapositives** sans charger le fichier complet en mémoire, ce qui le rend idéal pour l’automatisation à grande échelle.

## Prérequis

- **Aspose.Slides for Java** – le tutoriel fait référence à la version 25.4 (la plus récente au moment de la rédaction).  
- **Java Development Kit** – JDK 16 ou supérieur est recommandé.  
- **Maven** ou **Gradle** pour la gestion des dépendances.  

## Configuration d'Aspose.Slides pour Java

### Maven
Ajoutez cette dépendance à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez ce qui suit dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sinon, téléchargez la dernière version directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licence
Pour utiliser Aspose.Slides sans limitations :

- Commencez avec un **essai gratuit** pour évaluer l'API.  
- Demandez une **licence temporaire** pour des tests prolongés sur la page [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Achetez un abonnement complet via la [Purchase page](https://purchase.aspose.com/buy).

## Comment ajouter un diagramme circulaire PowerPoint avec Aspose.Slides pour Java

Chargez une nouvelle présentation, insérez un diagramme circulaire et enregistrez le fichier — le tout en trois étapes concises. Ce modèle fonctionne pour tout jeu de données et peut être encapsulé dans une boucle pour générer automatiquement des dizaines de diapositives. L'approche est légère, ne nécessitant que quelques lignes de code et aucune ressource externe, ce qui la rend adaptée tant aux petites utilités qu'aux gros traitements par lots.

### Étape 1 : Initialiser la présentation
La classe `Presentation` représente un fichier PowerPoint unique en mémoire. Créer une instance vous fournit un nouveau jeu de diapositives vide avec lequel travailler.
```java
Presentation pres = new Presentation();
```

### Étape 2 : Ajouter le diagramme circulaire
Insérez un diagramme circulaire sur la première diapositive. Les coordonnées (50, 50) et la taille (600 × 400) conviennent à une mise en page standard 16 : 9 et laissent de l'espace pour les titres.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Étape 3 : Enregistrer la présentation
Écrivez la présentation sur le disque. Remplacez `YOUR_OUTPUT_DIRECTORY` par le dossier où vous souhaitez enregistrer le fichier.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Étape 4 : Nettoyer les ressources
Libérez l'objet `Presentation` pour libérer les ressources natives et éviter les fuites de mémoire.
```java
if (pres != null) pres.dispose();
```

## Comment personnaliser l'explosion et la couleur d'un point de données ?

Chargez le graphique, localisez le point de données cible, puis appliquez un décalage d'explosion et une couleur de remplissage solide. Cela fait ressortir la tranche pour la mettre en évidence. Ces ajustements aident à attirer l'attention du public sur les valeurs critiques et améliorent la lisibilité globale du graphique.

### Étape 1 : Charger une présentation existante (ou réutiliser celle que vous venez de créer)
L'objet `Presentation` charge un fichier PowerPoint existant en mémoire, vous permettant de modifier son contenu.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Étape 2 : Accéder au graphique et au point de données cible
L'interface `IDataPoint` représente un point de données individuel (tranche) au sein d'une série de graphique.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Étape 3 : Appliquer l'explosion et la couleur
`setExplosion(int)` définit la distance, en pixels, à laquelle une tranche est décalée du centre du graphique. Séparez visuellement la tranche avec `setExplosion(20)` et changez son remplissage en bleu en utilisant `setFillType(FillType.Solid)` et `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Étape 4 : Enregistrer et libérer
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Applications pratiques
- **Rapports de ventes :** Mettre en évidence les produits les plus vendus avec des tranches éclatées.  
- **Analyse budgétaire :** Attribuer des couleurs distinctes aux départements pour une comparaison visuelle rapide.  
- **Diapositives éducatives :** Décomposer des concepts complexes en segments de graphique digestes.  

## Considérations de performance
- **Libérez les objets** rapidement pour éviter les fuites de mémoire, surtout lors de la génération de nombreuses diapositives dans une boucle.  
- **Surveillez l'utilisation du tas** pour les grandes présentations ; utilisez la surcharge `Save` qui accepte un `OutputStream` pour diffuser les données et maintenir une faible empreinte mémoire.  
- Restez sur **JDK 16+** pour profiter des dernières améliorations du ramasse-miettes, ce qui peut réduire le temps de traitement jusqu'à 30 % pour des présentations de 1 000 diapositives.

## Conclusion
Vous disposez maintenant d’un flux de travail complet et prêt pour la production afin de **ajouter des fichiers PowerPoint avec diagramme circulaire** en utilisant Aspose.Slides pour Java. Expérimentez différentes distances d'explosion, couleurs et jeux de données pour correspondre à votre identité visuelle. Lorsque vous êtes prêt, explorez d’autres types de graphiques — barres, lignes ou nuages de points—pour créer un tableau de bord analytique complet dans PowerPoint.

## Questions fréquemment posées

**Q : Quel est le principal avantage d’utiliser Aspose.Slides pour Java ?**  
R : Il vous permet de créer, modifier et rendre des fichiers PowerPoint de manière programmatique sans nécessiter l’installation de Microsoft Office, en prenant en charge plus de 70 types de graphiques et plus de 100 formats de fichiers.

**Q : Puis‑je générer un fichier PowerPoint à partir de zéro ?**  
R : Oui, créez une instance de l’objet `Presentation`, ajoutez des diapositives, des graphiques ou des formes, puis appelez `save` — le tout en code Java pur.

**Q : Comment exploser une tranche de diagramme circulaire spécifique ?**  
R : Récupérez le `IDataPoint` de la tranche et appelez `setExplosion(pixelOffset)`. Le décalage définit la distance à laquelle la tranche se déplace vers l’extérieur.

**Q : Existe‑t‑il une limite au nombre de diapositives que je peux créer ?**  
R : Aspose.Slides peut gérer des présentations contenant jusqu’à **10 000 diapositives** dans un seul fichier, à condition de diffuser la sortie pour éviter de charger tout en mémoire.

**Q : Où puis‑je trouver des exemples plus avancés de personnalisation de graphiques ?**  
R : Consultez la [documentation officielle d'Aspose.Slides](https://reference.aspose.com/slides/java/) pour des références API détaillées et des projets d’exemple.

## Ressources
- **Documentation :** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Télécharger la bibliothèque :** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Acheter une licence :** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Essai gratuit :** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Licence temporaire :** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum de support :** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-07-08  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animer les graphiques PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Créer et valider les mises en page de graphiques dans PowerPoint avec Aspose.Slides pour Java | guide SEO optimisé](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
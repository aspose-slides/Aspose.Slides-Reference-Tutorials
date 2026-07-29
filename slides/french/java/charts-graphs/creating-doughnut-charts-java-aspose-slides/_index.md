---
date: '2026-07-27'
description: Apprenez à créer un Doughnut Chart Java avec Aspose.Slides – un guide
  rapide pour configurer la bibliothèque, ajouter un Doughnut Chart personnalisable,
  ajuster la taille du trou et enregistrer la présentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Apprenez à créer un Doughnut Chart Java avec Aspose.Slides – un guide
  rapide pour configurer la bibliothèque, ajouter un Doughnut Chart personnalisable,
  ajuster la taille du trou et enregistrer la présentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Créer un Doughnut Chart Java – Étape par étape avec Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Créer un Doughnut Chart Java – Étape par étape avec Aspose.Slides
url: /fr/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques en anneau en Java avec Aspose.Slides pour les présentations

## Introduction
Créer des présentations visuellement attrayantes est essentiel pour transmettre efficacement l'information. **Create doughnut chart java** est une exigence courante lorsque vous devez illustrer des données proportionnelles avec un aspect moderne. Dans ce tutoriel, vous apprendrez à configurer Aspose.Slides pour Java, à créer un graphique en anneau, à personnaliser la taille de son trou et ses couleurs, puis à enregistrer le fichier de présentation. À la fin, vous disposerez d'un modèle réutilisable que vous pourrez intégrer à n'importe quel projet Java générant automatiquement des présentations PowerPoint.

**Ce que vous apprendrez :**
- Configurer Aspose.Slides pour Java
- Créer et configurer des graphiques en anneau dans les présentations
- Ajuster l'esthétique du graphique, comme la taille du trou
- Enregistrer la présentation avec votre nouveau graphique

Commençons par configurer notre environnement !

## Réponses rapides
- **Quelle bibliothèque crée doughnut chart java ?** Aspose.Slides for Java.  
- **Combien de lignes de code sont nécessaires pour un graphique en anneau de base ?** Environ 8 à 10 lignes après l'instanciation de la présentation.  
- **Puis-je modifier la taille du trou ?** Oui, la méthode `setHoleSize(double)` accepte des valeurs de 0 % à 100 %.  
- **Quels formats de sortie sont pris en charge ?** PPTX, PDF, XPS, PNG, JPEG et plusieurs autres (plus de 50 au total).  
- **Ai-je besoin d'une licence pour la production ?** Une licence commerciale est requise pour une utilisation illimitée ; une version d'essai gratuite suffit pour l'évaluation.

## Qu'est-ce qu'Aspose.Slides pour Java ?
**Aspose.Slides for Java** est une API entièrement gérée qui permet aux développeurs de créer, modifier, convertir et rendre des fichiers PowerPoint sans Microsoft Office. Elle prend en charge plus de 50 formats de fichiers et peut gérer des présentations contenant des milliers de diapositives tout en maintenant une faible consommation de mémoire.

## Pourquoi utiliser les graphiques en anneau dans les présentations ?
Les graphiques en anneau affichent les relations partie‑tout tout en libérant de l'espace au centre pour des étiquettes ou des images. Aspose.Slides peut rendre des graphiques en anneau jusqu'à **500 diapositives par minute** sur un serveur typique de 2,5 GHz, et il traite des **présentations de plusieurs centaines de pages** sans charger le fichier complet en mémoire, ce qui le rend idéal pour les solutions de reporting à grande échelle.

## Prérequis
Avant de commencer, assurez-vous d'avoir rempli ces prérequis :

### Bibliothèques requises et versions
Pour travailler avec Aspose.Slides pour Java, incluez-le dans votre projet via Maven ou Gradle, ou téléchargez-le directement.

#### Exigences de configuration de l'environnement
- Un JDK (Java Development Kit) fonctionnel, de préférence la version 8 ou supérieure.
- Un environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse.

### Prérequis de connaissances
Une familiarité avec Java et les concepts de programmation de base est bénéfique. Une connaissance de base de Maven ou Gradle facilitera le processus d'installation.

## Configuration d'Aspose.Slides pour Java
Intégrer Aspose.Slides à votre projet peut se faire de plusieurs manières :

**Maven :**  
Ajoutez cette dépendance à votre fichier `pom.xml` :  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle :**  
Incluez ceci dans votre fichier `build.gradle` :  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct :**  
Alternativement, téléchargez la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Acquisition de licence
- **Essai gratuit :** Commencez par télécharger une version d'essai pour explorer les fonctionnalités d'Aspose.Slides.  
- **Licence temporaire :** Obtenez une licence temporaire pour une fonctionnalité étendue sans limitations.  
- **Achat :** Pour une utilisation continue, l'achat d'une licence est requis.

Une fois la bibliothèque installée et votre environnement prêt, passons à la mise en œuvre de notre graphique en anneau.

## Comment créer un graphique en anneau en Java ?
Chargez un nouvel objet `Presentation`, ajoutez un graphique en anneau à une diapositive, définissez la taille du trou et enregistrez le fichier – le tout en quelques appels d'API simples. Cette approche vous donne un contrôle complet sur les données du graphique, son apparence et le format d'exportation, et fonctionne sans nécessiter Microsoft PowerPoint installé sur le serveur.

### Initialiser l'objet Presentation
La classe `Presentation` est l'objet de haut niveau d'Aspose.Slides qui représente un fichier PowerPoint en mémoire.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Cette étape crée une présentation vide où vous pouvez ajouter des diapositives, des formes et des graphiques.

### Ajouter un graphique en anneau à la diapositive
`ISlide` est l'interface d'une diapositive unique ; vous pouvez récupérer la première diapositive ou en ajouter une nouvelle.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
La méthode `addChart` crée un graphique en anneau ; les paramètres définissent sa position (X, Y) et sa taille (largeur, hauteur) sur la diapositive.

### Configurer la taille du trou du graphique en anneau
`Chart` expose la méthode `setHoleSize(double)` pour contrôler le rayon interne en pourcentage du rayon du graphique.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Définir la taille du trou à 90 % fait apparaître le graphique presque comme un cercle complet, ce qui est utile lorsque vous souhaitez mettre en avant les segments extérieurs.

### Enregistrer la présentation
`presentation.save(String, SaveFormat)` écrit le fichier sur le disque dans le format choisi.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
L'exemple enregistre le résultat sous `DoughnutHoleSize_out.pptx`, mais vous pouvez également choisir PDF, PNG ou tout autre format parmi les plus de 50 pris en charge.

### Nettoyer les ressources
Appeler `presentation.dispose()` libère les ressources natives et empêche les fuites de mémoire, ce qui est particulièrement important dans les applications serveur à long terme.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Applications pratiques
Les graphiques en anneau sont polyvalents. Voici quelques scénarios où ils brillent :
1. **Répartition du budget :** Afficher comment un budget est réparti entre les départements.  
2. **Résultats d'enquête :** Visualiser les réponses aux questions à choix multiples.  
3. **Sources de trafic du site web :** Montrer le pourcentage de trafic provenant de différents canaux (organique, payant, référent, etc.).

## Considérations de performance
Lors de l'utilisation d'Aspose.Slides, considérez ces conseils pour des performances optimales :
- Libérez les objets `Presentation` dès que vous avez fini afin de libérer la mémoire native.  
- Utilisez des flux (`FileInputStream`, `ByteArrayOutputStream`) pour les grands ensembles de données afin d'éviter de charger des fichiers entiers en RAM.  
- Réutilisez les objets de graphique lors de la génération de nombreuses diapositives dans une boucle afin de réduire la surcharge de création d'objets.

## Problèmes courants et solutions
- **Erreur lors de l'enregistrement :** Vérifiez que le répertoire de sortie existe et que l'application dispose des permissions d'écriture.  
- **Données du graphique manquantes :** Assurez-vous de remplir la collection `ChartData` du graphique avant d'appeler `setHoleSize`.  
- **Pics de mémoire :** Pour les présentations contenant des milliers de diapositives, activez `Presentation.setSlideSize` à une taille plus petite et libérez rapidement les diapositives intermédiaires.

## Questions fréquemment posées

**Q : Puis-je ajuster les couleurs des segments de mon graphique en anneau ?**  
R : Oui. Utilisez `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` puis spécifiez la couleur RGB souhaitée.

**Q : Comment ajouter des étiquettes de données à mon graphique ?**  
R : Appelez `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` pour afficher la valeur à l'intérieur de chaque segment.

**Q : Est-il possible d'enregistrer les graphiques dans des formats autres que PPTX ?**  
R : Absolument. Aspose.Slides prend en charge PDF, XPS, PNG, JPEG, TIFF et de nombreux autres formats—plus de 50 au total.

**Q : Que faire si je rencontre une exception lors du chargement d'une grande présentation ?**  
R : Utilisez le constructeur `Presentation` qui accepte un flux et activez `loadOptions.setLoadFormat(LoadFormat.Pptx)` pour diffuser le fichier et réduire la consommation de mémoire.

**Q : Puis-je automatiser les mises à jour du graphique avec des sources de données en direct ?**  
R : Oui. Récupérez les données d'une base de données ou d'une API REST, mettez à jour la collection `ChartData`, puis appelez `chart.refresh()` avant d'enregistrer la présentation.

## Ressources
- **Documentation :** Explorez les références détaillées de l'API sur [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Téléchargement :** Obtenez la dernière version de la bibliothèque depuis [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Achat :** Pour un accès complet, achetez une licence sur [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Essai gratuit :** Testez Aspose.Slides avec un essai gratuit disponible sur leur page de téléchargement.  
- **Licence temporaire :** Obtenez une licence temporaire pour des tests étendus sans limitations.  
- **Support :** Des questions ? Visitez le [Aspose Forum](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide.

---

**Dernière mise à jour :** 2026-07-27  
**Testé avec :** Aspose.Slides for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Comment créer un graphique en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
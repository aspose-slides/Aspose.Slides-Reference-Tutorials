---
date: '2026-09-17'
description: Apprenez à créer un graphique à bulles PowerPoint avec Aspose.Slides
  for Java. Ce guide vous montre comment ajouter un graphique à une diapositive, configurer
  la taille des bulles et enregistrer le fichier PPTX efficacement.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Apprenez à créer un graphique à bulles PowerPoint avec Aspose.Slides
  for Java. Ce tutoriel explique comment ajouter un graphique à une diapositive, ajuster
  la taille des bulles et enregistrer la présentation efficacement.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Créer un graphique à bulles PowerPoint avec Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Créer un graphique à bulles PowerPoint avec Aspose.Slides for Java
url: /fr/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un diagramme à bulles PowerPoint avec Aspose.Slides pour Java

## Introduction
Si vous devez **créer un diagramme à bulles PowerPoint** de manière programmatique, Aspose.Slides for Java vous offre une API propre côté serveur qui fonctionne sans Microsoft Office. Dans ce tutoriel, vous apprendrez comment ajouter un graphique à une diapositive, contrôler la taille des bulles et enregistrer le PPTX final tout en gérant efficacement les ressources. Les étapes sont détaillées afin que vous puissiez copier‑coller le code dans n’importe quel projet Java et voir les résultats immédiatement.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.Slides for Java
- **Quelle version de Java est requise ?** JDK 16 ou supérieure
- **Comment ajouter un diagramme à bulles ?** Appelez `addChart(ChartType.Bubble, …)` sur une diapositive
- **Puis‑je modifier la taille des bulles ?** Oui, via `setBubbleSizeScale()`
- **Comment enregistrer le fichier ?** Utilisez `pres.save("Result.pptx", SaveFormat.Pptx)`

## Qu’est‑ce que créer un diagramme à bulles PowerPoint ?
Créer un diagramme à bulles dans PowerPoint signifie générer de façon programmatique un graphique où chaque point de données est représenté par une bulle dont la position X, la position Y et la taille codent trois dimensions de données. Aspose.Slides for Java gère le rendu, vous n’avez donc pas besoin d’avoir PowerPoint installé.

## Pourquoi utiliser Aspose.Slides pour Java ?
Aspose.Slides prend en charge **plus de 50 types de graphiques**, peut traiter des présentations jusqu’à **2 Go** sans charger le fichier complet en mémoire, et fonctionne sur toute plateforme supportant Java 16+. Ces capacités quantifiées en font un choix fiable pour les rapports de niveau entreprise.

## Prérequis
- **Java Development Kit** 16 ou plus récent installé.
- **Bibliothèque Aspose.Slides for Java** (ajoutez via Maven, Gradle ou téléchargement direct du JAR).
- Familiarité de base avec la syntaxe Java et la programmation orientée objet.

## Configuration d’Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, incluez la bibliothèque dans votre système de build.

### Maven
Ajoutez la dépendance suivante à votre `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez ceci dans votre `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct download
Vous pouvez également obtenir le dernier JAR depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – évaluation prolongée pour des projets plus importants.  
- **Licence complète** – requise pour les déploiements en production.

### Initialisation et configuration de base
La classe `Presentation` est le point d’entrée pour créer ou charger des fichiers PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Guide d’implémentation
Voici un guide étape par étape pour créer un diagramme à bulles et gérer les ressources.

## Comment créer un diagramme à bulles PowerPoint
Dans cette section, vous apprendrez la séquence exacte d’appels d’API nécessaires pour générer un diagramme à bulles, configurer ses propriétés visuelles et enregistrer le résultat sous forme de fichier PPTX. Cette approche fonctionne pour tout projet Java incluant Aspose.Slides et suivant les meilleures pratiques de gestion des ressources.

Chargez la présentation, ajoutez un diagramme à bulles, configurez son apparence, puis enregistrez le fichier.

### Réponse directe
Créez une nouvelle `Presentation`, appelez `addChart(ChartType.Bubble, …)` sur la diapositive souhaitée, ajustez l’échelle de taille des bulles avec `setBubbleSizeScale(150)`, puis enregistrez avec `pres.save("Result.pptx", SaveFormat.Pptx)`. Cette séquence ajoute un diagramme à bulles pleinement fonctionnel en quelques lignes de Java.

- **`ChartType.Bubble`** représente le type de diagramme à bulles.  
- **`addChart`** insère un nouveau graphique du type spécifié sur une diapositive.  
- **`setBubbleSizeScale`** ajuste la taille globale des bulles dans le graphique.  
- **`SaveFormat.Pptx`** spécifie le format de fichier PPTX pour l’enregistrement.  

#### Implémentation étape par étape
**1. Initialiser la présentation** – instancier l’objet `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Ajouter un diagramme à bulles** – insérer le graphique aux coordonnées choisies.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` indique à Aspose.Slides de créer un diagramme à bulles.  
- Les paramètres numériques définissent la position X/Y ainsi que la largeur/hauteur en points.

**3. Configurer l’échelle de taille des bulles** – agrandir les bulles pour un meilleur impact visuel.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Définir l’échelle à **150 %** rend chaque bulle 1,5 × plus grande que la valeur par défaut.

**4. Enregistrer la présentation** – écrire le PPTX sur le disque.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Conseils de dépannage
- Vérifiez les permissions d’écriture pour le dossier de sortie.  
- Confirmez que le JAR Aspose.Slides correspond à la version du JDK que vous utilisez.

## Comment gérer efficacement les ressources PowerPoint
Une gestion efficace des ressources évite les fuites de mémoire et maintient une empreinte JVM faible, surtout lors du traitement de gros jeux de diapositives ou en environnement serveur. Suivez le modèle ci‑dessous pour garantir que les ressources natives sont libérées même en cas d’exception.

Une gestion efficace des ressources évite les fuites de mémoire, surtout lors du traitement de gros jeux de diapositives.

### Réponse directe
Après avoir terminé de travailler avec une `Presentation`, appelez toujours `pres.dispose()` dans un bloc `try‑finally` ; cela libère les ressources natives et permet à la JVM de récupérer rapidement la mémoire.

- **`pres.dispose()`** libère les ressources natives utilisées par la présentation.

**1. Créer et modifier** – travailler avec la présentation selon les besoins.  
```java
Presentation pres = new Presentation();
```

**2. Libérer les ressources** – libérer la mémoire une fois le traitement terminé.  
```java
if (pres != null) pres.dispose();
```

## Applications pratiques
Les diagrammes à bulles excellent dans les scénarios où trois dimensions de données doivent être visualisées simultanément :

1. **Analyse du marché** – la taille des bulles représente le chiffre d’affaires tandis que les axes X/Y affichent la croissance et la part de marché.  
2. **Métriques de performance** – comparer la productivité des employés (X), la satisfaction (Y) et l’impact (taille).  
3. **Données géographiques** – tracer les villes avec la population encodée dans la taille des bulles.  
4. **Gestion de projet** – visualiser la chronologie (X), le coût (Y) et le risque (taille) sur une seule diapositive.

## Considérations de performance
- **Utilisation des ressources** – libérer les présentations rapidement pour maintenir une faible utilisation du tas.  
- **Gestion de la mémoire Java** – encapsuler le travail sur la présentation dans un `try‑finally` pour garantir la libération même en cas d’exception.  
- **Restez à jour** – mettez à jour vers la dernière version d’Aspose.Slides pour bénéficier des optimisations de performance et des corrections de bugs.

## Questions fréquentes

**Q : Qu’est‑ce qu’Aspose.Slides pour Java ?**  
R : Aspose.Slides for Java est une bibliothèque autonome qui vous permet de créer, modifier et convertir des fichiers PowerPoint sans nécessiter Microsoft Office.

**Q : Comment intégrer Aspose.Slides à mon projet Java existant ?**  
R : Ajoutez la dépendance Maven ou Gradle montrée précédemment, ou placez le JAR dans votre classpath, puis importez `com.aspose.slides.*`.

**Q : Puis‑je utiliser Aspose.Slides pour de grandes présentations ?**  
R : Oui, la bibliothèque gère efficacement des présentations jusqu’à **2 Go** et prend en charge le streaming pour éviter de charger le fichier complet en mémoire.

**Q : Quels types de graphiques sont disponibles en plus des diagrammes à bulles ?**  
R : Plus de **50 types de graphiques** sont pris en charge, y compris les graphiques à barres, lignes, secteurs, radar et cascade.

**Q : Existe‑t‑il une prise en charge intégrée pour le style des éléments du graphique ?**  
R : Absolument. Vous pouvez personnaliser les couleurs, polices, bordures et étiquettes de données via les objets `ChartSeries` et `ChartTitle` du graphique.

## Ressources
- **Documentation** : [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download** : [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Purchase** : [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial** : [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license** : [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support** : [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

## Tutoriels associés

- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Créer un graphique PowerPoint Java avec Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Créer un graphique PowerPoint Java – Enregistrer des présentations avec graphiques en utilisant Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
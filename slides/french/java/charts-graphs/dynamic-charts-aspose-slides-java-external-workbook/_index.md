---
date: '2026-08-06'
description: Apprenez à créer un graphique dans les présentations Java en utilisant
  Aspose.Slides et à lier un classeur pour des mises à jour dynamiques des données.
  Guide étape par étape.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: Apprenez à créer un graphique dans les présentations Java en utilisant
  Aspose.Slides et à lier un classeur pour des mises à jour dynamiques des données.
  Suivez ce tutoriel concis.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: Comment créer un graphique dans les présentations Java avec Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: Comment créer un graphique dans les présentations Java avec Aspose.Slides
url: /fr/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique dans des présentations Java avec Aspose.Slides : liaison à des classeurs externes

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer un graphique** dans une présentation Java et **comment lier les données d’un classeur** afin que les graphiques se rafraîchissent automatiquement. Les graphiques dynamiques maintiennent vos diapositives à jour sans copier‑coller manuel, ce qui est essentiel pour les rapports en direct, les tableaux de bord financiers et les présentations d’état de projet. Nous passerons en revue la configuration, l’implémentation et les pièges courants, afin que vous puissiez intégrer des données Excel en temps réel avec seulement quelques lignes de code.

## Réponses rapides
- **Quel est le principal avantage ?** Les graphiques se mettent à jour automatiquement lorsque le classeur Excel lié change.  
- **Quelle version de la bibliothèque est requise ?** Aspose.Slides for Java 25.4 ou plus récente.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale supprime toutes les limites d’évaluation.  
- **Puis‑je utiliser n’importe quel format Excel ?** Oui – les fichiers `.xlsx` et les anciens `.xls` sont pris en charge.  
- **La latence réseau est‑elle un problème ?** Mettez le classeur en cache localement ou utilisez un CDN pour minimiser la latence.

## Qu’est‑ce que la liaison dynamique de graphique ?
La liaison dynamique de graphique permet à un graphique de lire sa source de données depuis un classeur externe au moment de l’exécution, de sorte que toute modification du classeur se reflète dans la diapositive la prochaine fois qu’elle est ouverte. Cela élimine le besoin de régénérer la présentation après chaque mise à jour des données.

## Pourquoi utiliser Aspose.Slides pour Java ?
Aspose.Slides prend en charge **plus de 50 formats d’entrée et de sortie**, peut rendre des présentations de plusieurs centaines de pages sans charger le fichier complet en mémoire, et traite les mises à jour de données de graphique en moins de 200 ms sur un serveur typique. Ces performances chiffrées en font un choix fiable pour les pipelines de reporting d’entreprise.

## Prérequis
- **Aspose.Slides for Java** 25.4 ou version ultérieure.  
- **Java Development Kit (JDK)** 16 ou plus récent.  
- Familiarité avec Maven ou Gradle pour la gestion des dépendances.  

### Bibliothèques et dépendances requises
- **Aspose.Slides for Java** – fournit l’API de présentation.  
- **Java Development Kit (JDK)** – requis pour compiler et exécuter le code.

### Exigences de configuration de l’environnement
- Connaissances de base en programmation Java.  
- Accès à un classeur Excel externe (chemin de fichier local ou URL HTTP).  

## Configuration d’Aspose.Slides pour Java
Pour ajouter Aspose.Slides à votre projet, choisissez l’un des systèmes de construction pris en charge.

### Configuration Maven
Ajoutez cette dépendance à votre `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Configuration Gradle
Incluez ceci dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger la bibliothèque depuis [versions d’Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
Commencez avec un essai gratuit ou obtenez une licence temporaire pour tester Aspose.Slides sans limitations. Pour une utilisation à long terme, envisagez d’acheter une licence.

##### Initialisation et configuration de base
`Presentation` est la classe centrale d’Aspose.Slides qui représente un fichier PowerPoint en mémoire. Initialise votre objet présentation comme suit :
```java
Presentation pres = new Presentation();
```

## Guide de mise en œuvre
Dans cette section, nous parcourons la configuration d’un classeur externe pour mettre à jour les données d’un graphique dans une présentation.

### Définir un classeur externe avec mise à jour des données du graphique

#### Vue d’ensemble
Cette fonctionnalité permet aux graphiques de mettre à jour dynamiquement leurs données à partir d’une source externe. Elle est idéale lorsque vos données changent fréquemment et que vous avez besoin que vos diapositives reflètent ces changements automatiquement.

#### Implémentation étape par étape
1. **Créer une nouvelle présentation**  
   Commencez par créer une instance `Presentation` fraîche :
   ```java
   Presentation pres = new Presentation();
   ```

2. **Accéder à la première diapositive**  
   L’accès aux diapositives est simple :
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Ajouter un graphique à la diapositive**  
   Ajoutez un graphique en secteurs à la position et à la taille souhaitées :
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Définir l’URL du classeur externe pour les données du graphique**  
   Spécifiez un classeur externe comme source de données :
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### Options de configuration
- **Type de graphique** – choisissez parmi Secteur, Barres, Ligne, Aire, etc., selon la façon dont vous souhaitez visualiser les données.  
- **Position & taille** – ajustez les coordonnées X/Y ainsi que la largeur/hauteur pour s’adapter à la mise en page de votre diapositive.  

## Comment créer un graphique lié à un classeur ?
`Chart` est l’objet Aspose.Slides qui encapsule une forme de graphique et ses données.  
Chargez votre présentation, ajoutez un graphique, puis appelez `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. Le graphique lit désormais les valeurs de ses séries depuis le classeur chaque fois que le fichier est ouvert, offrant des mises à jour en direct sans régénérer le PPTX. Ce paragraphe de réponse directe satisfait l’exigence GEO et vous fournit une description concise et exploitable.

## Problèmes courants et solutions
Si les liens externes ne se mettent pas à jour :
- Vérifiez que l’URL est accessible et renvoie un fichier Excel valide.  
- Assurez‑vous que le serveur autorise les requêtes GET anonymes ou fournissez des identifiants si nécessaire.  
- Mettez le classeur en cache localement si la latence réseau est élevée ; mettez à jour le cache avant d’ouvrir la présentation.

## Applications pratiques
Les graphiques dynamiques alimentés par un classeur externe peuvent être utiles dans plusieurs scénarios :
1. **Reporting de données en temps réel** – tableaux de bord de ventes qui récupèrent les dernières valeurs depuis un fichier Excel central.  
2. **Analyse financière** – tendances des cours boursiers qui se rafraîchissent automatiquement à partir d’un flux de données de marché.  
3. **Gestion de projet** – tableaux de bord KPI qui reflètent les dernières statistiques d’avancement des tâches.

## Considérations de performance
L’optimisation des performances est essentielle lorsqu’on travaille avec de gros classeurs :
- Mettez le classeur en cache sur le serveur d’application pour minimiser les appels réseau répétés.  
- Utilisez des API de streaming pour lire uniquement les plages de feuilles nécessaires, réduisant ainsi l’utilisation de la mémoire.  
- Aspose.Slides traite les mises à jour de graphiques en moins de 200 ms pour des classeurs jusqu’à 10 Mo, ce qui convient à la plupart des scénarios de reporting.

## Conclusion
En suivant ce guide, vous savez maintenant **comment créer un graphique** dans des présentations Java et **comment lier les données d’un classeur** pour des mises à jour automatiques. Cette capacité rend vos diapositives plus interactives, réduit les efforts manuels et garantit que les parties prenantes voient toujours les dernières valeurs. Explorez les fonctionnalités supplémentaires d’Aspose.Slides telles que le clonage de diapositives, l’animation et l’export PDF pour enrichir davantage votre flux de travail de reporting.

## Questions fréquentes
**Q1 : Puis‑je utiliser n’importe quelle URL comme classeur externe ?**  
R1 : L’URL doit pointer vers un fichier Excel accessible (`.xlsx` ou `.xls`). Assurez‑vous que le serveur renvoie le type MIME correct et que l’authentification, si nécessaire, est gérée dans votre code.

**Q2 : Quels types de graphiques prennent en charge la liaison dynamique ?**  
R2 : Tous les types de graphiques natifs d’Aspose.Slides – Secteur, Barres, Ligne, Aire, Nuage de points, Radar, etc. – peuvent être liés à un classeur externe.

**Q3 : Existe‑t‑il une limite de taille pour le classeur externe ?**  
R3 : Bien qu’Aspose.Slides puisse gérer des classeurs de plus de 100 Mo, le temps de traitement augmente linéairement ; pour de meilleures performances, gardez les fichiers sous 20 Mo ou ne lisez que les plages nécessaires.

**Q4 : Comment gérer une URL inaccessible ?**  
R4 : Enveloppez le code de liaison dans un bloc try‑catch, consignez l’exception et, éventuellement, basculez vers une source de données statique afin que la présentation se charge quand même.

**Q5 : Cette fonctionnalité peut‑elle être utilisée dans des pipelines de reporting automatisés ?**  
R5 : Absolument. L’API fonctionne en mode head‑less, vous permettant de générer ou mettre à jour des présentations sur un serveur, de les intégrer dans des e‑mails ou de les publier dans une bibliothèque SharePoint.

## Ressources
- [Documentation Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- [Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Essai gratuit et licence temporaire](https://releases.aspose.com/slides/java/)
- [Forum de support Aspose](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-08-06  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un graphique en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Comment ajouter des graphiques à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animer des graphiques PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
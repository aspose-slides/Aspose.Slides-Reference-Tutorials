---
date: '2026-03-20'
description: Apprenez à ajouter un graphique à colonnes groupées à une présentation
  PowerPoint, à personnaliser le graphique PowerPoint et à insérer un graphique de
  séries de données en utilisant Aspose.Slides pour Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Comment ajouter un graphique à colonnes groupées dans PowerPoint en utilisant
  Aspose.Slides pour Java
url: /fr/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un graphique à colonnes groupées dans PowerPoint en utilisant Aspose.Slides for Java

## Introduction

Lorsque vous devez **ajouter un graphique à colonnes groupées** à une présentation PowerPoint, un visuel clair peut transformer des chiffres bruts en une histoire immédiatement compréhensible. Le faire manuellement dans PowerPoint peut être chronophage, surtout lorsque vous devez générer de nombreuses diapositives de façon programmatique. **Aspose.Slides for Java** élimine les frictions – il vous permet de créer, personnaliser un graphique PowerPoint et d’insérer un graphique de séries de données en quelques lignes de code.

Dans ce tutoriel, vous apprendrez à :
- Initialiser une nouvelle présentation PowerPoint avec Aspose.Slides for Java.
- **Ajouter un graphique à la diapositive** et le configurer en tant que graphique à colonnes groupées.
- **Créer un graphique à colonnes groupées** en définissant des niveaux de regroupement pour les catégories.
- **Insérer un graphique de séries de données** afin que vos données soient affichées correctement.
- Enregistrer la présentation finale au format PPTX.

Assurons‑nous que vous avez tout ce dont vous avez besoin avant de plonger dans le code.

## Réponses rapides
- **Quelle est la classe principale ?** `Presentation` de `com.aspose.slides`.
- **Quel type de graphique est utilisé ?** `ChartType.ClusteredColumn`.
- **Ai‑je besoin d’une licence pour les tests ?** Un essai gratuit fonctionne, mais une licence supprime les limites d’évaluation.
- **Quelle version de Java est prise en charge ?** JDK 16 ou plus récent (l’exemple utilise JDK 16).
- **Comment exécuter l’exemple ?** Ajoutez la dépendance Maven/Gradle, compilez et exécutez la méthode `main`.

## Qu’est‑ce que « add clustered column chart » ?

Un *graphique à colonnes groupées* (également appelé *graphique à colonnes groupées*) affiche plusieurs séries de données côte à côte pour chaque catégorie, ce qui facilite la comparaison des valeurs entre les groupes. Dans PowerPoint, ce type de graphique est idéal pour les ventes trimestrielles, les résultats d’enquêtes ou tout scénario où vous devez contraster plusieurs ensembles de données au sein de la même catégorie.

## Pourquoi utiliser Aspose.Slides pour ajouter un graphique à colonnes groupées ?

- **Automatisation complète** – générez des dizaines de diapositives sans effort manuel.
- **Personnalisation fine** – contrôlez les couleurs, les libellés, les niveaux de regroupement, etc.
- **Cross‑platform** – fonctionne sur tout OS supportant Java.
- **Pas d’installation d’Office requise** – générez des fichiers PPTX sur des serveurs ou des pipelines CI.

## Prérequis

- Bibliothèque **Aspose.Slides for Java** (la dernière version est recommandée).  
- JDK 16 ou ultérieur.  
- Outil de construction Maven ou Gradle (ou vous pouvez ajouter le JAR manuellement).  
- Un IDE ou un éditeur de texte pour exécuter du code Java.

## Installation d’Aspose.Slides for Java

Ajoutez la bibliothèque à votre projet à l’aide de l’un des scripts de construction suivants.

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

Vous pouvez également télécharger directement la dernière version depuis [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Acquisition de licence

Avant de déployer en production, obtenez une licence :
- **Essai gratuit** – explorez toutes les fonctionnalités sans achat.
- **Licence temporaire** – évaluez des capacités étendues pendant une courte période.
- **Licence complète** – débloquez une utilisation illimitée. Obtenez‑la sur la [page d’achat d’Aspose](https://purchase.aspose.com/buy).

## Guide de mise en œuvre

Nous parcourrons chaque étape, en expliquant **comment ajouter un graphique** et **personnaliser le graphique PowerPoint** au fur et à mesure.

### Initialiser la présentation

Créez d’abord un objet `Presentation` et récupérez la diapositive par défaut.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Ajouter un graphique à la diapositive

Nous **ajoutons un graphique à la diapositive** en utilisant le type `ClusteredColumn` et supprimons toutes les données par défaut.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Préparer le classeur de données du graphique

Le graphique stocke ses données dans un classeur interne. Nous le vidons pour repartir de zéro.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Ajouter des catégories avec des niveaux de regroupement

Regrouper les catégories crée l’effet de **graphique à colonnes groupées**. Chaque catégorie peut appartenir à un groupe logique.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Ajouter des séries de données au graphique

Ici nous **insérons des séries de données** qui seront visualisées sous forme de colonnes séparées.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Enregistrer la présentation avec le graphique

Enfin, écrivez le fichier PPTX sur le disque.

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
- **Opérations par lots** – évitez de mettre à jour le graphique à l’intérieur de boucles serrées ; collectez d’abord les données, puis appliquez‑les.  
- **Optimisations intégrées** – Aspose.Slides propose des méthodes comme `Presentation.optimize()` pour les fichiers volumineux.

## Pièges courants & conseils

- **Piège** : oublier de vider les séries/catégories existantes peut entraîner des doublons de données.  
  **Conseil** : appelez toujours `clear()` avant de peupler de nouvelles données.  
- **Piège** : utiliser une mauvaise adresse de cellule (par ex., `"c2"` au lieu de `"C2"`).  
  **Conseil** : les références de cellules ne sont pas sensibles à la casse, mais maintenez‑les cohérentes pour la lisibilité.  
- **Conseil** : utilisez `setGroupingItem` pour créer des libellés de groupe significatifs ; ils apparaissent automatiquement dans la légende du graphique.

## Foire aux questions

**Q1 : Comment ajouter plusieurs séries à mon graphique ?**  
R1 : Appelez `ch.getChartData().getSeries().add()` de façon répétée, en fournissant un nom unique et les points de données pour chaque série.

**Q2 : Quels sont les problèmes courants avec les graphiques Aspose.Slides ?**  
R2 : Les problèmes proviennent souvent de plages de données incompatibles ou de cellules de classeur manquantes. Vérifiez que chaque catégorie et chaque point de données possède une cellule correspondante.

**Q3 : Puis‑je utiliser Aspose.Slides avec d’autres langages de programmation ?**  
R3 : Oui, Aspose propose des bibliothèques équivalentes pour .NET, C++, Python, etc.

**Q4 : Comment mettre à jour un graphique existant dans une présentation ?**  
R4 : Chargez la présentation, localisez le graphique via `slide.getShapes().get_Item(index)`, puis modifiez ses séries ou son formatage selon vos besoins.

**Q5 : Existe‑t‑il des limitations sur les types de graphiques avec Aspose.Slides ?**  
R5 : La bibliothèque prend en charge un large éventail de types de graphiques, mais consultez toujours la documentation la plus récente pour les types récemment ajoutés ou dépréciés.

## Ressources

- **Documentation** : [Référence Aspose.Slides](https://reference.aspose.com/slides/java/)
- **Téléchargement** : [Dernières versions](https://releases.aspose.com/slides/java/)
- **Achat** : [Acheter Aspose.Slides](https://purchase.aspose.com/buy)
- **Essai gratuit** : [Commencer votre essai gratuit](https://releases.aspose.com/slides/java/)
- **Licence temporaire** : [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- **Forum de support** : [Support Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-20  
**Testé avec :** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur :** Aspose
---
date: '2026-01-17'
description: Apprenez comment ajouter des séries à un graphique et personnaliser les
  graphiques à colonnes empilées dans les présentations .NET en utilisant Aspose.Slides
  pour Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Ajouter une série au graphique avec Aspose.Slides for Java dans .NET
url: /fr/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser la personnalisation des graphiques dans les présentations .NET avec Aspose.Slides pour Java

## Introduction
Dans le domaine des présentations orientées sur les données, les graphiques sont des outils indispensables qui transforment des chiffres bruts en histoires visuelles captivantes. Lorsque vous devez **ajouter une série au graphique** de façon programmatique, en particulier dans des fichiers de présentation .NET, la tâche peut sembler intimidante. Heureusement, **Aspose.Slides for Java** propose une API puissante et indépendante du langage qui rend la création et la personnalisation de graphiques simples — même lorsque votre format cible est un PPTX .NET.

Dans ce tutoriel, vous découvrirez comment **add series to chart**, comment **how to add chart** de type colonne empilée, et comment affiner les aspects visuels tels que la largeur de l'écart. À la fin, vous serez capable de générer des diapositives dynamiques et riches en données, au rendu soigné et professionnel.

**Ce que vous apprendrez**
- Comment créer une présentation vidéo avec Aspose.Slides
- Commentaire **ajouter un histogramme empilé** à une diapositive
- Commentez **add series to chart** et définissez les catégories
- Comment remplir les points de données et ajuster les paramètres visuels

Préparons votre environnement de développement.

## Réponses rapides
- **Quelle est la classe principale pour démarrer une présentation?** `Presentation`
- **Quelle méthode ajoute un graphique à une diapositive ?** `slide.getShapes().addChart(...)`
- **Comment ajouter une nouvelle série?** `chart.getChartData().getSeries().add(...)`
- **Peut‑on modifier la largeur de l’écart entre les barres?** Oui, en utilisant `setGapWidth()` sur le groupe de séries
- **Ai‑je besoin d’une licence pour la production?** Oui, une licence valide d’Aspose.Slides for Java est requise

## Qu'est-ce que « ajouter une série au graphique » ?
Ajouter une série à un graphique signifie insérer une nouvelle collection de données que le graphique affichera comme un élément visuel distinct (par exemple, une nouvelle barre, ligne ou tranche). Chaque série peut avoir son propre ensemble de valeurs, couleurs et formatage, vous permettant de comparer plusieurs ensembles de données côte à côte.

## Pourquoi utiliser Aspose.Slides pour Java pour modifier des présentations .NET ?
- **Cross‑platform** : écrivez le code Java une fois et ciblez les fichiers PPTX utilisés par des applications .NET.
- **Pas de dépendances COM ou Office** : fonctionne sur les serveurs, pipelines CI et conteneurs.
- **API graphique riche** : prend en charge plus de 50 types de graphiques, y compris les graphiques à colonnes empilées.

## Prérequis
1. Bibliothèque **Aspose.Slides for Java** (version25.4 ou ultérieure).
2. Outil de construction Maven ou Gradle, ou téléchargement manuel du JAR.
3. Connaissances de base en Java et familiarité avec la structure PPTX.

## Configuration d'Aspose.Slides pour Java
###Installation de Maven
Ajoutez la dépendance suivante à votre `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installation progressive
Incluez cette ligne dans votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger le JAR le plus récent depuis la page officielle : [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Acquisition de licence**
Commencez avec un essai gratuit en bénéficiant d'une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/). Pour une utilisation en production, achetez une licence complète afin de débloquer toutes les fonctionnalités.

## Guide de mise en œuvre étape par étape
Sous chaque étape, vous trouverez un extrait de code concis (inchangé par rapport au didacticiel original) suivi d'une explication de ce qu'il fait.

### Étape 1 : Créer une présentation vide
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Nous commençons avec un fichier PPTX vierge, qui nous fournit une toile pour ajouter des graphiques.*

### Étape 2 : Ajouter un graphique à colonnes empilées à la diapositive
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*La méthode `addChart` crée un **add stacked column chart** et le place dans le coin supérieur gauche de la diapositive.*

### Étape 3 : Ajouter des séries au graphique (Objectif principal)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Ici nous **add series to chart** – chaque appel crée une nouvelle série de données qui apparaîtra comme un groupe de colonnes distinct.*

### Étape 4 : Ajouter des catégories au graphique
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Les catégories servent d’étiquettes de l’axe X, donnant du sens à chaque colonne.*

### Étape 5 : Remplir les données des séries
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Les points de données attribuent à chaque série ses valeurs numériques, que le graphique affichera sous forme de hauteurs de barres.*

### Étape 6 : Définir l’espacement entre les groupes de séries du graphique
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*L’ajustement de la largeur de l’écart améliore la lisibilité, surtout lorsque de nombreuses catégories sont présentes.*

## Cas d'utilisation courants
- **Reporting financier** – comparer le chiffre d’affaires trimestriel entre les unités commerciales.
- **Tableaux de bord de projet** – afficher les pourcentages d’achèvement des tâches par équipe.
- **Analyse marketing** – visualiser les performances des campagnes côte à côte.

## Conseils sur les performances
- **Réutilisez l’objet `Présentation`** lors de la création de plusieurs graphiques afin de réduire la consommation de mémoire.
- **Limitez le nombre de points de données** aux seuls nécessaires pour l’histoire visuelle.
- **Libérez les objets** (`presentation.dispose()`) après l’enregistrement pour libérer les ressources.

## Questions fréquemment posées
**Q : Puis‑je ajouter d’autres types de graphiques en plus de la colonne empilée ?**
R : Oui, Aspose.Slides prend en charge les graphiques linéaires, circulaires, de zone et bien d’autres.

**Q : Ai-je besoin d’une licence séparée pour la sortie .NET ?**
R : Non, la même licence Java fonctionne pour tous les formats de sortie, y compris les fichiers PPTX .NET.

**Q : Comment changer la palette de couleurs du graphique ?**
R : Utilisez `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` et définissez la `Color` souhaitée.

**Q : Est‑il possible d’ajouter des étiquettes de données par programmation ?**
R : Absolument. Appelez `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` pour afficher les valeurs.

**Q : Que faire si je dois mettre à jour une présentation existante?**
R: Chargez le fichier avec `new Présentation("existing.pptx")`, modifiez le graphique, puis enregistrez-le à nouveau.

## Conclusion
Vous disposez maintenant d'un guide complet, de bout en bout, sur la façon de **add series to chart**, de créer un **stacked histogramme**, et d'ajuster son apparence dans les présentations .NET à l'aide d'Aspose.Slides for Java. Expérimentez avec différents types de graphiques, couleurs et sources de données pour créer des rapports visuels percutants qui impressionneront vos parties.

---

**Dernière mise à jour :** 2026-01-17
**Testé avec :** Aspose.Slides pour Java 25.4 (jdk16)
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

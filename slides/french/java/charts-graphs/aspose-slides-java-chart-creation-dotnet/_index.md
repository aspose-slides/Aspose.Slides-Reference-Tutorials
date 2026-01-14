---
date: '2026-01-14'
description: Apprenez comment ajouter un graphique à colonnes groupées et l’insérer
  dans une diapositive de présentations .NET à l’aide d’Aspose.Slides pour Java. Suivez
  ce guide étape par étape avec des exemples de code complets.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Ajouter un diagramme à colonnes groupées aux diapositives .NET Aspose.Slides
  Java
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Création de graphiques dans des présentations .NET avec Aspose.Slides for Java
## Introduction
Créer des présentations percutantes implique souvent d'intégrer des représentations visuelles de données, comme des graphiques, afin d'améliorer la compréhension et l'engagement du public. Si vous êtes développeur et que vous souhaitez ajouter des graphiques dynamiques et personnalisables à vos présentations .NET en utilisant Aspose.Slides for Java, ce tutoriel est fait pour vous. Nous explorerons comment initialiser des présentations, ajouter différents types de graphiques, gérer les données du graphique et formater efficacement les séries de données.

**Ce que vous apprendrez :**
- Comment configurer et utiliser Aspose.Slides for Java dans votre environnement .NET.
- Initialiser une nouvelle présentation avec Aspose.Slides.
- Ajouter et personnaliser des graphiques dans les diapositives.
- Gérer les classeurs de données du graphique.
- Formater les données des séries, en particulier la gestion des valeurs négatives.

Passer à la section des prérequis vous garantira d'être prêt à suivre facilement.

## Réponses rapides
- **Quel est l'objectif principal ?** Ajouter un graphique à colonnes groupées à une diapositive .NET.
- **Quelle bibliothèque est requise ?** Aspose.Slides for Java (v25.4+).
- **Puis-je l'utiliser dans un projet .NET ?** Oui – la bibliothèque Java fonctionne via le pont Java‑to‑.NET.
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un graphique de base.

## Qu'est‑ce qu'un graphique à colonnes groupées ?
Un graphique à colonnes groupées affiche plusieurs séries de données côte à côte pour chaque catégorie, ce qui facilite la comparaison des valeurs entre les groupes. Cette visualisation est idéale pour les tableaux de bord d'entreprise, les rapports de performance et tout scénario nécessitant la comparaison de plusieurs indicateurs.

## Pourquoi ajouter un graphique à une diapositive avec Aspose.Slides for Java ?
Utiliser Aspose.Slides vous permet de générer, modifier et enregistrer des présentations sans avoir Microsoft PowerPoint installé. Il offre un contrôle complet sur les types de graphiques, les données et le style, ce qui vous permet d'automatiser la génération de rapports directement depuis vos applications .NET.

## Prérequis
Avant de vous lancer dans la création de graphiques avec Aspose.Slides for Java, présentons ce dont vous avez besoin :

### Bibliothèques requises et versions
- **Aspose.Slides for Java** : Version 25.4 ou ultérieure.

### Exigences de configuration de l'environnement
- Un environnement de développement prenant en charge les applications .NET.
- Une compréhension de base des concepts de programmation Java.

### Prérequis de connaissances
- Familiarité avec la création de présentations dans un contexte d'application .NET.
- Compréhension des dépendances Java et de leur gestion (Maven/Gradle).

## Configuration d'Aspose.Slides for Java
Pour commencer à utiliser Aspose.Slides, vous devez l'inclure comme dépendance dans votre projet. Voici comment procéder :

### Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez ceci dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d'obtention de licence
- **Essai gratuit** : Commencez avec une licence temporaire pour explorer les fonctionnalités.
- **Achat** : Envisagez d'acheter une licence pour une utilisation intensive.

#### Initialisation et configuration de base
Voici comment initialiser Aspose.Slides dans votre code :
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Cette configuration garantit une gestion efficace des ressources.

## Guide d'implémentation
Nous vous guiderons à travers l'implémentation des fonctionnalités étape par étape.

### Initialisation de la présentation
**Vue d'ensemble :**  
Créer une instance de présentation prépare le terrain pour toutes les opérations suivantes. Cette fonctionnalité montre comment démarrer à partir de zéro avec Aspose.Slides.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
```

#### Étape 2 : Créer un nouvel objet Presentation
Voici comment procéder :
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Cela garantit que l'objet présentation est correctement libéré après utilisation, évitant les fuites de mémoire.*

### Ajout d'un graphique à la diapositive
**Vue d'ensemble :**  
Ajouter un graphique à votre diapositive peut rendre la visualisation des données plus efficace et attrayante.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Étape 2 : Initialiser la présentation et ajouter le graphique
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Ici, nous ajoutons un graphique à colonnes groupées à la première diapositive aux coordonnées et dimensions spécifiées.*

### Gestion du classeur de données du graphique
**Vue d'ensemble :**  
Gérer efficacement le classeur de données de votre graphique vous permet de manipuler les séries et les catégories de manière fluide.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Étape 2 : Accéder et vider le classeur de données
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Vider le classeur est essentiel pour repartir d'une base propre lors de l'ajout de nouvelles séries et catégories.*

### Ajout de séries et de catégories au graphique
**Vue d'ensemble :**  
Cette fonctionnalité montre comment ajouter des points de données pertinents en gérant les séries et les catégories.

#### Étape 1 : Ajouter des séries et des catégories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*L'ajout de séries et de catégories permet une présentation des données plus organisée.*

### Remplissage des données de séries et formatage
**Vue d'ensemble :**  
Remplissez votre graphique avec des points de données et formatez son apparence pour améliorer la lisibilité, notamment lorsqu'il s'agit de valeurs négatives.

#### Étape 1 : Remplir les données de séries
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Cette section montre comment remplir les données et appliquer un format de couleur pour une meilleure visualisation.*

## Problèmes courants et solutions
- **Fuites de mémoire :** Appelez toujours `dispose()` sur l'objet `Presentation` dans un bloc `finally`.
- **Type de graphique incorrect :** Assurez-vous d'utiliser `ChartType.ClusteredColumn` lorsque vous souhaitez un graphique à colonnes groupées ; d'autres types produiront des résultats visuels différents.
- **Couleurs des valeurs négatives non appliquées :** Vérifiez que la valeur `IDataPoint` est correctement convertie en `Number` avant la comparaison.

## Foire aux questions
**Q : Puis-je utiliser Aspose.Slides for Java dans un projet .NET pur sans Java ?**  
R : Oui. La bibliothèque fonctionne via le pont Java‑to‑.NET, vous permettant d'appeler les API Java depuis les langages .NET.

**Q : L'essai gratuit prend‑il en charge la création de graphiques ?**  
R : La version d'essai inclut toutes les fonctionnalités de graphiques, mais les fichiers générés contiennent un petit filigrane d'évaluation.

**Q : Quelles versions de .NET sont compatibles ?**  
R : Toute version de .NET pouvant interopérer avec Java 16+, y compris .NET Framework 4.6+, .NET Core 3.1+, et .NET 5/6/7.

**Q : Comment gérer de grandes présentations contenant de nombreux graphiques ?**  
R : Réutilisez la même instance `IChartDataWorkbook` lorsque cela est possible et libérez chaque `Presentation` rapidement afin de libérer la mémoire.

**Q : Est‑il possible d'exporter le graphique sous forme d'image ?**  
R : Oui. Utilisez les méthodes `chart.getImage()` ou `chart.exportChartImage()` pour obtenir des représentations PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

---
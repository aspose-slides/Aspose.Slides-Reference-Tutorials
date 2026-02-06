---
date: '2026-02-06'
description: Apprenez à initialiser une présentation Aspose Slides et à personnaliser
  un graphique à colonnes groupées dans .NET en utilisant Aspose.Slides pour Java.
  Suivez ce guide étape par étape pour améliorer la visualisation des données.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Initialiser une présentation avec Aspose Slides : graphiques .NET'
url: /fr/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques dans les présentations .NET à l'aide d'Aspose.Slides pour Java

## Introduction
Dans ce tutoriel, vous allez **initialize presentation Aspose Slides** et apprendre comment intégrer des graphiques dynamiques et personnalisables dans vos diapositives .NET. Les données visuelles—comme les graphiques à colonnes groupées—aident votre audience à saisir les tendances instantanément, et Aspose.Slides pour Java vous offre un contrôle programmatique complet même lorsque vous ciblez un environnement .NET. Nous parcourrons la configuration de la bibliothèque, la création d’une nouvelle présentation, l’ajout d’un graphique, le remplissage des données et l’application d’astuces de formatage telles que la coloration des valeurs négatives.

**Ce que vous apprendrez**
- Comment configurer Aspose.Slides for Java dans un projet .NET.  
- Comment **initialize presentation Aspose Slides** et ajouter un graphique.  
- Comment **customize clustered column chart** les séries et catégories.  
- Gestion du classeur de données du graphique et application du formatage conditionnel.  

### Quick Answers
- **Quelle est la première étape ?** Initialise un objet `Presentation`.  
- **Quel type de graphique est utilisé dans l'exemple ?** `ClusteredColumn`.  
- **Puis-je formater différemment les valeurs négatives ?** Oui, en utilisant des couleurs de remplissage conditionnelles.  
- **Ai-je besoin d'une licence pour les tests ?** Une licence d'essai gratuite suffit pour le développement.  
- **Quel artefact Maven est requis ?** `com.aspose:aspose-slides:25.4` avec le classificateur `jdk16`.

## Qu’est-ce que « initialize presentation Aspose Slides » ?
Initialiser une présentation crée un fichier PPTX en mémoire que vous pouvez manipuler avant de l’enregistrer. Aspose.Slides abstrait le format de fichier, vous permettant d’ajouter des diapositives, des formes et des graphiques sans gérer les structures OPC de bas niveau.

## Pourquoi personnaliser un graphique à colonnes groupées ?
Les graphiques à colonnes groupées sont idéaux pour comparer plusieurs séries de données à travers des catégories. Personnaliser les couleurs, les points de données et les libellés vous permet de mettre en avant les informations clés—comme souligner les valeurs négatives en rouge et les positives en vert—rendant vos diapositives plus percutantes.

## Prérequis
- **Aspose.Slides for Java** ≥ 25.4  
- Environnement de développement .NET (Visual Studio, .NET 6+ recommandé)  
- Connaissances de base en Java (vous écrirez du code Java qui s’exécute sur la JVM et sera appelé depuis .NET via JNI ou une couche de pont)  

### Bibliothèques requises et versions
- **Aspose.Slides for Java** : version 25.4 ou ultérieure.

### Exigences de configuration de l’environnement
- Un runtime Java compatible .NET (par ex., AdoptOpenJDK 16).  
- Maven ou Gradle pour la gestion des dépendances.

### Prérequis de connaissances
- Familiarité avec la création de présentations dans un contexte .NET.  
- Compréhension de la configuration de projets Java (Maven/Gradle).

## Configuration d’Aspose.Slides pour Java
Ajoutez la bibliothèque à votre projet en utilisant l’outil de construction de votre choix.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger le JAR le plus récent depuis la page officielle des versions : [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d’obtention de licence
- **Essai gratuit** – générez un fichier de licence temporaire pour le développement.  
- **Achat** – obtenez une licence complète pour les déploiements en production.

#### Initialisation et configuration de base
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
Le bloc `try/finally` garantit que les ressources natives sont libérées, évitant les fuites de mémoire.

## Comment initialiser la présentation Aspose Slides
Ci‑dessous, nous détaillons les étapes concrètes pour créer une nouvelle présentation et la préparer à l’insertion d’un graphique.

### Initialisation de la présentation
**Aperçu :**  
Créer une instance de présentation prépare le terrain pour toutes les opérations suivantes.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
```

#### Étape 2 : Créer un nouvel objet Presentation
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Cela garantit que l’objet présentation est correctement libéré après utilisation, évitant les fuites de mémoire.*

## Comment personnaliser le graphique à colonnes groupées
La présentation étant prête, ajoutons et ajustons un graphique à colonnes groupées.

### Ajout d’un graphique à la diapositive
**Aperçu :**  
Ajouter un graphique donne vie aux données sur la diapositive.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Étape 2 : Initialiser la présentation et ajouter le graphique
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
**Aperçu :**  
Gérer efficacement le classeur de données du graphique vous permet de manipuler les séries et les catégories de façon fluide.

#### Étape 1 : Importer les packages nécessaires
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Étape 2 : Accéder au classeur et le vider
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
*Vider le classeur est crucial pour repartir d’une base propre lors de l’ajout de nouvelles séries et catégories.*

### Ajout de séries et de catégories au graphique
**Aperçu :**  
Cette étape montre comment ajouter des points de données pertinents en gérant les séries et les catégories.

#### Étape 1 : Ajouter des séries et des catégories
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
*L’ajout de séries et de catégories permet une présentation des données plus organisée.*

### Remplissage des données de série et formatage
**Aperçu :**  
Alimentez votre graphique avec des points de données et formatez l’apparence pour améliorer la lisibilité, notamment lorsqu’il s’agit de valeurs négatives.

#### Étape 1 : Remplir les données de série
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
- **Fuites de mémoire** – Enveloppez toujours l’objet `Presentation` dans un bloc `try/finally` comme indiqué pour garantir la libération.  
- **Coordonnées de cellule incorrectes** – Rappelez‑vous que les lignes et colonnes sont indexées à partir de zéro ; des indices discordants provoquent un `NullPointerException`.  
- **Licence introuvable** – Placez le fichier de licence dans le répertoire de travail de l’application ou définissez explicitement le chemin via `License.setLicense("Aspose.Slides.Java.lic")`.

## FAQ

**Q : Puis‑je utiliser cette approche avec .NET Core ?**  
R : Oui. Aspose.Slides for Java fonctionne sur n’importe quelle JVM, et vous pouvez appeler le code Java depuis .NET Core à l’aide d’un pont tel qu’IKVM ou JNI.

**Q : Ai‑je besoin d’une licence payante pour le développement ?**  
R : Une licence d’essai gratuite suffit pour le développement et les tests. Les déploiements en production nécessitent une licence achetée.

**Q : Comment changer le type de graphique après sa création ?**  
R : Vous pouvez appeler `chart.getChartData().setChartType(ChartType.Pie)` pour passer à un autre type de graphique.

**Q : Est‑il possible d’ajouter des libellés de données par programme ?**  
R : Oui. Utilisez `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` pour afficher les valeurs sur le graphique.

**Q : Quels formats puis‑je utiliser pour enregistrer la présentation ?**  
R : Aspose.Slides prend en charge PPTX, PPT, PDF, XPS et plusieurs formats d’image comme PNG et JPEG.

---

**Dernière mise à jour :** 2026-02-06  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
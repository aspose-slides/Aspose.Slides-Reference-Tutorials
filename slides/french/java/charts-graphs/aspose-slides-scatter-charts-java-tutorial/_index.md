---
date: '2026-02-24'
description: Apprenez à personnaliser les graphiques de dispersion Aspose en utilisant
  Aspose.Slides pour Java. Ce guide vous accompagne dans la création, la mise en forme
  et l’enregistrement de graphiques de dispersion dynamiques dans vos présentations.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Personnaliser le graphique de dispersion Aspose en Java
url: /fr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personnaliser le diagramme de dispersion Aspose en Java

Dans ce tutoriel, vous apprendrez à **customize scatter chart aspose** avec la puissante bibliothèque Aspose.Slides for Java. Nous parcourrons la configuration de votre projet, la création d’un diagramme de dispersion, l’ajustement des types de séries et des marqueurs, puis l’enregistrement de la présentation. À la fin, vous pourrez générer des diagrammes de dispersion à l’aspect professionnel de façon programmatique et ajuster chaque détail visuel pour correspondre à votre marque ou à vos besoins de reporting.

## Réponses rapides
- **Quelle bibliothèque est‑t‑elle nécessaire ?** Aspose.Slides for Java (v25.4+).  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieur.  
- **Puis‑je changer les formes des marqueurs ?** Oui – utilisez `MarkerStyleType` pour choisir des étoiles, des cercles, etc.  
- **Comment enregistrer le fichier ?** Appelez `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Une licence est‑elle requise ?** Un essai gratuit suffit pour le développement ; une licence commerciale est nécessaire pour la production.

## Qu’est‑ce que « customize scatter chart aspose » ?
Personnaliser un diagramme de dispersion avec Aspose signifie définir programmatique­ment les données du diagramme, son apparence et son comportement—tout, des coordonnées des points aux symboles des marqueurs—sans ouvrir PowerPoint manuellement. Cette approche est idéale pour les rapports automatisés, les présentations pilotées par les données, ou tout scénario nécessitant des visualisations répétables et de haute qualité.

## Pourquoi personnaliser les diagrammes de dispersion avec Aspose.Slides ?
- **Contrôle total** – modifiez les types de séries, les styles de marqueurs, les couleurs, etc. via du code Java.  
- **Automatisation** – générez des dizaines de diagrammes à la volée pour des tableaux de bord ou des rapports batch.  
- **Cross‑platform** – fonctionne sur tout OS supportant Java, aucune installation d’Office requise.  
- **Performance** – API légère qui gère efficacement de grands ensembles de données.

## Prérequis

Pour suivre ce tutoriel, assurez‑vous d’avoir :

- **Aspose.Slides for Java** (v25.4 ou ultérieure).  
- **Java Development Kit (JDK)** 8 + installé.  
- Maven ou Gradle pour la gestion des dépendances (ou vous pouvez télécharger le JAR manuellement).  
- Connaissances de base en Java et familiarité avec l’outil de construction de votre choix.

## Configuration d’Aspose.Slides pour Java

Intégrez la bibliothèque à votre projet en utilisant l’une des méthodes ci‑dessous.

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

Ou récupérez la dernière version depuis [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- **Essai gratuit** – évaluation de 30 jours.  
- **Licence temporaire** – période de test prolongée.  
- **Licence complète** – utilisation en production avec support premium.

## Guide étape par étape pour personnaliser le diagramme de dispersion Aspose

### 1️⃣ Préparer un dossier pour vos fichiers de présentation
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Pourquoi c’est important :* S’assurer que le dossier de sortie existe évite `FileNotFoundException` lors de l’enregistrement du PPTX.

### 2️⃣ Créer une nouvelle présentation et récupérer la première diapositive
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Un nouveau `Presentation` vous offre une toile vierge ; la première diapositive est l’endroit où nous placerons le diagramme.

### 3️⃣ Ajouter un diagramme de dispersion avec des lignes lisses
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` crée un diagramme de dispersion à lignes lisses, idéal pour visualiser les tendances.

### 4️⃣ Effacer les séries par défaut et ajouter les vôtres
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Supprimer les séries par défaut vous donne un contrôle total sur les données affichées.

### 5️⃣ Remplir la première série avec des points de données
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` prend une cellule de valeur X et une cellule de valeur Y, construisant le nuage de points point par point.

### 6️⃣ Personnaliser le type de série et l’apparence du marqueur
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Ici nous **personnalisons le diagramme de dispersion Aspose** en passant à des lignes droites, en agrandissant les marqueurs et en choisissant des symboles distincts (étoile vs. cercle) pour plus de clarté visuelle.

### 7️⃣ Enregistrer la présentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Enregistrer au format `Pptx` préserve toutes les personnalisations du diagramme et rend le fichier prêt à être partagé ou modifié.

## Cas d’utilisation courants pour les diagrammes de dispersion personnalisés
- **Tableaux de bord financiers** – tracer le cours de l’action vs. le volume.  
- **Recherche scientifique** – afficher des mesures expérimentales avec des marqueurs d’erreur.  
- **Gestion de projet** – comparer l’effort prévu vs. réel sur les tâches.  

## Conseils de performance
- Libérez l’objet `Presentation` (`pres.dispose()`) après l’enregistrement pour libérer les ressources natives.  
- Pour de grands ensembles de données, remplissez d’abord le classeur puis liez les séries afin d’éviter des rafraîchissements UI répétés.  
- Réutilisez une seule instance `IChartDataWorkbook` lors de l’ajout de nombreuses séries.

## Questions fréquemment posées

### Comment changer la couleur des marqueurs ?
Utilisez `series.getMarker().getFillFormat().setFillColor(Color)` où `Color` est une instance de `java.awt.Color` (par ex., `Color.RED`).

### Puis‑je ajouter plus de deux séries à un diagramme de dispersion ?
Absolument. Répétez l’appel `chart.getChartData().getSeries().add(...)` pour chaque série supplémentaire et remplissez ses points de données en conséquence.

### Est‑il possible de définir une légende personnalisée pour chaque série ?
Oui. Après avoir créé une série, appelez `series.getLegend().setText("Your Legend Text")` pour remplacer le nom par défaut.

### Comment exporter le diagramme en image plutôt qu’en PPTX ?
Appelez `chart.getImage().save("chart.png", ImageFormat.Png)` après avoir configuré le diagramme. Cela vous donne un fichier PNG autonome.

### Que faire si je dois animer les points de dispersion ?
Aspose.Slides prend en charge les effets d’animation. Utilisez `chart.getTimeline().getMainSequence().addEffect(...)` pour ajouter des animations d’entrée ou d’accentuation au diagramme ou aux séries individuelles.

---

**Dernière mise à jour :** 2026-02-24  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
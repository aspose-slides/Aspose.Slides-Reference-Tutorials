---
date: '2026-01-24'
description: Guide étape par étape pour créer un graphique de dispersion en Java avec
  Aspose.Slides, ajouter des points de données de dispersion et travailler avec plusieurs
  séries de graphiques de dispersion.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Créer un diagramme de dispersion Java avec Aspose.Slides – Personnaliser et
  enregistrer
url: /fr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un graphique de dispersion Java avec Aspose.Slides

Dans ce tutoriel, vous **créerez des projets de graphique de dispersion java** à partir de zéro, ajouterez des points de données de dispersion et apprendrez à travailler la présentation, la création du graphiqueurs, puis l’enregistrement de la présentation.

**Ce que vous allez apprendre**
- Configurer un répertoire pour stocker les fichiers de présentation  
- Initialiser et manipuler des présentations avec Aspose.Slides  
- Créer supérieur ( plus de Utilisez `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Une licence est‑elle nécessaire en production ?** Oui, une licence commerciale supprime les limites d’évaluation  

## Prérequis

Pour suivre ce tutoriel, assurez-vous d’avoir :
- **Aspose.Slides pour Java** – version 25.4 ou ultérieure.  
- **Java Development Kit (JDK)** – JDK 8 ou plus récent.  
- Des connaissances de base en Java et une familiarité avec Maven ou Gradle.  

## Installation d’Aspose.Slides pour Java

Intégrez Aspose.Slides à votre projet avec l’une des méthodes suivantes.

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

Ou téléchargez le dernier package depuis [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- **Essai gratuit** – évaluation de 30 jours.  
- **Licence temporaire** – test prolongé.  
- **Licence commerciale** – utilisation en production complète.

Passons maintenant au code.

## Guide de mise en œuvre

### Étape 1 : Configuration du répertoire
Tout d’abord, assurez‑vous que le dossier de sortie existe afin que la présentation puisse être enregistrée sans erreur.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Étape 2  nouvelle présentation et récupérez la première diapositive.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Étape 3 : Ajouter un graphique de dispersion
Insérez un graphique de dispersion avec des lignes lisses sur la diapositive.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Étape 4 : Gérer les données du graphique (effacer & ajouter des séries)
Supprimez les séries par défaut et ajoutez vos propres séries pour le **graphique de dispersion à séries multiples**.

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

### Étape 5 : Ajouter des points de données de dispersion
Alimentez chaque série avec des valeurs X‑Y en utilisant **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Étape 6 : Personnaliser les types de séries & les marqueurs
Ajustez le style visuel — passez à des lignes droites avec des marqueurs et définissez des symboles de marqueur distincts.

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

### Étape 7 : Enregistrer la présentation
Enregistrez le fichier sur le disque.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Applications pratiques
-ales en utilisant add data points scatter pour une représentation précise des données.  
- **Gestion de projet** – Montrer les tendances d’allocation des ressources à travers plusieurs projets sur un même graphique de dispersion.

## Considérations de performance
- Libérez l’objet `Presentation` après l’enregistrement pour libérer la mémoire.  
- Pour par lots plutôt qu’un point à la fois.  
- Évitez de trop styliser à l’intérieur de boucles serrées ; appliquez les styles après l’insertion des données.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Le graphique apparaît vide** | Vérifiez que les points de donnéesMarker().setSize()` est réglé sur une valeur supérieure à 0 et que le symbole du marque graphique de de création de séries (Étape 4) pour chaque série supplémentaire dont vous avez besoin.

### Est‑il possible d’exporter le graphique sous forme d’image ?
Oui. Appelez `chart.exportChartImage("chart.png", ImageFormat.Png)` après avoir ajouté toutes les données.

### Aspose.Slides prend‑il en charge les info-bulles interactives sur les points de dispersion ?
Bien que PowerPoint ne fournisse pas d’info-bulles à l’exécution, vous pouvez intégrer des étiquettes de données avec `series.getDataPoints().get_Item(i).getLabel().setText("Votre texte")`.

### Comment animer les séries de dispersion ?
Utilisez `chart.getChartData().get().setPresetEffect(PresetEffectType.Appear)` pour ajouter une animation d’apparition simple.

---

**Dernière mise à jour :** 2026-01-24  
**Testé avec :** Aspose.Slides pour Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
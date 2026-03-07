---
date: '2026-03-07'
description: Apprenez à créer un graphique linéaire en Java avec Aspose.Slides, ajoutez
  un titre au graphique, ajoutez des lignes de grille, formatez les étiquettes du
  graphique et enregistrez des présentations professionnelles.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Comment créer un graphique en courbes avec Aspose.Slides en Java – Guide complet
url: /fr/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique en courbes avec Aspose.Slides en Java

## Comment créer un graphique en courbes en Java avec Aspose.Slides

### Introduction
Créer des présentations visuellement attrayantes est crucial pour une communication efficace. Que vous soyez un professionnel du business ou un éducateur, vous avez souvent besoin de **créer des graphiques en courbes** visuels à la fois informatifs et esthétiquement plaisants. Dans ce tutoriel, nous allons parcourir l'utilisation de **Aspose.Slides for Java** pour générer un graphique en courbes, ajouter un titre au graphique, ajouter des lignes de grille, formater les étiquettes du graphique, et enregistrer le résultat sous forme de fichier PowerPoint.

#### Réponses rapides
- **Quelle bibliothèque est la meilleure pour créer des graphiques en Java ?** Aspose.Slides for Java
- **Quel type de graphique ce guide couvre-t-il ?** Graphique en courbes avec marqueurs
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Une licence temporaire gratuite suffit pour l’évaluation
- **Quel IDE puis‑je utiliser ?** Tout IDE Java tel qu’IntelliJ IDEA, Eclipse ou NetBeans
- **Comment les éléments du graphique sont‑ils formatés ?** En utilisant des appels d’API fluides pour les titres, les axes, les lignes de grille, les légendes et les arrière‑plans

### Qu’est‑ce qu’un graphique en courbes et pourquoi utiliser Aspose.Slides ?
Un graphique en courbes affiche des points de données reliés par des lignes droites, ce qui le rend idéal pour montrer des tendances au fil du temps. Aspose.Slides vous permet de créer et de personnaliser entièrement ces graphiques de manière programmatique, éliminant ainsi le besoin d’une édition manuelle de PowerPoint.

### Prérequis
- **Java Development Kit (JDK) 8+** installé
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, etc.)
- **Aspose.Slides for Java** library (ajoutée via Maven ou Gradle)

#### Bibliothèques et dépendances requises
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

Sinon, téléchargez le JAR le plus récent depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- Obtenez une [licence d'essai gratuite](https://purchase.aspose.com/temporary-license/) pour les tests.
- Achetez une licence complète sur le [site officiel d'Aspose](https://purchase.aspose.com/buy) pour une utilisation en production.

### Configuration d'Aspose.Slides pour Java
1. **Ajoutez la dépendance** indiquée ci‑dessus à votre projet.
2. **Appliquez la licence** (si vous en avez une) avant de créer tout objet de présentation.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Implémentation étape par étape

### Étape 1 : Créer le répertoire de sortie (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Pourquoi c’est important :* S’assurer que le dossier existe évite le `FileNotFoundException` lors de l’enregistrement ultérieur de la présentation.

### Étape 2 : Ajouter une diapositive et insérer un graphique en courbes
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Explication :* Cela crée une nouvelle diapositive et place un **graphique en courbes avec marqueurs** aux coordonnées spécifiées.

### Étape 3 : Ajouter le titre du graphique (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Conseil :* Utiliser un titre en gras et gris rend le graphique immédiatement reconnaissable.

### Étape 4 : Formater les axes et ajouter des lignes de grille (add grid lines)
#### Formatage de l'axe vertical
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Formatage de l'axe horizontal
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Pourquoi c’est important :* Des lignes de grille claires et des étiquettes pivotées améliorent la lisibilité, surtout lorsque les points de données sont denses.

### Étape 5 : Personnaliser la légende (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Étape 6 : Définir les couleurs d’arrière‑plan (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Étape 7 : Enregistrer la présentation
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Résultat :* Vous avez maintenant un fichier PowerPoint (`FormattedChart_out.pptx`) contenant un graphique en courbes entièrement formaté.

## Applications pratiques
- **Rapports d’entreprise :** Présenter la performance trimestrielle avec des lignes de tendance.
- **Diapositives éducatives :** Visualiser des données scientifiques pour les cours.
- **Propositions de projet :** Mettre en avant les jalons et les prévisions.
- **Analyse marketing :** Présenter les tendances du ROI des campagnes.
- **Intégration de tableau de bord :** Exporter des données en temps réel vers PowerPoint pour les réunions avec les parties prenantes.

## Considérations de performance
- **Gestion de la mémoire :** Appelez toujours `dispose()` sur l’objet `Presentation` pour libérer rapidement les ressources natives.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Licence non appliquée** | Chargez la licence d’essai/complète avant de créer tout objet `Presentation`. |
| **Le graphique apparaît vide** | Vérifiez que la diapositive contient réellement des séries de données ; ajoutez des séries si nécessaire. |
| **Fichier non enregistré** | Assurez‑vous que le répertoire de sortie existe (utilisez l’étape « create directory java »). |
| **Couleurs non appliquées** | Utilisez les constantes `Color` de `java.awt.Color` ou `PresetColor`. |

## Questions fréquemment posées

**Q : Puis‑je créer d’autres types de graphiques en plus des graphiques en courbes ?**  
R : Oui, Aspose.Slides prend en charge les graphiques à barres, secteurs, nuages de points, et bien d’autres types.

**Q : Comment ajouter plusieurs séries de données au graphique en courbes ?**  
R : Utilisez `chart.getChartData().getSeries().add(...)` pour insérer des séries supplémentaires avant le formatage.

**Q : Est‑il possible d’exporter le graphique sous forme d’image ?**  
R : Absolument. Appelez `chart.getChartData().getChartDataWorkbook().save(...)` ou rendez la diapositive dans un format d’image.

**Q : Ai‑je besoin d’une licence payante pour le développement ?**  
R : Une licence temporaire gratuite suffit pour l’évaluation ; une licence commerciale est requise pour les déploiements en production.

**Q : Quelles versions de Java sont prises en charge ?**  
R : La bibliothèque fonctionne avec JDK 8 à JDK 22 (utilisez le classificateur approprié, par ex. `jdk16`). 

---

**Dernière mise à jour :** 2026-03-07  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
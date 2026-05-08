---
date: '2026-02-17'
description: Apprenez à créer un graphique en anneau PowerPoint en utilisant Aspose.Slides
  for Java et à ajouter des points de données au graphique de manière programmatique.
  Suivez des étapes simples et des exemples de code.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Créer un diagramme en anneau PowerPoint avec Aspose.Slides pour Java
url: /fr/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un diagramme en anneau PowerPoint avec Aspose.Slides for Java

## Introduction
Créer des présentations percutantes nécessite souvent plus que du texte et des images ; les graphiques peuvent améliorer considérablement le storytelling en visualisant les données de manière efficace. Cependant, de nombreux développeurs peinent à intégrer des fonctionnalités de graphiques dynamiques dans les fichiers PowerPoint de façon programmatique. Ce tutoriel montre comment **créer un diagramme en anneau PowerPoint** avec Aspose.Slides for Java — un outil puissant qui combine flexibilité et facilité d’utilisation.

**Ce que vous apprendrez :**
- Comment initialiser une présentation avec Aspose.Slides for Java
- Un guide étape par étape pour ajouter un diagramme en anneau à vos diapositives
- Configurer les points de données et personnaliser les propriétés des étiquettes
- Enregistrer la présentation modifiée avec une haute fidélité

Explorons comment vous pouvez exploiter ces fonctionnalités pour améliorer vos présentations. Avant de commencer, assurez-vous de maîtriser les concepts de base de la programmation Java.

## Réponses rapides
- **Quelle bibliothèque crée un diagramme en anneau PowerPoint ?** Aspose.Slides for Java
- **Puis-je ajouter des points de données au graphique de façon programmatique ?** Oui, en utilisant l’API du graphique
- **Ai-je besoin d’une licence pour la production ?** Une licence valide d’Aspose.Slides est requise
- **Quelles versions de Java sont prises en charge ?** Java 8 et ultérieures (classificateur JDK 16 indiqué)
- **Combien de séries puis-je ajouter ?** L’exemple ajoute jusqu’à 15 séries, mais vous pouvez ajuster selon vos besoins

## Qu’est‑ce qu’un diagramme en anneau dans PowerPoint ?
Un diagramme en anneau est une variante du diagramme circulaire avec un centre creux, vous permettant d’afficher plusieurs séries de données de façon compacte et visuellement attrayante. Il est idéal pour montrer des relations partie‑tout tout en conservant un design épuré.

## Pourquoi utiliser Aspose.Slides for Java pour créer des diagrammes en anneau ?
- **Contrôle total** sur l’apparence du graphique, les données et la mise en page sans ouvrir PowerPoint
- **Pas d’interop COM** – fonctionne sur toute plateforme supportant Java
- **Haute performance** pour générer de grands jeux de diapositives ou s’intégrer aux services web
- **Personnalisation riche** comme l’explosion, la taille du trou, les angles des tranches et le formatage des étiquettes

## Prérequis
- Connaissances de base en programmation Java.
- Un IDE tel qu’IntelliJ IDEA ou Eclipse.
- Maven ou Gradle pour la gestion des dépendances.
- Une licence valide d’Aspose.Slides for Java (essai gratuit disponible).

## Configuration d’Aspose.Slides for Java
Choisissez le gestionnaire de dépendances qui convient à votre projet.

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

Si vous préférez télécharger directement, visitez la page des [versions d’Aspose.Slides for Java](https://releases.aspose.com/slides/java/) .

### Acquisition de licence
Vous pouvez commencer avec un essai gratuit pour explorer les fonctionnalités d’Aspose.Slides. Pour une utilisation prolongée, achetez une licence ou demandez une licence temporaire depuis le [site d’Aspose](https://purchase.aspose.com/temporary-license/). Suivez les instructions fournies pour configurer votre environnement et initialiser Aspose.Slides dans votre application.

## Comment créer un diagramme en anneau PowerPoint avec Aspose.Slides for Java
Voici un guide complet, étape par étape. Chaque bloc de code est expliqué juste avant, afin que vous sachiez exactement ce qui se passe.

### Étape 1 : Initialiser la présentation
Tout d’abord, chargez un PPTX existant ou créez‑en un nouveau. Cela prépare la collection de diapositives pour les modifications ultérieures.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Étape 2 : Ajouter un diagramme en anneau à la diapositive
Nous ajoutons la forme du graphique, supprimons les séries/catégories par défaut et définissons les propriétés visuelles de base.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Étape 3 : Ajouter des points de données au graphique et personnaliser les étiquettes
Ici nous remplissons les catégories, ajoutons des points de données pour chaque série et ajustons l’apparence des étiquettes. C’est à ce moment que le mot‑clé **add chart data points** entre en jeu.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Étape 4 : Enregistrer la présentation mise à jour
Enfin, persistez les modifications dans un nouveau fichier PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Applications pratiques
- **Rapports financiers :** Visualiser les allocations budgétaires ou la répartition des dépenses.
- **Analyse de marché :** Montrer la répartition des parts de marché entre les concurrents.
- **Résultats d’enquête :** Présenter les données d’enquête catégorielles de façon compacte.
- **Génération de tableaux de bord :** Combiner avec des requêtes de base de données pour générer des diapositives mises à jour en temps réel.

## Considérations de performance
- **Libérer les ressources** : Appelez `pres.dispose()` lorsque vous avez terminé pour libérer la mémoire native.
- **Limiter le nombre de graphiques** : Ajouter des centaines de graphiques peut augmenter l’utilisation de la mémoire ; traitez par lots si nécessaire.
- **Utiliser le streaming** : Pour des ensembles de données massifs, remplissez le classeur directement à partir de flux plutôt que d’arrays en mémoire.

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Le graphique apparaît vide** | Cellules de données non remplies correctement | Vérifiez que `workBook.getCell(...)` référence les bons indices de ligne/colonne. |
| **Les étiquettes se chevauchent** | Trop de catégories dans un espace limité | Augmentez `DoughnutHoleSize` ou ajustez `FirstSliceAngle`. |
| **OutOfMemoryError** | Présentations volumineuses sans libération | Appelez `pres.dispose()` après l’enregistrement et envisagez d’augmenter la taille du tas JVM. |

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.Slides for Java dans des applications commerciales ?**  
R : Oui, mais vous avez besoin d’une licence commerciale valide. Un essai gratuit est disponible pour l’évaluation.

**Q : Comment ajouter plus de 15 séries ?**  
R : Augmentez la limite de boucle dans l’étape « Ajouter un diagramme en anneau » et assurez‑vous que votre classeur de données possède suffisamment de lignes.

**Q : Est‑il possible de modifier la taille du trou du diagramme en anneau après création ?**  
R : Oui, appelez `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` à tout moment avant l’enregistrement.

**Q : Puis‑je exporter le graphique sous forme d’image au lieu d’un PPTX ?**  
R : Absolument. Utilisez `chart.getImage()` et enregistrez le `java.awt.image.BufferedImage` retourné dans le format de votre choix.

**Q : Aspose.Slides prend‑il en charge les graphiques animés ?**  
R : L’animation peut être ajoutée via l’API `ISlide.getTimeline()`, bien que cela dépasse le cadre de ce tutoriel.

## Conclusion
Vous disposez maintenant d’une méthode complète, prête pour la production, pour **créer des fichiers PowerPoint avec diagramme en anneau** à l’aide d’Aspose.Slides for Java, incluant comment **ajouter des points de données au graphique**, personnaliser les étiquettes et gérer les considérations de performance. Expérimentez avec différentes couleurs, sources de données et types de graphiques pour rendre vos présentations vraiment remarquables.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
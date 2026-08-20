---
date: '2026-08-16'
description: Apprenez comment ajouter des doughnut charts en Java avec Aspose.Slides.
  Ce guide étape par étape couvre la configuration des dépendances Maven, la configuration
  du diagramme, les couleurs, les libellés et l'enregistrement du PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Comment ajouter des doughnut charts en Java avec Aspose.Slides. Suivez
  ce guide pour configurer Maven, personnaliser les couleurs, les libellés et générer
  des fichiers PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Comment ajouter un doughnut chart en Java avec Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Comment ajouter un doughnut chart en Java avec Aspose.Slides
url: /fr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un diagramme en anneau en Java avec Aspose.Slides

## Introduction

Créer un **diagramme en anneau** de façon programmatique peut transformer des chiffres bruts en une visualisation attrayante qui raconte immédiatement une histoire. En Java, **Aspose.Slides** rend ce processus simple, vous permettant de générer des graphiques prêts pour une présentation sans jamais ouvrir PowerPoint. Dans ce tutoriel, vous apprendrez **comment ajouter des diagrammes en anneau** à un fichier PPTX étape par étape — de la configuration de la dépendance Maven Aspose Slides à la personnalisation des séries, catégories, couleurs et libellés, puis à l’enregistrement de la présentation.

À la fin de ce guide, vous serez capable d’intégrer des diagrammes en anneau dynamiques dans n’importe quel fichier PPTX, idéal pour les rapports, tableaux de bord ou présentations automatisées.

### Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Slides for Java  
- **Tâche principale ?** Ajouter un diagramme en anneau dans un fichier PPTX  
- **Comment ajouter la bibliothèque ?** Utiliser la dépendance Maven Aspose Slides (ou Gradle)  
- **Version minimale de Java ?** JDK 16 ou supérieur  
- **Puis‑je personnaliser les couleurs et les libellés ?** Oui, l’API offre un contrôle complet du formatage  

## Qu’est‑ce qu’un diagramme en anneau et pourquoi l’utiliser ?

Un diagramme en anneau est une variante du diagramme circulaire avec un centre vide, permettant d’afficher plusieurs séries de données sous forme d’anneaux concentriques. **Il visualise les parties d’un tout sur plusieurs catégories tout en conservant de l’espace au centre pour des informations supplémentaires.** Cela le rend idéal pour comparer les ventes par région sur plusieurs trimestres, les allocations budgétaires entre départements, ou tout scénario nécessitant de montrer des données proportionnelles hiérarchiques.

## Pourquoi utiliser Aspose.Slides pour Java ?

Vous pouvez ajouter un diagramme en anneau sans installer Microsoft Office, et la bibliothèque traite **plus de 50 + formats d’entrée et de sortie** tout en gérant des présentations de plus de 500 diapositives. Aspose.Slides offre **un rendu jusqu’à 3 × plus rapide** comparé à l’automatisation native d’Office sur le même matériel, et fonctionne sous Windows, Linux et macOS. Ces avantages quantifiés vous permettent de générer de grands jeux de diapositives sur des serveurs sans interface graphique avec des performances prévisibles.

## Prérequis

- **Bibliothèques requises**  
  - Aspose.Slides for Java 25.4 ou version ultérieure (la bibliothèque qui vous permet d’ajouter des diagrammes en anneau).  

- **Environnement**  
  - JDK 16 ou supérieur installé sur votre machine.  
  - Un IDE tel qu’IntelliJ IDEA, Eclipse ou NetBeans.  

- **Connaissances**  
  - Syntaxe Java de base et concepts orientés objet.  
  - Familiarité avec Maven ou Gradle pour la gestion des dépendances.  

## Dépendance Maven Aspose Slides

Ajoutez la dépendance Maven suivante à votre `pom.xml`. Il s’agit de la **dépendance Maven Aspose Slides** dont vous avez besoin pour intégrer la bibliothèque à votre projet.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Si vous préférez Gradle, utilisez le fragment équivalent ci‑dessous.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Vous pouvez également télécharger le JAR directement depuis la page officielle des versions :  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obtention d’une licence

Pour supprimer le filigrane d’évaluation et débloquer l’ensemble des fonctionnalités :

- **Essai gratuit** – commencez avec une licence temporaire.  
- **Licence temporaire** – demandez‑en une sur le [site Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licence commerciale** – achetez‑la pour une utilisation en production.

Appliquez la licence dans votre code :

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Guide d’implémentation

### Initialisation d’une présentation et ajout d’un diagramme en anneau

`Presentation` est la classe Aspose.Slides qui représente une présentation PowerPoint.  
Chargez un PPTX existant ou créez un nouvel objet `Presentation`, puis ajoutez un diagramme en anneau à la première diapositive.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Configuration du classeur de données du graphique et suppression des données existantes

Le classeur est une feuille de calcul interne qui stocke les données du graphique.  
Obtenez le classeur qui alimente le graphique, puis supprimez toute série ou catégorie par défaut afin de repartir d’une base propre.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Ajout de séries au graphique

Une série représente une collection de points de données tracés sur le graphique.  
Vous pouvez ajouter jusqu’à 15 séries. Chaque série peut être personnalisée — ici nous définissons l’explosion, la taille du trou d’anneau et l’angle de la première tranche.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Ajout de catégories et de points de données

Les catégories sont les libellés de chaque point de données le long de l’axe du graphique.  
Créez 15 catégories et remplissez chaque série avec un point de données. La dernière série reçoit un formatage spécial des libellés.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Personnalisation des couleurs et des libellés de données

`FillType.Solid` spécifie une couleur de remplissage solide pour les éléments du graphique.  
Définissez une couleur de remplissage solide pour chaque série et activez les libellés de données. Pour la série finale, nous changeons également la couleur de police du libellé.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Enregistrement de la présentation

`save` écrit la présentation dans un fichier au format choisi.  
Enregistrez la présentation mise à jour sur le disque au format PPTX, ou exportez‑la en PDF si nécessaire.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Problèmes courants et solutions

- **Licence introuvable** – Vérifiez que le chemin vers `license.lic` est correct et que le fichier est lisible.  
- **Le graphique apparaît vide** – Assurez‑vous d’avoir supprimé les séries/catégories existantes avant d’en ajouter de nouvelles.  
- **Couleurs incorrectes** – Confirmez que `FillType.Solid` est bien défini pour les formats de remplissage et de ligne.  
- **Performance avec de nombreuses séries** – Limitez le nombre de séries/catégories ou réutilisez les cellules du classeur pour garder la consommation mémoire sous contrôle.  

## FAQ

**Q : Puis‑je générer un diagramme en anneau sans fichier PPTX préexistant ?**  
R : Oui, créez `new Presentation()` pour démarrer à partir d’un jeu de diapositives vierge, puis ajoutez un graphique comme indiqué ci‑dessus.

**Q : Aspose.Slides prend‑il en charge l’exportation en PDF ?**  
R : Absolument. Après avoir créé le graphique, appelez `pres.save("output.pdf", SaveFormat.Pdf);` pour obtenir une version PDF de la diapositive.

**Q : Comment modifier la taille du trou d’anneau ?**  
R : Utilisez `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` où `value` varie de 0 à 100.

**Q : Est‑il possible d’ajouter des libellés de données à toutes les séries, pas seulement à la dernière ?**  
R : Oui, déplacez le bloc de formatage des libellés en dehors de la condition `if (i == ...)` et appliquez‑le à chaque `dataPoint`.

**Q : Quelles versions de Java sont prises en charge ?**  
R : Aspose.Slides 25.4 prend en charge JDK 16 et les versions ultérieures. Les JDK antérieurs nécessitent le classificateur approprié dans la dépendance Maven.

---

**Dernière mise à jour :** 2026-08-16  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur jdk16)  
**Auteur :** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Tutoriels associés

- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Comment personnaliser les couleurs d’un diagramme circulaire en Java avec Aspose.Slides – guide complet](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animer les catégories de graphiques PowerPoint avec Aspose.Slides pour Java | guide pas à pas](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
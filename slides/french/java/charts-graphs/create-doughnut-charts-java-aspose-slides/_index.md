---
date: '2026-03-07'
description: Apprenez à créer un graphique en anneau en Java avec Aspose.Slides. Ce
  guide étape par étape couvre la configuration de la dépendance Maven Aspose Slides,
  la configuration du graphique et l’enregistrement des présentations.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Créer un diagramme en anneau Java avec le guide Aspose.Slides
url: /fr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer un diagramme en anneau Java avec le guide Aspose.Slides

## Introduction

Créer un **diagramme en anneau** de façon programmatique peut transformer des chiffres bruts en une visualisation accrocheuse qui raconte instantanément une histoire. En Java, **Aspose.Slides** simplifie ce processus, vous permettant de générer des graphiques prêts pour une présentation sans jamais ouvrir PowerPoint. Dans ce tutoriel, vous apprendrez comment **créer un diagramme en anneau Java** étape par étape — depuis la configuration de la dépendance Maven Aspose Slides jusqu'à la personnalisation des séries, des catégories, et enfin l'enregistrement de la présentation.

À la fin de ce guide, vous serez capable d'intégrer des diagrammes en anneau dynamiques dans n'importe quel fichier PPTX, parfaits pour les rapports, les tableaux de bord ou les présentations automatisées.

### Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Slides for Java  
- **Tâche principale ?** Créer un diagramme en anneau Java dans un fichier PPTX  
- **Comment ajouter la bibliothèque ?** Utilisez la dépendance Maven Aspose Slides (ou Gradle)  
- **Version minimale de Java ?** JDK 16 ou supérieur  
- **Puis-je personnaliser les couleurs et les libellés ?** Oui, l'API offre un contrôle complet du formatage  

## Qu'est-ce qu'un diagramme en anneau et pourquoi l'utiliser ?

Un diagramme en anneau est une variante du diagramme circulaire avec un centre vide, permettant d'afficher plusieurs séries de données sous forme d'anneaux concentriques. Cela le rend idéal pour comparer des parties d'un tout à travers plusieurs catégories — par exemple les ventes par région sur plusieurs trimestres ou les allocations budgétaires par département.

## Pourquoi utiliser Aspose.Slides pour Java ?

- **Aucune installation d'Office requise** – générez des fichiers PPTX sur n'importe quel serveur.  
- **API riche** – contrôle complet sur les types de graphiques, les points de données et le style.  
- **Haute performance** – optimisé pour les présentations volumineuses.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS.

## Prérequis

- **Bibliothèques requises :**  
  - Aspose.Slides for Java version 25.4 ou ultérieure.  

- **Configuration de l'environnement :**  
  - JDK 16 ou supérieur.  
  - Votre IDE préféré (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Prérequis de connaissances :**  
  - Programmation Java de base.  
  - Familiarité avec Maven ou Gradle pour la gestion des dépendances.

## Dépendance Maven Aspose Slides

Ajoutez la dépendance Maven suivante à votre `pom.xml`. Il s'agit de la **dépendance maven aspose slides** nécessaire pour intégrer la bibliothèque à votre projet.

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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vous pouvez également télécharger le JAR directement depuis la page officielle des versions :  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obtention d'une licence

Pour supprimer le filigrane d'évaluation et débloquer l'ensemble complet des fonctionnalités :

- **Essai gratuit** – commencez avec une licence temporaire.  
- **Licence temporaire** – demandez‑en une sur le [site Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licence commerciale** – achetez‑la pour une utilisation en production.

Appliquez la licence dans votre code :

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guide d'implémentation

### Initialisation de la présentation et ajout d'un diagramme en anneau

Tout d'abord, créez ou chargez une présentation et ajoutez un diagramme en anneau à la première diapositive.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuration du classeur de données du graphique et suppression des données existantes

Ensuite, obtenez le classeur qui alimente le graphique et supprimez toutes les séries ou catégories par défaut.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Ajout de séries au graphique

Nous allons maintenant ajouter jusqu'à 15 séries. Chaque série peut être personnalisée — ici nous définissons l'explosion, la taille du trou du diagramme en anneau et l'angle de la première tranche.

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

### Ajout de catégories et de points de données

Nous créerons 15 catégories et remplirons chaque série avec un point de données. La dernière série reçoit un formatage spécial des libellés.

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

### Enregistrement de la présentation

Enfin, écrivez la présentation mise à jour sur le disque.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Problèmes courants et solutions

- **Licence introuvable** – Vérifiez que le chemin vers `license.lic` est correct et que le fichier est lisible.  
- **Le graphique apparaît vide** – Assurez‑vous d'avoir supprimé les séries/catégories existantes avant d'en ajouter de nouvelles.  
- **Couleurs incorrectes** – Vérifiez que `FillType.Solid` est défini à la fois pour le remplissage et le format de ligne.  
- **Performance avec de nombreuses séries** – Limitez le nombre de séries/catégories ou réutilisez les cellules du classeur.

## Questions fréquentes

**Q : Puis‑je générer un diagramme en anneau sans fichier PPTX préexistant ?**  
R : Oui, instanciez `new Presentation()` pour démarrer à partir d'un jeu de diapositives vierge.

**Q : Aspose.Slides prend‑il en charge l'exportation en PDF ?**  
R : Absolument. Après avoir créé le graphique, appelez `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q : Comment modifier la taille du trou du diagramme en anneau ?**  
R : Utilisez `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` où la valeur est comprise entre 0‑100.

**Q : Est‑il possible d'ajouter des libellés de données à toutes les séries, pas seulement à la dernière ?**  
R : Oui, déplacez le bloc de formatage des libellés en dehors de la condition `if (i == ...)` et appliquez‑le à chaque `dataPoint`.

**Q : Quelles versions de Java sont prises en charge ?**  
R : Aspose.Slides 25.4 prend en charge JDK 16 et les versions ultérieures. Les versions antérieures de JDK nécessitent le classificateur approprié.

---

**Dernière mise à jour :** 2026-03-07  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-17"
"description": "Apprenez à utiliser Aspose.Slides pour Java pour créer des graphiques en anneau dynamiques dans PowerPoint. Améliorez vos présentations grâce à des étapes faciles à suivre et des exemples de code."
"title": "Créer des graphiques en anneau dynamiques dans PowerPoint avec Aspose.Slides pour Java"
"url": "/fr/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques en anneau dynamiques dans PowerPoint avec Aspose.Slides pour Java

## Introduction
Créer des présentations convaincantes ne se limite souvent pas à du texte et des images ; les graphiques peuvent considérablement enrichir la narration en visualisant efficacement les données. Cependant, de nombreux développeurs peinent à intégrer les fonctionnalités de graphiques dynamiques dans les fichiers PowerPoint par programmation. Ce tutoriel montre comment utiliser Aspose.Slides pour Java pour créer un graphique en anneau dans PowerPoint : un outil puissant alliant flexibilité et simplicité d'utilisation.

**Ce que vous apprendrez :**
- Comment initialiser une présentation avec Aspose.Slides pour Java
- Un guide étape par étape pour ajouter un graphique en anneau à vos diapositives
- Configuration des points de données et personnalisation des propriétés des étiquettes
- Sauvegarde de la présentation modifiée avec une haute fidélité

Voyons comment exploiter ces fonctionnalités pour améliorer vos présentations. Avant de commencer, assurez-vous de bien connaître les concepts de base de la programmation Java.

## Prérequis
Pour suivre efficacement ce tutoriel, assurez-vous d'avoir :
- Connaissances de base de la programmation Java.
- Un environnement de développement intégré (IDE) comme IntelliJ IDEA ou Eclipse.
- Maven ou Gradle installé pour la gestion des dépendances.
- Une licence Aspose.Slides pour Java valide. Vous pouvez obtenir un essai gratuit pour tester ses fonctionnalités.

## Configuration d'Aspose.Slides pour Java
Commencez par intégrer Aspose.Slides à votre projet. Choisissez entre Maven et Gradle, selon vos préférences :

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

Si vous préférez télécharger directement, visitez le [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/) page.

### Acquisition de licence
Vous pouvez commencer par un essai gratuit pour explorer les fonctionnalités d'Aspose.Slides. Pour une utilisation prolongée, achetez une licence ou demandez-en une temporaire auprès de [Site Web d'Aspose](https://purchase.aspose.com/temporary-license/)Suivez les instructions fournies pour configurer votre environnement et initialiser Aspose.Slides dans votre application.

## Guide de mise en œuvre
Décomposons les étapes nécessaires à la création d'un graphique en anneau dans PowerPoint avec Aspose.Slides pour Java. Chaque section est consacrée à une fonctionnalité spécifique, pour plus de clarté et de précision.

### Initialiser la présentation
Commencez par charger ou créer un fichier PowerPoint. Cette étape configure votre environnement de présentation.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Vérifiez le chargement réussi en enregistrant la présentation initiale
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Ajouter un graphique en anneau
Ajoutez un graphique en anneau à votre diapositive, en personnalisant ses dimensions et son apparence.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configurer les propriétés de la série
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Configurer les points de données et les étiquettes
Personnalisez l'apparence de chaque point de données et configurez les étiquettes pour une meilleure lisibilité.

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
        
        // Formater le point de données
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Personnaliser les propriétés des étiquettes pour la dernière série de chaque catégorie
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

### Enregistrer la présentation
Après avoir configuré votre graphique, enregistrez la présentation pour conserver vos modifications.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Applications pratiques
Les graphiques en anneau peuvent être utilisés dans divers scénarios :
- **Rapports financiers :** Visualisez les allocations budgétaires ou les indicateurs financiers.
- **Analyse de marché:** Afficher la répartition des parts de marché entre les concurrents.
- **Résultats de l'enquête :** Présenter efficacement les données catégorielles issues des réponses aux enquêtes.

L'intégration avec d'autres systèmes, tels que des bases de données et des applications Web, permet la génération de graphiques dynamiques basés sur des données en temps réel.

## Considérations relatives aux performances
Pour des performances optimales :
- Gérez l’utilisation de la mémoire en éliminant rapidement les ressources.
- Limitez le nombre de graphiques ou de diapositives si cela n’est pas nécessaire pour économiser la puissance de traitement.
- Utilisez des structures de données efficaces pour gérer de grands ensembles de données.

Le respect des meilleures pratiques garantit le bon fonctionnement de votre application, en particulier lorsqu'il s'agit de présentations complexes.

## Conclusion
Créer des graphiques en anneau dynamiques dans PowerPoint avec Aspose.Slides pour Java est un processus simple une fois les étapes clés maîtrisées. Grâce à ce guide, vous êtes désormais prêt à améliorer vos présentations en intégrant des graphiques attrayants qui communiquent efficacement vos données.

Pour explorer davantage les fonctionnalités d'Aspose.Slides et approfondir ses capacités, envisagez d'expérimenter différents types de graphiques ou des fonctionnalités avancées telles que les animations et les transitions.

## Section FAQ
**Q : Puis-je utiliser Aspose.Slides pour Java dans des applications commerciales ?**
R : Oui, mais vous devrez acquérir une licence. Vous pouvez commencer par un essai gratuit pour évaluer ses fonctionnalités.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
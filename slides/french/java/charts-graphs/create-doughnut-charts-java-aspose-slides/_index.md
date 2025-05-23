---
"date": "2025-04-17"
"description": "Apprenez à créer de superbes graphiques en anneau en Java avec Aspose.Slides. Ce guide complet couvre l'initialisation, la configuration des données et l'enregistrement des présentations."
"title": "Créer des graphiques en anneau en Java à l'aide d'Aspose.Slides &#58; un guide complet"
"url": "/fr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques en anneau en Java avec Aspose.Slides : guide étape par étape

## Introduction

Dans l'environnement actuel axé sur les données, visualiser efficacement les informations est essentiel pour améliorer la compréhension et l'engagement. Créer des graphiques professionnels par programmation peut sembler complexe, surtout avec Java. Ce guide vous explique comment utiliser Aspose.Slides pour Java pour créer facilement des graphiques en anneau.

En suivant ces étapes, les développeurs acquerront une expérience pratique dans la manipulation de diapositives de présentation et l’intégration transparente de la visualisation des données.

**Points clés à retenir :**
- Initialisez un objet de présentation à l'aide d'Aspose.Slides Java.
- Configurez les données du graphique et gérez les séries ou catégories existantes.
- Ajoutez et personnalisez des séries et des catégories pour vos graphiques.
- Formatez et affichez efficacement les points de données.
- Enregistrez facilement votre présentation dans différents formats.

Avant de vous lancer dans la mise en œuvre, assurez-vous d’avoir tout ce dont vous avez besoin pour commencer.

## Prérequis

Pour suivre ce tutoriel, assurez-vous d'avoir :

- **Bibliothèques requises :**
  - Aspose.Slides pour Java version 25.4 ou ultérieure.
  
- **Configuration de l'environnement :**
  - JDK 16 ou supérieur installé sur votre système.
  - Un IDE comme IntelliJ IDEA, Eclipse ou NetBeans.

- **Prérequis en matière de connaissances :**
  - Compréhension de base des concepts de programmation Java.
  - Connaissance de la gestion des dépendances dans les projets Maven ou Gradle.

## Configuration d'Aspose.Slides pour Java

Pour intégrer Aspose.Slides dans votre projet, suivez ces étapes en fonction de votre outil de construction :

**Configuration Maven :**
Ajoutez la dépendance suivante à votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Configuration de Gradle :**
Incluez les éléments suivants dans votre `build.gradle` déposer:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct :**
Vous pouvez également télécharger la dernière version directement depuis [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Obtention d'une licence

Pour utiliser Aspose.Slides sans limitations d'évaluation :
- **Essai gratuit :** Commencez avec une licence temporaire pour explorer toutes les fonctionnalités.
- **Licence temporaire :** Obtenez-en un via le [Site Web d'Aspose](https://purchase.aspose.com/temporary-license/).
- **Achat:** Envisagez d’acheter pour une utilisation continue.

Appliquez votre licence dans votre application Java en utilisant :
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guide de mise en œuvre

### Initialisation de la présentation et du graphique

#### Aperçu
Commencez par initialiser un objet de présentation et ajoutez un graphique en anneau à la première diapositive.

**Étape 1 : Initialiser la présentation**
Chargez un fichier PPTX existant ou créez-en un nouveau :
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Étape 2 : Ajouter un graphique en anneau**
Créez un graphique sur la première diapositive aux coordonnées spécifiées :
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuration du classeur de données de graphique et suppression des séries/catégories existantes

#### Aperçu
Configurez le classeur de données du graphique et supprimez toutes les séries ou catégories préexistantes.

**Étape 1 : Accéder au classeur de données graphiques**
Récupérez le classeur lié à votre graphique :
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Étape 2 : Effacer les séries et catégories existantes**
Assurez-vous qu'il n'y a pas de points de données résiduels :
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Ajout de séries au graphique

#### Aperçu
Remplissez votre graphique avec plusieurs séries, chacune personnalisée en termes d'apparence et de comportement.

**Étape 1 : Ajouter des séries de manière itérative**
Boucle sur les indices pour ajouter des séries :
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Personnaliser la série
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Ajout de catégories et de points de données au graphique

#### Aperçu
Configurez des catégories et ajoutez des points de données avec un formatage spécifique pour les étiquettes.

**Étape 1 : Ajouter des catégories**
Boucle sur les indices pour chaque catégorie :
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Étape 2 : ajouter des points de données à chaque série**
Parcourez chaque série pour la catégorie actuelle :
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Paramètres de format de point de données
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formatage des étiquettes pour la dernière série
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

        // Ajuster les options d'affichage
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Ajuster la position de l'étiquette
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Enregistrer la présentation

#### Aperçu
Une fois votre graphique configuré, enregistrez la présentation dans un répertoire spécifié.

**Étape 1 : Enregistrer la présentation**
Utilisez le `save` méthode pour écrire les modifications :
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Vous avez maintenant appris à créer et personnaliser des graphiques en anneau en Java avec Aspose.Slides. Ces étapes constituent une base pour intégrer des visualisations de données sophistiquées à vos présentations.

**Prochaines étapes :**
- Expérimentez avec différents types de graphiques disponibles dans Aspose.Slides.
- Explorez des options de personnalisation supplémentaires telles que les couleurs, les polices et les styles pour répondre à vos besoins de marque.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
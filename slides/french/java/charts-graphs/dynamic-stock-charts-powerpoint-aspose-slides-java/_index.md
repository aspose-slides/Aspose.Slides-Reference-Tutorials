---
"date": "2025-04-17"
"description": "Apprenez à créer et personnaliser des graphiques boursiers dynamiques dans PowerPoint avec Aspose.Slides pour Java. Ce guide couvre l'initialisation des présentations, l'ajout de séries de données, la mise en forme des graphiques et l'enregistrement des fichiers."
"title": "Créer des graphiques boursiers dynamiques dans PowerPoint avec Aspose.Slides pour Java"
"url": "/fr/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques boursiers dynamiques dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Améliorez vos présentations PowerPoint en intégrant des graphiques boursiers dynamiques. Que vous soyez analyste financier, professionnel ou enseignant souhaitant visualiser efficacement les tendances des données, ce tutoriel vous guide dans la création et la personnalisation de graphiques boursiers avec Aspose.Slides pour Java. À la fin de ce guide, vous serez capable de charger des fichiers PowerPoint existants, d'ajouter des graphiques boursiers détaillés avec des séries et des catégories personnalisées, de les mettre en forme de manière élégante et d'enregistrer votre présentation améliorée.

**Ce que vous apprendrez :**
- Initialiser une présentation en Java avec Aspose.Slides
- Ajouter et personnaliser des graphiques boursiers
- Séries et catégories de données claires
- Insérer de nouveaux points de données pour une analyse complète
- Formater efficacement les lignes et les barres du graphique
- Enregistrer la présentation mise à jour

Prêt à créer des présentations visuellement attrayantes ? C'est parti !

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Kit de développement Java (JDK)**Assurez-vous que JDK est installé sur votre système.
- **IDE**:Utilisez n'importe quel IDE comme IntelliJ IDEA ou Eclipse pour écrire et exécuter du code Java.
- **Bibliothèque Aspose.Slides pour Java**: Ce tutoriel nécessite la version 25.4 d'Aspose.Slides pour Java.

### Configuration d'Aspose.Slides pour Java

#### Maven
Pour intégrer Aspose.Slides dans votre projet à l'aide de Maven, ajoutez la dépendance suivante à votre `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Pour les utilisateurs de Gradle, incluez ceci dans votre `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Téléchargement direct
Vous pouvez également télécharger le dernier JAR à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

**Acquisition de licence**: Vous pouvez commencer par un essai gratuit ou demander une licence temporaire. Pour une utilisation prolongée, envisagez l'achat d'une licence complète.

## Guide de mise en œuvre

Décomposons chaque fonctionnalité étape par étape.

### Initialiser la présentation
#### Aperçu
Commencez par charger un fichier PowerPoint existant pour le préparer aux modifications.

#### Guide étape par étape
1. **Importer la bibliothèque**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Charger le fichier de présentation**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Prêt à effectuer des opérations sur « pres »
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter un graphique boursier à la diapositive
#### Aperçu
Cette étape consiste à ajouter un graphique boursier à la première diapositive de votre présentation.

3. **Ajouter le graphique**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Effacer les séries de données et les catégories existantes dans le graphique
#### Aperçu
Supprimez toutes les séries de données ou catégories préexistantes du graphique pour repartir à zéro.

4. **Effacer les données**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter des catégories aux données du graphique
#### Aperçu
Ajoutez des catégories personnalisées pour une meilleure segmentation et compréhension des données.

5. **Insérer des catégories**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Ajouter des catégories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter une série de données au graphique
#### Aperçu
Intégrez différentes séries de données telles que l'ouverture, le plus haut, le plus bas et la clôture pour une analyse complète.

6. **Ajouter une série de données**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Ajoutez des séries pour « Ouvert », « Haut », « Bas » et « Fermeture »
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Ajouter des points de données à la série
#### Aperçu
Remplissez chaque série avec des points de données spécifiques pour une représentation précise.

7. **Insérer des points de données**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Ajouter des points de données à la série « Ouvrir »
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Ajouter des points de données à la série « Élevé »
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Ajouter des points de données à la série « Faible »
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Ajouter des points de données à la série « Fermer »
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formater les lignes hautes-basses et les barres haut/bas
#### Aperçu
Personnalisez l'apparence des lignes hautes-basses et des barres haut/bas pour une meilleure visualisation.

8. **Format des lignes hautes-basses**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Formater les lignes hautes et basses pour la série « Fermer »
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **Afficher les barres haut/bas**:
   
   ```java
   // Afficher les barres haut/bas pour le groupe de séries de graphiques boursiers
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Personnaliser les étiquettes de données sur les lignes hautes-basses
#### Aperçu
Ajoutez et formatez des étiquettes de données pour afficher les valeurs sur les lignes hautes et basses.

10. **Afficher les valeurs sur les barres haut/bas**:
    
    ```java
    // Afficher les valeurs sur les barres haut/bas pour chaque série du groupe de graphiques
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Définir les barres de haut en bas, remplir la couleur
#### Aperçu
Définissez une couleur de remplissage personnalisée pour les barres haut/bas afin d'améliorer la distinction visuelle.

11. **Changer les couleurs de la barre haut/bas**:
    
    ```java
    // Modifiez les couleurs des barres haut/bas pour chaque série du groupe de graphiques
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // Série « Ouvert »
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Barres montantes en cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // Série « High »
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Barres descendantes en vert mer foncé
        }
    }
    ```

### Enregistrer le fichier PowerPoint
#### Aperçu
Enregistrez vos modifications dans un nouveau fichier PowerPoint.

12. **Enregistrer la présentation**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Conclusion

Félicitations ! Vous avez créé et personnalisé avec succès des graphiques boursiers dynamiques dans PowerPoint avec Aspose.Slides pour Java. Ce processus enrichit vos présentations avec des visualisations de données attrayantes, vous permettant de communiquer efficacement des informations financières. Si vous souhaitez personnaliser davantage ou explorer d'autres types de graphiques, n'hésitez pas à consulter notre guide complet. [Documentation Aspose.Slides](https://docs.aspose.com/slides/java/).

## Lectures et références complémentaires
- Documentation Aspose.Slides pour Java : explorez des guides détaillés sur l’utilisation de diverses fonctionnalités d’Aspose.Slides.
- Présentation des outils de création de graphiques PowerPoint : découvrez les différents outils de création de graphiques disponibles dans Microsoft PowerPoint.
- Bonnes pratiques de visualisation des données : apprenez à présenter efficacement les données par des moyens visuels.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
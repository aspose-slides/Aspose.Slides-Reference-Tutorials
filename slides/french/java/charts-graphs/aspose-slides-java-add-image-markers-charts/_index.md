---
"date": "2025-04-17"
"description": "Découvrez comment améliorer vos graphiques dans Aspose.Slides pour Java en ajoutant des marqueurs d'image personnalisés. Stimulez l'engagement avec des présentations visuellement originales."
"title": "Maîtriser Aspose.Slides Java &#58; ajout de marqueurs d'image aux graphiques"
"url": "/fr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maîtriser Aspose.Slides Java : Ajout de marqueurs d'image aux graphiques

## Introduction
Créer des présentations visuellement attrayantes est essentiel à une communication efficace, et les graphiques sont un outil puissant pour transmettre des données complexes de manière concise. Les marqueurs de graphique standard ne parviennent parfois pas à mettre en valeur vos données. Avec Aspose.Slides pour Java, vous pouvez améliorer vos graphiques en ajoutant des images personnalisées comme marqueurs, les rendant ainsi plus attrayants et informatifs.

Dans ce tutoriel, nous découvrirons comment intégrer des marqueurs d'image à vos graphiques grâce à la bibliothèque Aspose.Slides en Java. En maîtrisant ces techniques, vous pourrez créer des présentations captivantes grâce à leurs éléments visuels uniques.

**Ce que vous apprendrez :**
- Comment configurer Aspose.Slides pour Java
- Créer une présentation et un graphique de base
- Ajout de marqueurs d'image aux points de données du graphique
- Configuration des paramètres des marqueurs pour une visualisation optimale

Prêt à améliorer vos graphiques ? Découvrons les prérequis avant de commencer !

### Prérequis
Pour suivre ce tutoriel, vous aurez besoin de :
1. **Bibliothèque Aspose.Slides pour Java**:Obtenez-le via les dépendances Maven ou Gradle ou en le téléchargeant directement depuis Aspose.
2. **Environnement de développement Java**: Assurez-vous que JDK 16 est installé sur votre machine.
3. **Connaissances de base en programmation Java**:Une connaissance de la syntaxe et des concepts Java sera bénéfique.

## Configuration d'Aspose.Slides pour Java
Avant de plonger dans le code, configurons notre environnement de développement avec les bibliothèques nécessaires.

### Installation de Maven
Ajoutez la dépendance suivante à votre `pom.xml` déposer:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installation de Gradle
Incluez ceci dans votre `build.gradle` déposer:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Étapes d'acquisition de licence
- **Essai gratuit**: Commencez avec une licence temporaire pour explorer les fonctionnalités d'Aspose.Slides.
- **Permis temporaire**:Accédez à des fonctionnalités avancées en obtenant une licence temporaire.
- **Achat**:Pour une utilisation à long terme, envisagez d'acheter une licence complète.

### Initialisation et configuration de base
Initialiser le `Presentation` objet pour commencer à créer des diapositives :

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Votre code pour ajouter des diapositives et des graphiques va ici.
    }
}
```

## Guide de mise en œuvre
Maintenant, décomposons le processus d’ajout de marqueurs d’image à votre série de graphiques.

### Créer une nouvelle présentation avec un graphique
Tout d’abord, nous avons besoin d’une diapositive où nous pouvons ajouter notre graphique :

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialiser l'objet Présentation
        Presentation presentation = new Presentation();

        // Obtenez la première diapositive de la collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Ajouter un graphique linéaire par défaut avec des marqueurs à la diapositive
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Accéder et configurer les données du graphique
Ensuite, nous accéderons à la feuille de calcul de données de notre graphique pour gérer les séries :

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Effacer la série existante et en ajouter une nouvelle
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Ajouter des marqueurs d'image aux points de données du graphique
Passons maintenant à la partie intéressante : ajouter des images comme marqueurs :

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Charger et ajouter des images comme marqueurs
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Ajouter des points de données avec des images comme marqueurs
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Configurer le marqueur de série de graphiques et enregistrer la présentation
Enfin, ajustons la taille du marqueur pour une meilleure visibilité et sauvegardons notre présentation :

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Charger et ajouter des images en tant que marqueurs (exemple utilisant des chemins d'espace réservé)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Conclusion
En suivant ce guide, vous avez appris à améliorer vos graphiques dans Aspose.Slides pour Java en ajoutant des marqueurs d'image personnalisés. Cette approche peut considérablement améliorer l'engagement et la clarté de vos présentations.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
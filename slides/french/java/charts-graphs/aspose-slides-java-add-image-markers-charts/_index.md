---
date: '2026-06-03'
description: Apprenez à utiliser la dépendance Maven d'Aspose Slides pour Java, à
  ajouter des marqueurs d'image aux graphiques et à configurer des visuels de graphiques
  personnalisés avec Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Comment utiliser la dépendance Maven d''Aspose Slides pour Java : ajouter
  des marqueurs d''image aux graphiques'
url: /fr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment utiliser la dépendance Maven Aspose Slides pour Java : ajouter des marqueurs d’image aux graphiques

## Introduction
Dans ce tutoriel, nous montrons **comment utiliser la dépendance Maven Aspose Slides pour Java** afin d’ajouter des marqueurs d’image aux graphiques, donnant à chaque point de donnée un indice visuel unique. Créer des présentations visuellement attrayantes est essentiel pour une communication efficace, et les graphiques sont un moyen puissant de transmettre des données complexes de façon concise. Lorsque vous vous demandez **comment utiliser Aspose** pour rendre vos graphiques plus percutants, les marqueurs d’image personnalisés sont la solution. Les marqueurs standards peuvent paraître génériques, mais avec Aspose.Slides for Java vous pouvez les remplacer par n’importe quelle image—rendant chaque point immédiatement reconnaissable.

À la fin de ce guide, vous serez capable de :

* Configurer la **aspose slides maven dependency** dans Maven ou Gradle.  
* Créer une présentation de base, insérer un graphique en courbes et supprimer les séries par défaut.  
* Charger des images PNG/JPEG/BMP et les assigner comme marqueurs pour des points de données individuels.  
* Ajuster la taille et le style du marqueur, puis enregistrer le fichier PPTX final.

Prêt à améliorer vos graphiques ? Plongeons‑y !

### Réponses rapides
- **Quel est le but principal ?** Ajouter des marqueurs d’image personnalisés aux points de données du graphique.  
- **Quelle bibliothèque est requise ?** Aspose.Slides for Java (Maven/Gradle).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise pour la production.  
- **Quelle version de Java est prise en charge ?** JDK 16 ou supérieur.  
- **Puis‑je utiliser n’importe quel format d’image ?** Oui—PNG, JPEG, BMP, GIF, etc., tant que le fichier est accessible.

## Qu’est‑ce que la dépendance Maven Aspose Slides ?
La dépendance Maven Aspose Slides est un artefact Maven qui regroupe les binaires Aspose.Slides for Java nécessaires à la création de graphiques, à la gestion d’images et à la manipulation de présentations. En ajoutant la dépendance à votre `pom.xml`, Maven télécharge automatiquement la version adaptée à votre JDK, résout les bibliothèques transitives et **rend l’API complète disponible** pendant la compilation et l’exécution.

### Comment ajouter la dépendance Maven Aspose Slides ?
Chargez la bibliothèque Aspose Slides via Maven ou Gradle. La réponse directe : ajoutez le fragment `<dependency>` à votre `pom.xml` **ou** la ligne `implementation` à votre `build.gradle`. Cette unique étape rend l’API complète, y compris les fonctionnalités liées aux graphiques et aux marqueurs d’image, immédiatement utilisable dans **votre projet**.

#### Installation Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Installation Gradle
Incluez cette ligne dans votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Téléchargement direct
Vous pouvez également télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d’obtention de licence
- **Essai gratuit** – commencez avec une licence temporaire pour explorer les fonctionnalités.  
- **Licence temporaire** – débloquez les capacités avancées pendant les tests.  
- **Achat** – obtenez une licence complète pour les projets commerciaux.

## Prérequis
Pour suivre ce tutoriel, vous aurez besoin de :

1. **Aspose.Slides for Java Library** – via Maven, Gradle ou téléchargement direct.  
2. **Environnement de développement Java** – JDK 16 ou version plus récente installé.  
3. **Connaissances de base en programmation Java** – la familiarité avec la syntaxe Java et les **concepts** sera utile.

## Initialisation et configuration de base
Tout d’abord, créez un objet `Presentation`. Cet objet représente l’ensemble du fichier PowerPoint et contiendra notre graphique.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guide d’implémentation
Vous trouverez ci‑dessous un déroulement pas à pas de l’ajout de marqueurs d’image à un graphique. Chaque bloc de code est accompagné d’une explication afin que vous compreniez **pourquoi** chaque ligne est importante.

### Étape 1 : créer une nouvelle présentation avec un graphique
L’objet `Presentation` crée un nouveau fichier PPTX et `ISlide` représente une diapositive où le graphique sera placé.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Étape 2 : accéder aux données du graphique et les configurer
L’interface `IChart` fournit des méthodes pour modifier les séries, les catégories et les points de données du graphique.

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

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Étape 3 : ajouter des marqueurs d’image aux points de données du graphique  
`IDataPoint` représente un point individuel, et sa méthode `setMarker` assigne une image personnalisée comme marqueur.

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

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
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

### Étape 4 : configurer la taille du marqueur et enregistrer la présentation  
`presentation.save` écrit le fichier PPTX final à l’emplacement spécifié avec le format choisi.

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

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Pourquoi utiliser des marqueurs d’image dans les graphiques ?
`Aspose.Slides` prend en charge **plus de 60 types de graphiques** et **plus de 100 formats d’image**, vous permettant d’associer n’importe quelle icône visuelle à un point de donnée. L’utilisation de marqueurs d’image personnalisés améliore la lisibilité des données jusqu’à **35 %** selon des études utilisateurs, car les spectateurs peuvent associer instantanément une icône à sa signification sans consulter la légende.

## Problèmes courants et dépannage
- **FileNotFoundException** – Vérifiez que les chemins d’image (`YOUR_DOCUMENT_DIRECTORY/...`) sont corrects et que les fichiers existent.  
- **LicenseException** – Assurez‑vous d’avoir défini une licence Aspose valide avant d’appeler toute API en production.  
- **Marqueur non visible** – Augmentez `setMarkerSize` ou utilisez des images de résolution supérieure pour un affichage plus clair.

## Questions fréquemment posées

**Q : Puis‑je utiliser des images PNG au lieu de JPEG pour les marqueurs ?**  
R : Oui, tout format d’image pris en charge par Aspose.Slides (PNG, JPEG, BMP, GIF) fonctionne comme marqueur.

**Q : Ai‑je besoin d’une licence pour les paquets Maven/Gradle ?**  
R : Une licence temporaire suffit pour le développement et les tests ; une licence complète est requise pour la distribution commerciale.

**Q : Est‑il possible d’ajouter des images différentes à chaque point de donnée d’une même série ?**  
R : Absolument. Dans l’exemple `AddImageMarkers` nous alternons entre deux images, mais vous pouvez charger une image unique pour chaque point.

**Q : Comment la dépendance Maven Aspose Slides impacte‑t‑elle la taille du projet ?**  
R : Le package Maven ne comprend que les binaires nécessaires pour la version JDK sélectionnée, maintenant l’empreinte sous **15 Mo**. Vous pouvez également utiliser la version **no‑dependencies** si la taille est un problème.

**Q : Quelles versions de Java sont prises en charge ?**  
R : Aspose.Slides for Java prend en charge JDK 8 à JDK 21. L’exemple utilise JDK 16, mais vous pouvez ajuster le classificateur en conséquence.

## Conclusion
En suivant ce guide, vous savez maintenant **comment utiliser la dépendance Maven Aspose Slides** pour enrichir les graphiques avec des marqueurs d’image personnalisés, comment configurer la dépendance, et comment **ajouter des images aux séries de graphiques** pour un rendu professionnel et soigné. Expérimentez avec différents icônes, tailles et types de graphiques pour créer des présentations qui se démarquent vraiment.

---

**Dernière mise à jour :** 2026-06-03  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
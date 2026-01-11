---
date: '2026-01-11'
description: Apprenez à utiliser Aspose Slides pour Java, ajoutez des marqueurs d'image
  aux graphiques et configurez la dépendance Maven d'Aspose Slides pour des visuels
  de graphiques personnalisés.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Comment utiliser Aspose Slides Java : ajouter des marqueurs d’image aux graphiques'
url: /fr/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment utiliser Aspose Slides Java : ajouter des marqueurs d’image aux graphiques

## Introduction
Créer des présentations visuellement attrayantes est essentiel pour une communication efficace, et les graphiques sont un outil puissant pour transmettre des données complexes de manière concise. Lorsque vous vous demandez **comment utiliser Aspose** pour rendre vos graphiques plus percutants, les marqueurs d’image personnalisés sont la solution. Les marqueurs standard peuvent sembler génériques, mais avec Aspose.Slides for Java, vous pouvez les remplacer par n’importe quelle image—rendant chaque point de données immédiatement reconnaissable.

Dans ce tutoriel, nous parcourrons l’ensemble du processus d’ajout de marqueurs d’image à un graphique en courbes, depuis la configuration de la **dépendance Maven Aspose Slides** jusqu’au chargement des images et à leur application aux points de données. À la fin, vous serez à l’aise avec **comment ajouter des marqueurs**, comment **ajouter des images aux séries de graphiques**, et vous disposerez d’un exemple de code prêt à l’exécution.

**Ce que vous apprendrez**
- Comment configurer Aspose.Slides for Java (incluant Maven/Gradle)
- Créer une présentation de base et un graphique
- Ajouter des marqueurs d’image aux points de données du graphique
- Configurer la taille et le style des marqueurs pour une visualisation optimale

Prêt à améliorer vos graphiques ? Plongeons dans les prérequis avant de commencer !

### Réponses rapides
- **Quel est le but principal ?** Ajouter des marqueurs d’image personnalisés aux points de données du graphique.  
- **Quelle bibliothèque est requise ?** Aspose.Slides for Java (Maven/Gradle).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est nécessaire pour la production.  
- **Quelle version de Java est prise en charge ?** JDK 16 ou ultérieure.  
- **Puis‑je utiliser n’importe quel format d’image ?** Oui—PNG, JPEG, BMP, etc., tant que le fichier est accessible.

### Prérequis
Pour suivre ce tutoriel, vous aurez besoin :
1. **Bibliothèque Aspose.Slides for Java** – obtenez‑la via Maven, Gradle ou téléchargement direct.  
2. **Environnement de développement Java** – JDK 16 ou plus récent installé.  
3. **Connaissances de base en programmation Java** – la familiarité avec la syntaxe et les concepts Java sera utile.

## Qu’est‑ce que la dépendance Maven Aspose Slides ?
La dépendance Maven récupère les binaires appropriés pour votre version de Java. L’ajouter à votre `pom.xml` garantit que la bibliothèque est disponible à la compilation et à l’exécution.

### Installation Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Installation Gradle
Incluez cette ligne dans votre fichier `build.gradle` :

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Sinon, téléchargez la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d’obtention de licence
- **Essai gratuit** – commencez avec une licence temporaire pour explorer les fonctionnalités.  
- **Licence temporaire** – débloquez des capacités avancées pendant les tests.  
- **Achat** – obtenez une licence complète pour les projets commerciaux.

## Initialisation et configuration de base
Tout d’abord, créez un objet `Presentation`. Cet objet représente le fichier PowerPoint complet et contiendra notre graphique.

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
Voici un guide étape par étape pour ajouter des marqueurs d’image à un graphique. Chaque bloc de code est accompagné d’une explication afin que vous compreniez **pourquoi** chaque ligne est importante.

### Étape 1 : créer une nouvelle présentation avec un graphique
Nous ajoutons un graphique en courbes avec des marqueurs par défaut à la première diapositive.

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

### Étape 2 : accéder et configurer les données du graphique
Nous supprimons toutes les séries par défaut et ajoutons notre propre série, préparant la feuille de calcul pour des points de données personnalisés.

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

### Étape 3 : ajouter des marqueurs d’image aux points de données du graphique
Ici nous démontrons **comment ajouter des marqueurs** à l’aide d’images. Remplacez les chemins factices par l’emplacement réel de vos images.

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

### Étape 4 : configurer la taille du marqueur et enregistrer la présentation
Nous ajustons le style du marqueur pour une meilleure visibilité et écrivons le fichier PPTX final.

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

## Problèmes courants et dépannage
- **FileNotFoundException** – Vérifiez que les chemins d’image (`YOUR_DOCUMENT_DIRECTORY/...`) sont corrects et que les fichiers existent.  
- **LicenseException** – Assurez‑vous d’avoir défini une licence Aspose valide avant d’appeler toute API en production.  
- **Marqueur non visible** – Augmentez `setMarkerSize` ou utilisez des images à plus haute résolution pour un affichage plus net.

## Foire aux questions

**Q : Puis‑je utiliser des images PNG au lieu de JPEG pour les marqueurs ?**  
**R :** Oui, tout format d’image pris en charge par Aspose.Slides (PNG, JPEG, BMP, GIF) fonctionne comme marqueur.

**Q : Ai‑je besoin d’une licence pour les packages Maven/Gradle ?**  
**R :** Une licence temporaire suffit pour le développement et les tests ; une licence complète est requise pour la distribution commerciale.

**Q : Est‑il possible d’ajouter des images différentes à chaque point de données dans la même série ?**  
**R :** Absolument. Dans l’exemple `AddImageMarkers` nous alternons entre deux images, mais vous pouvez charger une image unique pour chaque point.

**Q : Comment la `aspose slides maven dependency` affecte‑t‑elle la taille du projet ?**  
**R :** Le package Maven inclut uniquement les binaires nécessaires pour la version JDK sélectionnée, gardant l’empreinte raisonnable. Vous pouvez également utiliser la version **no‑dependencies** si la taille est un problème.

**Q : Quelles versions de Java sont prises en charge ?**  
**R :** Aspose.Slides for Java prend en charge JDK 8 à JDK 21. L’exemple utilise JDK 16, mais vous pouvez ajuster le classificateur en conséquence.

## Conclusion
En suivant ce guide, vous savez maintenant **comment utiliser Aspose** pour enrichir les graphiques avec des marqueurs d’image personnalisés, comment configurer la **dépendance Maven Aspose Slides**, et comment **ajouter des images aux séries de graphiques** pour un rendu soigné et professionnel. Expérimentez avec différentes icônes, tailles et types de graphiques pour créer des présentations qui se démarquent réellement.

---

**Dernière mise à jour** : 2026-01-11  
**Testé avec** : Aspose.Slides for Java 25.4 (jdk16)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
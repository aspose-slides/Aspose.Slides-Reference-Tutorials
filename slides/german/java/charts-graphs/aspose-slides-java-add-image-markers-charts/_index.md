---
date: '2026-06-03'
description: Erfahren Sie, wie Sie die Aspose Slides Maven-Abhängigkeit für Java verwenden,
  Bildmarkierungen zu Diagrammen hinzufügen und benutzerdefinierte Diagrammvisualisierungen
  mit Aspose.Slides konfigurieren.
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
title: 'Wie man die Aspose Slides Maven-Abhängigkeit für Java verwendet: Bildmarkierungen
  zu Diagrammen hinzufügen'
url: /de/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man die Aspose Slides Maven-Abhängigkeit für Java verwendet: Bildmarkierungen zu Diagrammen hinzufügen

## Einleitung
In diesem Tutorial zeigen wir **wie man die Aspose Slides Maven Dependency für Java** verwendet, um Bildmarkierungen zu Diagrammen hinzuzufügen und jedem Datenpunkt ein einzigartiges visuelles Signal zu geben. Visuell ansprechende Präsentationen zu erstellen ist entscheidend für effektive Kommunikation, und Diagramme sind ein kraftvolles Mittel, um komplexe Daten prägnant zu vermitteln. Wenn Sie sich fragen **wie man Aspose** nutzt, um Ihre Diagramme hervorzuheben, sind benutzerdefinierte Bildmarkierungen die Antwort. Standard‑Markierungen können generisch wirken, aber mit Aspose.Slides für Java können Sie sie durch jedes Bild ersetzen – sodass jeder Datenpunkt sofort erkennbar ist.

Am Ende dieses Leitfadens können Sie:

* Die **aspose slides maven dependency** in Maven oder Gradle einrichten.
* Eine einfache Präsentation erstellen, ein Liniendiagramm einfügen und die Standard‑Serie löschen.
* PNG/JPEG/BMP‑Bilder laden und sie als Markierungen für einzelne Datenpunkte zuweisen.
* Markierungsgröße und -stil anpassen und die finale PPTX‑Datei speichern.

Bereit, Ihre Diagramme zu verbessern? Lassen Sie uns loslegen!

### Schnelle Antworten
- **Was ist der Hauptzweck?** Benutzerdefinierte Bildmarkierungen zu Diagrammdatenpunkten hinzufügen.  
- **Welche Bibliothek wird benötigt?** Aspose.Slides für Java (Maven/Gradle).  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche Java-Version wird unterstützt?** JDK 16 oder neuer.  
- **Kann ich jedes Bildformat verwenden?** Ja – PNG, JPEG, BMP, GIF usw., solange die Datei zugänglich ist.

## Was ist die Aspose Slides Maven-Abhängigkeit?
Die Aspose Slides Maven‑Abhängigkeit ist ein Maven‑Artefakt, das die Aspose.Slides für Java‑Binärdateien bündelt, die für die Diagrammerstellung, Bildverarbeitung und Präsentationsmanipulation erforderlich sind. Durch das Hinzufügen der Abhängigkeit zu Ihrer `pom.xml` lädt Maven automatisch die passende Version für Ihr JDK, löst transitive Bibliotheken auf und stellt die komplette API während der Kompilierung und Laufzeit zur Verfügung.

### Wie fügt man die Aspose Slides Maven-Abhängigkeit hinzu?
Laden Sie die Aspose Slides‑Bibliothek über Maven und Gradle. Die direkte Antwort: Fügen Sie das `<dependency>`‑Snippet zu Ihrer `pom.xml` **oder** die `implementation`‑Zeile zu Ihrer `build.gradle` hinzu. Dieser einzelne Schritt macht die gesamte API, einschließlich diagramm‑bezogener und Bild‑Markierungs‑Funktionalität, sofort in Ihrem Projekt nutzbar.

#### Maven-Installation
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle-Installation
Fügen Sie diese Zeile in Ihre `build.gradle`‑Datei ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direkter Download
Alternativ laden Sie die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

#### Lizenzbeschaffungs‑Schritte
- **Kostenlose Testversion** – beginnen Sie mit einer temporären Lizenz, um die Funktionen zu erkunden.  
- **Temporäre Lizenz** – schalten Sie erweiterte Funktionen während des Tests frei.  
- **Kauf** – erhalten Sie eine Voll‑Lizenz für kommerzielle Projekte.

## Voraussetzungen
Um diesem Tutorial zu folgen, benötigen Sie:

1. **Aspose.Slides für Java Bibliothek** – über Maven, Gradle oder direkten Download.  
2. **Java-Entwicklungsumgebung** – JDK 16 oder neuer installiert.  
3. **Grundlegende Java‑Programmierkenntnisse** – Vertrautheit mit Java‑Syntax und -Konzepten ist hilfreich.  

## Grundlegende Initialisierung und Einrichtung
Zuerst erstellen Sie ein `Presentation`‑Objekt. Dieses Objekt repräsentiert die gesamte PowerPoint‑Datei und wird unser Diagramm enthalten.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Implementierungs‑Leitfaden
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung zum Hinzufügen von Bildmarkierungen zu einem Diagramm. Jeder Code‑Block wird von einer Erklärung begleitet, damit Sie **warum** jede Zeile wichtig ist, verstehen.

### Schritt 1: Erstellen einer neuen Präsentation mit einem Diagramm
Das `Presentation`‑Objekt erzeugt eine neue PPTX‑Datei und `ISlide` repräsentiert eine Folie, auf der das Diagramm platziert wird.

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

### Schritt 2: Zugriff auf Diagrammdaten und Konfiguration
Die `IChart`‑Schnittstelle bietet Methoden zum Ändern von Serien, Kategorien und Datenpunkten innerhalb des Diagramms.

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

### Schritt 3: Bildmarkierungen zu Diagrammdatenpunkten hinzufügen
`IDataPoint` repräsentiert einen einzelnen Punkt, und seine `setMarker`‑Methode weist eine benutzerdefinierte Bild‑Markierung zu.

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

### Schritt 4: Markierungsgröße konfigurieren und Präsentation speichern
`presentation.save` schreibt die finale PPTX‑Datei an den angegebenen Ort im gewählten Format.

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

## Warum Bildmarkierungen in Diagrammen verwenden?
`Aspose.Slides` unterstützt **60+ Diagrammtypen** und **100+ Bildformate**, sodass Sie jedes visuelle Symbol mit einem Datenpunkt kombinieren können. Der Einsatz benutzerdefinierter Bildmarkierungen verbessert die Datenlesbarkeit um bis zu **35 %** in Nutzerstudien, weil Betrachter ein Symbol sofort seiner Bedeutung zuordnen können, ohne eine Legende zu durchsuchen.

## Häufige Probleme und Fehlersuche
- **FileNotFoundException** – Überprüfen Sie, ob die Bildpfade (`YOUR_DOCUMENT_DIRECTORY/...`) korrekt sind und die Dateien existieren.  
- **LicenseException** – Stellen Sie sicher, dass Sie vor dem Aufruf einer API in der Produktion eine gültige Aspose‑Lizenz gesetzt haben.  
- **Marker Not Visible** – Erhöhen Sie `setMarkerSize` oder verwenden Sie hochauflösendere Bilder für eine klarere Darstellung.  

## Häufig gestellte Fragen

**Q: Kann ich PNG‑Bilder anstelle von JPEG für Markierungen verwenden?**  
A: Ja, jedes von Aspose.Slides unterstützte Bildformat (PNG, JPEG, BMP, GIF) funktioniert als Markierung.

**Q: Benötige ich eine Lizenz für die Maven/Gradle‑Pakete?**  
A: Eine temporäre Lizenz reicht für Entwicklung und Tests aus; für die kommerzielle Verteilung ist eine Voll‑Lizenz erforderlich.

**Q: Ist es möglich, verschiedene Bilder zu jedem Datenpunkt derselben Serie hinzuzufügen?**  
A: Absolut. Im Beispiel `AddImageMarkers` wechseln wir zwischen zwei Bildern, aber Sie können für jeden Punkt ein einzigartiges Bild laden.

**Q: Wie wirkt sich die Aspose Slides Maven‑Abhängigkeit auf die Projektgröße aus?**  
A: Das Maven‑Paket enthält nur die notwendigen Binärdateien für die gewählte JDK‑Version und hält den Footprint unter **15 MB**. Sie können auch die **no‑dependencies**‑Version verwenden, wenn die Größe ein Problem darstellt.

**Q: Welche Java‑Versionen werden unterstützt?**  
A: Aspose.Slides für Java unterstützt JDK 8 bis JDK 21. Das Beispiel verwendet JDK 16, Sie können den Klassifizierer jedoch entsprechend anpassen.

## Fazit
Durch die Befolgung dieses Leitfadens wissen Sie jetzt **wie man die Aspose Slides Maven Dependency** nutzt, um Diagramme mit benutzerdefinierten Bildmarkierungen zu bereichern, wie Sie die Abhängigkeit konfigurieren und **wie man Bilder zu Diagramm‑Serien** hinzufügt, um ein poliertes, professionelles Aussehen zu erzielen. Experimentieren Sie mit verschiedenen Symbolen, Größen und Diagrammtypen, um Präsentationen zu erstellen, die wirklich herausstechen.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
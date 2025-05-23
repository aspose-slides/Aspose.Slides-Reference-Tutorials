---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie Ihre Diagramme in Aspose.Slides für Java durch Hinzufügen benutzerdefinierter Bildmarkierungen optimieren. Steigern Sie das Engagement mit optisch ansprechenden Präsentationen."
"title": "Master Aspose.Slides Java&#58; Hinzufügen von Bildmarkierungen zu Diagrammen"
"url": "/de/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java meistern: Bildmarkierungen zu Diagrammen hinzufügen

## Einführung
Visuell ansprechende Präsentationen sind der Schlüssel zu effektiver Kommunikation. Diagramme sind ein leistungsstarkes Werkzeug, um komplexe Daten prägnant darzustellen. Standard-Diagrammmarkierungen reichen manchmal nicht aus, um Ihre Daten hervorzuheben. Mit Aspose.Slides für Java können Sie Ihre Diagramme durch Hinzufügen benutzerdefinierter Bilder als Markierungen optimieren und sie so ansprechender und informativer gestalten.

In diesem Tutorial erfahren Sie, wie Sie Bildmarkierungen mithilfe der Aspose.Slides-Bibliothek in Java in Ihre Diagramme integrieren. Mit diesen Techniken können Sie Präsentationen erstellen, die mit ihren einzigartigen visuellen Elementen die Aufmerksamkeit auf sich ziehen.

**Was Sie lernen werden:**
- So richten Sie Aspose.Slides für Java ein
- Erstellen einer grundlegenden Präsentation und eines Diagramms
- Hinzufügen von Bildmarkierungen zu Diagrammdatenpunkten
- Konfigurieren der Markierungseinstellungen für eine optimale Visualisierung

Bereit, Ihre Diagramme zu verbessern? Lassen Sie uns zunächst die Voraussetzungen besprechen!

### Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie:
1. **Aspose.Slides für die Java-Bibliothek**: Erhalten Sie es über Maven- oder Gradle-Abhängigkeiten oder durch direkten Download von Aspose.
2. **Java-Entwicklungsumgebung**: Stellen Sie sicher, dass JDK 16 auf Ihrem Computer installiert ist.
3. **Grundlegende Java-Programmierkenntnisse**: Kenntnisse der Java-Syntax und -Konzepte sind von Vorteil.

## Einrichten von Aspose.Slides für Java
Bevor wir uns in den Code stürzen, richten wir unsere Entwicklungsumgebung mit den erforderlichen Bibliotheken ein.

### Maven-Installation
Fügen Sie die folgende Abhängigkeit zu Ihrem `pom.xml` Datei:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle-Installation
Nehmen Sie dies in Ihre `build.gradle` Datei:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie die neueste Version von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

#### Schritte zum Lizenzerwerb
- **Kostenlose Testversion**: Beginnen Sie mit einer temporären Lizenz, um die Funktionen von Aspose.Slides zu erkunden.
- **Temporäre Lizenz**: Greifen Sie auf erweiterte Funktionen zu, indem Sie eine temporäre Lizenz erwerben.
- **Kaufen**: Für eine langfristige Nutzung sollten Sie den Erwerb einer Volllizenz in Erwägung ziehen.

### Grundlegende Initialisierung und Einrichtung
Initialisieren Sie den `Presentation` Objekt, um mit der Erstellung von Folien zu beginnen:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Ihr Code zum Hinzufügen von Folien und Diagrammen kommt hier hin.
    }
}
```

## Implementierungshandbuch
Lassen Sie uns nun den Vorgang zum Hinzufügen von Bildmarkierungen zu Ihrer Diagrammreihe aufschlüsseln.

### Erstellen einer neuen Präsentation mit einem Diagramm
Zuerst benötigen wir eine Folie, auf der wir unser Diagramm einfügen können:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialisieren Sie das Präsentationsobjekt
        Presentation presentation = new Presentation();

        // Holen Sie sich die erste Folie aus der Sammlung
        ISlide slide = presentation.getSlides().get_Item(0);

        // Fügen Sie der Folie ein Standardliniendiagramm mit Markierungen hinzu
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Zugreifen auf und Konfigurieren von Diagrammdaten
Als Nächstes greifen wir auf das Datenarbeitsblatt unseres Diagramms zu, um Reihen zu verwalten:

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

        // Vorhandene Serie löschen und eine neue hinzufügen
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Bildmarkierungen zu Diagrammdatenpunkten hinzufügen
Jetzt kommt der spannende Teil – das Hinzufügen von Bildern als Markierungen:

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

        // Bilder laden und als Markierungen hinzufügen
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Fügen Sie Datenpunkte mit Bildern als Markierungen hinzu
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

### Diagrammreihenmarkierung konfigurieren und Präsentation speichern
Zum Schluss passen wir die Markierungsgröße für eine bessere Sichtbarkeit an und speichern unsere Präsentation:

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

        // Bilder laden und als Markierungen hinzufügen (Beispiel mit Platzhalterpfaden)
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

## Abschluss
In dieser Anleitung erfahren Sie, wie Sie Ihre Diagramme in Aspose.Slides für Java durch Hinzufügen benutzerdefinierter Bildmarkierungen verbessern. Dieser Ansatz kann die Attraktivität und Übersichtlichkeit Ihrer Präsentationen deutlich steigern.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
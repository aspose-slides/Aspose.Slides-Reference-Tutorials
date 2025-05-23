---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java professionelle Präsentationen erstellen. Diese Anleitung beschreibt die Einrichtung Ihrer Umgebung, das Hinzufügen gestapelter Säulendiagramme und deren Anpassung für mehr Übersichtlichkeit."
"title": "Meistern Sie gestapelte Säulendiagramme in Java mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meistern Sie gestapelte Säulendiagramme in Java mit Aspose.Slides: Ein umfassender Leitfaden

## Einführung

Optimieren Sie Ihre Präsentationen durch aussagekräftige Datenvisualisierungen mit Aspose.Slides für Java. Professionelle Folien mit gestapelten Säulendiagrammen lassen sich ganz einfach erstellen – egal, ob Sie Geschäftsberichte erstellen oder Projektstatistiken präsentieren.

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java dynamische Präsentationen erstellen und optisch ansprechende gestapelte Säulendiagramme hinzufügen. Am Ende dieses Leitfadens verfügen Sie über die erforderlichen Kenntnisse für:
- Richten Sie Ihre Umgebung für die Verwendung von Aspose.Slides ein
- Erstellen Sie eine Präsentation von Grund auf neu
- Hinzufügen und Anpassen von prozentual gestapelten Säulendiagrammen
- Formatieren Sie Diagrammachsen und Datenbeschriftungen zur besseren Übersicht

Lassen Sie uns in die Erstellung von Präsentationen eintauchen, die Ihr Publikum fesseln.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Java Development Kit (JDK):** Version 8 oder höher.
- **IDE:** Jede integrierte Entwicklungsumgebung wie IntelliJ IDEA oder Eclipse.
- **Maven/Gradle:** Zum Verwalten von Abhängigkeiten (optional, aber empfohlen).
- **Grundlegende Java-Kenntnisse:** Vertrautheit mit Java-Programmierkonzepten.

## Einrichten von Aspose.Slides für Java
Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek in Ihr Projekt einbinden. So geht's:

**Maven:**
Fügen Sie diese Abhängigkeit zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Nehmen Sie dies in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktdownload:**
Alternativ können Sie die neueste JAR-Datei von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Lizenzerwerb
Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides kennenzulernen. Um die Testeinschränkungen aufzuheben, sollten Sie eine temporäre oder kostenpflichtige Lizenz erwerben.
- **Kostenlose Testversion:** Greifen Sie ohne sofortige Kosten auf eingeschränkte Funktionen zu.
- **Temporäre Lizenz:** Anfrage über [Asposes Website](https://purchase.aspose.com/temporary-license/).
- **Kaufen:** Besuchen Sie die Kaufseite, um vollständigen Zugriff zu erhalten.

### Grundlegende Initialisierung
So initialisieren Sie Aspose.Slides in Ihrer Java-Anwendung:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Erstellen Sie eine Instanz der Präsentationsklasse
        Presentation presentation = new Presentation();
        
        // Ausführen von Vorgängen am Präsentationsobjekt
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementierungshandbuch

### Erstellen einer Präsentation und Hinzufügen einer Folie
**Überblick:**
Beginnen Sie mit der Erstellung einer einfachen Präsentation mit einer ersten Folie. Diese bildet die Grundlage für weitere Verbesserungen.

#### Schritt 1: Präsentationsobjekt initialisieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Erstellen einer neuen Präsentationsinstanz
        Presentation presentation = new Presentation();
        
        // Verweis auf die erste Folie (automatisch erstellt)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Schritt 2: Speichern Sie die Präsentation
```java
// Speichern der Präsentation in einer Datei
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Hinzufügen eines gestapelten Prozentsäulendiagramms zu einer Folie
**Überblick:**
Verbessern Sie Ihre Folie, indem Sie ein prozentual gestapeltes Säulendiagramm hinzufügen, das einen einfachen Datenvergleich ermöglicht.

#### Schritt 1: Folie initialisieren und darauf zugreifen
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Fahren Sie im nächsten Schritt mit dem Hinzufügen eines Diagramms fort
    }
}
```

#### Schritt 2: Diagramm zur Folie hinzufügen
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Anpassen des Zahlenformats der Diagrammachsen
**Überblick:**
Passen Sie das Zahlenformat der vertikalen Achse Ihres Diagramms an, um die Lesbarkeit zu verbessern.

#### Schritt 1: Diagramm hinzufügen und darauf zugreifen
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Schritt 2: Benutzerdefiniertes Zahlenformat festlegen
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Hinzufügen von Reihen und Datenpunkten zum Diagramm
**Überblick:**
Füllen Sie Ihr Diagramm mit Datenreihen, um es informativ und optisch ansprechend zu gestalten.

#### Schritt 1: Präsentation und Diagramm initialisieren
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Schritt 2: Datenreihen hinzufügen
```java
// Vorhandene Serien löschen und neue hinzufügen
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Fügen Sie bei Bedarf weitere Datenpunkte hinzu
```

### Formatierungsreihen-Füllfarbe
**Überblick:**
Verbessern Sie die Ästhetik Ihres Diagramms, indem Sie die Füllfarbe jeder Reihe formatieren.

#### Schritt 1: Diagramm initialisieren und darauf zugreifen
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Schritt 2: Füllfarben festlegen
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Wiederholen Sie dies für andere Serien mit unterschiedlichen Farben
```

### Formatieren von Datenbeschriftungen
**Überblick:**
Machen Sie Ihre Datenbeschriftungen lesbarer, indem Sie ihr Format anpassen.

#### Schritt 1: Zugriff auf Diagrammreihen und Datenpunkte
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Schritt 2: Datenbeschriftungen anpassen
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Abschluss
In dieser Anleitung erfahren Sie, wie Sie Aspose.Slides für Java einrichten und dynamische Präsentationen mit prozentual gestapelten Säulendiagrammen erstellen. Passen Sie Ihre Diagramme weiter an, indem Sie Farben und Beschriftungen Ihren Bedürfnissen anpassen.

Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
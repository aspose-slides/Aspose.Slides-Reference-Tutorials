---
date: '2026-02-22'
description: Erfahren Sie, wie Sie ein gestapeltes Säulendiagramm in Java mit Aspose.Slides
  erstellen. Dieses Tutorial behandelt die Aspose Slides Maven‑Abhängigkeit, das Hinzufügen
  eines prozentual gestapelten Diagramms, das Formatieren von Diagrammdatenbeschriftungen
  und das Speichern der Präsentation als PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Wie man ein gestapeltes Säulendiagramm in Java mit Aspose.Slides erstellt –
  Ein umfassender Leitfaden
url: /de/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein gestapeltes Säulendiagramm in Java mit Aspose.Slides erstellt – Ein umfassender Leitfaden

## Einführung

Steigern Sie Ihre Präsentationen, indem Sie aussagekräftige Datenvisualisierungen mit der Leistungsfähigkeit von Aspose.Slides für Java einbinden. In diesem Leitfaden **erstellen Sie gestapelte Säulendiagramm‑Folien**, die professionell aussehen, egal ob Sie Geschäftsberichte vorbereiten oder Projektdaten präsentieren. Am Ende dieses Tutorials können Sie:

- Ihre Umgebung mit der Aspose Slides Maven‑Abhängigkeit einrichten
- Eine Präsentation von Grund auf neu erstellen
- **Ein prozentual gestapeltes Diagramm** hinzufügen und das Aussehen anpassen
- **Diagrammdatenbeschriftungen formatieren** und **das Zahlenformat der vertikalen Achse ändern**
- **Die Präsentation als PPTX** mit einer einzigen Codezeile speichern

Gehen wir die einzelnen Schritte durch, damit Sie sofort überzeugende Präsentationen erstellen können.

## Schnellantworten
- **Welche Bibliothek benötige ich?** `aspose-slides` Maven/Gradle‑Abhängigkeit (siehe unten „aspose slides maven dependency“)  
- **Welcher Diagrammtyp wird verwendet?** `ChartType.PercentsStackedColumn` für ein prozentual gestapeltes Säulendiagramm  
- **Wie ändere ich das Zahlenformat der Achse?** Verwenden Sie `IAxis.setNumberFormat()` und deaktivieren Sie die Verknüpfung zur Quelle  
- **Kann ich Datenbeschriftungen anpassen?** Ja – iterieren Sie über `IChartDataPoint`‑Objekte und setzen Sie ein benutzerdefiniertes `ITextFrame`  
- **Wie speichere ich die Datei?** Rufen Sie `presentation.save("output.pptx", SaveFormat.Pptx)` auf

## Was ist ein gestapeltes Säulendiagramm?
Ein gestapeltes Säulendiagramm visualisiert mehrere Datenreihen, die übereinander in vertikalen Säulen angeordnet sind. Wenn Sie die **prozentual gestapelte** Variante verwenden, summiert sich jede Säule stets auf 100 %, was den Vergleich von proportionalen Beiträgen über Kategorien hinweg erleichtert.

## Warum Aspose.Slides für Java verwenden?
Aspose.Slides bietet eine reine Java‑API, die auf jeder Plattform ohne installierte Microsoft‑Office‑Software funktioniert. Sie ermöglicht eine feinkörnige Steuerung von Diagrammobjekten, unterstützt zahlreiche Formate und lässt sich programmatisch zur Erstellung von Präsentationen nutzen – ideal für automatisierte Berichte oder serverseitige Dokumentengenerierung.

## Voraussetzungen
- **Java Development Kit (JDK):** 8 oder höher  
- **IDE:** IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor  
- **Build‑Tool:** Maven oder Gradle (optional, aber empfohlen)  
- **Grundlegende Java‑Kenntnisse** – Sie sollten mit Klassen und Methoden vertraut sein  

## Aspose.Slides für Java einrichten
Fügen Sie zunächst die Aspose.Slides‑Bibliothek zu Ihrem Projekt hinzu.

### Aspose Slides Maven‑Abhängigkeit
Fügen Sie das Folgende zu Ihrer `pom.xml` hinzu (dies ist die **aspose slides maven dependency**, die Sie benötigen):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑Alternative
Falls Sie Gradle bevorzugen, ergänzen Sie diese Zeile in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie das neueste JAR von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung
Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides zu erkunden. Um Evaluierungsbeschränkungen zu entfernen, sollten Sie eine temporäre oder gekaufte Lizenz erwerben.

- **Kostenlose Testversion:** Zugriff auf eingeschränkte Funktionen ohne sofortige Kosten.  
- **Temporäre Lizenz:** Anforderung über die [Aspose‑Website](https://purchase.aspose.com/temporary-license/).  
- **Kauf:** Besuchen Sie die Kaufseite für vollen Zugriff.

### Grundlegende Initialisierung
Hier ein minimaler Ausschnitt, der zeigt, wie ein `Presentation`‑Objekt erstellt wird:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementierungs‑Leitfaden

### Eine Präsentation erstellen und eine Folie hinzufügen
**Übersicht:**  
Zunächst erstellen wir eine leere Präsentation und prüfen, dass eine Folie vorhanden ist.

#### Schritt 1: Präsentationsobjekt initialisieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Schritt 2: Präsentation speichern
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Prozentual gestapeltes Säulendiagramm zu einer Folie hinzufügen
**Übersicht:**  
Jetzt platzieren wir ein **prozentual gestapeltes Diagramm** auf der ersten Folie.

#### Schritt 1: Folie initialisieren und zugreifen
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Schritt 2: Diagramm zur Folie hinzufügen
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Zahlenformat der Diagrammachse anpassen
**Übersicht:**  
Zur besseren Lesbarkeit **ändern wir das Zahlenformat der vertikalen Achse** auf Prozente.

#### Schritt 1: Diagramm hinzufügen und zugreifen
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

#### Schritt 2: Benutzerdefiniertes Zahlenformat setzen
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Serien und Datenpunkte zum Diagramm hinzufügen
**Übersicht:**  
Wir füllen das Diagramm mit Beispieldatenreihen.

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

#### Schritt 2: Datenserien hinzufügen
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Füllfarbe der Serien formatieren
**Übersicht:**  
Geben Sie jeder Serie eine eigene Farbe, um das Diagramm leichter lesbar zu machen.

#### Schritt 1: Diagramm initialisieren und zugreifen
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

#### Schritt 2: Füllfarben setzen
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Datenbeschriftungen formatieren
**Übersicht:**  
Jetzt **formatieren wir die Diagrammdatenbeschriftungen**, sodass sie benutzerdefinierten Text anzeigen.

#### Schritt 1: Diagrammserien und Datenpunkte zugreifen
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

## Häufige Probleme und Lösungen
- **Diagramm erscheint leer:** Stellen Sie sicher, dass Sie mindestens eine Datenreihe und einen Datenpunkt hinzugefügt haben, bevor Sie speichern.  
- **Achsenzahlen zeigen keine Prozente:** Denken Sie daran, `verticalAxis.setNumberFormatLinkedToSource(false)` zu setzen; sonst wird das benutzerdefinierte Format ignoriert.  
- **Lizenz‑Evaluierungsnachricht:** Laden Sie eine gültige Lizenzdatei, bevor Sie das `Presentation`‑Objekt erstellen, um das Evaluierungsbanner zu unterdrücken.

## Häufig gestellte Fragen

**F: Kann ich diesen Code mit Java 11 oder neuer verwenden?**  
A: Ja. Die Bibliothek unterstützt JDK 8+; verwenden Sie einfach den passenden Classifier (z. B. `jdk16` für JDK 16 oder höher).

**F: Wie exportiere ich das Diagramm als Bild statt als PPTX?**  
A: Verwenden Sie `chart.getImage().save("chart.png", ImageFormat.Png);` nachdem Sie das Diagramm zur Folie hinzugefügt haben.

**F: Ist es möglich, eine Legende zum gestapelten Säulendiagramm hinzuzufügen?**  
A: Absolut. Rufen Sie `chart.getChartTitle().addTextFrameForOverriding("My Chart");` auf und konfigurieren Sie `chart.getLegend()` nach Bedarf.

**F: Was, wenn ich Daten nach der Generierung der Präsentation aktualisieren muss?**  
A: Sie können die Zellen des `ChartDataWorkbook` ändern und anschließend `chart.refresh();` aufrufen, um die Änderungen zu übernehmen.

**F: Funktioniert Aspose.Slides auf Linux‑Servern?**  
A: Ja. Die Bibliothek ist reines Java und läuft auf jedem Betriebssystem mit einer kompatiblen JRE.

## Fazit
Durch die Befolgung dieses Leitfadens haben Sie gelernt, **gestapelte Säulendiagramm‑Präsentationen** mit Aspose.Slides für Java zu erstellen – von der Umgebungseinrichtung bis zur feinen visuellen Gestaltung. Experimentieren Sie mit verschiedenen Datensätzen, Farben und Beschriftungsformaten, um Ihre Berichte wirklich hervorzuheben.

---

**Zuletzt aktualisiert:** 2026-02-22  
**Getestet mit:** Aspose.Slides 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
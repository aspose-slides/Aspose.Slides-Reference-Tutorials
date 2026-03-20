---
date: '2026-03-20'
description: Erfahren Sie, wie Sie ein Diagramm zu Java‑Präsentationen mit Aspose.Slides
  hinzufügen und Präsentationsdiagrammdateien schnell erzeugen.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Wie man ein Diagramm zu Java‑Präsentationen mit Aspose.Slides hinzufügt
url: /de/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Diagramm zu einer Präsentation mit Aspose.Slides für Java hinzufügt

## Einführung

Dynamische Präsentationen zu erstellen, die Daten effektiv vermitteln, ist in der heutigen schnelllebigen Geschäftswelt unerlässlich. Egal, ob Sie einen Finanzbericht, ein Marketing‑Deck oder ein Projekt‑Status‑Update vorbereiten – **zu wissen, wie man ein Diagramm** zu Ihren Folien hinzufügt, kann die Zuschauerbindung erheblich steigern. In diesem Tutorial lernen Sie Schritt für Schritt, wie Sie ein 3D‑gestapeltes Säulendiagramm hinzufügen, dessen Daten konfigurieren und die endgültige Datei speichern – alles mit Aspose.Slides für Java.

### Schnellantworten
- **Was ist die primäre Bibliothek?** Aspose.Slides für Java  
- **Welcher Diagrammtyp wird demonstriert?** 3D‑gestapelte Säule  
- **Kann ich Präsentations‑Diagrammdateien programmgesteuert erzeugen?** Ja, mit den unten gezeigten API‑Methoden  
- **Welche Java‑Version wird empfohlen?** JDK 16 oder höher  
- **Benötige ich eine Lizenz für die Produktion?** Eine gültige Aspose.Slides‑Lizenz ist für die kommerzielle Nutzung erforderlich  

## Was bedeutet „how to add chart“ in Aspose.Slides?

Aspose.Slides für Java bietet ein umfangreiches Set an Objekten, mit denen Sie PowerPoint‑Dateien ohne Microsoft Office erstellen, bearbeiten und exportieren können. Ein Diagramm hinzuzufügen ist so einfach wie das Erzeugen eines `Presentation`‑Objekts, das Einfügen einer Diagramm‑Form und das Befüllen über das integrierte Workbook.

## Warum ein Diagramm zu Java‑Präsentationen hinzufügen?

- **Visuelle Wirkung:** Diagramme verwandeln Rohdaten in sofort verständliche Visualisierungen.  
- **Automatisierung:** Berichte on‑the‑fly generieren – ideal für geplante E‑Mail‑Zusammenfassungen oder Dashboards.  
- **Konsistenz:** Einheitliches Styling und Branding in allen erzeugten Decks verwenden.  
- **Portabilität:** Mit einem einzigen Methodenaufruf nach PPTX, PDF oder Bild exportieren.

## Voraussetzungen

- **Bibliotheken und Abhängigkeiten:** Aspose.Slides für Java muss installiert sein.  
- **Umgebungs‑Setup:** Arbeiten Sie in einer Java‑Umgebung (empfohlen JDK 16 oder höher).  
- **Wissensbasis:** Grundkenntnisse in Java‑Programmierung sind von Vorteil.

## Einrichtung von Aspose.Slides für Java

### Installation

Um Aspose.Slides in Ihr Projekt zu integrieren, folgen Sie einer der nachstehenden Optionen.

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

**Direkter Download**: Alternativ laden Sie die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

### Lizenzbeschaffung
- **Kostenlose Testversion:** Starten Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.  
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz für ausgedehnte Tests.  
- **Kauf:** Erwerb einer Voll‑Lizenz für die kommerzielle Nutzung.

Nach der Installation können Sie die Klasse `Presentation` instanziieren, die als Einstiegspunkt für alle diagrammbezogenen Vorgänge dient.

## Implementierungs‑Leitfaden

### Wie man ein Diagramm zu einer Präsentation mit einer 3D‑gestapelten Säule hinzufügt

#### Überblick
Eine Präsentation von Grund auf zu erstellen ist mit Aspose.Slides unkompliziert. In diesem Abschnitt fügen wir ein 3D‑gestapeltes Säulendiagramm zur ersten Folie unserer Präsentation hinzu.

**Schritte:**

1. **Presentation‑Objekt initialisieren**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Parameter erläutern**  
   - `ChartType.StackedColumn3D`: Gibt den Diagrammtyp an.  
   - Position und Größe `(0, 0, 500, 500)`: Bestimmt, wo das Diagramm auf der Folie erscheint.

### Diagrammdaten konfigurieren

#### Überblick
Damit Ihr Diagramm aussagekräftig wird, konfigurieren Sie die Datenreihen und Kategorien. Dieser Abschnitt zeigt, wie Sie bestimmte Datenpunkte zu Ihrem Diagramm hinzufügen.

**Schritte:**

1. **Auf das Daten‑Workbook des Diagramms zugreifen**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Rotation3D‑Eigenschaften für das Diagramm festlegen

#### Überblick
Verbessern Sie die optische Attraktivität Ihres Diagramms mit 3D‑Rotations‑Eigenschaften. Diese Anpassung ermöglicht das Einstellen von Perspektive und Tiefe.

**Schritte:**

1. **3D‑Rotationen konfigurieren**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Parameter erläutern**  
   - `setRightAngleAxes(true)`: Stellt sicher, dass die Achsen rechtwinklig zueinander stehen.  
   - Rotationswerte: Passen Sie den Winkel und die Tiefe der 3D‑Ansicht an.

### Datenreihen im Diagramm befüllen

#### Überblick
Das Befüllen Ihres Diagramms mit Datenpunkten ist für Analysen entscheidend. Hier fügen wir einer Reihe im Diagramm konkrete Werte hinzu.

**Schritte:**

1. **Datenpunkte hinzufügen**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Überlappung der Datenreihen im Diagramm anpassen

#### Überblick
Feinabstimmung des Erscheinungsbildes Ihres Diagramms kann die Lesbarkeit verbessern. Dieser Abschnitt erklärt, wie Sie die Überlappungs‑Eigenschaft für eine bessere Datenvisualisierung einstellen.

**Schritte:**

1. **Series Overlap setzen**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Präsentation speichern

#### Überblick
Nachdem Ihre Präsentation konfiguriert ist, speichern Sie sie im gewünschten Format auf dem Datenträger. Dieser Schritt stellt sicher, dass alle Änderungen erhalten bleiben.

**Schritte:**

1. **Präsentation speichern**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **Diagramm erscheint flach** | 3D‑Rotation nicht gesetzt | `setRotation3D` mit geeigneten X/Y‑Werten aufrufen. |
| **Daten werden nicht angezeigt** | Workbook‑Zellen nicht verknüpft | Sicherstellen, dass `fact.getCell` die korrekten Zeilen‑/Spalten‑Indizes referenziert. |
| **Datei wird nicht gespeichert** | Falscher Pfad oder fehlende Berechtigungen | Prüfen, ob `outputFilePath` beschreibbar ist und das Verzeichnis existiert. |

## Häufig gestellte Fragen

**F: Kann ich Präsentations‑Diagrammdateien in anderen Formaten als PPTX erzeugen?**  
A: Ja, Aspose.Slides unterstützt PDF, ODP und Bildformate über das `SaveFormat`‑Enum.

**F: Benötige ich eine Lizenz, um den Code in der Entwicklung auszuführen?**  
A: Eine temporäre oder Evaluations‑Lizenz reicht für die Entwicklung aus, für Produktions‑Deployments ist jedoch eine Voll‑Lizenz erforderlich.

**F: Ist es möglich, mehrere Diagramme auf derselben Folie zu platzieren?**  
A: Absolut. Rufen Sie `slide.getShapes().addChart` mehrfach mit unterschiedlichen Positionen oder Größen auf.

**F: Wie ändere ich die Farbpalette des Diagramms?**  
A: Verwenden Sie `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` und setzen Sie eine `SolidFillColor`.

**F: Kann ich das Diagramm an eine externe Datenquelle wie eine Datenbank binden?**  
A: Ja. Daten per JDBC abrufen und dann die Workbook‑Zellen programmgesteuert befüllen, bevor Sie speichern.

## Fazit

Sie haben nun gelernt, **wie man ein Diagramm** zu einer Java‑Präsentation hinzufügt, dessen Daten konfiguriert, die 3D‑Rotation angepasst, die Überlappung der Reihen eingestellt und die endgültige Datei gespeichert. Dieses Wissen ermöglicht Ihnen die Automatisierung der Berichtserstellung, die konsistente Markenbildung und die Bereitstellung datengetriebener Präsentationen ohne manuellen Aufwand. Für weitergehende Anpassungen – etwa das Stylen von Legenden, Achsen oder das Anwenden von Themes – erkunden Sie die umfassenden Möglichkeiten in der offiziellen Dokumentation.

Für erweiterte Funktionen und Anpassungsoptionen lesen Sie bitte die [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-20  
**Getestet mit:** Aspose.Slides für Java 25.4 (JDK 16)  
**Autor:** Aspose
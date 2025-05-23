---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides dynamische Präsentationen mit Diagrammen in Java erstellen und konfigurieren. Meistern Sie das effektive Hinzufügen, Anpassen und Speichern von Präsentationen."
"title": "Erstellen Sie Java-Präsentationen mit Diagrammen mit Aspose.Slides für Java"
"url": "/de/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und konfigurieren Sie eine Präsentation mit einem Diagramm mithilfe von Aspose.Slides für Java

## Einführung

Dynamische Präsentationen, die Daten effektiv vermitteln, sind in der heutigen schnelllebigen Geschäftswelt unerlässlich. Ob Sie einen Finanzbericht erstellen oder Projektkennzahlen präsentieren – Diagramme können die Wirkung Ihrer Präsentation deutlich steigern. Dieses Tutorial führt Sie durch die Erstellung und Konfiguration einer Präsentation mit einem gestapelten 3D-Säulendiagramm mithilfe von Aspose.Slides für Java, einer leistungsstarken Bibliothek für die programmgesteuerte Präsentationsverwaltung.

**Was Sie lernen werden:**
- So erstellen Sie eine neue Präsentation
- Diagramme in Folien hinzufügen und konfigurieren
- Anpassen der Diagrammdaten und des Erscheinungsbilds
- Speichern Sie Ihre Präsentation effektiv

Sind Sie bereit, visuell ansprechende Präsentationen mit Java zu erstellen? Dann legen wir los!

## Voraussetzungen

Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

- **Bibliotheken und Abhängigkeiten**: Aspose.Slides für Java muss installiert sein.
- **Umgebungs-Setup**: Arbeiten Sie in einer Java-Umgebung (JDK 16 oder höher empfohlen).
- **Wissensdatenbank**: Kenntnisse der grundlegenden Konzepte der Java-Programmierung sind von Vorteil.

## Einrichten von Aspose.Slides für Java

### Installation

Um Aspose.Slides in Ihr Projekt zu integrieren, gehen Sie folgendermaßen vor:

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

**Direkter Download**: Alternativ können Sie die neueste Version von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Lizenzerwerb
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.
- **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz für erweiterte Tests.
- **Kaufen**: Erwerben Sie eine Volllizenz für die kommerzielle Nutzung.

Nach der Installation initialisieren Sie die Bibliothek in Ihrer Java-Umgebung, indem Sie eine Instanz der `Presentation` Klasse. Dies legt den Grundstein für das Hinzufügen von Diagrammen und anderen Elementen zu Ihrer Präsentation.

## Implementierungshandbuch

### Erstellen und Konfigurieren einer Präsentation mit einem Diagramm

#### Überblick
Mit Aspose.Slides ist das Erstellen einer Präsentation von Grund auf ganz einfach. In diesem Abschnitt fügen wir der ersten Folie unserer Präsentation ein gestapeltes 3D-Säulendiagramm hinzu.

**Schritte:**

1. **Präsentationsobjekt initialisieren**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialisieren Sie ein neues Präsentationsobjekt
           Presentation presentation = new Presentation();
           
           // Greifen Sie auf die erste Folie der Präsentation zu
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Fügen Sie der Folie an Position (0,0) ein gestapeltes 3D-Säulendiagramm hinzu
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

2. **Parameter erklären**:
   - `ChartType.StackedColumn3D`: Gibt den Diagrammtyp an.
   - Position und Größe `(0, 0, 500, 500)`: Bestimmt, wo das Diagramm auf der Folie angezeigt wird.

### Konfigurieren der Diagrammdaten

#### Überblick
Konfigurieren Sie die Datenreihen und Kategorien Ihres Diagramms, um es aussagekräftiger zu gestalten. Dieser Abschnitt zeigt, wie Sie Ihrem Diagramm spezifische Datenpunkte hinzufügen.

**Schritte:**

1. **Access Chart-Datenarbeitsmappe**

   ```java
   public static void configureChartData(IChart chart) {
       // Legen Sie den Index des Arbeitsblatts fest, das Diagrammdaten enthält
       int defaultWorksheetIndex = 0;
       
       // Zugriff auf die Datenarbeitsmappe des Diagramms
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Fügen Sie zwei Serien mit Namen hinzu
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Drei Kategorien hinzufügen
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Rotation3D-Eigenschaften für Diagramm festlegen

#### Überblick
Verbessern Sie die visuelle Attraktivität Ihres Diagramms mit 3D-Rotationseigenschaften. Mit dieser Anpassung können Sie Perspektive und Tiefe anpassen.

**Schritte:**

1. **3D-Rotationen konfigurieren**

   ```java
   public static void setRotation3D(IChart chart) {
       // Aktivieren Sie rechtwinklige Achsen und konfigurieren Sie Drehungen in X- und Y-Richtung sowie die Tiefe in Prozent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Parameter erklären**:
   - `setRightAngleAxes(true)`: Stellt sicher, dass die Achsen senkrecht sind.
   - Rotationswerte: Passt den Winkel und die Tiefe der 3D-Ansicht an.

### Datenreihen im Diagramm auffüllen

#### Überblick
Das Füllen Ihres Diagramms mit Datenpunkten ist für die Analyse entscheidend. Hier fügen wir einer Reihe in unserem Diagramm bestimmte Werte hinzu.

**Schritte:**

1. **Datenpunkte hinzufügen**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Zugriff auf die zweite Diagrammreihe
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Datenpunkte für Balkenreihen mit angegebenen Werten hinzufügen
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

### Serienüberlappung im Diagramm anpassen

#### Überblick
Durch die Feinabstimmung der Darstellung Ihres Diagramms können Sie die Lesbarkeit verbessern. In diesem Abschnitt erfahren Sie, wie Sie die Überlappungseigenschaft für eine bessere Datenvisualisierung anpassen.

**Schritte:**

1. **Serienüberlappung festlegen**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Holen Sie sich die zweite Reihe aus dem Diagramm und setzen Sie ihre Überlappung auf 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Präsentation speichern

#### Überblick
Sobald Ihre Präsentation konfiguriert ist, speichern Sie sie im gewünschten Format auf der Festplatte. Dadurch wird sichergestellt, dass alle Änderungen erhalten bleiben.

**Schritte:**

1. **Speichern der Präsentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Speichern Sie die geänderte Präsentation in einer Datei
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Abschluss

Sie haben nun gelernt, wie Sie mit Aspose.Slides für Java Präsentationen mit Diagrammen erstellen und konfigurieren. Diese Anleitung behandelt das Initialisieren einer Präsentation, das Hinzufügen eines gestapelten 3D-Säulendiagramms, das Konfigurieren von Datenreihen und Kategorien, das Festlegen von Rotationseigenschaften, das Füllen von Reihendaten, das Anpassen der Reihenüberlappung und das Speichern der fertigen Präsentation.

Weitere erweiterte Funktionen und Anpassungsoptionen finden Sie im [Aspose.Slides für Java-Dokumentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-06-03'
description: Erfahren Sie, wie Sie ein gruppiertes Säulendiagramm in Java mit Aspose.Slides
  erstellen. Dieser Leitfaden behandelt die Maven-Abhängigkeit, die Schritte zur Diagrammerstellung
  und die Datenverarbeitung.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Erstellen eines gruppierten Säulendiagramms in Java mit Aspose.Slides
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen eines gruppierten Säulendiagramms in Java mit Aspose.Slides

## Wie man ein Diagramm in Java erstellt: Einführung
Das Erstellen dynamischer Präsentationen beinhaltet häufig die Visualisierung von Daten mittels Diagrammen. Mit **Aspose.Slides for Java** können Sie mühelos **groupierte Säulendiagramm**-Objekte erstellen, die Klarheit erhöhen und einen stärkeren Eindruck bei Ihrem Publikum hinterlassen. Dieses Tutorial führt Sie durch die Einrichtung der Bibliothek, das Hinzufügen eines gruppierten Säulendiagramms, die Verwaltung von Serien und das bedingte Invertieren negativer Datenpunkte.

**Was Sie lernen werden**
- Wie man Aspose.Slides für Java einrichtet.
- Schritte zum **Erstellen eines gruppierten Säulendiagramms** in Ihrer Präsentation.
- Techniken zur Verwaltung von Diagrammserien und Datenpunkten.
- Methoden zum bedingten Invertieren negativer Datenpunkte für eine bessere Visualisierung.
- Wie man die Präsentation sicher speichert.

## Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Slides for Java.  
- **Welcher Diagrammtyp wird demonstriert?** Gruppiertes Säulendiagramm.  
- **Kann ich negative Werte invertieren?** Ja, mit `invertIfNegative`.  
- **Welche Java-Version ist erforderlich?** JDK 16 oder neuer.  
- **Wird für die Produktion eine Lizenz benötigt?** Ja, eine gültige Aspose‑Lizenz.

## Was ist ein gruppiertes Säulendiagramm?
Ein gruppiertes Säulendiagramm ist eine visuelle Darstellung, die mehrere Datenserien nebeneinander für jede Kategorie platziert und so einen schnellen Vergleich zwischen Gruppen ermöglicht. Es ist ideal für Finanzberichte, Vertriebsdashboards und jede Situation, in der Sie mehrere Kennzahlen gleichzeitig gegenüberstellen müssen.

## Warum Aspose.Slides für die Diagrammerstellung verwenden?
Aspose.Slides ermöglicht es Ihnen, Diagramme programmgesteuert zu erzeugen und vollständig anzupassen, wodurch die manuelle PowerPoint‑Bearbeitung entfällt. Es unterstützt **mehr als 70 Eingabe‑ und Ausgabeformate** und kann Präsentationen mit **bis zu 10.000 Folien** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was eine hohe Leistung für groß angelegte Berichte gewährleistet.

## Voraussetzungen
1. **Erforderliche Bibliotheken**  
   - Aspose.Slides for Java (version 25.4 or later).  

2. **Umgebung**  
   - JDK 16 or newer.  
   - Maven or Gradle for dependency management.  

3. **Kenntnisse**  
   - Basic Java programming.  
   - Familiarity with build tools (Maven/Gradle).  

## Einrichtung von Aspose.Slides für Java
### Maven-Installation
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle-Installation
Fügen Sie die folgende Zeile zu Ihrer `build.gradle`‑Datei hinzu:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung
- **Kostenlose Testversion:** Funktionen ohne Lizenz erkunden.  
- **Temporäre Lizenz:** Während der Evaluierung verwenden.  
- **Vollständige Lizenz:** Für den Produktionseinsatz erwerben.

### Grundlegende Initialisierung
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Wie füge ich ein gruppiertes Säulendiagramm zu einer Folie hinzu?
`Presentation` ist die Kernklasse, die eine PowerPoint‑Datei repräsentiert. Laden Sie eine neue `Presentation`, fügen Sie eine Folie hinzu und rufen Sie `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)` auf. Dieser einzelne Aufruf erstellt ein voll funktionsfähiges gruppiertes Säulendiagramm, das an den angegebenen Koordinaten positioniert ist. Anschließend können Sie das Diagrammobjekt verwenden, um Serien, Datenpunkte und visuelle Stile zu ändern.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Eine Präsentation erstellen und ein gruppiertes Säulendiagramm hinzufügen
`Presentation`‑Klasse repräsentiert ein PowerPoint‑Dokument und ermöglicht das Erstellen von Folien.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Schritt 2: Diagrammserien verwalten
Jetzt werden wir alle Standardserien löschen, eine neue hinzufügen und sie mit positiven und negativen Werten füllen.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Schritt 3: Negative Datenpunkte bedingt invertieren
`invertIfNegative`‑Methode ermöglicht das Invertieren negativer Werte in einer Diagrammserie.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Häufige Fallstricke & Tipps
- **Haben Sie vergessen, das `Presentation`‑Objekt zu entsorgen?** Rufen Sie immer `dispose()` in einem `finally`‑Block auf, um native Ressourcen freizugeben.  
- **Werden negative Werte nicht invertiert angezeigt?** Stellen Sie sicher, dass Sie `invertIfNegative(true)` **nach** dem Hinzufügen des Datenpunkts aufrufen.  
- **Probleme mit der Diagrammgröße:** Die Koordinaten (X, Y) und Abmessungen (Breite, Höhe) sind in Punkten angegeben; passen Sie sie an das Layout Ihrer Folie an.  

## Häufig gestellte Fragen

**Q:** Kann ich mit dem gleichen Ansatz andere Diagrammtypen erstellen?  
A: Ja, ersetzen Sie einfach `ChartType.ClusteredColumn` durch einen anderen `ChartType`‑Enum‑Wert (z. B. `Line`, `Pie`).  

**Q:** Benötige ich eine Lizenz für Entwicklungs‑Builds?  
A: Für den vollen Funktionsumfang ist eine temporäre oder Evaluationslizenz erforderlich; andernfalls funktioniert die Bibliothek im Testmodus mit Wasserzeichen‑Einschränkungen.  

**Q:** Wie exportiere ich die Präsentation nach dem Hinzufügen von Diagrammen nach PDF?  
`SaveFormat.Pdf` gibt PDF als Ausgabeformat zum Speichern einer Präsentation an. Verwenden Sie `pres.save("output.pdf", SaveFormat.Pdf);` nachdem Sie die Diagrammbearbeitung abgeschlossen haben.  

**Q:** Ist es möglich, einzelne Säulen (Farbe, Rahmen) zu formatieren?  
`IChartDataPoint` repräsentiert einen einzelnen Datenpunkt in einem Diagramm und ermöglicht die Formatierung. Jeder `IChartDataPoint` bietet Optionen wie `getFillFormat().setFillType(FillType.Solid)` und `getLineFormat()`.  

**Q:** Was ist, wenn ich die Diagrammdaten nach dem Speichern der Präsentation aktualisieren muss?  
A: Laden Sie die Präsentation erneut mit `new Presentation("file.pptx")`, ändern Sie die Diagrammdaten und speichern Sie erneut.  

---

**Letzte Aktualisierung:** 2026-06-03  
**Getestet mit:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man ein gestapeltes Säulendiagramm in Java mit Aspose.Slides erstellt – Ein umfassender Leitfaden](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Wie man ein Diagramm in Java mit Aspose.Slides erstellt – Diagrammerstellung und Validierung meistern](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Diagramme in Java mit Aspose.Slides erstellen & formatieren: Ein umfassender Leitfaden](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
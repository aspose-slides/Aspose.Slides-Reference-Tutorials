---
date: '2026-02-12'
description: Erfahren Sie, wie Sie Diagramme mit Aspose.Slides für Java erstellen
  und verwalten. Dieses Tutorial zeigt, wie man ein gruppiertes Säulendiagramm erstellt,
  Datenreihen verarbeitet und die Visualisierung anpasst.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Wie man ein Diagramm in Java mit Aspose.Slides erstellt: Ein umfassender Leitfaden'
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Diagramm in Java mit Aspose.Slides erstellt

## Wie man ein Diagramm in Java erstellt: Einführung
Das Erstellen dynamischer Präsentationen beinhaltet häufig die Visualisierung von Daten mittels Diagrammen. Mit **Aspose.Slides for Java** können Sie mühelos **Diagrammobjekte erstellen**, die Klarheit erhöhen und einen stärkeren Eindruck bei Ihrem Publikum hinterlassen. Dieses Tutorial führt Sie durch die Einrichtung der Bibliothek, das Hinzufügen eines **create clustered column chart**, die Verwaltung von Serien und das bedingte Invertieren negativer Datenpunkte.

**Was Sie lernen werden**
- Wie man Aspose.Slides for Java einrichtet.
- Schritte zum **create clustered column chart** in Ihrer Präsentation.
- Techniken zur Verwaltung von Diagrammserien und Datenpunkten.
- Methoden zum bedingten Invertieren negativer Datenpunkte für eine bessere Visualisierung.
- Wie man die Präsentation sicher speichert.

### Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Slides for Java.
- **Welcher Diagrammtyp wird demonstriert?** Clustered column chart.
- **Kann ich negative Werte invertieren?** Ja, mit `invertIfNegative`.
- **Welche Java-Version wird benötigt?** JDK 16 oder höher.
- **Wird für die Produktion eine Lizenz benötigt?** Ja, eine gültige Aspose-Lizenz.

## Was ist ein Clustered Column Chart?
Ein Clustered Column Chart zeigt mehrere Datenserien nebeneinander für jede Kategorie, was den Vergleich von Werten über Gruppen hinweg erleichtert. Er ist ideal für Finanzberichte, Vertriebs‑Dashboards und jede Situation, in der Sie mehrere Kennzahlen gegenüberstellen müssen.

## Warum Aspose.Slides für die Diagrammerstellung verwenden?
- **Vollständige Kontrolle** über das Aussehen des Diagramms, ohne auf die PowerPoint‑Benutzeroberfläche angewiesen zu sein.
- **Programmgesteuerte Erstellung** ermöglicht automatisierte Reporting‑Pipelines.
- **Cross‑platform** Unterstützung stellt sicher, dass Ihr Code auf jedem Java‑kompatiblen System läuft.
- **Umfangreiche API** für feinkörnige Anpassungen (Farben, Datenbeschriftungen, Inversion usw.).

## Prerequisites
1. **Erforderliche Bibliotheken**
   - Aspose.Slides for Java (Version 25.4 oder höher).

2. **Umgebung**
   - JDK 16 oder neuer.
   - Maven oder Gradle für das Abhängigkeitsmanagement.

3. **Kenntnisse**
   - Grundlegende Java‑Programmierung.
   - Vertrautheit mit Build‑Tools (Maven/Gradle).

## Setting Up Aspose.Slides for Java
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
- **Free Trial:** Funktionen ohne Lizenz erkunden.
- **Temporary License:** Während der Evaluierung verwenden.
- **Full License:** Für den Produktionseinsatz erwerben.

### Grundlegende Initialisierung
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Eine Präsentation erstellen und ein Clustered Column Chart hinzufügen
In diesem Schritt erstellen wir **how to create chart** Objekte und platzieren ein **create clustered column chart** auf der ersten Folie.

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
Jetzt werden wir alle Standardserien entfernen, eine neue hinzufügen und sie mit positiven und negativen Werten füllen.

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
Standardmäßig invertiert Aspose.Slides negative Werte nicht. Wir aktivieren die Inversion nur für die Punkte, die sie benötigen.

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

### Häufige Fallstricke & Tipps
- **Forgot to dispose the `Presentation` object?** Rufen Sie immer `dispose()` in einem `finally`‑Block auf, um native Ressourcen freizugeben.
- **Negative values not showing as inverted?** Stellen Sie sicher, dass Sie `invertIfNegative(true)` **nach** dem Hinzufügen des Datenpunkts aufrufen.
- **Chart size issues:** Die Koordinaten (X, Y) und Abmessungen (Breite, Höhe) sind in Punkten angegeben; passen Sie sie an das Folienlayout an.

## Häufig gestellte Fragen

**Q: Kann ich mit dem gleichen Ansatz andere Diagrammtypen erstellen?**  
**A:** Ja, ersetzen Sie einfach `ChartType.ClusteredColumn` durch einen anderen `ChartType`‑Enum‑Wert (z. B. `Line`, `Pie`).

**Q: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
**A:** Eine temporäre oder Evaluationslizenz ist für den vollen Funktionsumfang erforderlich; andernfalls funktioniert die Bibliothek im Testmodus mit Wasserzeichen‑Beschränkungen.

**Q: Wie exportiere ich die Präsentation nach dem Hinzufügen von Diagrammen nach PDF?**  
**A:** Verwenden Sie `pres.save("output.pdf", SaveFormat.Pdf);`, nachdem Sie die Diagrammbearbeitung abgeschlossen haben.

**Q: Ist es möglich, einzelne Spalten (Farbe, Rand) zu formatieren?**  
**A:** Ja, jeder `IChartDataPoint` bietet Formatierungsoptionen wie `getFillFormat().setFillType(FillType.Solid)` und `getLineFormat()`.

**Q: Was ist, wenn ich die Diagrammdaten nach dem Speichern der Präsentation aktualisieren muss?**  
**A:** Laden Sie die Präsentation erneut mit `new Presentation("file.pptx")`, ändern Sie die Diagrammdaten und speichern Sie erneut.

---

**Zuletzt aktualisiert:** 2026-02-12  
**Getestet mit:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
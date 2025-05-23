---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagramme erstellen und verwalten. Dieser Leitfaden behandelt gruppierte Säulendiagramme, die Verwaltung von Datenreihen und mehr."
"title": "Diagrammerstellung in Java meistern mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagrammerstellung in Java mit Aspose.Slides meistern

## So erstellen und verwalten Sie Diagramme mit Aspose.Slides für Java

### Einführung
Bei der Erstellung dynamischer Präsentationen werden Daten oft durch Diagramme visualisiert. Mit **Aspose.Slides für Java**Erstellen und verwalten Sie mühelos verschiedene Diagrammtypen und verbessern Sie so Übersichtlichkeit und Wirkung. Dieses Tutorial führt Sie durch die Erstellung einer leeren Präsentation, das Hinzufügen gruppierter Säulendiagramme, die Verwaltung von Reihen und die Anpassung der Datenpunktinversion – alles mit Aspose.Slides für Java.

**Was Sie lernen werden:**
- So richten Sie Aspose.Slides für Java ein.
- Schritte zum Erstellen eines gruppierten Säulendiagramms in Ihrer Präsentation.
- Techniken zur effektiven Verwaltung von Diagrammreihen und Datenpunkten.
- Methoden zum bedingten Invertieren negativer Datenpunkte zur besseren Visualisierung.
- So speichern Sie die Präsentation sicher.

Lassen Sie uns zunächst einen Blick auf die Voraussetzungen werfen.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:

1. **Erforderliche Bibliotheken:**
   - Aspose.Slides für Java (Version 25.4 oder höher).

2. **Anforderungen für die Umgebungseinrichtung:**
   - Eine kompatible JDK-Version (z. B. JDK 16).
   - Wenn Sie Abhängigkeitsverwaltung bevorzugen, müssen Maven oder Gradle installiert sein.

3. **Erforderliche Kenntnisse:**
   - Grundlegende Kenntnisse der Java-Programmierung.
   - Vertrautheit mit der Handhabung von Abhängigkeiten in Ihrer Entwicklungsumgebung.

## Einrichten von Aspose.Slides für Java
Um Aspose.Slides zu verwenden, führen Sie die folgenden Schritte aus:

**Maven-Installation:**
Fügen Sie die folgende Abhängigkeit zu Ihrem `pom.xml` Datei:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle-Installation:**
Fügen Sie die folgende Zeile zu Ihrem `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktdownload:**
Alternativ können Sie die neueste Version von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Lizenzerwerb
- **Kostenlose Testversion:** Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen zu erkunden.
- **Temporäre Lizenz:** Erwerben Sie eine temporäre Lizenz für den vollständigen Zugriff während Ihres Evaluierungszeitraums.
- **Kaufen:** Erwägen Sie einen Kauf, wenn Sie der Meinung sind, dass es Ihren langfristigen Anforderungen entspricht.

### Grundlegende Initialisierung
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Ihr Code hier...
pres.dispose(); // Entsorgen Sie das Präsentationsobjekt immer, wenn Sie fertig sind.
```

## Implementierungshandbuch
Lassen Sie uns nun jede Funktion in überschaubare Schritte unterteilen.

### Erstellen einer Präsentation mit einem gruppierten Säulendiagramm
#### Überblick
In diesem Abschnitt erfahren Sie, wie Sie eine leere Präsentation erstellen und an bestimmten Koordinaten auf Ihrer Folie ein gruppiertes Säulendiagramm hinzufügen.

**Schritte:**
1. **Initialisieren Sie das Präsentationsobjekt:**
   - Erstellen Sie eine neue Instanz von `Presentation`.
2. **Fügen Sie ein gruppiertes Säulendiagramm hinzu:**
   - Verwenden `getSlides().get_Item(0).getShapes().addChart()` , um das Diagramm hinzuzufügen.
   - Geben Sie Position, Maße und Typ an.

**Codebeispiel:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Fügen Sie bei (50, 50) ein gruppiertes Säulendiagramm mit einer Breite von 600 und einer Höhe von 400 hinzu.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Verwalten von Diagrammserien
#### Überblick
Erfahren Sie, wie Sie vorhandene Reihen löschen und neue mit benutzerdefinierten Datenpunkten hinzufügen.

**Schritte:**
1. **Vorhandene Serien löschen:**
   - Verwenden `series.clear()` um alle bereits vorhandenen Daten zu entfernen.
2. **Neue Serie hinzufügen:**
   - Fügen Sie eine neue Serie hinzu mit `series.add()`.
3. **Datenpunkte einfügen:**
   - Nutzen `getDataPoints().addDataPointForBarSeries()` zum Addieren von Werten, auch negativen.

**Codebeispiel:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Vorhandene Serie löschen und eine neue hinzufügen.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Fügen Sie Datenpunkte mit unterschiedlichen Werten (positiv und negativ) hinzu.
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

### Umkehren von Datenpunkten einer Reihe basierend auf Bedingungen
#### Überblick
Passen Sie die Visualisierung negativer Datenpunkte an, indem Sie sie bedingt invertieren.

**Schritte:**
1. **Standard-Inversionsverhalten festlegen:**
   - Verwenden `setInvertIfNegative(false)` um das allgemeine Inversionsverhalten zu bestimmen.
2. **Bestimmte Datenpunkte bedingt invertieren:**
   - Anwenden `setInvertIfNegative(true)` an einem bestimmten Datenpunkt, wenn dieser negativ ist.

**Codebeispiel:**
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
    
    // Fügen Sie Datenpunkte mit unterschiedlichen Werten (positiv und negativ) hinzu.
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
    
    // Standardmäßiges Inversionsverhalten festlegen
    series.get_Item(0).invertIfNegative(false);
    
    // Bedingtes Invertieren eines bestimmten Datenpunkts
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie Aspose.Slides für Java einrichten und ein gruppiertes Säulendiagramm erstellen. Außerdem haben Sie die Verwaltung von Datenreihen und die Anpassung der Visualisierung negativer Datenpunkte erlernt. Mit diesen Kenntnissen können Sie nun sicher dynamische Diagramme in Ihren Java-Anwendungen erstellen.

**Nächste Schritte:**
- Experimentieren Sie mit verschiedenen Diagrammtypen, die in Aspose.Slides für Java verfügbar sind.
- Entdecken Sie zusätzliche Anpassungsoptionen zur Verbesserung Ihrer Präsentationen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
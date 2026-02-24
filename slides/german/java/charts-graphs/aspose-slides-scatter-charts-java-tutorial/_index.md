---
date: '2026-02-24'
description: Erfahren Sie, wie Sie Scatter‑Diagramme mit Aspose.Slides für Java anpassen.
  Dieser Leitfaden führt Sie durch das Erstellen, Gestalten und Speichern dynamischer
  Scatter‑Diagramme in Ihren Präsentationen.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Streudiagramm Aspose in Java anpassen
url: /de/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

< blocks/products/products-backtop-button >}}

All preserved.

Now ensure we didn't translate any code block placeholders. They remain.

Check for any URLs: only one link, kept.

Check for any markdown links: none else.

Check for images: none.

Check for shortcodes: all preserved.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Scatter-Diagramm Aspose in Java anpassen

In diesem Tutorial lernen Sie, wie Sie **Scatter-Diagramm Aspose anpassen** mit der leistungsstarken Aspose.Slides for Java Bibliothek. Wir gehen Schritt für Schritt durch die Einrichtung Ihres Projekts, das Erstellen eines Scatter-Diagramms, das Anpassen von Serienarten und Markern und schließlich das Speichern der Präsentation. Am Ende können Sie professionell aussehende Scatter-Diagramme programmgesteuert erzeugen und jedes visuelle Detail an Ihre Marke oder Berichtsanforderungen anpassen.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Slides for Java (v25.4+).  
- **Welche Java-Version wird unterstützt?** JDK 8 oder höher.  
- **Kann ich die Markerformen ändern?** Ja – verwenden Sie `MarkerStyleType`, um Sterne, Kreise usw. auszuwählen.  
- **Wie speichere ich die Datei?** Rufen Sie `pres.save("output.pptx", SaveFormat.Pptx)` auf.  
- **Ist eine Lizenz erforderlich?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.

## Was bedeutet „Scatter-Diagramm Aspose anpassen“?
Das Anpassen eines Scatter-Diagramms mit Aspose bedeutet, dass Sie die Diagrammdaten, das Aussehen und das Verhalten programmgesteuert festlegen – alles von Punktkoordinaten bis zu Markersymbolen – ohne PowerPoint manuell zu öffnen. Dieser Ansatz ist ideal für automatisierte Berichte, datenbasierte Präsentationen oder jede Situation, in der wiederholbare, hochwertige Visualisierungen benötigt werden.

## Warum Scatter-Diagramme mit Aspose.Slides anpassen?
- **Vollständige Kontrolle** – Serienarten, Marker‑Stile, Farben und mehr über Java-Code ändern.  
- **Automatisierung** – Dutzende Diagramme on-the-fly für Dashboards oder Batch-Berichte erzeugen.  
- **Plattformübergreifend** – funktioniert auf jedem OS, das Java unterstützt, ohne Office-Installation.  
- **Performance** – leichte API, die große Datensätze effizient verarbeitet.

## Voraussetzungen

Um dem Tutorial zu folgen, stellen Sie sicher, dass Sie folgendes haben:

- **Aspose.Slides for Java** (v25.4 oder neuer).  
- **Java Development Kit (JDK)** 8 + installiert.  
- Maven oder Gradle für das Abhängigkeitsmanagement (oder Sie können das JAR manuell herunterladen).  
- Grundkenntnisse in Java und Vertrautheit mit Ihrem bevorzugten Build-Tool.

## Einrichtung von Aspose.Slides für Java

Integrieren Sie die Bibliothek in Ihr Projekt mit einer der folgenden Methoden.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Oder holen Sie sich das neueste Release von [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Lizenzbeschaffung
- **Kostenlose Testversion** – 30‑tägige Evaluierung.  
- **Temporäre Lizenz** – erweiterter Testzeitraum.  
- **Vollständige Lizenz** – Produktionseinsatz mit Premium‑Support.

## Schritt‑für‑Schritt‑Anleitung zum Anpassen von Scatter-Diagrammen mit Aspose

### 1️⃣ Einen Ordner für Ihre Präsentationsdateien vorbereiten
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Warum das wichtig ist:* Das Vorhandensein des Ausgabeverzeichnisses verhindert `FileNotFoundException`, wenn Sie später die PPTX speichern.

### 2️⃣ Eine neue Präsentation erstellen und die erste Folie holen
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Eine neue `Presentation` bietet Ihnen eine leere Leinwand; die erste Folie ist der Ort, an dem wir das Diagramm platzieren.

### 3️⃣ Ein Scatter-Diagramm mit glatten Linien hinzufügen
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` erzeugt ein Scatter-Diagramm mit glatten Linien, ideal zur Trendvisualisierung.

### 4️⃣ Alle Standardserien entfernen und eigene hinzufügen
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Das Entfernen der Standardserie gibt Ihnen die volle Kontrolle über die angezeigten Daten.

### 5️⃣ Die erste Serie mit Datenpunkten füllen
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` nimmt eine X‑Wert‑Zelle und eine Y‑Wert‑Zelle und baut das Scatter‑Diagramm Punkt für Punkt auf.

### 6️⃣ Serienart und Marker‑Aussehen anpassen
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Hier **passen wir das Scatter-Diagramm mit Aspose** an, indem wir zu geraden Linien wechseln, Marker vergrößern und unterschiedliche Symbole (Stern vs. Kreis) für bessere Sichtbarkeit auswählen.

### 7️⃣ Die Präsentation speichern
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Das Speichern als `Pptx` bewahrt alle Diagrammanpassungen und macht die Datei bereit zum Teilen oder Weiterbearbeiten.

## Häufige Anwendungsfälle für angepasste Scatter-Diagramme
- **Finanz‑Dashboards** – Aktienkurs gegen Volumen darstellen.  
- **Wissenschaftliche Forschung** – experimentelle Messungen mit Fehler‑Markern anzeigen.  
- **Projektmanagement** – geplanten vs. tatsächlichen Aufwand über Aufgaben vergleichen.  

## Performance‑Tipps
- Entsorgen Sie das `Presentation`‑Objekt (`pres.dispose()`) nach dem Speichern, um native Ressourcen freizugeben.  
- Bei großen Datensätzen zuerst das Arbeitsbuch füllen und dann die Serien binden, um wiederholte UI‑Aktualisierungen zu vermeiden.  
- Verwenden Sie eine einzelne `IChartDataWorkbook`‑Instanz, wenn Sie viele Serien hinzufügen.

## Häufig gestellte Fragen

### Wie ändere ich die Farbe der Marker?
Verwenden Sie `series.getMarker().getFillFormat().setFillColor(Color)`, wobei `Color` eine Instanz von `java.awt.Color` ist (z. B. `Color.RED`).

### Kann ich mehr als zwei Serien zu einem Scatter-Diagramm hinzufügen?
Natürlich. Wiederholen Sie den Aufruf `chart.getChartData().getSeries().add(...)` für jede zusätzliche Serie und füllen Sie deren Datenpunkte entsprechend.

### Ist es möglich, eine benutzerdefinierte Legende für jede Serie festzulegen?
Ja. Nach dem Erstellen einer Serie rufen Sie `series.getLegend().setText("Your Legend Text")` auf, um den Standardnamen zu überschreiben.

### Wie kann ich das Diagramm als Bild statt als PPTX exportieren?
Rufen Sie `chart.getImage().save("chart.png", ImageFormat.Png)` nach der Konfiguration des Diagramms auf. Dadurch erhalten Sie eine eigenständige PNG‑Datei.

### Was, wenn ich die Scatter‑Punkte animieren muss?
Aspose.Slides unterstützt Animationseffekte. Verwenden Sie `chart.getTimeline().getMainSequence().addEffect(...)`, um Eingangs‑ oder Betonungsanimationen zum Diagramm oder einzelnen Serien hinzuzufügen.

---

**Zuletzt aktualisiert:** 2026-02-24  
**Getestet mit:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
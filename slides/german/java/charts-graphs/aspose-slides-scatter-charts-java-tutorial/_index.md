---
date: '2026-07-27'
description: Erfahren Sie, wie Sie Diagramme mit Aspose.Slides für Java anpassen.
  Lernen Sie, PowerPoint-Diagramme zu erstellen, Streudiagramm-Serien zu formatieren
  und Präsentationen effizient zu speichern.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Wie man Diagramme mit Aspose.Slides für Java anpasst. Dieser Leitfaden
  zeigt, wie man ein PowerPoint-Diagramm erstellt, Streudiagramm-Punkte formatiert
  und Präsentationen exportiert.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Wie man Diagramme anpasst: Streudiagramm Aspose in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Wie man Diagramme anpasst: Streudiagramm Aspose in Java'
url: /de/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Anpassen von Scatter-Diagrammen mit Aspose in Java

In diesem Tutorial erfahren Sie **wie man Diagramme anpasst** — insbesondere ein Scatter-Diagramm — mit der leistungsstarken Aspose.Slides for Java-Bibliothek. Wir führen Sie durch die Projektkonfiguration, das Erstellen eines Scatter-Diagramms, das Anpassen von Serienarten und Markern und schließlich das Speichern der Präsentation. Am Ende können Sie professionell aussehende Scatter-Diagramme programmgesteuert erzeugen und jedes visuelle Detail an Ihre Marke oder Berichtsanforderungen anpassen.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Slides for Java (v25.4+).  
- **Welche Java-Version wird unterstützt?** JDK 8 oder höher.  
- **Kann ich Markerformen ändern?** Ja – verwenden Sie `MarkerStyleType`, um Sterne, Kreise usw. auszuwählen.  
- **Wie speichere ich die Datei?** Rufen Sie `pres.save("output.pptx", SaveFormat.Pptx)` auf.  
- **Ist eine Lizenz erforderlich?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.

## Wie man Diagramme in Java mit Aspose.Slides anpasst?
`Presentation` ist die Aspose.Slides‑Klasse, die eine gesamte PowerPoint‑Datei im Speicher repräsentiert. Laden Sie ein neues `Presentation`, fügen Sie ein Scatter‑Diagramm auf der ersten Folie hinzu, konfigurieren Sie Serien‑ und Marker‑Stile und rufen Sie anschließend `save` auf. Dieser einzelne Workflow erstellt ein vollständig gestaltetes Diagramm in nur wenigen Zeilen Java‑Code, bereit zur Einbindung in jede PowerPoint‑Präsentation.

## Was bedeutet „customize scatter chart aspose“?
Das Anpassen eines Scatter‑Diagramms mit Aspose bedeutet, das Diagramm‑Daten, das Aussehen und das Verhalten programmgesteuert zu definieren – alles von Punktkoordinaten bis zu Markersymbolen – ohne PowerPoint manuell zu öffnen. Dieser Ansatz ist ideal für automatisierte Berichte, datengetriebene Präsentationen oder jede Situation, in der wiederholbare, hochwertige Visualisierungen benötigt werden.

## Warum Scatter‑Diagramme mit Aspose.Slides anpassen?
Aspose.Slides bietet Entwicklern die vollständige programmgesteuerte Kontrolle über das Aussehen von Diagrammen, ermöglicht die automatisierte Erstellung hochwertiger Visualisierungen, die nahtlose Integration in Reporting‑Pipelines und die Möglichkeit, jedes visuelle Element anzupassen, ohne PowerPoint manuell zu öffnen. Das spart Zeit und sorgt für Konsistenz über alle Präsentationen hinweg.

- **Vollständige Kontrolle** – ändern Sie Serienarten, Marker‑Stile, Farben und mehr über Java‑Code.  
- **Automatisierung** – erzeugen Sie im laufenden Betrieb Dutzende von Diagrammen für Dashboards oder Batch‑Berichte.  
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt, ohne Office‑Installation.  
- **Performance** – leichte API, die **150+ Diagrammtypen** verarbeitet und mehrseitige Präsentationen handhabt, ohne die gesamte Datei in den Speicher zu laden.

## Voraussetzungen

Um dem Tutorial zu folgen, stellen Sie sicher, dass Sie folgendes haben:

- **Aspose.Slides for Java** (v25.4 oder neuer).  
- **Java Development Kit (JDK)** 8 + installiert.  
- Maven oder Gradle für das Abhängigkeitsmanagement (oder Sie können das JAR manuell herunterladen).  
- Grundlegende Java‑Kenntnisse und Vertrautheit mit Ihrem bevorzugten Build‑Tool.

## Einrichtung von Aspose.Slides für Java

Integrieren Sie die Bibliothek in Ihr Projekt mit einer der untenstehenden Methoden.

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

## Schritt‑für‑Schritt‑Anleitung zum Anpassen von Scatter‑Diagrammen mit Aspose

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
`Presentation` repräsentiert ein PowerPoint‑Dokument und bietet Zugriff auf Folien und Formen. Die `Presentation`‑Klasse stellt eine gesamte PowerPoint‑Datei im Speicher dar.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Ein Scatter‑Diagramm mit glatten Linien hinzufügen
`ChartType.ScatterWithSmoothLines` erzeugt ein Scatter‑Diagramm, bei dem die Punkte durch glatte Linien verbunden werden.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Standard‑Serien löschen und eigene hinzufügen
`IChartSeries` repräsentiert eine Datenserie innerhalb eines Diagramms.  
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

### 5️⃣ Die erste Serie mit Datenpunkten füllen
`addDataPointForScatterSeries` fügt einem Scatter‑Series einen einzelnen X‑Y‑Punkt hinzu.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Serientyp und Marker‑Aussehen anpassen
`Marker` steuert das visuelle Symbol, das für jeden Datenpunkt einer Diagrammserie verwendet wird.  
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

### 7️⃣ Die Präsentation speichern
`save` schreibt die Präsentation in eine Datei im angegebenen Format.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Häufige Anwendungsfälle für angepasste Scatter‑Diagramme
- **Finanz‑Dashboards** – Aktienkurs vs. Volumen darstellen.  
- **Wissenschaftliche Forschung** – experimentelle Messungen mit Fehler‑Markern anzeigen.  
- **Projektmanagement** – geplanten vs. tatsächlichen Aufwand über Aufgaben vergleichen.  

## Performance‑Tipps
- Rufen Sie `pres.dispose()` nach dem Speichern auf, um nativen Speicher freizugeben.  
- Bei großen Datensätzen zuerst das Arbeitsbuch füllen und dann die Serie binden, um wiederholte UI‑Aktualisierungen zu vermeiden.  
- Verwenden Sie eine einzelne `IChartDataWorkbook`‑Instanz, wenn Sie viele Serien hinzufügen, um den Speicherverbrauch gering zu halten.

## Häufig gestellte Fragen

**Q: Wie ändere ich die Farbe der Marker?**  
A: Verwenden Sie `series.getMarker().getFillFormat().setFillColor(Color)`, wobei `Color` eine `java.awt.Color`‑Instanz ist, z. B. `Color.RED`.

**Q: Kann ich mehr als zwei Serien zu einem Scatter‑Diagramm hinzufügen?**  
A: Ja. Rufen Sie `chart.getChartData().getSeries().add(...)` für jede zusätzliche Serie auf und füllen Sie deren Punkte entsprechend.

**Q: Ist es möglich, eine benutzerdefinierte Legende für jede Serie festzulegen?**  
A: Absolut. Nach dem Erstellen einer Serie rufen Sie `series.getLegend().setText("Your Legend Text")` auf, um den Standardnamen zu überschreiben.

**Q: Wie kann ich das Diagramm als Bild statt als PPTX exportieren?**  
A: Rufen Sie `chart.getImage().save("chart.png", ImageFormat.Png)` nach der Konfiguration des Diagramms auf. Dies erzeugt eine eigenständige PNG‑Datei.

**Q: Was ist, wenn ich die Scatter‑Punkte animieren muss?**  
A: Aspose.Slides unterstützt Animationseffekte. Verwenden Sie `chart.getTimeline().getMainSequence().addEffect(...)`, um Eingangs‑ oder Betonungsanimationen zum Diagramm oder einzelnen Serien hinzuzufügen.

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [PowerPoint‑Diagramme in Java erstellen und anpassen mit Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Wie man ein Bubble‑Diagramm in PowerPoint mit Aspose.Slides für Java erstellt (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Diagramme mit Trendlinien in Aspose.Slides für Java erstellen und anpassen](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
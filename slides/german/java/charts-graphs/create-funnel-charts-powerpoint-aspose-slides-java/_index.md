---
date: '2026-09-02'
description: Erfahren Sie, wie Sie ein Funnel-Diagramm in PowerPoint mit Aspose.Slides
  for Java erstellen. Diese Schritt‑für‑Schritt‑Anleitung behandelt das setting chart
  data, customizing colors und exporting the presentation.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Erfahren Sie, wie Sie ein Funnel-Diagramm in PowerPoint mit Aspose.Slides
  for Java erstellen. Diese Anleitung führt Sie durch data setup, color customization
  und das Exportieren der final presentation.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Funnel-Diagramm in PowerPoint mit Aspose.Slides for Java erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Funnel-Diagramm in PowerPoint mit Aspose.Slides for Java erstellen
url: /de/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mastering funnel chart creation in PowerPoint with Aspose.Slides for Java

## Einführung
Das Erstellen überzeugender Präsentationen ist eine Kunst, die Datenvisualisierung, Design und Storytelling verbindet. Eine kraftvolle Visualisierung, die sofort einen mehrstufigen Prozess verdeutlicht, ist das Trichterdiagramm. Ob Sie eine Vertriebspipeline, einen Konversionsfluss oder einen Produktionsengpass darstellen möchten – ein gut gestaltetes Trichterdiagramm verwandelt Rohdaten in eine intuitive Erzählung. In diesem Tutorial lernen Sie, wie Sie **ein Trichterdiagramm** in PowerPoint programmgesteuert mit Aspose.Slides for Java erstellen, dessen Daten konfigurieren, die Farbe jedes Segments anpassen und die fertige Präsentation exportieren.

**Was Sie lernen werden**
- Wie Sie Aspose.Slides for Java zu einem Maven‑ oder Gradle‑Projekt hinzufügen  
- Wie Sie ein `Presentation`‑Objekt instanziieren und auf seine Folien zugreifen  
- Wie Sie ein Trichterdiagramm einfügen, Kategorien definieren und Serien‑Daten befüllen  
- Wie Sie jeden Trichterscheibe mit Vollfüllungen oder markenspezifischen Farben stylen  
- Wie Sie die Präsentation als PPTX‑Datei speichern oder eine Folie als Bild exportieren  

## Schnelle Antworten
- **Was ist die primäre Bibliothek für Java‑Datenvisualisierung?** Aspose.Slides for Java.  
- **Wie erstellt man ein Trichterdiagramm in PowerPoint?** Auf der Ziel‑Folien‑Instanz `slide.addChart(ChartType.Funnel, …)` aufrufen.  
- **Welche API legt die Datenquelle des Diagramms fest?** Verwenden Sie `IChartDataWorkbook` zusammen mit `chart.getChartData()`.  
- **Kann man Farben für jedes Trichtersegment anpassen?** Ja – `FillFormat.setFillType(FillType.Solid)` setzen und ein `java.awt.Color` zuweisen.  
- **Benötigt man eine Lizenz für den Produktionseinsatz?** Für kommerzielle Deployments ist eine gekaufte Aspose.Slides‑Lizenz erforderlich.

## Was ist Java‑Datenvisualisierung?
Java‑Datenvisualisierung ist die Praxis, Rohdaten aus Java‑Anwendungen in Diagramme, Grafiken oder interaktive Visualisierungen zu verwandeln. Aspose.Slides for Java ist eine führende Bibliothek, die Entwicklern ermöglicht, über 100 Diagrammtypen – einschließlich Trichterdiagrammen – zu erzeugen, ohne PowerPoint manuell zu starten, und unterstützt Präsentationen mit bis zu 500 Folien bei geringem Speicherverbrauch.

## Warum Trichterdiagramme in PowerPoint verwenden?
Trichterdiagramme zeigen sofort Abbruchquoten über aufeinanderfolgenden Stufen hinweg und eignen sich daher ideal für Vertriebspipelines, Konversionsanalysen oder Prozess‑Effizienz‑Reviews. Aspose.Slides bietet pixelgenaue Kontrolle über Layout, Segmentfarben und Datenbeschriftungen, sodass Sie Marken­konsistenz wahren und den manuellen Aufwand beim Bearbeiten von Diagrammen in der PowerPoint‑Benutzeroberfläche vermeiden können.

## Voraussetzungen (H2)

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
Um Aspose.Slides for Java in Ihrem Projekt zu verwenden, fügen Sie die entsprechenden Maven‑ oder Gradle‑Koordinaten hinzu. Die Bibliothek funktioniert mit Java 8‑21 und benötigt keine externen nativen Abhängigkeiten.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sie können das JAR auch direkt von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Anforderungen an die Umgebungseinrichtung
Stellen Sie sicher, dass JDK 8 oder neuer installiert ist und dass `JAVA_HOME` auf das korrekte JDK‑Verzeichnis zeigt. Aspose.Slides läuft auf jedem Betriebssystem, das das JDK unterstützt, einschließlich Windows, macOS und Linux.

### Wissensvoraussetzungen
Grundlegende Kenntnisse der Java‑Syntax, objektorientierter Programmierung und des Konzepts einer Präsentationsdatei sind hilfreich, aber die Code‑Snippets werden vollständig erklärt und sind für Entwickler jeder Erfahrungsstufe geeignet.

## Einrichtung von Aspose.Slides for Java (H2)

1. **Abhängigkeit hinzufügen** – Verwenden Sie das oben gezeigte Maven‑ oder Gradle‑Snippet.  
2. **Lizenz erhalten** –  
   - **Kostenlose Testversion** – Laden Sie eine temporäre Lizenz von [Aspose's website](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke herunter.  
   - **Vollständige Lizenz** – Kaufen Sie eine Produktionslizenz über die [purchase page](https://purchase.aspose.com/buy).  
3. **Grundlegende Initialisierung** –  

`Presentation` ist die Kernklasse von Aspose.Slides, die eine PowerPoint‑Datei im Speicher repräsentiert. Sie bietet Zugriff auf Folien, Formen und Diagrammobjekte.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Der obige Code erstellt eine neue `Presentation`‑Instanz, bereit für die Folienbearbeitung, und stellt sicher, dass Ressourcen mit `dispose()` freigegeben werden.

## Implementierungs‑Leitfaden

Wir gehen Schritt für Schritt jede erforderliche Funktion durch, um ein vollständiges Trichterdiagramm zu erstellen, und fügen vor jedem Code‑Platzhalter einen kurzen erklärenden Text ein.

### Feature 1: Erstellung einer Präsentation (H2)

#### Überblick
Erstellen Sie zunächst eine Instanz der Klasse `Presentation`. Dieses Objekt ist der Einstiegspunkt für alle nachfolgenden Operationen.

`Presentation` ist das Top‑Level‑Objekt von Aspose.Slides, das die Folien‑Sammlung und globale Dokumenteinstellungen enthält.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Das Snippet öffnet eine leere Präsentation, die Sie später als `.pptx`‑Datei speichern können.

### Feature 2: Hinzufügen eines Trichterdiagramms zu einer Folie (H2)

#### Überblick
Fügen Sie ein Trichterdiagramm auf der ersten Folie ein, definieren Sie dessen Größe und legen Sie den Diagrammtyp fest.

`ChartType.Funnel` weist Aspose.Slides an, eine Trichter‑Visualisierung statt eines Balken‑ oder Liniendiagramms zu rendern.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Der Aufruf `addChart` erzeugt das Diagramm‑Shape, positioniert es bei `(50, 50)` Punkten und gibt ihm eine Breite von `500` und eine Höhe von `400`.

### Feature 3: Diagrammdaten löschen (H2)

#### Überblick
Bevor Sie das Diagramm befüllen, entfernen Sie alle Platzhalter‑Kategorien oder -Serien, die das Template enthalten könnte.

`chart.getChartData().getCategories().clear()` entfernt alle vorhandenen Kategorien, während `chart.getChartData().getSeries().clear()` alle vorab gefüllten Serien löscht.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Damit haben Sie eine saubere Basis, sodass Ihre eigenen Daten exakt wie gewünscht angezeigt werden.

### Feature 4: Einrichten des Diagramm‑Daten‑Workbooks (H2)

#### Überblick
Das Objekt `IChartDataWorkbook` speichert die Rohwerte, die das Diagramm antreiben. Durch die Initialisierung können Sie Daten direkt in Zellen schreiben.

`IChartDataWorkbook` ist ein leichtgewichtiges In‑Memory‑Spreadsheet, das Aspose.Slides verwendet, um Diagramm‑Serien und -Kategorien zu füttern.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Der Code löscht vorhandene Zellen und bereitet das Workbook für neue Einträge vor.

### Feature 5: Kategorien zu einem Diagramm hinzufügen (H2)

#### Überblick
Definieren Sie die Textbeschriftungen, die links am Trichter erscheinen – sie repräsentieren jede Stufe Ihres Prozesses.

`chart.getChartData().getCategories().add()` erzeugt ein neues Kategorie‑Objekt, das mit einer bestimmten Workbook‑Zelle verknüpft ist.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Hier fügen wir drei Stufen hinzu: „Prospects“, „Qualified Leads“ und „Closed Deals“.

### Feature 6: Datenserien zu einem Diagramm hinzufügen (H2)

#### Überblick
Befüllen Sie das Trichterdiagramm mit numerischen Werten und weisen Sie optional jeder Scheibe eine eigene Farbe zu.

`IDataPoint` repräsentiert einen einzelnen Datenpunkt innerhalb einer Diagramm‑Serie.  

`chart.getChartData().getSeries().add()` erzeugt eine Serie, die die numerischen Datenpunkte enthält; jeder `IDataPoint` kann eine eigene Füllfarbe erhalten.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Die Schleife zeigt, wie man für jeden Punkt eine Vollfüllung setzt, entweder mit markenspezifischen `java.awt.Color`‑Konstanten oder zufällig generierten Farben für visuelle Vielfalt.

## Häufige Anwendungsfälle & Tipps (H2)

- **Vertriebs‑Pipeline‑Reporting** – Zeigt, wie viele Leads von Prospect zu Closed‑Won in jeder Stufe übergehen.  
- **Prozess‑Effizienz‑Analyse** – Visualisiert Materialverlust oder Zeitverzögerungen über Fertigungsschritte hinweg.  
- **Marketing‑Trichter‑Review** – Vergleicht Konversionsraten über Kampagnen oder Traffic‑Quellen.  

**Pro‑Tipp:** Statt zufälliger Farben verwenden Sie das Marken‑Farbschema Ihres Unternehmens (z. B. `new Color(0, 112, 192)`), um die Präsentation konsistent zu anderen Marketing‑Assets zu halten.

## Häufig gestellte Fragen (H2)

**F: Wie ändere ich die Ausrichtung des Trichterdiagramms?**  
A: Setzen Sie die Eigenschaft `ChartOrientation` des `IChart`‑Objekts auf `ChartOrientation.Vertical` oder `ChartOrientation.Horizontal`.

**F: Kann ich die Folie nach dem Hinzufügen des Diagramms als Bild exportieren?**  
A: Ja – rufen Sie `pres.getSlides().get_Item(0).getThumbnail(1, 1)` auf und schreiben Sie das resultierende `java.awt.image.BufferedImage` in eine PNG‑ oder JPEG‑Datei.

**F: Was, wenn ich mehr als drei Kategorien benötige?**  
A: Fügen Sie einfach weitere Kategorien mit `chart.getChartData().getCategories().add(...)` hinzu und stellen Sie passende Datenpunkte für jede neue Kategorie bereit.

**F: Gibt es eine Möglichkeit, die Legende auszublenden?**  
A: Verwenden Sie `chart.getChartTitle().setVisible(false)` und `chart.getLegend().setVisible(false)`, um sowohl Titel als auch Legende zu entfernen.

**F: Benötige ich eine Lizenz für Entwicklungs‑Builds?**  
A: Eine temporäre Lizenz reicht für Evaluierungen; für Produktions‑Deployments ist eine vollständige kommerzielle Lizenz erforderlich.

---

**Zuletzt aktualisiert:** 2026-09-02  
**Getestet mit:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
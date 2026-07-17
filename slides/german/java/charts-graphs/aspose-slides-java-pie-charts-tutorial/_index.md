---
date: '2026-07-17'
description: Erfahren Sie, wie Sie Rotate Pie Chart, Customize Pie Chart colors und
  export slide to PDF mit Aspose.Slides für Java – ein umfassender Leitfaden zur Datenvisualisierung.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Rotate Pie Chart und Customize Pie Chart colors mit Aspose.Slides
  für Java. Erfahren Sie, wie Sie export slide to PDF durchführen und mit chart data
  worksheet arbeiten.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Rotate Pie Chart und Customize Colors in Java – Aspose.Slides Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Wie man Rotate Pie Chart und Customize Colors in Java mit Aspose.Slides
url: /de/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellung von Kreisdiagrammen mit Aspose.Slides für Java: Ein vollständiges Tutorial

## Einführung
In diesem Leitfaden lernen Sie, wie Sie **Kreisdiagramm drehen**‑Elemente, die Farbe jeder Scheibe anpassen und die endgültige Folie als PDF exportieren – alles mit Aspose.Slides für Java. Egal, ob Sie ein Vertriebs‑Dashboard, einen Finanzbericht oder eine datenbasierte Präsentation erstellen, das Beherrschen dieser Techniken ermöglicht es Ihnen, klare, auffällige Visualisierungen zu liefern, ohne Microsoft Office zu benötigen. Lassen Sie uns die Werkzeuge bereitstellen und loslegen.

## Schnelle Antworten
- **Welche Klasse startet eine neue Präsentation?** `Presentation` aus `com.aspose.slides`.
- **Welcher API‑Aufruf fügt ein Kreisdiagramm hinzu?** `slide.addChart(ChartType.Pie, …)`.
- **Wie können Sie jeder Scheibe eine eindeutige Farbe zuweisen?** Rufen Sie `series.setColorVaried(true)` auf und setzen Sie für jeden Datenpunkt eine einfarbige Füllung.
- **Welche Methode dreht das Diagramm?** `chart.setRotationAngle(double)` – verwenden Sie Gradwerte von 0 bis 360.
- **Kann die Folie als PDF exportiert werden?** Ja, rufen Sie `presentation.save("output.pdf", SaveFormat.Pdf)` auf.

## Was bedeutet „Kreisdiagramm‑Farben anpassen“?
Das Anpassen der Farben von Kreisdiagrammen bedeutet, jeder Scheibe des Diagramms eine eigene Füllfarbe zuzuweisen, um die Lesbarkeit und die visuelle Wirkung zu verbessern. In Aspose.Slides erreichen Sie dies, indem Sie variierende Farben aktivieren und anschließend für einzelne Datenpunkte einfarbige Füllungen festlegen. Dieser Ansatz sorgt dafür, dass jeder Datenabschnitt in der Präsentation deutlich hervorsticht.

## Warum Aspose.Slides für Java zur Erstellung von Kreisdiagrammen verwenden?
Aspose.Slides unterstützt **mehr als 150 Diagrammtypen** und kann eine 300‑seitige Präsentation in weniger als **5 Sekunden** auf einem typischen Server rendern, und das ganz ohne Installation von Microsoft Office. Die Bibliothek läuft auf Windows, Linux und macOS und bietet Ihnen plattformübergreifende Flexibilität für jedes Java‑basierte Datenvisualisierungsprojekt.

## Voraussetzungen
- **Aspose.Slides für Java** ≥ 25.4
- **JDK** 16 oder neuer
- IDE wie IntelliJ IDEA, Eclipse oder NetBeans
- Grundlegende Java‑Kenntnisse und Vertrautheit mit Maven oder Gradle

## Einrichtung von Aspose.Slides für Java
Fügen Sie die Bibliothek zu Ihrer Build‑Konfiguration hinzu.

**Maven**  
Fügen Sie diesen Ausschnitt zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Fügen Sie das Folgende in Ihre `build.gradle`‑Datei ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download**  
Wenn Sie einen manuellen Ansatz bevorzugen, laden Sie das neueste JAR von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

### Schritte zum Erwerb einer Lizenz
- **Kostenlose Testversion** – erkunden Sie alle Funktionen kostenlos.  
- **Temporäre Lizenz** – erweitern Sie die Testgrenzen für einen kurzen Zeitraum.  
- **Kauf** – erhalten Sie eine permanente Lizenz für den Produktionseinsatz.

**Basic Initialization and Setup**  
Die Klasse `Presentation` repräsentiert eine PowerPoint‑Datei im Speicher und bietet Methoden zur Manipulation von Folien.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementierungs‑Leitfaden
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die alles von der Erstellung einer Folie bis zum Drehen des endgültigen Kreisdiagramms abdeckt.

### Präsentation und Folie initialisieren
Erstellen Sie eine neue `Presentation`‑Instanz und rufen Sie die erste Folie ab, die als Zeichenfläche für das Diagramm dient.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Kreisdiagramm zur Folie hinzufügen
`addChart` fügt der Folie an den angegebenen Koordinaten ein Diagramm‑Shape des angegebenen Typs hinzu.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagrammtitel festlegen
`setTitle` weist dem Diagramm einen Texttitel zu und positioniert ihn zentriert.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Datenbeschriftungen für Serie konfigurieren
`setShowValue(true)` aktiviert numerische Wertebeschriftungen für jeden Datenpunkt der Serie.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Diagrammdaten‑Arbeitsblatt vorbereiten
`ChartDataWorkbook` speichert die zugrunde liegende Datentabelle, die die Diagrammserien und -kategorien versorgt.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategorien zum Diagramm hinzufügen
`addCategory` erstellt ein neues Kategorielabel für die Datenserie des Diagramms.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Serie hinzufügen und Datenpunkte füllen
`addSeries` erstellt eine Datenserie und `addDataPointForBarSeries` fügt für jede Kategorie numerische Werte ein.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Serienfarben und -rahmen anpassen
`setColorVaried(true)` aktiviert Farben pro Scheibe, und `setFillFormat` weist jedem Datenpunkt eine einfarbige Füllung zu.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Benutzerdefinierte Datenbeschriftungen konfigurieren
`setDataLabelFormat` passt das Aussehen, die Position und die Schriftart der Beschriftungen an, um klarere Diagramm‑Anmerkungen zu ermöglichen.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Rotationswinkel festlegen und Präsentation speichern
`setRotationAngle` dreht das gesamte Kreisdiagramm, und `save` schreibt die Präsentation in eine Datei.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Wie dreht man ein Kreisdiagramm?
Laden Sie das Diagramm‑Objekt, rufen Sie `chart.setRotationAngle(45.0)` (oder einen beliebigen Gradwert) auf und speichern Sie anschließend die Präsentation. Das Drehen eines Kreisdiagramms verschiebt den Startwinkel, sodass Sie einen bestimmten Abschnitt hervorheben können, ohne die Daten zu ändern. Dieser einzelne Methodenaufruf funktioniert für jede `Chart`‑Instanz in Aspose.Slides. Sie können die Drehung auch mit variierenden Scheibenfarben kombinieren, um den wichtigsten Datenpunkt hervorzuheben.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|-----|
| **Scheiben haben alle dieselbe Farbe** | `setColorVaried(true)` nicht aufgerufen | Stellen Sie sicher, dass Sie variierende Farben für die Seriengruppe aktivieren. |
| **Datenbeschriftungen werden nicht angezeigt** | `showValue`‑Flag deaktiviert | Rufen Sie `setShowValue(true)` im Beschriftungsformat auf. |
| **Drehung hat keine Wirkung** | Verwendung einer älteren Aspose.Slides‑Version | Aktualisieren Sie auf Version 25.4 oder höher. |
| **Lizenzausnahme zur Laufzeit** | Fehlende oder ungültige Lizenzdatei | Laden Sie Ihre Lizenz mit `License license = new License(); license.setLicense("Aspose.Slides.lic");` bevor Sie die `Presentation` erstellen. |

## Häufig gestellte Fragen

**Q: Wie erhalte ich eine Aspose.Slides‑Lizenz für Java?**  
A: Fordern Sie eine kostenlose Testversion auf der Aspose-Website an und erwerben Sie anschließend eine permanente Lizenz. Laden Sie sie zur Laufzeit, wie in der Tabelle „Häufige Probleme und Lösungen“ gezeigt.

**Q: Kann ich diesen Code mit älteren JDK‑Versionen verwenden?**  
A: Die API erfordert JDK 16 oder höher; ältere Versionen werden nicht unterstützt.

**Q: Ist es möglich, das Diagramm als Bild statt als PPTX zu exportieren?**  
A: Ja – nach dem Rendern rufen Sie `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` auf.

**Q: Was ist, wenn ich mehr als eine Serie in einem Kreisdiagramm benötige?**  
A: Kreisdiagramme sind für eine einzelne Datenserie vorgesehen; für mehrere Serien sollten Sie ein Donut‑Diagramm in Betracht ziehen.

**Q: Läuft Aspose.Slides auf Linux‑Servern?**  
A: Absolut – Aspose.Slides für Java ist plattformunabhängig und funktioniert auf jedem Betriebssystem mit einem kompatiblen JDK.

---

**Letzte Aktualisierung:** 2026-07-17  
**Getestet mit:** Aspose.Slides für Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Kreisdiagramme in Java‑Präsentationen mit Aspose.Slides erstellt: Ein umfassender Leitfaden](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Kreisdiagramme in Java mit Aspose.Slides meistern: Ein umfassender Leitfaden](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Diagrammtexte in Java mit Aspose.Slides drehen: Ein umfassender Leitfaden](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
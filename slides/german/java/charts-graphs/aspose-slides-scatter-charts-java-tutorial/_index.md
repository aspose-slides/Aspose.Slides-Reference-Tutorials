---
date: '2026-01-24'
description: Schritt‑für‑Schritt‑Anleitung zur Erstellung eines Streudiagramms in
  Java mit Aspose.Slides, zum Hinzufügen von Datenpunkten im Streudiagramm und zur
  Arbeit mit mehreren Serien im Streudiagramm.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Scatter-Diagramm in Java mit Aspose.Slides erstellen – Anpassen und speichern
url: /de/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Scatter-Diagramm in Java mit Aspose.Slides erstellen

In diesem Tutorial **Scatter‑Diagramm in Java erstellen** Sie Projekte von Grund auf, fügen Datenpunkte für Scatter hinzu und lernen, wie man mit einem Scatter‑Diagramm mit mehreren Serien arbeitet – alles mit Aspose.Slides für Java. Wir gehen die Verzeichnis‑Einrichtung, die Initialisierung der Präsentation, die Diagrammerstellung, die Datenverwaltung, die Anpassung von Markern und schließlich das Speichern der Präsentation durch.

**Was Sie lernen werden**
- Einrichten eines Verzeichnisses zum Speichern von Präsentationsdateien  
- Initialisieren und Manipulieren von Präsentationen mit Aspose.Slides  
- Erstellen eines Scatter‑Diagramms auf einer Folie  
- Hinzufügen und Verwalten von Datenpunkten für jede Serie  
- Anpassen von Serientypen, Markern und Umgang mit einem Scatter‑Diagramm mit mehreren Serien  
- Speichern der fertigen Präsentation  

Lassen Sie uns mit den Voraussetzungen beginnen.

## Quick Answers
- **Was ist die primäre Bibliothek?** Aspose.Slides für Java  
- **Welche Java‑Version wird benötigt?** JDK 8 oder höher (JDK 16 empfohlen)  
- **Kann ich mehr als zwei Serien hinzufügen?** Ja – Sie können beliebig viele Serien zu einem Scatter‑Diagramm hinzufügen  
- **Wie ändere ich die Farben der Marker?** Verwenden Sie `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Wird für die Produktion eine Lizenz benötigt?** Ja, eine kommerzielle Lizenz entfernt die Evaluationsbeschränkungen  

## Prerequisites

Um diesem Tutorial zu folgen, stellen Sie sicher, dass Sie folgendes haben:
- **Aspose.Slides für Java** – Version 25.4 oder höher.  
- **Java Development Kit (JDK)** – JDK 8 oder neuer.  
- Grundlegende Java‑Kenntnisse und Vertrautheit mit Maven oder Gradle.  

## Setting Up Aspose.Slides for Java

Integrieren Sie Aspose.Slides in Ihr Projekt mit einer der folgenden Methoden.

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

Oder laden Sie das neueste Paket von [Aspose Releases](https://releases.aspose.com/slides/java/) herunter.

#### License Acquisition
- **Kostenlose Testversion** – 30‑tägige Evaluierung.  
- **Temporäre Lizenz** – Erweiterte Tests.  
- **Kommerzielle Lizenz** – Vollständige Nutzung in der Produktion.

Jetzt tauchen wir in den Code ein.

## Implementation Guide

### Step 1: Directory Setup
Stellen Sie zunächst sicher, dass der Ausgabepfad existiert, damit die Präsentation ohne Fehler gespeichert werden kann.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Step 2: Presentation Initialization
Erstellen Sie eine neue Präsentation und holen Sie die erste Folie.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Step 3: Add a Scatter Chart
Fügen Sie ein Scatter‑Diagramm mit glatten Linien auf die Folie ein.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Step 4: Manage Chart Data (Clear & Add Series)
Löschen Sie alle Standardserien und fügen Sie unsere eigenen Serien für das **Scatter‑Diagramm mit mehreren Serien** hinzu.

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

### Step 5: Add Data Points Scatter
Füllen Sie jede Serie mit X‑Y‑Werten mithilfe von **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Step 6: Customize Series Types & Markers
Passen Sie den visuellen Stil an – wechseln Sie zu geraden Linien mit Markern und setzen Sie unterschiedliche Markersymbole.

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

### Step 7: Save the Presentation
Speichern Sie die Datei auf dem Datenträger.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Finanzanalyse** – Plotten Sie Kursbewegungen von Aktien mit einem Scatter‑Diagramm mit mehreren Serien.  
- **Wissenschaftliche Forschung** – Visualisieren Sie experimentelle Messungen mit add data points scatter für eine präzise Datenrepräsentation.  
- **Projektmanagement** – Zeigen Sie Ressourcenzuweisungstrends über mehrere Projekte in einem einzigen Scatter‑Diagramm.  

##orgen Sie das `Presentation`‑Objekt nach dem Speichern, um Speicher freizugeben.  
- Bei großen Datensätzen füllen Sie das Arbeitsbuch stapelweise statt einzeln.  
- Vermeiden Sie übermäßiges Styling innerhalb enger Schleifen; wenden Sie Stile nach dem Einfügen der Daten an.  

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Diagramm erscheint leer** | Stellen Sie sicher, dass Datenpunkte zur richtigen Serie hinzugefügt werden und dass die Arbeitsbuch‑Indizes übereinstimmen. |
| **Marker nicht sichtbar** | Stellen Sie sicher, dass `series.getMarker().setSize()` auf einen Wert größer als 0 gesetzt ist und dass das Markersymbol definiert ist. |
| **OutOfMemoryError bei großen Diagrammen** | Verwmx`)### How do I change the color of the Sie benötigen.

### Is it possible to export the chart as an image?
Ja. Rufen Sie `chart.exportChartImage("chart.png", ImageFormat.Png)` nachose.Slides support interactive tooltips on scatter points?
Obwohl PowerPoint selbst keine Laufzeit‑Tooltips bereitstellt, können Sie Datenbeschriftungen einbetten, indem Sie `series.getDataPoints().getgetSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)`, um eine einfache Auftau‑Animation hinzuzufügen.

**Zuletzt aktualisiert:** 2026-01-24  
**Getestet mit:** Aspose.Slides für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-06-03'
description: Erfahren Sie, wie Sie Diagramme in .NET‑Präsentationen erstellen und
  ein Diagramm zu einer Folie mit Aspose.Slides for Java hinzufügen. Folgen Sie dieser
  Schritt‑für‑Schritt‑Anleitung zur Datenvisualisierung.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Diagramme in .NET mit Aspose.Slides for Java erstellen
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramme in .NET mit Aspose.Slides für Java erstellen

## Einleitung
Das Erstellen überzeugender Präsentationen beinhaltet häufig die Integration visueller Datenrepräsentationen wie Diagrammen, um das Verständnis und die Beteiligung des Publikums zu verbessern. **Wenn Sie Diagramme in .NET erstellen möchten**, bietet Aspose.Slides für Java eine leistungsstarke, sprachunabhängige API, die nahtlos in .NET‑Anwendungen funktioniert. In diesem Tutorial lernen Sie, wie Sie eine Präsentation initialisieren, verschiedene Diagrammtypen hinzufügen, das Diagrammdaten‑Workbook verwalten und Seriendaten formatieren – einschließlich der Behandlung negativer Werte. Am Ende können Sie Diagramme programmgesteuert in Präsentationsdateien erzeugen und ein Diagramm mit nur wenigen Codezeilen zur Folie hinzufügen.

## Schnelle Antworten
- **Was ist das Hauptziel?** Diagramme in .NET‑Präsentationen mit Aspose.Slides für Java erstellen.  
- **Welche Bibliotheksversion ist erforderlich?** Aspose.Slides für Java 25.4 oder höher.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich Maven oder Gradle verwenden?** Ja – beide Build‑Systeme werden unterstützt.  
- **Welche Diagrammtypen stehen zur Verfügung?** Gruppierte Säulen, Linie, Kreis, Balken, Fläche und mehr.

## Wie erstelle ich Diagramme in .NET‑Präsentationen mit Aspose.Slides für Java?
Die Klasse `Presentation` repräsentiert eine PowerPoint‑Datei und bietet Methoden zur Manipulation ihrer Folien. Laden Sie ein neues `Presentation`‑Objekt, rufen Sie `slides.addEmptySlide()` auf, um eine Folie zu erhalten, und verwenden Sie anschließend `slide.getShapes().addChart()`, um den gewünschten Diagrammtyp an den von Ihnen angegebenen Koordinaten einzufügen. Nachdem das Diagramm hinzugefügt wurde, füllen Sie das zugehörige Daten‑Workbook mit Serien und Kategorien, wenden ggf. Formatierungen an (z. B. Farben für negative Werte) und speichern schließlich die Präsentation als .pptx‑Datei. Dieser Ablauf ermöglicht es Ihnen, **Diagramme in .NET** mit einer knappen Menge an API‑Aufrufen zu erstellen.

## Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine plattformübergreifende API, die Entwicklern ermöglicht, PowerPoint‑Dateien zu erstellen, zu ändern und zu rendern, ohne Microsoft Office zu benötigen. Sie unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate** und kann Präsentationen mit Tausenden von Folien verarbeiten, während der Speicherverbrauch unter 200 MB bleibt.

## Warum Aspose.Slides für Java in einem .NET‑Projekt verwenden?
Aspose.Slides für Java läuft auf der Java Virtual Machine und kann über einen nativen Wrapper aus .NET aufgerufen werden, wodurch .NET‑Entwicklern Zugriff auf eine ausgereifte Diagramm‑Engine, eine Hochleistungs‑Verarbeitung großer Datensätze und volle Kompatibilität mit bestehendem Java‑Code ohne Umschreiben der Logik erhalten.

## Voraussetzungen
Bevor Sie mit dem Erstellen von Diagrammen mit Aspose.Slides für Java beginnen, listen wir auf, was Sie benötigen:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java**: Version 25.4 oder höher.

### Anforderungen an die Umgebungseinrichtung
- Eine Entwicklungsumgebung, die .NET‑Anwendungen unterstützt.  
- Grundlegendes Verständnis von Java‑Programmierkonzepten.

### Wissensvoraussetzungen
- Vertrautheit mit dem Erstellen von Präsentationen im Kontext einer .NET‑Anwendung.  
- Verständnis von Java‑Abhängigkeiten und deren Verwaltung (Maven/Gradle).

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides zu verwenden, müssen Sie es als Abhängigkeit in Ihr Projekt einbinden. So geht's:

### Maven
Der Maven‑Abhängigkeits‑Snippet fügt Aspose.Slides für Java zu Ihrem Projekt hinzu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie diese Zeile in Ihre `build.gradle`‑Datei ein, um die Bibliothek von Maven Central zu beziehen.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

#### Schritte zum Lizenzieren
- **Free Trial**: Beginnen Sie mit einer temporären Lizenz, um die Funktionen zu erkunden.  
- **Purchase**: Kaufen Sie eine Lizenz für uneingeschränkte Produktion.

#### Grundlegende Initialisierung und Einrichtung
Die Initialisierung von `Slides` erfordert das Setzen der Lizenz und das Erstellen einer `Presentation`‑Instanz.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Diese Einrichtung stellt sicher, dass das Ressourcen‑Management effektiv gehandhabt wird.

## Implementierungs‑Leitfaden
Wir führen Sie Schritt für Schritt durch die Implementierung der Funktionen.

### Initialisierung der Präsentation
**Übersicht:**  
Das Erstellen einer Präsentationsinstanz legt die Grundlage für alle nachfolgenden Vorgänge. Diese Funktion zeigt, wie Sie von Grund auf mit Aspose.Slides beginnen.

#### Schritt 1: Notwendige Pakete importieren
`Presentation` und verwandte Klassen gehören zum Namensraum `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Schritt 2: Neues Präsentationsobjekt erstellen
Instanziieren Sie ein `Presentation`‑Objekt und umschließen Sie es in einem try‑with‑resources‑Block, um die Entsorgung sicherzustellen.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Dies stellt sicher, dass das Präsentationsobjekt nach der Verwendung ordnungsgemäß entsorgt wird und Speicherlecks verhindert.*

### Diagramm zur Folie hinzufügen
**Übersicht:**  
Das Hinzufügen eines Diagramms zu Ihrer Folie kann die Datenvisualisierung effektiver und ansprechender machen.

#### Schritt 1: Notwendige Pakete importieren
Die Klasse `Chart` stellt ein Diagramm‑Shape dar, das auf einer Folie platziert und angepasst werden kann.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Schritt 2: Präsentation initialisieren und Diagramm hinzufügen
Erstellen Sie eine Folie und rufen Sie dann `addChart` mit `ChartType.ClusteredColumn` sowie der gewünschten Position und Größe auf.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Hier fügen wir ein gruppiertes Säulendiagramm zur ersten Folie an den angegebenen Koordinaten und Abmessungen hinzu.*

### Verwaltung des Diagramm‑Daten‑Workbooks
**Übersicht:**  
Eine effiziente Verwaltung des Daten‑Workbooks Ihres Diagramms ermöglicht es Ihnen, Serien und Kategorien nahtlos zu manipulieren.

#### Schritt 1: Notwendige Pakete importieren
`IChartDataWorkbook` bietet Zugriff auf das zugrunde liegende Excel‑ähnliche Workbook, das von Diagrammen verwendet wird.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Schritt 2: Auf das Workbook zugreifen und es leeren
Rufen Sie das Workbook aus dem Diagramm ab und leeren Sie vorhandene Daten, um neu zu beginnen.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Das Leeren des Workbooks ist entscheidend, um mit einer sauberen Basis neue Serien und Kategorien hinzuzufügen.*

### Serien und Kategorien zum Diagramm hinzufügen
**Übersicht:**  
Diese Funktion zeigt, wie Sie durch Verwaltung von Serien und Kategorien sinnvolle Datenpunkte hinzufügen können.

#### Schritt 1: Serien und Kategorien hinzufügen
Verwenden Sie `chart.getChartData().getSeries().add()` und `chart.getChartData().getCategories().add()`, um die Struktur zu definieren.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Das Hinzufügen von Serien und Kategorien ermöglicht eine besser organisierte Datenpräsentation.*

### Befüllen von Seriendaten und Formatierung
**Übersicht:**  
Befüllen Sie Ihr Diagramm mit Datenpunkten und formatieren Sie das Erscheinungsbild, um die Lesbarkeit zu verbessern, insbesondere bei negativen Werten.

#### Schritt 1: Seriendaten befüllen
Weisen Sie jedem Feld im Workbook numerische Werte zu und wenden Sie für negative Zahlen eine rote Füllung an.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Dieser Abschnitt demonstriert, wie Daten befüllt und Farbformatierungen für eine bessere Visualisierung angewendet werden.*

## Häufige Probleme und Lösungen
- **LicenseNotFoundException** – Stellen Sie sicher, dass der Pfad zur Lizenzdatei korrekt ist und die Datei zur Laufzeit zugänglich ist.  
- **NullPointerException on chart data** – Leeren Sie das Workbook stets, bevor Sie neue Serien hinzufügen, um Restdaten zu vermeiden.  
- **Chart not rendering in .NET** – Vergewissern Sie sich, dass Sie die .NET‑kompatible Version des Aspose.Slides‑JAR verwenden und dass die Java‑Runtime korrekt in Ihrem .NET‑Projekt konfiguriert ist.

## Häufig gestellte Fragen

**Q: Kann ich ein Diagramm in Präsentationsdateien ohne GUI erzeugen?**  
A: Ja, Aspose.Slides für Java ist vollständig headless und funktioniert auf Servern ohne grafische Komponenten.

**Q: Welche .NET‑Versionen werden unterstützt?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 und .NET 6 werden alle unterstützt.

**Q: Wie viele Diagrammtypen kann ich hinzufügen?**  
A: Mehr als 20 Diagrammtypen stehen zur Verfügung, darunter Säulen, Linien, Kreis, Flächen und Radar‑Diagramme.

**Q: Ist es möglich, einzelne Datenpunkte zu formatieren?**  
A: Absolut – Sie können über die `IDataPoint`‑API Füllfarben, Rahmen und Marker für jeden Datenpunkt festlegen.

**Q: Muss ich Java‑Objekte manuell in .NET‑Typen konvertieren?**  
A: Nein, der Aspose.Slides für Java .NET‑Wrapper übernimmt die Typkonvertierung automatisch.

**Letzte Aktualisierung:** 2026-06-03  
**Getestet mit:** Aspose.Slides für Java 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Diagramme in .NET‑Präsentationen mit Aspose.Slides für effektive Datenvisualisierung einbettet](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Wie man den Diagrammdatenquellentyp mit Aspose.Slides für .NET abruft – Diagramme & Grafiken](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Meisterhafte Erstellung und Manipulation von Diagrammserien mit Aspose.Slides .NET für effektive Datenvisualisierung](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
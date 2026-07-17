---
date: '2026-07-17'
description: Erfahren Sie, wie Sie ein Diagramm zu PowerPoint hinzufügen, indem Sie
  ein Pie of Pie Chart mit Aspose.Slides for Java erstellen. Enthält Einrichtung,
  Code, Anpassung und das Speichern als PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Diagramm zu PowerPoint hinzufügen mit Aspose.Slides for Java. Diese
  Anleitung zeigt, wie Sie ein Pie of Pie Chart erstellen, anpassen und innerhalb
  weniger Minuten als PPTX speichern.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Diagramm zu PowerPoint hinzufügen – Erstellen Sie ein Pie of Pie Chart in
  Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Diagramm zu PowerPoint hinzufügen – Erstellen Sie ein Pie of Pie Chart in Java
  mit Aspose.Slides
url: /de/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramm zu PowerPoint hinzufügen – Erstellen Sie ein Pie‑of‑Pie‑Diagramm in Java mit Aspose.Slides

## Diagramme & Grafiken

### Einleitung

In modernen datengetriebenen Präsentationen ist **das Hinzufügen eines Diagramms zu PowerPoint** oft der schnellste Weg, Rohdaten in visuelle Erkenntnisse zu verwandeln. Ein normales Kreisdiagramm funktioniert gut für einige wenige Kategorien, aber wenn einige Segmente sehr klein sind, werden sie unlesbar. Ein *Pie of Pie*-Diagramm löst dieses Problem, indem es diese kleinen Segmente in ein sekundäres Kreisdiagramm auslagert, wodurch das Hauptdiagramm übersichtlich bleibt und die Details zugänglich sind.

In diesem Tutorial lernen Sie, wie Sie **ein Diagramm zu PowerPoint hinzufügen** können, indem Sie ein Pie‑of‑Pie‑Diagramm mit Aspose.Slides für Java erstellen. Wir führen Sie durch die Einrichtung der Umgebung, die Diagrammerstellung, die Anpassung von Beschriftungen, die Feinabstimmung der Aufteilungsposition und schließlich das Speichern der Präsentation als PPTX‑Datei. Am Ende sind Sie bereit, anspruchsvolle Diagramme in jede Folienpräsentation einzubetten.

## Schnelle Antworten
In Aspose.Slides repräsentiert `Presentation` eine PPTX‑Datei, `ChartType.PieOfPie` wählt das Pie‑of‑Pie‑Diagramm aus, `setShowValue(true)` zeigt Werte in den Beschriftungen an und `save` schreibt die Datei.

- **Was ist die primäre Klasse für die PowerPoint‑Manipulation?** `Presentation` – es repräsentiert eine gesamte PPTX‑Datei im Speicher.  
- **Welcher Diagrammtyp erstellt ein sekundäres Kreisdiagramm für kleine Segmente?** `ChartType.PieOfPie`.  
- **Wie zeigen Sie Werte auf jedem Segment an?** Set `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Können Sie die Datei direkt als PPTX speichern?** Ja – rufen Sie `presentation.save("output.pptx", SaveFormat.Pptx)` auf.  
- **Benötigen Sie eine Lizenz für die Entwicklung?** Eine kostenlose 30‑Tage‑Testversion funktioniert für Tests; eine permanente Lizenz entfernt die Evaluationswasserzeichen.

## Was ist ein Pie‑of‑Pie‑Diagramm?

Ein **Pie of Pie‑Diagramm** ist eine zweistufige Kreisvisualisierung, die ein oder mehrere kleine Segmente in ein separates, verknüpftes Kreisdiagramm auslagert, wodurch sie leichter lesbar werden. Aspose.Slides unterstützt diesen Diagrammtyp sofort und ermöglicht die Steuerung von Aufteilungsgröße, Position und Beschriftungsformatierung.

## Warum ein Diagramm zu PowerPoint mit Aspose.Slides hinzufügen?

Aspose.Slides kann PowerPoint‑Dateien erzeugen, bearbeiten und rendern, ohne dass Microsoft Office installiert sein muss. Es unterstützt **mehr als 50 Eingabe‑ und Ausgabeformate**, verarbeitet Präsentationen mit **bis zu 500 Folien** in weniger als einer Sekunde auf typischer Serverhardware und bietet **volle API‑Kontrolle** über Diagramm‑Styling, Datenbeschriftungen und Layout – perfekt für automatisierte Reporting‑Pipelines.

## Voraussetzungen

- **Java Development Kit (JDK) 16+** installiert.
- Eine IDE wie **IntelliJ IDEA**, **Eclipse** oder **NetBeans**.
- Maven oder Gradle für das Abhängigkeitsmanagement (siehe die Abschnitte unten).
- Grundlegende Java‑Kenntnisse und Vertrautheit mit dem Erstellen von Projekten.

## Einrichtung von Aspose.Slides für Java

### Installationsinformationen

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

**Direct Download:** Sie können die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Schritte zum Erwerb einer Lizenz
- **Free Trial:** Beginnen Sie mit einer 30‑Tage‑Testversion, um alle Funktionen zu erkunden.  
- **Temporary License:** Fordern Sie einen temporären Schlüssel für eine erweiterte Evaluierung an.  
- **Purchase:** Erwerben Sie eine permanente Lizenz für den Produktionseinsatz, um Evaluationswasserzeichen zu entfernen.

### Grundlegende Initialisierung und Einrichtung
`Presentation` ist das Hauptobjekt zum Erstellen von PowerPoint‑Dateien, und `Chart` repräsentiert ein Diagramm‑Shape innerhalb einer Folie.

```java
Presentation presentation = new Presentation();
```  

Dies erstellt eine leere Präsentation, die bereit für Folien und Diagramme ist.

## Implementierungsleitfaden

### Wie fügen Sie ein Diagramm zu PowerPoint mit Aspose.Slides für Java hinzu?

Laden Sie eine neue `Presentation`, fügen Sie eine Folie hinzu und fügen Sie ein `Chart` vom Typ `PieOfPie` ein. Die API‑Aufrufkette ist kompakt: Diagramm erstellen, Seriendaten befüllen, Beschriftungs‑Sichtbarkeit anpassen, Größe des sekundären Kreisdiagramms konfigurieren und schließlich speichern. Der gesamte Vorgang passt in der Regel in weniger als 20 Code‑Zeilen und ist damit ideal für die automatisierte Berichtserstellung.

### Erstellen eines 'Pie of Pie'-Diagramms

#### Übersicht
Wir werden ein Pie‑of‑Pie‑Diagramm auf der ersten Folie erstellen, die kleinsten Segmente auslagern und jedes Segment mit seinem Wert beschriften.

#### Schritt 1: Erstellen Sie eine Instanz der Klasse Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Dies initialisiert den Container für alle nachfolgenden Folien und Diagramme.

#### Schritt 2: Fügen Sie ein 'Pie of Pie'-Diagramm auf der ersten Folie hinzu
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Hier geben wir `ChartType.PieOfPie` an und definieren die Position (X, Y) und Größe (Breite, Höhe) des Diagramms auf der Folienfläche.

#### Schritt 3: Datenbeschriftungen so einstellen, dass Werte für die Serie angezeigt werden
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Durch Aktivieren von `showValue` wird jeder Abschnitt mit seinem numerischen Wert angezeigt, was für eine schnelle Dateninterpretation entscheidend ist.

#### Schritt 4: Größe des zweiten Kreisdiagramms konfigurieren und nach Prozentsatz aufteilen
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Diese Optionen ermöglichen es Ihnen zu bestimmen, wie viel des Diagramms dem sekundären Kreis zugewiesen wird und welche Segmente basierend auf einem Prozentsatz‑Schwellenwert verschoben werden.

#### Schritt 5: Speichern Sie die Präsentation im PPTX‑Format auf dem Datenträger
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Verwenden Sie einen absoluten Pfad oder Java’s `Paths.get()`, um plattformspezifische Trennzeichen zu vermeiden.

## Häufige Probleme und Lösungen

Die Klasse `License` lädt eine Lizenzdatei, um Evaluationsbeschränkungen zu entfernen.

- **Missing license warning:** Wenn Sie „Evaluation Only“ im Diagramm sehen, stellen Sie sicher, dass Sie eine gültige Lizenzdatei über `License license = new License(); license.setLicense("Aspose.Slides.lic");` angewendet haben.
- **Incorrect slice split:** Überprüfen Sie, dass die Eigenschaft `splitBy` auf `SplitBy.Percentage` gesetzt ist und dass `secondPieSize` einen Wert zwischen 0 und 100 hat.
- **Data not displaying:** Stellen Sie sicher, dass die Serie des Diagramms mindestens einen Datenpunkt enthält; andernfalls wird das Diagramm leer angezeigt.

## Häufig gestellte Fragen

`IChart` repräsentiert ein Diagrammobjekt, das zu einer Folie hinzugefügt werden kann.

**Q: Kann ich mehrere Diagramme in einer einzigen Präsentation erzeugen?**  
A: Ja, instanziieren Sie für jede Folie oder Position ein neues `IChart`; die API erlaubt unbegrenzte Diagrammobjekte pro Datei.

`SaveFormat.Pdf` gibt das PDF‑Ausgabeformat zum Speichern an.

**Q: Unterstützt Aspose.Slides auch das Speichern als PDF?**  
A: Absolut – rufen Sie `presentation.save("output.pdf", SaveFormat.Pdf)` auf, um das gleiche Foliendeck nach PDF zu exportieren.

`IPortion` repräsentiert ein einzelnes Segment eines Kreisdiagramms.

**Q: Wie viele Datenpunkte kann ein Pie‑of‑Pie‑Diagramm maximal verarbeiten?**  
A: Die Bibliothek unterstützt bis zu **10.000** Datenpunkte pro Serie, nur durch den verfügbaren Speicher begrenzt.

**Q: Ist es möglich, die Farben einzelner Segmente anzupassen?**  
A: Ja, greifen Sie auf jedes `IPortion` über `chart.getChartData().getSeries().get_Item(0).getPortions()` zu und setzen Sie `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Wie bette ich das erzeugte PPTX in eine Webanwendung ein?**  
A: Nach dem Speichern der Datei streamen Sie sie direkt zum Client mittels `HttpServletResponse` mit `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Fazit

Sie haben nun ein vollständiges, produktionsreifes Rezept für **das Hinzufügen eines Diagramms zu PowerPoint**, indem Sie ein Pie‑of‑Pie‑Diagramm mit Aspose.Slides für Java erstellen. Experimentieren Sie mit verschiedenen Aufteilungsschwellen, Beschriftungsformaten und Farbschemata, um Ihre Markenrichtlinien zu erfüllen. Als Nächstes erkunden Sie weitere Diagrammtypen – wie gestapelte Balken oder Radar – um Ihre automatisierten Folienpräsentationen weiter zu bereichern.

---

**Zuletzt aktualisiert:** 2026-07-17  
**Getestet mit:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Dynamisches Diagramm in Java erstellen – PowerPoint‑Diagramm‑Tutorials für Aspose.Slides](/slides/java/charts-graphs/)
- [Wie man ein Kreisdiagramm zu PowerPoint mit Aspose.Slides für Java hinzufügt](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
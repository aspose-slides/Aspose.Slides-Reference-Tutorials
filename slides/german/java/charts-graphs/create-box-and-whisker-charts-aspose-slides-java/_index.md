---
date: '2026-08-21'
description: Erfahren Sie, wie Sie mit Aspose.Slides ein Box‑Plot in Java erstellen,
  ein Diagramm zur Folie hinzufügen und ein Box‑and‑Whisker‑Chart in PowerPoint erzeugen.
  Ideal für Java‑Entwickler.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Erfahren Sie, wie Sie mit Aspose.Slides ein Box‑Plot in Java erstellen,
  ein Diagramm zur Folie hinzufügen und ein Box‑and‑Whisker‑Chart in PowerPoint erzeugen.
  Ideal für Java‑Entwickler.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Wie man ein Box‑Plot in Java mit Aspose.Slides für PowerPoint erstellt
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Wie man ein Box‑Plot in Java mit Aspose.Slides für PowerPoint erstellt
url: /de/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Box‑Plot in Java mit Aspose.Slides für PowerPoint erstellt

In diesem Leitfaden **Box‑Plot in Java erstellen** Sie mit Aspose.Slides und betten das Diagramm anschließend direkt in eine PowerPoint‑Folie ein. Das programmgesteuerte Erzeugen von Box‑and‑Whisker‑Diagrammen ermöglicht es, Rohdaten in klare visuelle Erkenntnisse zu verwandeln, ohne Ihren Java‑Code zu verlassen. Wenn Sie die PowerPoint‑Berichterstellung automatisieren müssen, bietet Aspose.Slides für Java eine zuverlässige, leistungsstarke API.

## Was Sie lernen werden

- Einrichten Ihrer Umgebung für Aspose.Slides für Java
- Schritte zum **Diagramm zur Folie hinzufügen** und zum Erzeugen eines Box‑Whisker‑Diagramms in PowerPoint mit Java
- Best Practices zur Optimierung der Leistung bei der Arbeit mit Aspose.Slides
- Echte Anwendungsfälle von Box‑and‑Whisker‑Diagrammen

## Schnelle Antworten
- **Welche Bibliothek erstellt ein Box‑Plot in Java?** Aspose.Slides for Java.  
- **Welcher Diagrammtyp wird verwendet?** `ChartType.BoxAndWhisker`.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich mehrere Serien hinzufügen?** Ja – wiederholen Sie den Serien‑Erstellungsblock für jeden Datensatz.  
- **Welches Format hat die endgültige Datei?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Was ist ein Box‑Plot und warum in Java verwenden?

Ein Box‑and‑Whisker‑Diagramm (oft *Box‑Plot* genannt) visualisiert die Datenverteilung – Median, Quartile und Ausreißer – in kompakter Form. In Java ermöglicht das programmgesteuerte Erzeugen dieses Diagramms, statistische Erkenntnisse direkt in PowerPoint‑Präsentationen einzubetten und damit die manuelle Diagrammerstellung zu eliminieren. Es ist besonders nützlich, um Verteilungen über mehrere Kategorien hinweg zu vergleichen, etwa Testergebnisse verschiedener Klassen oder Verkaufszahlen verschiedener Regionen. Durch die Generierung des Diagramms in Java können Sie es in automatisierte Reporting‑Pipelines integrieren und sicherstellen, dass stets aktuelle Daten in Ihren Präsentationen erscheinen.

## Warum ein Diagramm mit Aspose.Slides zur Folie hinzufügen?

Aspose.Slides abstrahiert die low‑level OpenXML‑Details und bietet Ihnen eine flüssige API zum Erstellen, Gestalten und Exportieren von Diagrammen. Das bedeutet, dass Sie die Berichtserstellung automatisieren, ein konsistentes Branding sicherstellen und Diagramme in größere Java‑Workflows integrieren können. Die Bibliothek unterstützt zudem Styling‑Optionen wie Farben, Schriftarten und Marker, sodass Sie das Corporate Design einhalten. Zusätzlich übernimmt sie komplexe Aufgaben wie Datenbindung und Diagramm‑Refresh, ohne dass Microsoft Office erforderlich ist.

## Wie fügt man in Java ein Diagramm zur Folie mit Aspose.Slides hinzu?

Laden oder erstellen Sie ein `Presentation`, fügen Sie ein `Chart` vom Typ `BoxAndWhisker` ein, übergeben Sie Ihre Daten und speichern Sie die Datei – alles in wenigen Java‑Zeilen. Die API übernimmt Layout, Skalierung und Rendering, sodass Sie kein XML selbst manipulieren müssen. Sie können zudem Diagrammtitel und Achsenbeschriftungen programmgesteuert setzen, um den Betrachtern Kontext zu geben.

## Voraussetzungen

- **Java Development Kit (JDK)**: JDK 8 oder höher.  
- **Aspose.Slides for Java Library**: Erforderlich für die PowerPoint‑Manipulation.  
- **IDE**: IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor.

## Einrichtung von Aspose.Slides für Java

Fügen Sie die Bibliothek als Maven‑, Gradle‑ oder manuelle Abhängigkeit hinzu.

### Maven

Fügen Sie die folgende Abhängigkeit in Ihre `pom.xml` ein:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

In Ihrer `build.gradle` fügen Sie hinzu:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download

Laden Sie alternativ die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

#### Lizenzbeschaffung

- **Kostenlose Testversion** – Funktionen ohne Kosten erkunden.  
- **Temporäre Lizenz** – für kurzfristige Evaluierung verwenden.  
- **Kauf** – volle Funktionalität für Produktions‑Workloads freischalten.

Um Aspose.Slides zu initialisieren, stellen Sie sicher, dass das JAR im Klassenpfad liegt und setzen Sie ggf. die Lizenzdatei wie in der Dokumentation beschrieben.

## Implementierungsleitfaden

Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Durchführung. Jeder Block wird vor dem Code‑Snippet erklärt, damit Sie genau wissen, was er bewirkt.

### Was ist die `Presentation`‑Klasse?

Die `Presentation`‑Klasse ist das zentrale Objekt in Aspose.Slides, das eine gesamte PowerPoint‑Datei im Speicher repräsentiert. Sie bietet Zugriff auf Folien, Diagramme, Formen und andere Folienelemente und ermöglicht das programmgesteuerte Erstellen, Ändern und Speichern von Präsentationen. Mit dieser Klasse können Sie neue Folien hinzufügen, Bilder einfügen und die Folienreihenfolge mit einfachen API‑Aufrufen manipulieren.

### Schritt 1: Präsentation erstellen oder öffnen

Öffnen Sie zunächst ein vorhandenes PPTX oder starten Sie ein neues:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro‑Tipp:** Existiert die Datei nicht, erstellt Aspose.Slides automatisch eine neue leere Präsentation.

### Schritt 2: Box‑and‑Whisker‑Diagramm zur Folie hinzufügen

Platzieren Sie das Diagramm dort, wo Sie es benötigen, indem Sie Position und Größe (in Punkten) angeben:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Schritt 3: Vorhandene Daten löschen

Bevor Sie neue Daten einfügen, entfernen Sie vorhandene Platzhalter‑Kategorien oder -Serien:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Schritt 4: Kategorien konfigurieren

Fügen Sie die Kategorien (X‑Achsen‑Beschriftungen) hinzu, die unter jedem Box‑Diagramm erscheinen sollen:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Hinweis:** Passen Sie den Beschriftungstext an Ihre Daten­domäne an (z. B. „Q1“, „Produkt A“).

### Schritt 5: Serie erstellen und anpassen

Erstellen Sie nun eine Serie, setzen Sie visuelle Optionen und übergeben Sie die numerischen Datenpunkte:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Sie können das `int[] data`‑Array durch Werte ersetzen, die aus einer Datenbank, einer CSV‑Datei oder einer anderen Quelle gelesen werden.

### Schritt 6: Präsentation speichern

Speichern Sie die Änderungen in einer neuen PPTX‑Datei:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Schritt 7: Ressourcen bereinigen

Entsorgen Sie das `Presentation`‑Objekt stets, um native Ressourcen freizugeben:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktische Anwendungen

1. **Finanzanalyse** – Umsatzverteilung über Regionen visualisieren.  
2. **Qualitätskontrolle** – Ausreißer in Fertigungsmessungen erkennen.  
3. **Akademische Forschung** – Variabilität von Versuchsergebnissen zeigen.  
4. **Marktforschung** – Produktleistung über demografische Gruppen vergleichen.

Das direkte Einbetten dieser Diagramme in PowerPoint‑Decks ermöglicht es Stakeholdern, komplexe Daten auf einen Blick zu erfassen.

## Leistungsüberlegungen

Aspose.Slides kann Präsentationen mit **500+ Folien** und Diagramme mit **100 000+ Datenpunkten** verarbeiten, während der Speicherverbrauch auf einem typischen Server unter 200 MB bleibt. Um innerhalb dieser Grenzen zu bleiben:

- **Speichermanagement** – `Presentation`‑Objekte sofort freigeben.  
- **Datenhandling** – nur die tatsächlich benötigten Daten laden; massive Datensätze nicht direkt in das Diagramm‑Workbook einspeisen.  
- **Lazy Loading** – beim Erzeugen vieler Folien Diagramme nur für die tatsächlich angezeigten Folien erstellen.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **Diagramm erscheint leer** | Datenzellen nicht korrekt befüllt | Überprüfen Sie, dass `wb.getCell` die richtige Zeile/Spalte referenziert und der Wert nicht `null` ist. |
| **Ausreißer werden nicht angezeigt** | `setShowOutlierPoints` ist auf `false` gesetzt | Stellen Sie sicher, dass `series.setShowOutlierPoints(true)` aufgerufen wird. |
| **Speicherleck** | Präsentation nicht freigegeben | Immer die Nutzung in `try/finally` einbetten und `dispose()` aufrufen. |
| **Falsche Quartile** | Verwendung der Standard‑`Inclusive`‑Methode | Wechseln Sie zu `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Häufig gestellte Fragen

**Q1: Was ist ein Box‑and‑Whisker‑Diagramm?**  
Ein Box‑and‑Whisker‑Diagramm, auch Box‑Plot genannt, zeigt die Verteilung von Daten anhand von fünf Kennzahlen: Minimum, erstes Quartil, Median, drittes Quartil und Maximum sowie eventuelle Ausreißer.

**Q2: Kann ich das Aussehen des Box‑and‑Whisker‑Diagramms anpassen?**  
Ja. Aspose.Slides ermöglicht das Ändern von Farben, Linienstilen, Marker‑Formen und das Hinzufügen von Datenbeschriftungen über die Formatierungs‑API des Diagramms.

**Q3: Ist es möglich, mehrere Serien in einem einzigen Diagramm zu handhaben?**  
Absolut. Wiederholen Sie den Serien‑Erstellungsblock für jeden Datensatz, den Sie visualisieren möchten.

**Q4: Wie löse ich Probleme, wenn Daten nicht korrekt angezeigt werden?**  
Stellen Sie sicher, dass die Daten korrekt in die Workbook‑Zellen geschrieben werden und dass Sichtbarkeits‑Eigenschaften wie `setShowMeanLine` aktiviert sind.

**Q5: Wo bekomme ich Unterstützung, wenn ich Probleme habe?**  
Besuchen Sie das [Aspose.Slides‑Forum](https://forum.aspose.com/c/slides/11) für Community‑Hilfe oder konsultieren Sie die offizielle Dokumentation.

**Q6: Unterstützt Aspose.Slides weitere Diagrammtypen?**  
Ja, es unterstützt mehr als 50 Diagrammtypen – darunter Linien-, Balken-, Kreis-, Streu‑, Radar‑ und Trichter‑Diagramme – sodass Sie das optimale Visual für Ihre Daten wählen können.

**Q7: Kann ich Diagramme in einer headless Server‑Umgebung erzeugen?**  
Die Bibliothek funktioniert vollständig in serverseitigen Szenarien; weder UI noch eine Microsoft‑Office‑Installation sind erforderlich.

## Ressourcen

- **Dokumentation**: Detaillierte API‑Referenzen unter [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Zugriff auf die Aspose.Slides‑Release‑Seite [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Kauf**: Lizenz erwerben, um alle Funktionen freizuschalten [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion & temporäre Lizenz**: Beginnen Sie mit einer kostenlosen Testversion oder fordern Sie eine temporäre Lizenz an [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Durch Befolgen dieses Leitfadens können Sie nun programmgesteuert aussagekräftige Box‑and‑Whisker‑Diagramme in Ihren Java‑Anwendungen erzeugen und direkt in PowerPoint‑Präsentationen einbetten. Viel Spaß beim Coden!

---

**Zuletzt aktualisiert:** 2026-08-21  
**Getestet mit:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man ein Diagramm zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java: PowerPoint‑Diagramm mit Aspose.Slides erstellen](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Animation zu PowerPoint‑Diagramm mit Aspose.Slides für Java hinzufügen – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
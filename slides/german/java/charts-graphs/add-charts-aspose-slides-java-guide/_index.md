---
date: '2026-06-03'
description: Erfahren Sie, wie Sie mit dem aspose slides maven dependency charts hinzufügen,
  data labels konfigurieren und dynamische charts in Java presentations erzeugen.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Hinzufügen und Konfigurieren von charts in
  Präsentationen mit Aspose.Slides für Java'
url: /de/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Diagramme in Präsentationen mit Aspose.Slides für Java hinzufügen und konfigurieren

## Einführung
Der **aspose slides maven dependency** ermöglicht Java‑Entwicklern das programmgesteuerte Erstellen, Ändern und Anreichern von PowerPoint‑Dateien, ohne PowerPoint selbst zu öffnen. In vielen geschäftlichen und akademischen Szenarien ist das manuelle Einfügen von Diagrammen zeitaufwändig und fehleranfällig. Dieses Tutorial zeigt Schritt für Schritt, wie man ein Blasendiagramm hinzufügt, Datenbeschriftungen an Arbeitsblattzellen bindet und das Ergebnis speichert – alles mithilfe des aspose slides maven dependency auf saubere, wiederholbare Weise.

**Was Sie lernen werden**
- Wie man Diagramme mit dem aspose slides maven dependency hinzufügt
- Einrichtung eines Java‑Projekts mit Maven oder Gradle
- Laden einer bestehenden Präsentation und Einfügen eines Blasendiagramms
- Konfigurieren von Datenbeschriftungen mittels Zellreferenzen (add data labels chart)
- Speichern der aktualisierten Datei für spätere Verteilung
- Praxisbeispiele wie dynamische Diagrammerstellung und Workflows zur Erstellung von Präsentationsdiagrammen

## Schnelle Antworten
- **Welches Maven‑Artifact fügt Diagrammfunktionen hinzu?** `com.aspose:aspose-slides:25.4` (oder neueste)  
- **Kann ich Datenbeschriftungen an Excel‑ähnliche Zellen binden?** Ja – verwenden Sie `ChartDataLabel` mit `setDataLabelFormat` und Zellreferenzen.  
- **Ist für die Produktion eine Lizenz erforderlich?** Eine Voll‑Lizenz entfernt das Evaluations‑Wasserzeichen und schaltet alle Funktionen frei.  
- **Funktioniert das unter Java 11+?** Absolut; die Bibliothek ist kompatibel mit Java 8 bis Java 21.  
- **Wie viele Diagrammtypen werden unterstützt?** Über 70 verschiedene Diagrammtypen, einschließlich Blasen-, Radar‑ und Aktien‑Diagrammen.

## Was ist der aspose slides maven dependency?
Der **aspose slides maven dependency** ist ein Maven‑kompatibles Paket, das eine voll ausgestattete API zum Erstellen und Bearbeiten von PowerPoint‑Dateien (PPTX, PPT, ODP) in Java bereitstellt. Durch das Hinzufügen dieser Abhängigkeit zu Ihrer `pom.xml` oder `build.gradle` erhalten Sie Zugriff auf über 70 Diagrammtypen, mehr als 150 Folienlayouts und die Möglichkeit, Formen, Animationen und Metadaten zu manipulieren, ohne dass Office installiert sein muss.

## Warum den aspose slides maven dependency für Diagramm‑Automatisierung verwenden?
Aspose.Slides verarbeitet tausende‑Folien‑Decks in weniger als einer Sekunde auf Standard‑Serverhardware, unterstützt **70+ Diagrammtypen**, und kann Präsentationen mit bis zu **10.000 Folien** rendern, ohne die gesamte Datei in den Speicher zu laden. Diese quantifizierten Fähigkeiten machen es ideal für unternehmensweite dynamische Diagrammerstellung, bei der Leistung und Skalierbarkeit nicht verhandelbar sind.

## Voraussetzungen
- **Java Development Kit (JDK)** 8 oder neuer (Java 11+ empfohlen).  
- **Maven** 3.6+ **oder** **Gradle** 6+.  
- **Aspose.Slides for Java**‑Bibliothek (der aspose slides maven dependency, Version 25.4 oder später).  
- Grundlegende Kenntnisse von Java‑Collections und Datei‑I/O.  
- Eine Evaluations‑ oder Voll‑Lizenzdatei (`license.json`), falls Sie den Code über den Testzeitraum hinaus ausführen möchten.

## Wie fügt man ein Diagramm zu einer Folie mit Aspose.Slides hinzu?
Laden Sie die Zielpräsentation, erstellen Sie ein neues Diagramm‑Shape auf der gewünschten Folie und geben Sie den Diagrammtyp an (in diesem Beispiel Blase). Der gesamte Vorgang kann in **drei knappen Code‑Zeilen** durchgeführt werden, sobald die Bibliothek referenziert ist, was ihn ideal für schnelles Prototyping und Produktions‑Pipelines macht.

### Schritt 1: Den aspose slides maven dependency hinzufügen
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Diese Snippets ziehen die komplette Aspose.Slides‑API – einschließlich Diagrammunterstützung – direkt von Maven Central.

### Schritt 2: Die Präsentation laden und ein Blasendiagramm einfügen
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Schritt 3: Die Datenserie und Beschriftungen des Diagramms konfigurieren
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Schritt 4: Die geänderte Präsentation speichern
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Wie konfiguriert man Datenbeschriftungen mittels Zellreferenzen?
Datenbeschriftungen können an externe Zellwerte gebunden werden, analog zur Excel‑Funktion „Link to Cell“. Dieser Ansatz eliminiert hartkodierte Werte und ermöglicht **dynamische Diagrammerstellung**, bei der der Beschriftungsinhalt automatisch aktualisiert wird, sobald sich die zugrunde liegenden Daten ändern. Durch das Verknüpfen jeder Beschriftung mit einer bestimmten Arbeitsmappenzelle stellen Sie sicher, dass jede Änderung der Quelldaten sofort in der Präsentation sichtbar wird, was den Wartungsaufwand reduziert und das Risiko veralteter Informationen minimiert.

### Direkte Antwort
Rufen Sie `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` auf und übergeben Sie ein `DataLabelFormat`, das eine Zelladresse wie `"Sheet1!A2"` referenziert. Aspose.Slides löst die Referenz zur Laufzeit auf und fügt den aktuellen Zellwert in die Diagrammbeschriftung ein.

### Schritt‑für‑Schritt
1. Identifizieren Sie die Serie, die Sie beschriften möchten.  
2. Holen Sie das `IDataLabel`‑Objekt für jeden Datenpunkt.  
3. Verwenden Sie `setDataLabelFormat` mit einem `DataLabelFormat`, das für `CellReference` konfiguriert ist.  
4. Optional Schriftart, Farbe und Anzeigeoptionen anpassen.

## Wie speichert man die geänderte Präsentation?
Das Speichern erfolgt mit einem einzigen Methodenaufruf, der das im Speicher befindliche `Presentation`‑Objekt in einen Dateipfad oder Ausgabestream schreibt. Sie können zudem das Ausgabeformat (PPTX, PDF, ODP) wählen, indem Sie das passende `SaveFormat`‑Enum übergeben. Dieser Vorgang streamt das Ergebnis direkt auf die Festplatte und gibt alle nativen Ressourcen automatisch frei, sobald die `Presentation`‑Instanz geschlossen oder aus dem Gültigkeitsbereich fällt, was den Speicherverbrauch selbst bei großen Decks gering hält.

### Direkte Antwort
Rufen Sie `presentation.save("output.pptx", SaveFormat.Pptx)` auf; die Bibliothek streamt das Ergebnis direkt auf die Festplatte und gibt alle nativen Ressourcen automatisch frei, sobald die `Presentation`‑Instanz geschlossen oder aus dem Gültigkeitsbereich fällt.

## Praktische Anwendungen
1. **Geschäftsberichte:** Quartals‑Verkaufsdiagramme automatisch aus einem Datenbank‑Dump generieren.  
2. **Akademische Vorlesungen:** Live‑Forschungsdaten in Vorlesungsfolien für jede Unterrichtsstunde einbinden.  
3. **Verkaufspräsentationen:** Kundenspezifische Leistungs‑Dashboards on‑the‑fly erstellen.  
4. **Projektmanagement:** Gantt‑ähnliche Zeitpläne mit dynamischen Datenbeschriftungen visualisieren.  
5. **Marketing‑Analytics:** Kampagnen‑KPIs in Präsentationen einbetten, die sich mit neuen Metriken aktualisieren.

## Leistungsüberlegungen
- **Speichermanagement:** Verwenden Sie try‑with‑resources oder explizites `presentation.dispose()`, um nativen Speicher zeitnah freizugeben.  
- **Große Datensätze:** Bei mehr als 10.000 Datenpunkten Daten über `ChartDataWorkbook` einfügen, um das Laden des gesamten Datensatzes in Java‑Objekte zu vermeiden.  
- **Thread‑Sicherheit:** Jeder Thread sollte mit seiner eigenen `Presentation`‑Instanz arbeiten; die API ist nicht thread‑sicher bei gemeinsam genutzten Objekten.  

## Häufige Probleme und Lösungen
- **Problem:** „Lizenzdatei nicht gefunden.“  
  **Lösung:** Legen Sie `license.json` im Klassenpfad ab und rufen Sie `License license = new License(); license.setLicense("license.json");` vor jeglicher API‑Nutzung auf.  
- **Problem:** Diagramm erscheint nach dem Speichern leer.  
  **Lösung:** Stellen Sie sicher, dass das Daten‑Workbook des Diagramms mit der Präsentation gespeichert wird (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problem:** Datenbeschriftungen zeigen „#REF!“‑Fehler.  
  **Lösung:** Prüfen Sie, ob die Zellreferenz‑Zeichenkette exakt den Blattnamen und die Adresse enthält und ob das referenzierte Workbook dem Diagramm zugeordnet ist.  

## Häufig gestellte Fragen

**F: Kann ich neben Blasen auch andere Diagrammtypen hinzufügen?**  
A: Ja, die `ChartType`‑Aufzählung enthält Linien-, Balken-, Kreis-, Radar-, Aktien‑ und mehr als 70 weitere Typen.

**F: Funktioniert der aspose slides maven dependency mit OpenJDK?**  
A: Absolut; er ist vollständig kompatibel mit OpenJDK 8‑21 und läuft auf allen gängigen Betriebssystemen.

**F: Wie bette ich ein Diagramm aus einer bestehenden Excel‑Datei ein?**  
A: Laden Sie die Excel‑Arbeitsmappe mit `WorkbookFactory.create(new FileInputStream("data.xlsx"))` und binden Sie das `ChartDataWorkbook` des Diagramms an die Arbeitsmappe, bevor Sie Zellreferenzen setzen.

**F: Gibt es ein Limit für die Anzahl der Diagramme pro Folie?**  
A: Praktisch kein – Aspose.Slides kann Dutzende von Diagrammen pro Folie verarbeiten, begrenzt nur durch den verfügbaren Speicher.

**F: In welchen Formaten kann ich die fertige Präsentation exportieren?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML und sogar Bildformate wie PNG und JPEG werden unterstützt.

## Ressourcen
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – die neuesten Bibliotheks‑Binaries herunterladen.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – umfassende API‑Referenz und Anleitungen.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – direkte Download‑Seite für die Maven/Gradle‑Pakete.  
- [Purchase a License](https://purchase.aspose.com/buy) – eine vollständige kommerzielle Lizenz erwerben.  
- [Free Trial](https://releases.aspose.com/slides/java/) – mit einer Testversion die Funktionen evaluieren.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – einen temporären Schlüssel für erweiterte Evaluation anfordern.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – Hilfe von der Community und Aspose‑Ingenieuren erhalten.

## Fazit
Sie haben nun eine vollständige End‑zu‑End‑Anleitung zur Verwendung des **aspose slides maven dependency**, um Diagramme in Java‑Präsentationen hinzuzufügen, zu konfigurieren und zu speichern. Durch Befolgen der obigen Schritte können Sie die Diagrammerstellung automatisieren, Datenbeschriftungen an Live‑Zellwerte binden und professionelle Decks in großem Maßstab erzeugen. Experimentieren Sie mit anderen Diagrammtypen, erkunden Sie die Animations‑APIs und integrieren Sie diesen Workflow in Ihre Reporting‑Pipelines für maximalen Nutzen.

---  
**Zuletzt aktualisiert:** 2026-06-03  
**Getestet mit:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Verwandte Tutorials

- [How to Create and Configure Presentations with Aspose.Slides Java&#58; A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
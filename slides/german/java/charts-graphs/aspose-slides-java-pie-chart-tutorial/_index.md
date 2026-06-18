---
date: '2026-06-13'
description: Erfahren Sie, wie Sie Excel zu PowerPoint hinzufügen und PowerPoint aus
  Excel generieren, indem Sie ein dynamisches Kreisdiagramm mit Aspose.Slides für
  Java erstellen.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'Excel zu PowerPoint hinzufügen: Dynamische Präsentation mit Kreisdiagramm
  unter Verwendung von Aspose.Slides für Java'
url: /de/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Excel zu PowerPoint hinzufügen: Dynamische Präsentation mit Kreisdiagramm mit Aspose.Slides für Java

In der heutigen datengetriebenen Umgebung **Excel zu PowerPoint hinzufügen** schnell und zuverlässig, damit Ihr Publikum die Zahlen in einem visuellen Format sehen kann. Dieses Tutorial führt Sie durch die Erstellung einer PowerPoint‑Präsentation aus Excel, das Erstellen eines Kreisdiagramms mit Java und das Konfigurieren des Datenbereichs des Diagramms – alles mit Aspose.Slides für Java. Am Ende haben Sie eine einsatzbereite Präsentation, die Live‑Daten direkt aus einer Excel‑Arbeitsmappe zieht.

## Schnelle Antworten
- **Welche Bibliothek erstellt Diagramme in Java?** Aspose.Slides for Java.  
- **Kann ich Excel-Daten direkt in ein PowerPoint‑Diagramm einbinden?** Ja – verwenden Sie Aspose.Cells, um die Arbeitsmappe zu lesen und sie dem Diagramm zu übergeben.  
- **Welcher Diagrammtyp wird demonstriert?** Ein Kreisdiagramm.  
- **Wie lege ich den Datenbereich für das Diagramm fest?** Durch Aufruf von `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **Was ist der Hauptvorteil dieses Ansatzes?** Automatisiert den „Excel zu PowerPoint hinzufügen“-Workflow und eliminiert manuelles Kopieren‑Einfügen.

## Was bedeutet **Excel zu PowerPoint hinzufügen**?
Excel zu PowerPoint hinzufügen bedeutet, Tabellenkalkulationsdaten programmgesteuert zu importieren und sie innerhalb einer Folienpräsentation zu visualisieren. Dadurch können Sie die Quelldaten im nativen Excel‑Format behalten und sie als professionelles Diagramm präsentieren, wobei jede Aktualisierung der Arbeitsmappe sofort in der Präsentation reflektiert wird.

## Warum PowerPoint aus Excel mit Aspose.Slides für Java erzeugen?
Die Erstellung von PowerPoint aus Excel mit Aspose.Slides für Java ermöglicht es Ihnen, Folienpräsentationen in Sekunden zu erstellen, indem Daten direkt aus der Arbeitsmappe gezogen werden, ohne manuelles Kopieren‑Einfügen. Die Bibliothek unterstützt mehr als 50 Eingabe‑ und Ausgabeformate, verarbeitet mehrseitige Arbeitsmappen, ohne die gesamte Datei in den Speicher zu laden, und bietet vollständige programmgesteuerte Kontrolle über Diagrammstil, Farben und Datenbereiche.

## Wie erzeugt man PowerPoint aus Excel mit Aspose.Slides für Java?
Laden Sie die Excel‑Arbeitsmappe mit Aspose.Cells, erstellen Sie ein neues `Presentation`, fügen Sie einer Folie ein Kreisdiagramm‑Shape hinzu und binden Sie das Diagramm an den Datenbereich der Arbeitsmappe. Mit nur wenigen Zeilen Java‑Code können Sie eine vollständige `.pptx`‑Datei erzeugen, die die neuesten Tabellenwerte widerspiegelt.

## Wie importiert man Excel in PowerPoint mit Aspose.Slides?
Das Importieren von Excel in PowerPoint erfolgt, indem die Excel‑Datei in ein `Workbook`‑Objekt eingelesen, die Arbeitsmappe in ein Byte‑Array konvertiert und dieses Byte‑Array an die Datenquelle des Diagramms übergeben wird. Das Diagramm liest automatisch den angegebenen Bereich, sodass die Visualisierung stets mit der Tabelle synchron bleibt.

## Wie legt man den Diagramm‑Datenbereich in Aspose.Slides für Java fest?
Verwenden Sie die Methode `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")`, um das Diagramm auf die genauen Zellen zu verweisen, die Ihre Kategorien und Werte enthalten. Dieser einzelne Aufruf definiert sowohl die Datenquelle als auch das Layout und eliminiert die Notwendigkeit einer manuellen Serienkonstruktion.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Java Development Kit (JDK) 1.8+** installiert.
- **Aspose.Slides for Java** und **Aspose.Cells for Java** Bibliotheken (Maven, Gradle oder direkter JAR‑Download).
- Eine Excel‑Arbeitsmappe (`book1.xlsx`) mit den Daten, die Sie visualisieren möchten.
- Eine gültige Aspose‑Lizenz (Kostenlose Testversion funktioniert für die Evaluierung).

### Erforderliche Bibliotheken
Sie benötigen Aspose.Slides und Aspose.Cells. Verwenden Sie eines dieser Abhängigkeits‑Management‑Tools:

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

Alternativ können Sie die JARs direkt von [Aspose.Slides für Java Releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung
- **Kostenlose Testversion:** Verfügbar auf der [Aspose-Download‑Seite](https://releases.aspose.com/slides/java/).  
- **Temporäre Lizenz:** Für Tests ohne Evaluationsbeschränkungen, beantragen Sie eine auf der [temporären Lizenzseite von Aspose](https://purchase.aspose.com/temporary-license/).  
- **Kauf‑Lizenz:** Um Aspose‑Produkte in der Produktion zu nutzen, erwerben Sie die Voll‑Lizenz.

## Einrichtung von Aspose.Slides für Java

Fügen Sie die Aspose.Slides‑Abhängigkeit zu Ihrem Projekt hinzu (siehe die Maven/Gradle‑Snippets oben) und legen Sie die JAR‑Dateien in Ihrem Klassenpfad ab, falls Sie kein Build‑Tool verwenden.

### Grundlegende Initialisierung und Einrichtung
Importieren Sie die Kernklasse, die eine PowerPoint‑Datei repräsentiert:  
```java
import com.aspose.slides.Presentation;
```  

## Implementierungs‑Leitfaden

Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die **create pie chart java**, **set chart data range** und **add Excel to PowerPoint** in einem einzigen Ablauf abdeckt.

### Diagramm erstellen und zur Präsentation hinzufügen

**Übersicht:** Initialisieren Sie eine neue Präsentation, holen Sie die erste Folie und fügen Sie ein Kreisdiagramm ein.

#### Schritt 1: Präsentation initialisieren  
```java
Presentation pres = new Presentation();
```  
- **Zweck:** Erstellt eine leere PowerPoint‑Datei im Speicher.

#### Schritt 2: Erste Folie zugreifen  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **Erklärung:** Ruft die automatisch erstellte erste Folie ab.

#### Schritt 3: Kreisdiagramm zur Folie hinzufügen  
Das `IChart`‑Objekt repräsentiert ein Diagramm‑Shape auf einer Folie.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **Parameter:** Position (`x`, `y`) und Größe (`width`, `height`).  
- **Zweck:** Platziert ein Kreisdiagramm‑Shape auf der Folie.

### Arbeitsmappe aus Datei laden

**Übersicht:** Laden Sie die Excel‑Arbeitsmappe, die die Daten für das Diagramm enthält.

#### Schritt 1: Dokumentverzeichnis definieren  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- Setzen Sie dies auf den Ordner, der `book1.xlsx` enthält.

#### Schritt 2: Arbeitsmappe öffnen  
Die `Workbook`‑Klasse von Aspose.Cells lädt eine Excel‑Datei in den Speicher.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **Zweck:** Liest die Excel‑Datei in den Speicher.

### Arbeitsmappe in ByteArrayOutputStream speichern

**Übersicht:** Konvertieren Sie die Arbeitsmappe in ein Byte‑Array, damit Aspose.Slides sie verwenden kann.

#### Schritt 1: ByteArrayOutputStream erstellen  
`ByteArrayOutputStream` stellt einen In‑Memory‑Puffer für Binärdaten bereit.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **Zweck:** Bietet einen In‑Memory‑Stream für temporäre Speicherung.

#### Schritt 2: Arbeitsmappe in den Stream speichern  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **Erklärung:** Schreibt die Arbeitsmappe als XLSX‑Byte‑Stream.

### Arbeitsmappendaten in Diagramm schreiben

**Übersicht:** Übergeben Sie das Excel‑Byte‑Array dem Diagramm als Datenquelle.

#### Schritt 1: Daten in das Diagramm einspeisen  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **Zweck:** Verknüpft das Diagramm mit den Excel‑Daten.

### Diagramm‑Datenbereich festlegen und Serien konfigurieren

**Übersicht:** Definieren Sie, welche Zellen das Diagramm lesen soll, und verbessern Sie das visuelle Styling.

#### Schritt 1: Datenbereich definieren  
Die `setRange`‑Methode definiert die Excel‑Zellen, die als Datenquelle des Diagramms verwendet werden.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **Erklärung:** Zeigt das Diagramm auf den genauen Bereich in *Sheet2*.

#### Schritt 2: Eigenschaften der Serien konfigurieren  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **Zweck:** Ermöglicht unterschiedliche Farben für jedes Segment des Kreisdiagramms.

### Präsentation in Datei speichern

**Übersicht:** Speichern Sie die fertige Präsentation auf dem Datenträger.

#### Schritt 1: Ausgabepfad definieren  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- Wählen Sie einen Ordner, in dem Sie die endgültige PowerPoint‑Datei speichern möchten.

#### Schritt 2: Präsentation speichern  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **Erklärung:** Schreibt die Präsentation als `.pptx`‑Datei.

## Praktische Anwendungsfälle

1. **Geschäftsberichte:** Wandeln Sie monatliche Verkaufs‑Tabellen in professionelle Folienpräsentationen mit einem einzigen Befehl um.  
2. **Bildungs‑Tools:** Zeigen Sie statistische Aufschlüsselungen für Unterrichtspräsentationen, ohne Diagramme manuell zu erstellen.  
3. **Dashboard‑Integration:** Automatisieren Sie die Erstellung von Folien‑Dashboards, die Live‑Daten aus Excel‑Arbeitsmappen ziehen.

## Leistungs‑Überlegungen

- **Speicherverwaltung:** Verpacken Sie Streams in try‑with‑resources oder schließen Sie sie in einem `finally`‑Block, um Lecks zu vermeiden.  
- **Große Datensätze:** Verarbeiten Sie Daten in Teilen oder verwenden Sie `Workbook.getWorksheets().clear()`, nachdem Sie die benötigten Werte extrahiert haben.  
- **Lazy Loading:** Laden Sie die Arbeitsmappe nur, wenn Sie das Diagramm füllen müssen, nicht beim Anwendungsstart.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|---------|--------|
| **Diagramm zeigt keine Daten** | Stellen Sie sicher, dass die Bereichszeichenfolge exakt den Blattnamen und die Zelladressen (`Sheet2!$A$1:$B$3`) entspricht. |
| **OutOfMemoryError** | Verwenden Sie `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }`, um sicherzustellen, dass der Stream sofort freigegeben wird. |
| **Lizenz nicht angewendet** | Laden Sie die Lizenz, bevor irgendeine Aspose‑Klasse instanziiert wird: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Slides ohne Lizenz verwenden?**  
A: Ja, aber der Evaluierungsmodus fügt Wasserzeichen hinzu und schränkt einige Funktionen ein. Für die Produktion erhalten Sie eine temporäre oder vollständige Lizenz.

**F: Wie gehe ich mit großen Präsentationen in Aspose.Slides um?**  
A: Nutzen Sie effizientes Ressourcen‑Management, teilen Sie die Präsentation in kleinere Teile und geben Sie ungenutzte Objekte zeitnah frei.

**F: Welche Dateiformate kann Aspose.Slides exportieren?**  
A: PPTX, PDF, XPS, ODP, HTML und Bildformate wie PNG, JPEG und BMP.

**F: Ist es möglich, eine bestehende PowerPoint‑Datei zu aktualisieren, anstatt eine neue zu erstellen?**  
A: Absolut. Laden Sie eine vorhandene Datei mit `new Presentation("existing.pptx")`, ändern Sie Folien/Diagramme und speichern Sie dann.

**F: Unterstützt die Bibliothek das Festlegen benutzerdefinierter Farben für einzelne Kreisdiagramm‑Segmente?**  
A: Ja – nachdem Sie die Serie abgerufen haben, können Sie `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` setzen und eine `Color` zuweisen.

## Ressourcen
- **Dokumentation:** [Aspose.Slides Java API‑Referenz](https://reference.aspose.com/slides/java/)
- **Download:** [Aspose.Slides für Java Releases](https://releases.aspose.com/slides/java/)
- **Lizenz kaufen:** [Aspose-Produkte kaufen](https://purchase.aspose.com/buy)
- **Kostenlose Testversion:** [Aspose.Slides kostenlos testen](https://releases.aspose.com/slides/java/)
- **Temporäre Lizenz:** [Temporäre Lizenz erhalten](https://purchase.aspose.com/temporary-license/)

---

**Zuletzt aktualisiert:** 2026-06-13  
**Getestet mit:** Aspose.Slides 25.4 für Java (JDK 16) & Aspose.Cells 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man den Datenbereich von PowerPoint‑Diagrammen mit Aspose.Slides für Java aktualisiert](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [Wie man ein Kreisdiagramm zu PowerPoint mit Aspose.Slides für Java hinzufügt](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
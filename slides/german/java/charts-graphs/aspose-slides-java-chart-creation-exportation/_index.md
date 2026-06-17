---
date: '2026-06-03'
description: Erfahren Sie, wie Sie ein Diagramm nach Excel exportieren und Diagramme
  in Java mit Aspose.Slides for Java erstellen. Meistern Sie Datenvisualisierung,
  Business-Report-Folien und die Erstellung von Arbeitsmappen.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Diagramm nach Excel exportieren und Diagramme mit Aspose.Slides erstellen
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramm nach Excel exportieren und Diagramme mit Aspose.Slides erstellen

**Meistern Sie Techniken zur Datenvisualisierung mit Aspose.Slides für Java**

In der heutigen datengetriebenen Landschaft ist das programmatische *export chart to excel* eine Fähigkeit, die rohe Zahlen in überzeugende visuelle Geschichten verwandeln kann. Egal, ob Sie ein Business‑Report‑Slide‑Deck oder ein interaktives Analyse‑Dashboard erstellen, Aspose.Slides für Java gibt Ihnen die Möglichkeit, Diagramme direkt aus Ihrem Code zu erzeugen, anzupassen und zu exportieren. In diesem Tutorial lernen Sie, wie Sie Diagrammobjekte erstellen, Diagrammdaten nach Excel exportieren und Diagramme mit externen Arbeitsmappen verknüpfen, um eine nahtlose Datenverwaltung zu ermöglichen.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.Slides for Java (v25.4+).  
- **Kann ich Diagrammdaten nach Excel exportieren?** Ja – verwenden Sie `readWorkbookStream()` und schreiben Sie die Bytes in eine *.xlsx*‑Datei.  
- **Welche Java-Version ist erforderlich?** JDK 16 oder höher.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Evaluierung; eine permanente Lizenz ist für die Produktion erforderlich.  
- **Welcher Diagrammtyp wird demonstriert?** Ein Kreisdiagramm, aber derselbe Ansatz funktioniert für Balken-, Linien‑ und andere Diagrammtypen.

## Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine reine Java‑API, die Entwicklern ermöglicht, PowerPoint‑Präsentationen zu erstellen, zu bearbeiten und zu konvertieren, ohne Microsoft Office zu benötigen. Sie bietet einen umfassenden Satz von Klassen für die Folienmanipulation, Diagrammerstellung und Formatkonvertierung, wodurch automatisierte Reporting‑Lösungen ermöglicht werden. Sie unterstützt **50+ Diagrammtypen**, vollständiges Data‑Binding und direkten Excel‑Export, was sie ideal für **data visualization java**‑Projekte macht.

## Warum Aspose.Slides zum Erstellen von Diagrammen und Exportieren von Diagrammen nach Excel verwenden?
Diagramme schnell und zuverlässig nach Excel exportieren. Aspose.Slides eliminiert die Notwendigkeit von Office‑Installationen, bietet **über 50 integrierte Diagramm‑Stile** und verarbeitet Präsentationen **bis zu 300 MB in weniger als 30 Sekunden** auf Standard‑Serverhardware. Sie erhalten zudem die native Excel‑Arbeitsmappengenerierung, die es nachgelagerten Analysten ermöglicht, mit Rohdaten zu arbeiten, ohne manuelles Kopieren‑Einfügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides for Java** version 25.4 or later (supports JDK 16+)

### Anforderungen an die Umgebungseinrichtung
- Java Development Kit (JDK) 16 or higher  
- An IDE such as IntelliJ IDEA or Eclipse (or any text editor you prefer)

### Vorkenntnisse
- Basic Java programming skills  
- Familiarity with Maven or Gradle build tools

## Einrichtung von Aspose.Slides für Java
Fügen Sie die Bibliothek zu Ihrem Projekt hinzu, indem Sie Ihr bevorzugtes Build‑System verwenden.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, you can [download the latest version directly](https://releases.aspose.com/slides/java/).

### Schritte zum Erwerb einer Lizenz
Aspose.Slides bietet eine kostenlose Testlizenz, um seine vollen Fähigkeiten zu erkunden. Sie können auch eine temporäre Lizenz beantragen oder eine für den erweiterten Gebrauch erwerben. Folgen Sie diesen Schritten:

1. Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get your license.  
2. For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).  
3. Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).

Sobald Sie die Lizenzdatei haben, initialisieren Sie sie in Ihrer Java‑Anwendung:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Schritt‑für‑Schritt‑Anleitung

### Wie man ein Diagramm erstellt – Präsentation laden
Load an existing PowerPoint file before you can add or modify charts.  
The `Presentation` class represents a PowerPoint file in memory, exposing slides, shapes, and chart objects.  
Load your file with `new Presentation("input.pptx")`, then work with the first slide using `presentation.getSlides().get_Item(0)`. Always call `presentation.dispose()` in a `finally` block to release native resources.

### Wie man ein Diagramm erstellt – Kreisdiagramm zu einer Folie hinzufügen
Insert a Pie chart, perfect for showing proportional data.  
The `IChart` interface is the primary entry point for chart manipulation; `addChart` creates a new chart on the target slide. Provide the chart type (`ChartType.Pie`), X/Y coordinates, and width/height. After creation, you can customize titles, legend, and data series through the `ChartData` object.

### Wie man ein Diagramm nach Excel exportiert – Diagrammdaten exportieren
Exporting chart data lets analysts work with the numbers in Excel, enabling deeper insights.  
`readWorkbookStream()` returns the chart's underlying Excel workbook as a byte array. Call `chart.getChartData().readWorkbookStream()` to retrieve the workbook and write this array to a file named `externalWorkbook1.xlsx` using standard Java I/O. The resulting Excel file contains the exact data used by the chart, ready for further analysis.

### Wie man ein Diagramm erstellt – Externe Arbeitsmappe für dynamische Daten festlegen
Link a chart to an external workbook to enable live data updates without rebuilding the slide.  
`setExternalWorkbook()` binds the chart to an external Excel file for dynamic data updates. Use `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` to bind the chart to the external file. When the Excel workbook is edited, the chart automatically reflects the changes the next time the presentation is opened, supporting dynamic reporting scenarios.

## Praktische Anwendungen
Aspose.Slides bietet vielseitige Lösungen für verschiedene reale Szenarien:

1. **Business‑Report‑Folien:** Erzeugen Sie vierteljährliche Leistungsdiagramme automatisch aus Ihren Datenpipelines.  
2. **Akademische Präsentationen:** Wandeln Sie Forschungsdaten in klare Visualisierungen um, ohne manuell Diagramme zu erstellen.  
3. **Finanzanalyse:** Exportieren Sie Diagrammdaten nach Excel, damit Prüfer die Zahlen verifizieren können, und reduzieren Sie manuelle Fehler.  
4. **Marketing‑Analytics:** Visualisieren Sie Kampagnenmetriken und teilen Sie editierbare Arbeitsmappen mit Stakeholdern für kollaborative Entscheidungsfindung.  
5. **Automatisierte Dashboard‑Erstellung:** Kombinieren Sie die Diagrammerstellungs‑API mit geplanten Jobs, um jeden Morgen aktuelle Foliendecks zu erzeugen.

## Häufige Probleme & Fehlerbehebung
- **`FileNotFoundException`** – Überprüfen Sie, dass `dataDir` auf einen gültigen Ordner zeigt und der Ausgabepfad beschreibbar ist.  
- **Speicherlecks** – Rufen Sie stets `presentation.dispose()` in einem `finally`‑Block auf, um native Ressourcen freizugeben.  
- **Diagramm erscheint nicht** – Stellen Sie sicher, dass der Folienindex (`get_Item(0)`) einer vorhandenen Folie entspricht und dass die Diagrammabmessungen innerhalb der Folienränder liegen.  
- **Excel‑Export erzeugt leere Datei** – Vergewissern Sie sich, dass das Diagramm tatsächlich Datenreihen enthält, bevor Sie `readWorkbookStream()` aufrufen.

## Häufig gestellte Fragen

**Q: Kann ich einen anderen Diagrammtyp (z. B. Balken, Linie) mit demselben Code verwenden?**  
A: Ja. Ersetzen Sie `ChartType.Pie` durch einen anderen `ChartType`‑Enum‑Wert wie `ChartType.Bar` oder `ChartType.Line`.

**Q: Ist es möglich, die externe Arbeitsmappe nach der Erstellung des Diagramms zu aktualisieren?**  
A: Absolut. Ändern Sie die Excel‑Datei direkt; das verknüpfte Diagramm spiegelt die Änderungen beim nächsten Öffnen der Präsentation wider.

**Q: Benötige ich eine separate Lizenz für die Excel‑Export‑Funktion?**  
A: Nein. Die Excel‑Export‑Funktion ist in der Standardlizenz von Aspose.Slides für Java enthalten.

**Q: Welche Java‑Versionen werden unterstützt?**  
A: Aspose.Slides für Java unterstützt JDK 16 und neuer; frühere Versionen können funktionieren, werden jedoch nicht offiziell getestet.

**Q: Wie kann ich die erzeugte Excel‑Arbeitsmappe in die PPTX‑Datei einbetten?**  
A: Verwenden Sie `chart.getChartData().setExternalWorkbook(null)`, um die Arbeitsmappe einzubetten, oder behalten Sie den externen Link für dynamische Updates bei.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Diagramm in Java mit Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Arbeitsmappendaten aus PowerPoint‑Diagrammen mit Aspose.Slides Java wiederherstellen](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Wie man den Datenbereich von PowerPoint‑Diagrammen mit Aspose.Slides für Java aktualisiert](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
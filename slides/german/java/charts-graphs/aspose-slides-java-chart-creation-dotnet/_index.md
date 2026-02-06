---
date: '2026-02-06'
description: Erfahren Sie, wie Sie eine Aspose Slides‑Präsentation initialisieren
  und ein gruppiertes Säulendiagramm in .NET mit Aspose.Slides für Java anpassen.
  Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung, um die Datenvisualisierung zu verbessern.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Präsentation mit Aspose Slides initialisieren: .NET‑Diagramme'
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Diagrammen in .NET‑Präsentationen mit Aspose.Slides für Java

## Einleitung
In diesem Tutorial werden Sie **initialize presentation Aspose Slides** und lernen, wie Sie dynamische, anpassbare Diagramme in Ihre .NET‑Folien einbetten. Visuelle Daten – wie gruppierte Säulendiagramme – helfen Ihrem Publikum, Trends sofort zu erfassen, und Aspose.Slides für Java bietet Ihnen die vollständige programmgesteuerte Kontrolle, selbst wenn Sie eine .NET‑Umgebung anvisieren. Wir führen Sie durch die Einrichtung der Bibliothek, das Erstellen einer neuen Präsentation, das Hinzufügen eines Diagramms, das Befüllen von Daten und das Anwenden von Formatierungstricks wie der Farbgebung negativer Werte.

**Was Sie lernen werden**
- Wie man Aspose.Slides für Java in einem .NET‑Projekt einrichtet.  
- Wie man **initialize presentation Aspose Slides** und ein Diagramm hinzufügt.  
- Wie man **customize clustered column chart** Serien und Kategorien anpasst.  
- Verwalten des Daten‑Workbook des Diagramms und Anwenden von bedingter Formatierung.  

### Schnelle Antworten
- **Was ist der erste Schritt?** Initialize a `Presentation` object.  
- **Welcher Diagrammtyp wird im Beispiel verwendet?** `ClusteredColumn`.  
- **Kann ich negative Werte anders formatieren?** Ja, mit bedingten Füllfarben.  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testlizenz funktioniert für die Entwicklung.  
- **Welches Maven‑Artefakt ist erforderlich?** `com.aspose:aspose-slides:25.4` mit `jdk16` classifier.

## Was ist „initialize presentation Aspose Slides“?
Das Initialisieren einer Präsentation erstellt eine im Speicher befindliche PPTX‑Datei, die Sie vor dem Speichern manipulieren können. Aspose.Slides abstrahiert das Dateiformat und ermöglicht das Hinzufügen von Folien, Formen und Diagrammen, ohne sich mit Low‑Level‑OPC‑Strukturen befassen zu müssen.

## Warum ein gruppiertes Säulendiagramm anpassen?
Gruppierte Säulendiagramme eignen sich ideal zum Vergleich mehrerer Datenreihen über Kategorien hinweg. Durch das Anpassen von Farben, Datenpunkten und Beschriftungen können Sie zentrale Erkenntnisse hervorheben – etwa negative Werte rot und positive Werte grün darstellen – und Ihre Folien überzeugender machen.

## Voraussetzungen
- **Aspose.Slides für Java** ≥ 25.4  
- .NET‑Entwicklungsumgebung (Visual Studio, .NET 6+ empfohlen)  
- Grundkenntnisse in Java (Sie schreiben Java‑Code, der auf der JVM läuft und über JNI oder eine Bridge von .NET aufgerufen wird)  

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java**: Version 25.4 oder höher.

### Anforderungen an die Umgebungseinrichtung
- Eine .NET‑kompatible Java‑Runtime (z. B. AdoptOpenJDK 16).  
- Maven oder Gradle für das Abhängigkeitsmanagement.

### Wissensvoraussetzungen
- Vertrautheit mit dem Erstellen von Präsentationen im .NET‑Kontext.  
- Verständnis der Java‑Projektkonfiguration (Maven/Gradle).

## Einrichtung von Aspose.Slides für Java
Fügen Sie die Bibliothek Ihrem Projekt mit dem bevorzugten Build‑Tool hinzu.

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

### Direkter Download
Sie können das neueste JAR auch von der offiziellen Release‑Seite herunterladen: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Schritte zum Erwerb einer Lizenz
- **Free Trial** – Erzeugen Sie eine temporäre Lizenzdatei für die Entwicklung.  
- **Purchase** – Erhalten Sie eine Voll‑Lizenz für Produktions‑Deployments.

#### Grundlegende Initialisierung und Einrichtung
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
Der `try/finally`‑Block stellt sicher, dass native Ressourcen freigegeben werden und Speicherlecks vermieden werden.

## Wie man initialize presentation Aspose Slides verwendet
Im Folgenden gehen wir die konkreten Schritte zum Erstellen einer frischen Präsentation und zur Vorbereitung für das Einfügen eines Diagramms durch.

### Initializing Presentation
**Übersicht:**  
Das Erstellen einer Präsentationsinstanz legt die Grundlage für alle nachfolgenden Vorgänge.

#### Schritt 1: Notwendige Pakete importieren
```java
import com.aspose.slides.Presentation;
```

#### Schritt 2: Ein neues Presentation‑Objekt erstellen
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Damit wird sichergestellt, dass das Präsentationsobjekt nach der Verwendung ordnungsgemäß verworfen wird, wodurch Speicherlecks verhindert werden.*

## Wie man clustered column chart anpasst
Jetzt, wo die Präsentation bereit ist, fügen wir ein gruppiertes Säulendiagramm hinzu und passen es an.

### Diagramm zur Folie hinzufügen
**Übersicht:**  
Das Hinzufügen eines Diagramms erweckt Daten auf der Folie zum Leben.

#### Schritt 1: Notwendige Pakete importieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Schritt 2: Präsentation initialisieren und Diagramm hinzufügen
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
*Hier fügen wir ein clustered column chart zur ersten Folie an den angegebenen Koordinaten und Abmessungen hinzu.*

### Daten‑Workbook des Diagramms verwalten
**Übersicht:**  
Durch effizientes Verwalten des Daten‑Workbook des Diagramms können Sie Serien und Kategorien nahtlos manipulieren.

#### Schritt 1: Notwendige Pakete importieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Schritt 2: Auf das Workbook zugreifen und es leeren
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
Dieser Schritt zeigt, wie Sie sinnvolle Datenpunkte hinzufügen, indem Sie Serien und Kategorien verwalten.

#### Schritt 1: Serien und Kategorien hinzufügen
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

### Serien‑Daten befüllen und formatieren
**Übersicht:**  
Befüllen Sie Ihr Diagramm mit Datenpunkten und formatieren Sie das Erscheinungsbild, um die Lesbarkeit zu erhöhen, insbesondere bei negativen Werten.

#### Schritt 1: Serien‑Daten befüllen
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
- **Memory leaks** – Wickeln Sie das `Presentation`‑Objekt immer in einen `try/finally`‑Block, wie gezeigt, um die Entsorgung zu garantieren.  
- **Incorrect cell coordinates** – Denken Sie daran, dass Zeilen und Spalten nullbasiert sind; falsche Indizes führen zu `NullPointerException`.  
- **License not found** – Legen Sie die Lizenzdatei im Arbeitsverzeichnis der Anwendung ab oder setzen Sie den Pfad explizit via `License.setLicense("Aspose.Slides.Java.lic")`.

## Häufig gestellte Fragen

**Q: Kann ich diesen Ansatz mit .NET Core verwenden?**  
A: Ja. Aspose.Slides für Java läuft auf jeder JVM, und Sie können den Java‑Code von .NET Core über eine Bridge wie IKVM oder JNI aufrufen.

**Q: Benötige ich eine kostenpflichtige Lizenz für die Entwicklung?**  
A: Eine kostenlose Testlizenz reicht für Entwicklung und Tests aus. Produktions‑Deployments erfordern eine gekaufte Lizenz.

**Q: Wie ändere ich den Diagrammtyp nach der Erstellung?**  
A: Sie können `chart.getChartData().setChartType(ChartType.Pie)` aufrufen, um zu einem anderen Diagrammtyp zu wechseln.

**Q: Ist es möglich, Datenbeschriftungen programmgesteuert hinzuzufügen?**  
A: Ja. Verwenden Sie `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)`, um Werte im Diagramm anzuzeigen.

**Q: In welchen Formaten kann ich die Präsentation speichern?**  
A: Aspose.Slides unterstützt PPTX, PPT, PDF, XPS und mehrere Bildformate wie PNG und JPEG.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides für Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
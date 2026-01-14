---
date: '2026-01-14'
description: Erfahren Sie, wie Sie ein gruppiertes Säulendiagramm einfügen und das
  Diagramm zu einer Folie in .NET‑Präsentationen mit Aspose.Slides für Java hinzufügen.
  Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung mit vollständigen Codebeispielen.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Fügen Sie ein gruppiertes Säulendiagramm zu .NET‑Folien Aspose.Slides Java
  hinzu.
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Diagrammen in .NET‑Präsentationen mit Aspose.Slides für Java
## Einführung
Fesselnde Präsentationen zu erstellen beinhaltet häufig die Integration visueller Datenrepräsentationen wie Diagrammen, um das Verständnis und die Einbindung des Publikums zu verbessern. Wenn Sie ein Entwickler sind, der dynamische, anpassbare Diagramme zu Ihren .NET‑Präsentationen mit Aspose.Slides für Java hinzufügen möchte, ist dieses Tutorial genau für Sie zugeschnitten. Wir gehen darauf ein, wie Sie Präsentationen initialisieren, verschiedene Diagrammtypen hinzufügen, Diagrammdaten verwalten und Seriendaten effektiv formatieren können.

**Was Sie lernen werden:**
- Wie Sie Aspose.Slides für Java in Ihrer .NET‑Umgebung einrichten und verwenden.
- Initialisierung einer neuen Präsentation mit Aspose.Slides.
- Hinzufügen und Anpassen von Diagrammen in Folien.
- Verwaltung von Diagrammdaten‑Workbooks.
- Formatierung von Seriendaten, insbesondere Umgang mit negativen Werten.

Der Übergang zum Abschnitt „Voraussetzungen“ stellt sicher, dass Sie bereit sind, problemlos zu folgen.

## Schnelle Antworten
- **Was ist das Hauptziel?** Ein gruppiertes Säulendiagramm zu einer .NET‑Folien hinzufügen.
- **Welche Bibliothek wird benötigt?** Aspose.Slides für Java (v25.4+).
- **Kann ich es in einem .NET‑Projekt verwenden?** Ja – die Java‑Bibliothek funktioniert über die Java‑zu‑.NET‑Brücke.
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Diagramm.

## Was ist ein gruppiertes Säulendiagramm?
Ein gruppiertes Säulendiagramm zeigt mehrere Datenserien nebeneinander für jede Kategorie, was den Vergleich von Werten über Gruppen hinweg erleichtert. Diese Visualisierung ist ideal für Business‑Dashboards, Leistungsberichte und jede Situation, in der mehrere Kennzahlen gegenübergestellt werden müssen.

## Warum ein Diagramm mit Aspose.Slides für Java zur Folie hinzufügen?
Mit Aspose.Slides können Sie Präsentationen erzeugen, ändern und speichern, ohne dass Microsoft PowerPoint installiert sein muss. Es bietet vollständige Kontrolle über Diagrammtypen, Daten und Stil, sodass Sie die Berichtserstellung direkt aus Ihren .NET‑Anwendungen automatisieren können.

## Voraussetzungen
Bevor Sie mit dem Erstellen von Diagrammen mit Aspose.Slides für Java beginnen, listen wir auf, was Sie benötigen:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java**: Version 25.4 oder höher.

### Anforderungen an die Umgebungseinrichtung
- Eine Entwicklungsumgebung, die .NET‑Anwendungen unterstützt.
- Grundlegendes Verständnis von Java‑Programmierkonzepten.

### Wissensvoraussetzungen
- Vertrautheit mit der Erstellung von Präsentationen im Kontext einer .NET‑Anwendung.
- Verständnis von Java‑Abhängigkeiten und deren Verwaltung (Maven/Gradle).

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides zu verwenden, müssen Sie es als Abhängigkeit in Ihr Projekt einbinden. So geht’s:

### Maven
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie dies in Ihre `build.gradle`‑Datei ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ können Sie die neueste Version von [Aspose.Slides für Java Releases](https://releases.aspose.com/slides/java/) herunterladen.

#### Schritte zum Lizenzieren
- **Kostenlose Testversion**: Beginnen Sie mit einer temporären Lizenz, um die Funktionen zu erkunden.
- **Kauf**: Erwägen Sie den Kauf einer Lizenz für umfangreiche Nutzung.

#### Grundlegende Initialisierung und Einrichtung
So initialisieren Sie Aspose.Slides in Ihrem Code:
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

### Präsentation initialisieren
**Übersicht:**  
Eine Präsentationsinstanz zu erstellen bildet die Grundlage für alle nachfolgenden Vorgänge. Diese Funktion zeigt, wie Sie von Grund auf mit Aspose.Slides starten.

#### Schritt 1: Notwendige Pakete importieren
```java
import com.aspose.slides.Presentation;
```

#### Schritt 2: Ein neues Präsentationsobjekt erstellen
So geht’s:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Damit wird sichergestellt, dass das Präsentationsobjekt nach Gebrauch ordnungsgemäß freigegeben wird, um Speicherlecks zu verhindern.*

### Diagramm zur Folie hinzufügen
**Übersicht:**  
Ein Diagramm zur Folie hinzuzufügen kann die Datenvisualisierung effektiver und ansprechender machen.

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
*Hier fügen wir ein gruppiertes Säulendiagramm zur ersten Folie an den angegebenen Koordinaten und Abmessungen hinzu.*

### Diagrammdaten‑Workbook verwalten
**Übersicht:**  
Ein effizientes Management des Diagrammdaten‑Workbooks ermöglicht es Ihnen, Serien und Kategorien nahtlos zu manipulieren.

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
Diese Funktion zeigt, wie Sie durch das Verwalten von Serien und Kategorien sinnvolle Datenpunkte hinzufügen können.

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

### Seriendaten befüllen und formatieren
**Übersicht:**  
Befüllen Sie Ihr Diagramm mit Datenpunkten und formatieren Sie das Erscheinungsbild, um die Lesbarkeit zu verbessern, insbesondere bei negativen Werten.

#### Schritt 1: Seriendaten befüllen
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
- **Speicherlecks:** Rufen Sie stets `dispose()` auf dem `Presentation`‑Objekt in einem `finally`‑Block auf.
- **Falscher Diagrammtyp:** Stellen Sie sicher, dass Sie `ChartType.ClusteredColumn` verwenden, wenn Sie ein gruppiertes Säulendiagramm wünschen; andere Typen erzeugen unterschiedliche visuelle Ergebnisse.
- **Farben für negative Werte werden nicht angewendet:** Vergewissern Sie sich, dass der Wert von `IDataPoint` korrekt in `Number` umgewandelt wird, bevor er verglichen wird.

## Häufig gestellte Fragen

**F: Kann ich Aspose.Slides für Java in einem reinen .NET‑Projekt ohne Java verwenden?**  
A: Ja. Die Bibliothek funktioniert über die Java‑zu‑.NET‑Brücke, sodass Sie Java‑APIs aus .NET‑Sprachen aufrufen können.

**F: Unterstützt die kostenlose Testversion die Diagrammerstellung?**  
A: Die Testversion enthält die vollständige Diagrammfunktionalität, jedoch enthalten erzeugte Dateien ein kleines Evaluations‑Wasserzeichen.

**F: Welche .NET‑Versionen sind kompatibel?**  
A: Jede .NET‑Version, die mit Java 16+ interoperieren kann, einschließlich .NET Framework 4.6+, .NET Core 3.1+ und .NET 5/6/7.

**F: Wie gehe ich mit großen Präsentationen mit vielen Diagrammen um?**  
A: Wiederverwenden Sie nach Möglichkeit dieselbe `IChartDataWorkbook`‑Instanz und geben Sie jede `Presentation`‑Instanz zeitnah frei, um Speicher zu sparen.

**F: Ist es möglich, das Diagramm als Bild zu exportieren?**  
A: Ja. Verwenden Sie die Methoden `chart.getImage()` oder `chart.exportChartImage()`, um PNG/JPEG‑Darstellungen zu erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-14  
**Getestet mit:** Aspose.Slides für Java 25.4  
**Autor:** Aspose  

---
---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Diagramme in .NET-Präsentationen erstellen und anpassen. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um die Datenvisualisierung Ihrer Präsentation zu verbessern."
"title": "Aspose.Slides für Java&#58; Erstellen von Diagrammen in .NET-Präsentationen"
"url": "/de/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Diagrammen in .NET-Präsentationen mit Aspose.Slides für Java
## Einführung
Das Erstellen überzeugender Präsentationen erfordert oft die Integration visueller Datendarstellungen wie Diagramme, um das Verständnis und die Einbindung des Publikums zu verbessern. Wenn Sie Entwickler sind und Ihre .NET-Präsentationen mit Aspose.Slides für Java um dynamische, anpassbare Diagramme erweitern möchten, ist dieses Tutorial genau das Richtige für Sie. Wir zeigen Ihnen, wie Sie Präsentationen initialisieren, verschiedene Diagrammtypen hinzufügen, Diagrammdaten verwalten und Seriendaten effektiv formatieren.
**Was Sie lernen werden:**
- So richten Sie Aspose.Slides für Java in Ihrer .NET-Umgebung ein und verwenden es.
- Initialisieren einer neuen Präsentation mit Aspose.Slides.
- Hinzufügen und Anpassen von Diagrammen in Folien.
- Verwalten von Arbeitsmappen mit Diagrammdaten.
- Formatieren von Seriendaten, insbesondere Umgang mit negativen Werten.
Durch den Übergang zum Abschnitt „Voraussetzungen“ wird sichergestellt, dass Sie problemlos weitermachen können.
## Voraussetzungen
Bevor wir uns in die Erstellung von Diagrammen mit Aspose.Slides für Java stürzen, wollen wir kurz skizzieren, was Sie benötigen:
### Erforderliche Bibliotheken und Versionen
Stellen Sie sicher, dass Sie über die folgenden Abhängigkeiten verfügen:
- **Aspose.Slides für Java**: Version 25.4 oder höher.
### Anforderungen für die Umgebungseinrichtung
- Eine Entwicklungsumgebung, die .NET-Anwendungen unterstützt.
- Grundlegendes Verständnis der Konzepte der Java-Programmierung.
### Voraussetzungen
- Vertrautheit mit der Erstellung von Präsentationen im Kontext einer .NET-Anwendung.
- Verstehen von Java-Abhängigkeiten und deren Verwaltung (Maven/Gradle).
## Einrichten von Aspose.Slides für Java
Um Aspose.Slides verwenden zu können, müssen Sie es als Abhängigkeit in Ihr Projekt einbinden. So geht's:
### Maven
Fügen Sie die folgende Abhängigkeit zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Nehmen Sie dies in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Direkter Download
Alternativ können Sie die neueste Version herunterladen von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).
#### Schritte zum Lizenzerwerb
- **Kostenlose Testversion**: Beginnen Sie mit einer temporären Lizenz, um die Funktionen zu erkunden.
- **Kaufen**Erwägen Sie den Kauf einer Lizenz für eine umfassende Nutzung.
#### Grundlegende Initialisierung und Einrichtung
So initialisieren Sie Aspose.Slides in Ihrem Code:
```java
import com.aspose.slides.Presentation;
// Initialisieren Sie ein neues Präsentationsobjekt
Presentation pres = new Presentation();
try {
    // Ihre Logik hier ...
} finally {
    if (pres != null) pres.dispose();
}
```
Diese Konfiguration stellt sicher, dass die Ressourcenverwaltung effektiv gehandhabt wird.
## Implementierungshandbuch
Wir führen Sie Schritt für Schritt durch die Implementierung der Funktionen.
### Präsentation wird initialisiert
**Überblick:**
Das Erstellen einer Präsentationsinstanz bildet die Grundlage für alle nachfolgenden Vorgänge. Diese Funktion zeigt, wie Sie mit Aspose.Slides von Grund auf neu beginnen.
#### Schritt 1: Erforderliche Pakete importieren
```java
import com.aspose.slides.Presentation;
```
#### Schritt 2: Erstellen Sie ein neues Präsentationsobjekt
So geht's:
```java
Presentation pres = new Presentation();
try {
    // Ihre Codelogik hier ...
} finally {
    if (pres != null) pres.dispose(); // Stellt sicher, dass Ressourcen freigegeben werden
}
```
*Dadurch wird sichergestellt, dass das Präsentationsobjekt nach der Verwendung ordnungsgemäß entsorgt wird, wodurch Speicherlecks vermieden werden.*
### Diagramm zur Folie hinzufügen
**Überblick:**
Durch Hinzufügen eines Diagramms zu Ihrer Folie können Sie die Datenvisualisierung effektiver und ansprechender gestalten.
#### Schritt 1: Erforderliche Pakete importieren
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

    // Zusätzliche Logik zur Diagrammanpassung ...
} finally {
    if (pres != null) pres.dispose();
}
```
*Hier fügen wir der ersten Folie an den angegebenen Koordinaten und Abmessungen ein gruppiertes Säulendiagramm hinzu.*
### Arbeitsmappe „Diagrammdaten verwalten“
**Überblick:**
Durch die effiziente Verwaltung der Datenarbeitsmappe Ihres Diagramms können Sie Reihen und Kategorien nahtlos bearbeiten.
#### Schritt 1: Erforderliche Pakete importieren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### Schritt 2: Auf die Datenarbeitsmappe zugreifen und sie löschen
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Vorhandene Daten löschen
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Ihre Anpassungslogik hier ...
} finally {
    if (pres != null) pres.dispose();
}
```
*Das Leeren der Arbeitsmappe ist entscheidend, um beim Hinzufügen neuer Serien und Kategorien mit einem sauberen Blatt beginnen zu können.*
### Hinzufügen von Serien und Kategorien zum Diagramm
**Überblick:**
Diese Funktion zeigt, wie Sie durch die Verwaltung von Reihen und Kategorien aussagekräftige Datenpunkte hinzufügen können.
#### Schritt 1: Serien und Kategorien hinzufügen
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Vorhandene Serien und Kategorien löschen
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Neue Serien und Kategorien hinzufügen
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Weitere Anpassungslogik ...
} finally {
    if (pres != null) pres.dispose();
}
```
*Durch das Hinzufügen von Reihen und Kategorien können die Daten besser organisiert präsentiert werden.*
### Auffüllen und Formatieren von Seriendaten
**Überblick:**
Füllen Sie Ihr Diagramm mit Datenpunkten und formatieren Sie die Darstellung, um die Lesbarkeit zu verbessern, insbesondere bei negativen Werten.
#### Schritt 1: Seriendaten auffüllen
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

    // Serien und Kategorien hinzufügen (vorherige Logik wiederverwenden)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Formatieren Sie Reihen für negative Werte
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

    // Speichern der Präsentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*In diesem Abschnitt wird gezeigt, wie Sie Daten auffüllen und Farbformatierungen zur besseren Visualisierung anwenden.*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
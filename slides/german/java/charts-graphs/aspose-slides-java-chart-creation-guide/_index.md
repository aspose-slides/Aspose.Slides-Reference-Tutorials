---
date: '2026-01-14'
description: Erfahren Sie, wie Sie ein gruppiertes Säulendiagramm in Java mit Aspose.Slides
  erstellen. Schritt‑für‑Schritt‑Anleitung, die eine leere Präsentation, das Hinzufügen
  eines Diagramms zur Präsentation und die Verwaltung von Serien abdeckt.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Wie man ein gruppiertes Säulendiagramm in Java mit Aspose.Slides erstellt
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Meisterung der Diagrammerstellung in Java mit Aspose.Slides

## Wie man Diagramme mit Aspose.Slides für Java erstellt und verwaltet

### Einleitung
Das Erstellen dynamischer Präsentationen beinhaltet häufig die Visualisierung von Daten mittels Diagrammen. Mit **Aspose.Slides for Java** können Sie mühelos **ein gruppiertes Säulendiagramm erstellen** und verschiedene Diagrammtypen verwalten, wodurch sowohl Klarheit als auch Wirkung verbessert werden. Dieses Tutorial führt Sie durch das Erstellen einer leeren Präsentation, das Hinzufügen eines gruppierten Säulendiagramms, das Verwalten von Serien und das Anpassen der Invertierung von Datenpunkten – alles mit Aspose.Slides for Java.

**Was Sie lernen werden:**
- Wie man Aspose.Slides für Java einrichtet.
- Schritte zum **Erstellen einer leeren Präsentation** und Hinzufügen eines Diagramms zur Präsentation.
- Techniken zum effektiven Verwalten von Diagrammserien und Datenpunkten.
- Methoden zum bedingten Invertieren negativer Datenpunkte für eine bessere Visualisierung.
- Wie man die Präsentation sicher speichert.

Lassen Sie uns zunächst die Voraussetzungen durchgehen, bevor wir beginnen.

## Schnelle Antworten
- **Welche Klasse ist die primäre Einstiegsklasse?** `Presentation` aus `com.aspose.slides`.
- **Welcher Diagrammtyp erzeugt ein gruppiertes Säulendiagramm?** `ChartType.ClusteredColumn`.
- **Wie fügt man ein Diagramm zu einer Folie hinzu?** Verwenden Sie `addChart()` in der Shape‑Collection der Folie.
- **Können Sie negative Werte invertieren?** Ja, mit `invertIfNegative(true)` an einem Datenpunkt.
- **Welche Version wird benötigt?** Aspose.Slides for Java 25.4 oder neuer.

## Was ist ein gruppiertes Säulendiagramm?
Ein gruppiertes Säulendiagramm zeigt mehrere Datenserien nebeneinander für jede Kategorie und ist damit ideal zum Vergleich von Werten über Gruppen hinweg. Aspose.Slides ermöglicht es Ihnen, dieses Diagramm programmgesteuert zu erzeugen, ohne PowerPoint zu öffnen.

## Warum Aspose.Slides für Java verwenden, um ein Diagramm zur Präsentation hinzuzufügen?
- **Vollständige Kontrolle** über Diagrammdaten, Aussehen und Layout.
- **Keine Office-Installation** auf dem Server erforderlich.
- **Unterstützt alle gängigen Diagrammtypen**, einschließlich gruppierter Säulendiagramme.
- **Einfache Integration** mit Maven/Gradle-Builds.

## Voraussetzungen
Bevor Sie starten, stellen Sie sicher, dass Sie Folgendes haben:

1. **Erforderliche Bibliotheken:**  
   - Aspose.Slides for Java (Version 25.4 oder neuer).

2. **Umgebungsanforderungen:**  
   - Eine kompatible JDK-Version (z. B. JDK 16).  
   - Maven oder Gradle installiert, falls Sie die Abhängigkeitsverwaltung bevorzugen.

3. **Wissensvoraussetzungen:**  
   - Grundlegendes Verständnis der Java-Programmierung.  
   - Vertrautheit mit dem Umgang mit Abhängigkeiten in Ihrer Entwicklungsumgebung.

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides zu nutzen, folgen Sie diesen Schritten:

**Maven-Installation:**  
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle-Installation:**  
Fügen Sie die folgende Zeile zu Ihrem `build.gradle` hinzu:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download:**  
Laden Sie alternativ die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

### Lizenzbeschaffung
- **Kostenlose Testversion:** Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen zu erkunden.  
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz für vollen Zugriff während Ihrer Evaluierungsphase.  
- **Kauf:** Erwägen Sie den Kauf, wenn es Ihren langfristigen Anforderungen entspricht.

### Grundlegende Initialisierung
Nachfolgend finden Sie den minimalen Code, der erforderlich ist, um eine neue Präsentationsinstanz zu erstellen:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Implementierungsleitfaden
Nun teilen wir jede Funktion in handhabbare Schritte auf.

### Erstellen einer Präsentation mit einem gruppierten Säulendiagramm
#### Übersicht
Dieser Abschnitt zeigt, wie man eine **leere Präsentation erstellt**, ein **gruppiertes Säulendiagramm hinzufügt** und es auf der ersten Folie positioniert.

**Schritte:**
1. **Initialisieren des Presentation‑Objekts** – erstellen Sie ein neues `Presentation`.  
2. **Hinzufügen eines gruppierten Säulendiagramms** – rufen Sie `addChart()` mit dem entsprechenden Typ und den Abmessungen auf.

**Code‑Beispiel:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Verwalten von Diagrammserien
#### Übersicht
Erfahren Sie, wie Sie vorhandene Standardserien löschen, eine neue Serie hinzufügen und sie mit positiven sowie negativen Werten füllen.

**Schritte:**
1. **Vorhandene Serien löschen** – entfernen Sie alle vorab gefüllten Daten.  
2. **Neue Serie hinzufügen** – verwenden Sie die Arbeitsmappen‑Zelle als Seriennamen.  
3. **Datenpunkte einfügen** – fügen Sie Werte, einschließlich negativer, hinzu, um später die Invertierung zu demonstrieren.

**Code‑Beispiel:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Invertieren von Serien‑Datenpunkten basierend auf Bedingungen
#### Übersicht
Standardmäßig kann Aspose.Slides negative Werte invertieren. Sie können dieses Verhalten global und pro Datenpunkt steuern.

**Schritte:**
1. **Globale Invertierung festlegen** – deaktivieren Sie die automatische Invertierung für die gesamte Serie.  
2. **Bedingte Invertierung anwenden** – aktivieren Sie die Invertierung nur für bestimmte negative Punkte.

**Code‑Beispiel:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Häufige Probleme und Lösungen
| Problem | Lösung |
|-------|----------|
| Diagramm erscheint leer | Stellen Sie sicher, dass der Folien‑Index (`0`) existiert und die Diagramm‑Abmessungen innerhalb der Folien‑Grenzen liegen. |
| Negative Werte nicht invertiert | Vergewissern Sie sich, dass `invertIfNegative(false)` für die Serie gesetzt ist und `invertIfNegative(true)` für den jeweiligen Datenpunkt. |
| Lizenz‑Ausnahme | Wenden Sie eine gültige Aspose‑Lizenz an, bevor Sie das `Presentation`‑Objekt erstellen. |

## Häufig gestellte Fragen

**Q: Kann ich neben dem gruppierten Säulendiagramm auch andere Diagrammtypen hinzufügen?**  
A: Ja, Aspose.Slides unterstützt Linien-, Kreis-, Balken-, Flächen‑ und viele weitere Diagrammtypen.

**Q: Benötige ich eine Lizenz für die Entwicklung?**  
A: Eine kostenlose Testversion reicht für die Evaluierung, aber für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.

**Q: Wie exportiere ich das Diagramm als Bild?**  
A: Verwenden Sie nach dem Rendern `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Ist es möglich, das Diagramm zu stylen (Farben, Schriftarten)?**  
A: Absolut. Jede `IChartSeries` und `IChartDataPoint` bietet Styling‑Eigenschaften.

**Q: Was, wenn ich ein Diagramm zu einer bestehenden PPTX‑Datei hinzufügen möchte?**  
A: Laden Sie die Datei mit `new Presentation("existing.pptx")` und fügen Sie das Diagramm dann der gewünschten Folie hinzu.

## Fazit
In diesem Tutorial haben Sie gelernt, wie man ein **gruppiertes Säulendiagramm** in Java erstellt, Serien verwaltet und negative Datenpunkte bedingt invertiert – alles mit Aspose.Slides. Mit diesen Techniken können Sie programmgesteuert überzeugende, datenbasierte Präsentationen erstellen.

**Nächste Schritte:**
- Experimentieren Sie mit anderen von Aspose.Slides für Java angebotenen Diagrammtypen.  
- Tauchen Sie ein in erweiterte Stiloptionen wie benutzerdefinierte Farben, Datenbeschriftungen und Achsenformatierung.  
- Integrieren Sie die Diagrammerstellung in Ihre Reporting‑ oder Analyse‑Pipelines.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
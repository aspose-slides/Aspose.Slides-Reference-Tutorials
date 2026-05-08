---
date: '2026-02-17'
description: Erfahren Sie, wie Sie ein Donut‑Diagramm in PowerPoint mit Aspose.Slides
  für Java erstellen und Diagrammdatenpunkte programmgesteuert hinzufügen. Folgen
  Sie einfachen Schritten und Codebeispielen.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Erstellen Sie ein Donut‑Diagramm in PowerPoint mit Aspose.Slides für Java
url: /de/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Donut‑Diagramm PowerPoint mit Aspose.Slides für Java erstellen

## Einführung
Ansprechende Präsentationen zu erstellen erfordert oft mehr als nur Text und Bilder; Diagramme können das Storytelling erheblich verbessern, indem sie Daten effektiv visualisieren. Viele Entwickler haben jedoch Schwierigkeiten, dynamische Diagrammfunktionen programmgesteuert in PowerPoint‑Dateien zu integrieren. Dieses Tutorial zeigt, wie man **ein Donut‑Diagramm in PowerPoint** mit Aspose.Slides für Java erstellt – ein leistungsstarkes Werkzeug, das Flexibilität und Benutzerfreundlichkeit kombiniert.

**Was Sie lernen werden:**
- Wie man eine Präsentation mit Aspose.Slides für Java initialisiert
- Eine Schritt‑für‑Schritt‑Anleitung zum Hinzufügen eines Donut‑Diagramms zu Ihren Folien
- Konfigurieren von Datenpunkten und Anpassen von Beschriftungseigenschaften
- Speichern der modifizierten Präsentation mit hoher Treue

Lassen Sie uns erkunden, wie Sie diese Funktionen nutzen können, um Ihre Präsentationen zu verbessern. Bevor wir beginnen, stellen Sie sicher, dass Sie mit den grundlegenden Konzepten der Java‑Programmierung vertraut sind.

## Schnelle Antworten
- **Welche Bibliothek erstellt ein Donut‑Diagramm in PowerPoint?** Aspose.Slides für Java
- **Kann ich Diagrammdatenpunkte programmgesteuert hinzufügen?** Ja, über die Chart‑API
- **Benötige ich eine Lizenz für die Produktion?** Eine gültige Aspose.Slides‑Lizenz ist erforderlich
- **Welche Java‑Versionen werden unterstützt?** Java 8 und höher (JDK 16‑Classifier angezeigt)
- **Wie viele Serien kann ich hinzufügen?** Das Beispiel fügt bis zu 15 Serien hinzu, Sie können jedoch nach Bedarf anpassen

## Was ist ein Donut‑Diagramm in PowerPoint?
Ein Donut‑Diagramm ist eine Variante eines Kreisdiagramms mit einem hohlen Zentrum, das Ihnen ermöglicht, mehrere Datenreihen kompakt und ansprechend darzustellen. Es ist ideal, um Teil‑zu‑Ganz‑Beziehungen zu zeigen, während das Design sauber bleibt.

## Warum Aspose.Slides für Java zum Erstellen von Donut‑Diagrammen verwenden?
- **Vollständige Kontrolle** über das Aussehen, die Daten und das Layout des Diagramms, ohne PowerPoint zu öffnen
- **Kein COM‑Interop** – funktioniert auf jeder Plattform, die Java unterstützt
- **Hohe Leistung** beim Erzeugen großer Präsentationen oder der Integration mit Webdiensten
- **Umfangreiche Anpassungen** wie Explosions‑Effekt, Lochgröße, Segmentwinkel und Beschriftungsformatierung

## Voraussetzungen
- Grundkenntnisse der Java‑Programmierung.
- Eine IDE wie IntelliJ IDEA oder Eclipse.
- Maven oder Gradle für das Abhängigkeitsmanagement.
- Eine gültige Aspose.Slides für Java Lizenz (kostenlose Testversion verfügbar).

## Einrichtung von Aspose.Slides für Java
Wählen Sie den Abhängigkeitsmanager, der zu Ihrem Projekt passt.

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

Wenn Sie lieber direkt herunterladen, besuchen Sie die Seite [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lizenzbeschaffung
Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides zu erkunden. Für den erweiterten Einsatz erwerben Sie eine Lizenz oder fordern Sie eine temporäre Lizenz von der [Aspose-Website](https://purchase.aspose.com/temporary-license/) an. Befolgen Sie die bereitgestellten Anweisungen, um Ihre Umgebung einzurichten und Aspose.Slides in Ihrer Anwendung zu initialisieren.

## Wie man ein Donut‑Diagramm in PowerPoint mit Aspose.Slides für Java erstellt
Im Folgenden finden Sie eine vollständige Schritt‑für‑Schritt‑Anleitung. Jeder Codeblock wird direkt davor erklärt, sodass Sie genau wissen, was passiert.

### Schritt 1: Präsentation initialisieren
Laden Sie zunächst ein vorhandenes PPTX oder erstellen Sie ein neues. Dadurch wird die Folienkollektion für weitere Änderungen vorbereitet.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Schritt 2: Donut‑Diagramm zur Folie hinzufügen
Wir fügen die Diagrammform hinzu, entfernen alle Standard‑Serien/Kategorien und setzen grundlegende visuelle Eigenschaften.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Schritt 3: Diagrammdatenpunkte hinzufügen und Beschriftungen anpassen
Hier füllen wir die Kategorien, fügen für jede Serie Datenpunkte hinzu und verfeinern das Aussehen der Beschriftungen. Hier kommt das Schlüsselwort **add chart data points** zum Einsatz.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Schritt 4: Aktualisierte Präsentation speichern
Abschließend speichern Sie die Änderungen in einer neuen PPTX‑Datei.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Praktische Anwendungsfälle
- **Finanzberichte:** Budgetzuweisungen oder Ausgabenaufstellungen visualisieren.
- **Marktanalyse:** Marktanteilsverteilung unter Wettbewerbern anzeigen.
- **Umfrageergebnisse:** Kategorische Umfragedaten kompakt darstellen.
- **Dashboard-Erstellung:** Mit Datenbankabfragen kombinieren, um Live‑Aktualisierungs‑Folien zu erzeugen.

## Leistungsüberlegungen
- **Ressourcen freigeben**: Rufen Sie `pres.dispose()` auf, wenn Sie fertig sind, um nativen Speicher freizugeben.
- **Diagrammzahl begrenzen**: Das Hinzufügen von Hunderten von Diagrammen kann den Speicherverbrauch erhöhen; bei Bedarf stapelweise verarbeiten.
- **Streaming verwenden**: Bei sehr großen Datensätzen das Arbeitsbuch direkt aus Streams füllen statt aus In‑Memory‑Arrays.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| **Diagramm erscheint leer** | Datenzellen nicht korrekt gefüllt | Überprüfen Sie, dass `workBook.getCell(...)` die richtigen Zeilen‑/Spaltenindizes referenziert. |
| **Beschriftungen überlappen** | Zu viele Kategorien bei begrenztem Platz | Erhöhen Sie `DoughnutHoleSize` oder passen Sie `FirstSliceAngle` an. |
| **OutOfMemoryError** | Große Präsentationen ohne Freigabe | Rufen Sie `pres.dispose()` nach dem Speichern auf und erwägen Sie, den JVM‑Heap zu vergrößern. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Slides für Java in kommerziellen Anwendungen verwenden?**  
A: Ja, Sie benötigen jedoch eine gültige kommerzielle Lizenz. Eine kostenlose Testversion steht zur Evaluierung bereit.

**F: Wie füge ich mehr als 15 Serien hinzu?**  
A: Erhöhen Sie das Schleifenlimit im Schritt „Add Doughnut Chart“ und stellen Sie sicher, dass Ihr Daten‑Workbook genügend Zeilen enthält.

**F: Ist es möglich, die Lochgröße des Donut‑Diagramms nach der Erstellung zu ändern?**  
A: Ja, rufen Sie `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` jederzeit vor dem Speichern auf.

**F: Kann ich das Diagramm als Bild statt als PPTX exportieren?**  
A: Natürlich. Verwenden Sie `chart.getImage()` und speichern Sie das zurückgegebene `java.awt.image.BufferedImage` in Ihrem bevorzugten Format.

**F: Unterstützt Aspose.Slides animierte Diagramme?**  
A: Animationen können über die `ISlide.getTimeline()`‑API hinzugefügt werden, jedoch liegt das außerhalb des Umfangs dieses Tutorials.

## Fazit
Sie haben nun eine vollständige, produktionsreife Methode, um **Donut‑Diagramm‑PowerPoint**‑Dateien mit Aspose.Slides für Java zu **erstellen**, einschließlich des **Hinzufügens von Diagrammdatenpunkten**, der Anpassung von Beschriftungen und der Berücksichtigung von Leistungsaspekten. Experimentieren Sie mit verschiedenen Farben, Datenquellen und Diagrammtypen, um Ihre Präsentationen wirklich hervorzuheben.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
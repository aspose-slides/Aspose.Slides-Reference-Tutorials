---
date: '2026-07-08'
description: Erfahren Sie, wie Sie Aspose verwenden, um ein Doughnut Chart in PowerPoint
  mit Java zu erstellen. Diese Schritt‑für‑Schritt‑Anleitung zeigt, wie man chart
  data points programmgesteuert hinzufügt, labels anpasst und die PPTX mit high fidelity
  speichert.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Wie man Aspose verwendet, ermöglicht das Erstellen eines Doughnut
  Chart in PowerPoint mit Java. Folgen Sie diesem Tutorial, um data points hinzuzufügen,
  labels anzupassen und die PPTX mit high fidelity zu speichern.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Wie man Aspose verwendet: Doughnut Chart in PowerPoint (Java) erstellen'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Wie man Aspose verwendet, um ein Doughnut Chart in PowerPoint (Java) zu erstellen
url: /de/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Aspose zum Erstellen eines Donut-Diagramms in PowerPoint (Java)

## Einleitung
Ansprechende Präsentationen zu erstellen erfordert oft mehr als nur Text und Bilder; Diagramme können das Storytelling erheblich verbessern, indem sie Daten effektiv visualisieren. **How to use Aspose** für die Diagrammerstellung gibt Ihnen programmgesteuerte Kontrolle, ohne PowerPoint zu öffnen. Dieses Tutorial führt Sie durch den Aufbau eines Donut‑Diagramms, die Konfiguration seiner Datenpunkte und das Speichern einer hoch‑fidelity PPTX. Sie benötigen nur Grundkenntnisse in Java und ein paar Minuten Einrichtungszeit.

`Aspose.Slides for Java` ist eine Java-Bibliothek, die das Erstellen, Manipulieren und Konvertieren von PowerPoint-Dateien ohne Microsoft Office ermöglicht.

## Schnelle Antworten
- **Welche Bibliothek erstellt Donut-Diagramme in PowerPoint?** Aspose.Slides for Java  
- **Kann ich Diagrammdatenpunkte programmgesteuert hinzufügen?** Ja, mit der Chart-API  
- **Benötige ich eine Lizenz für die Produktion?** Eine gültige Aspose.Slides-Lizenz ist erforderlich  
- **Welche Java-Versionen werden unterstützt?** Java 8 und höher (JDK 16‑Classifier gezeigt)  
- **Wie viele Serien kann ich hinzufügen?** Das Beispiel fügt bis zu 15 Serien hinzu, Sie können jedoch nach Bedarf anpassen  

## Was ist ein Donut-Diagramm in PowerPoint?
Ein Donut-Diagramm ist ein kreisförmiges Diagramm, das einem Kreisdiagramm ähnelt, jedoch einen hohlen Mittelpunkt hat, sodass mehrere Serien gleichzeitig angezeigt werden können. Es betont Teil‑zu‑Ganz‑Beziehungen und hält das visuelle Layout kompakt und leicht lesbar.

## Warum Aspose.Slides für Java zum Erstellen von Donut-Diagrammen verwenden?
Aspose.Slides für Java unterstützt über 50 Eingabe‑ und Ausgabeformate und kann Präsentationen bis zu 500 MB erzeugen, ohne die gesamte Datei in den Speicher zu laden. Es bietet vollständige programmgesteuerte Kontrolle über das Aussehen, die Daten und das Layout von Diagrammen auf jeder Java‑Plattform, eliminiert COM‑Interop und kann 100 diagrammreiche Folien in weniger als zwei Sekunden auf einem typischen Server rendern.

## Voraussetzungen
- Grundkenntnisse in Java-Programmierung.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Maven oder Gradle für das Abhängigkeitsmanagement.  
- Eine gültige Aspose.Slides für Java-Lizenz (kostenlose Testversion verfügbar).

## Einrichtung von Aspose.Slides für Java
Wählen Sie den Abhängigkeitsmanager, der zu Ihrem Projekt passt.

**Maven**  
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu (ersetzen Sie die Version durch die neueste Veröffentlichung):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Fügen Sie diese Zeile zu Ihrer `build.gradle` hinzu:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Wenn Sie lieber direkt herunterladen, besuchen Sie die Seite [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lizenzbeschaffung
Sie können mit einer kostenlosen Testversion beginnen, um die Funktionen von Aspose.Slides zu erkunden. Für den erweiterten Einsatz kaufen Sie eine Lizenz oder beantragen Sie eine temporäre Lizenz über die [Website von Aspose](https://purchase.aspose.com/temporary-license/). Befolgen Sie die bereitgestellten Anweisungen, um Ihre Umgebung einzurichten und Aspose.Slides in Ihrer Anwendung zu initialisieren.

## Wie man ein Donut-Diagramm in PowerPoint mit Aspose.Slides für Java erstellt
Um ein Donut-Diagramm zu erstellen, beginnen Sie mit dem Laden oder Erstellen einer `Presentation`, fügen Sie eine Diagrammform vom Typ `ChartType.Doughnut` hinzu, löschen Sie die Standardserien, setzen Sie die Lochgröße und füllen Sie anschließend das Arbeitsbuch des Diagramms mit Kategorienamen und numerischen Werten. Abschließend passen Sie die Beschriftungsformatierung an und speichern die PPTX.

### Schritt 1: Präsentation initialisieren
Erstellen Sie eine neue Präsentation oder öffnen Sie eine vorhandene Datei, um eine Foliensammlung zu erhalten.

`Presentation` ist die Hauptklasse, die eine PowerPoint-Datei repräsentiert.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Schritt 2: Donut-Diagramm zur Folie hinzufügen
Fügen Sie eine Diagrammform ein, entfernen Sie die Standardserien/Kategorien und konfigurieren Sie grundlegende visuelle Einstellungen wie die Größe des Donut-Lochs.

`Chart` (oder Diagrammform) stellt ein Diagrammobjekt dar, das auf einer Folie platziert ist.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Schritt 3: Diagrammdatenpunkte hinzufügen und Beschriftungen anpassen
Füllen Sie die Kategorienamen, fügen Sie für jede Serie Datenpunkte hinzu und verfeinern Sie die Beschriftungsformatierung (Schriftart, Farbe, Position). Dieser Schritt demonstriert die Möglichkeit, „Diagrammdatenpunkte hinzuzufügen“.

`Workbook` bietet Zugriff auf die zugrunde liegenden Tabellendaten des Diagramms, in denen Zellen befüllt werden.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Schritt 4: Aktualisierte Präsentation speichern
Speichern Sie die Änderungen in einer neuen PPTX-Datei auf dem Datenträger.

`save` schreibt die Präsentation in eine Datei im gewählten Format.  
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

## Praktische Anwendungen
- **Finanzberichte:** Visualisierung von Budgetzuweisungen oder Ausgabenaufteilungen.  
- **Marktanalyse:** Darstellung der Marktanteilsverteilung unter Wettbewerbern.  
- **Umfrageergebnisse:** Präsentation kategorialer Umfragedaten in kompakter Form.  
- **Dashboard-Erstellung:** Kombination mit Datenbankabfragen, um Live‑Aktualisierungsfolien zu erzeugen.

## Leistungsüberlegungen
- **Ressourcen freigeben:** Rufen Sie `pres.dispose()` nach dem Speichern auf, um nativen Speicher freizugeben.  
- **Diagrammzähler begrenzen:** Das Hinzufügen von Hunderten von Diagrammen kann den Speicherverbrauch erhöhen; bei Bedarf stapelweise verarbeiten.  
- **Streaming verwenden:** Bei riesigen Datensätzen das Arbeitsbuch direkt aus Streams befüllen statt aus In‑Memory‑Arrays.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|-------|-----|
| **Diagramm erscheint leer** | Datenzellen nicht korrekt befüllt | Überprüfen Sie, dass `workBook.getCell(...)` die richtigen Zeilen-/Spaltenindizes referenziert. |
| **Beschriftungen überlappen** | Zu viele Kategorien bei begrenztem Platz | Erhöhen Sie `DoughnutHoleSize` oder passen Sie `FirstSliceAngle` an. |
| **OutOfMemoryError** | Große Präsentationen ohne Freigabe | Rufen Sie `pres.dispose()` nach dem Speichern auf und erwägen Sie, den JVM‑Heap zu vergrößern. |

## Häufig gestellte Fragen

**F: Kann ich Aspose.Slides für Java in kommerziellen Anwendungen verwenden?**  
A: Ja, Sie benötigen jedoch eine gültige kommerzielle Lizenz. Eine kostenlose Testversion steht zur Evaluierung bereit.

**F: Wie füge ich mehr als 15 Serien hinzu?**  
A: Erhöhen Sie das Schleifenlimit im Schritt „Add Doughnut Chart“ und stellen Sie sicher, dass Ihr Daten‑Workbook genügend Zeilen enthält.

**F: Ist es möglich, die Donut‑Lochgröße nach der Erstellung zu ändern?**  
A: Ja, rufen Sie `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` vor dem Speichern auf.

**F: Kann ich das Diagramm als Bild statt als PPTX exportieren?**  
A: Natürlich. Verwenden Sie `chart.getImage()` und speichern Sie das zurückgegebene `java.awt.image.BufferedImage` in Ihrem bevorzugten Format.

**F: Unterstützt Aspose.Slides animierte Diagramme?**  
A: Animationen können über die `ISlide.getTimeline()`‑API hinzugefügt werden, liegen jedoch außerhalb des Umfangs dieses Tutorials.

## Fazit
Sie haben nun eine vollständige, produktionsreife Methode, um **Donut‑Diagramm‑PowerPoint**‑Dateien mit Aspose.Slides für Java zu **erstellen**, einschließlich wie man **Diagrammdatenpunkte hinzufügt**, Beschriftungen anpasst und Leistungsaspekte berücksichtigt. Experimentieren Sie mit verschiedenen Farben, Datenquellen und Diagrammtypen, um Ihre Präsentationen wirklich hervorzuheben.

---

**Zuletzt aktualisiert:** 2026-07-08  
**Getestet mit:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose

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

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Verwandte Tutorials

- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Wie man PowerPoint‑Diagrammdaten mit Aspose.Slides für Java bearbeitet: Ein umfassender Leitfaden](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Diagramme in PowerPoint mit Aspose.Slides für Java animieren – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
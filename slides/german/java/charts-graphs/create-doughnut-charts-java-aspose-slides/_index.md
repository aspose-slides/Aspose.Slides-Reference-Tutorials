---
date: '2026-03-07'
description: Erfahren Sie, wie Sie ein Donut‑Diagramm in Java mit Aspose.Slides erstellen.
  Diese Schritt‑für‑Schritt‑Anleitung behandelt die Einrichtung der Maven‑Aspose‑Slides‑Abhängigkeit,
  die Diagrammkonfiguration und das Speichern von Präsentationen.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Donut-Diagramm in Java mit Aspose.Slides erstellen – Anleitung
url: /de/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Donut-Diagrammen in Java mit Aspose.Slides Leitfaden

## Einführung

Das programmatische Erstellen eines **doughnut chart** kann Rohdaten in eine auffällige Visualisierung verwandeln, die sofort eine Geschichte erzählt. In Java macht **Aspose.Slides** diesen Prozess einfach, sodass Sie präsentationsfertige Diagramme erzeugen können, ohne PowerPoint zu öffnen. In diesem Tutorial lernen Sie, wie man **create doughnut chart java** Schritt für Schritt erstellt – von der Einrichtung der Maven Aspose Slides‑Abhängigkeit über die Anpassung von Serien, Kategorien bis hin zum Speichern der Präsentation.

Am Ende dieses Leitfadens können Sie dynamische doughnut charts in jede PPTX‑Datei einbetten, ideal für Berichte, Dashboards oder automatisierte Folienpräsentationen.

### Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Slides for Java  
- **Primäre Aufgabe?** Create doughnut chart java in a PPTX file  
- **Wie fügt man die Bibliothek hinzu?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Mindest‑Java‑Version?** JDK 16 oder höher  
- **Kann ich Farben und Beschriftungen anpassen?** Yes, the API provides full formatting control  

## Was ist ein Doughnut‑Diagramm und warum es verwenden?

Ein doughnut chart ist eine Variante eines Kreisdiagramms mit einem leeren Zentrum, das es ermöglicht, mehrere Datenserien in konzentrischen Ringen darzustellen. Das macht es ideal, um Anteile eines Ganzen über mehrere Kategorien hinweg zu vergleichen – denken Sie an Verkäufe nach Region über mehrere Quartale oder Budgetzuweisungen nach Abteilungen.

## Warum Aspose.Slides für Java verwenden?

- **Keine Office‑Installation erforderlich** – PPTX‑Dateien auf jedem Server erzeugen.  
- **Umfangreiche API** – volle Kontrolle über Diagrammtypen, Datenpunkte und Styling.  
- **Hohe Leistung** – optimiert für große Präsentationen.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS.

## Voraussetzungen

- **Erforderliche Bibliotheken:**  
  - Aspose.Slides for Java Version 25.4 oder höher.  

- **Umgebungs‑Setup:**  
  - JDK 16 oder höher.  
  - Ihre bevorzugte IDE (IntelliJ IDEA, Eclipse, NetBeans usw.).  

- **Vorkenntnisse:**  
  - Grundlegende Java‑Programmierung.  
  - Vertrautheit mit Maven oder Gradle für das Abhängigkeitsmanagement.

## Maven Aspose Slides Abhängigkeit

Fügen Sie die folgende Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu. Dies ist die **maven aspose slides dependency**, die Sie benötigen, um die Bibliothek in Ihr Projekt zu übernehmen.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Wenn Sie Gradle bevorzugen, verwenden Sie das entsprechende Snippet unten.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sie können das JAR auch direkt von der offiziellen Release‑Seite herunterladen:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Lizenz erwerben

Um das Evaluations‑Wasserzeichen zu entfernen und den vollen Funktionsumfang freizuschalten:

- **Kostenlose Testversion** – mit einer temporären Lizenz beginnen.  
- **Temporäre Lizenz** – eine von der [Aspose‑Website](https://purchase.aspose.com/temporary-license/) anfordern.  
- **Kommerzielle Lizenz** – für den Produktionseinsatz erwerben.

Wenden Sie die Lizenz in Ihrem Code an:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementierungs‑Leitfaden

### Initialisierung der Präsentation und Hinzufügen eines Doughnut‑Diagramms

Zuerst erstellen oder laden Sie eine Präsentation und fügen dem ersten Folie ein doughnut chart hinzu.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfiguration des Diagramm‑Daten‑Workbooks und Löschen vorhandener Daten

Als Nächstes erhalten Sie das Workbook, das dem Diagramm zugrunde liegt, und löschen alle Standard‑Serien oder -Kategorien.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Hinzufügen von Serien zum Diagramm

Jetzt fügen wir bis zu 15 Serien hinzu. Jede Serie kann angepasst werden – hier setzen wir die Explosion, die Größe des doughnut‑Lochs und den Winkel des ersten Segments.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Hinzufügen von Kategorien und Datenpunkten

Wir erstellen 15 Kategorien und füllen jede Serie mit einem Datenpunkt. Die letzte Serie erhält eine spezielle Beschriftungsformatierung.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Speichern der Präsentation

Abschließend schreiben Sie die aktualisierte Präsentation auf die Festplatte.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Häufige Probleme und Lösungen

- **Lizenz nicht gefunden** – Überprüfen Sie, ob der Pfad zu `license.lic` korrekt ist und die Datei lesbar ist.  
- **Diagramm erscheint leer** – Stellen Sie sicher, dass Sie vorhandene Serien/Kategorien gelöscht haben, bevor Sie neue hinzufügen.  
- **Falsche Farben** – Prüfen Sie, ob `FillType.Solid` sowohl für die Füll‑ als auch für die Linienformate gesetzt ist.  
- **Leistung bei vielen Serien** – Begrenzen Sie die Anzahl der Serien/Kategorien oder verwenden Sie die Workbook‑Zellen erneut.

## Häufig gestellte Fragen

**Q: Kann ich ein doughnut chart ohne eine bereits vorhandene PPTX‑Datei erzeugen?**  
A: Ja, instanziieren Sie `new Presentation()`, um mit einem leeren Folien‑Deck zu beginnen.

**Q: Unterstützt Aspose.Slides den Export nach PDF?**  
A: Absolut. Nach dem Erstellen des Diagramms rufen Sie `pres.save("output.pdf", SaveFormat.Pdf);` auf.

**Q: Wie ändere ich die Größe des doughnut‑Lochs?**  
A: Verwenden Sie `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, wobei value 0‑100 ist.

**Q: Ist es möglich, Datenbeschriftungen zu allen Serien hinzuzufügen, nicht nur zur letzten?**  
A: Ja, verschieben Sie den Beschriftungs‑Formatierungsblock außerhalb der Bedingung `if (i == ...)` und wenden Sie ihn auf jeden `dataPoint` an.

**Q: Welche Java‑Versionen werden unterstützt?**  
A: Aspose.Slides 25.4 unterstützt JDK 16 und neuer. Ältere JDKs benötigen den entsprechenden Klassifizierer.

---

**Zuletzt aktualisiert:** 2026-03-07  
**Getestet mit:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
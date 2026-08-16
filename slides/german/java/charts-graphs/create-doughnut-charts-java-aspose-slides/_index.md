---
date: '2026-08-16'
description: Erfahren Sie, wie Sie Donut‑Diagramme in Java mit Aspose.Slides hinzufügen.
  Diese Schritt‑für‑Schritt‑Anleitung behandelt die Einrichtung der Maven‑Abhängigkeit,
  die Diagrammkonfiguration, Farben, Beschriftungen und das Speichern der PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Wie man Donut‑Diagramme in Java mit Aspose.Slides hinzufügt. Folgen
  Sie dieser Anleitung, um Maven einzurichten, Farben und Beschriftungen anzupassen
  und PPTX‑Dateien zu erzeugen.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Wie man ein Donut‑Diagramm in Java mit Aspose.Slides hinzufügt
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Wie man ein Donut‑Diagramm in Java mit Aspose.Slides hinzufügt
url: /de/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Donut‑Diagramm in Java mit Aspose.Slides hinzufügt

## Einleitung

Das programmatische Erstellen eines **Donut‑Diagramms** kann rohe Zahlen in eine auffällige Visualisierung verwandeln, die sofort eine Geschichte erzählt. In Java macht **Aspose.Slides** diesen Prozess unkompliziert und ermöglicht es Ihnen, präsentationsfertige Diagramme zu erzeugen, ohne PowerPoint zu öffnen. In diesem Tutorial lernen Sie **wie man Donut‑Diagramme** zu einer PPTX‑Datei Schritt für Schritt hinzufügt – von der Einrichtung der Maven‑Aspose‑Slides‑Abhängigkeit über die Anpassung von Serien, Kategorien, Farben und Beschriftungen bis hin zum finalen Speichern der Präsentation.

Am Ende dieses Leitfadens können Sie dynamische Donut‑Diagramme in jede PPTX‑Datei einbetten, ideal für Berichte, Dashboards oder automatisierte Folienpräsentationen.

### Schnelle Antworten
- **Welche Bibliothek wird verwendet?** Aspose.Slides for Java  
- **Primäre Aufgabe?** Ein Donut‑Diagramm in einer PPTX‑Datei hinzufügen  
- **Wie fügt man die Bibliothek hinzu?** Verwenden Sie die Maven‑Aspose‑Slides‑Abhängigkeit (oder Gradle)  
- **Mindest‑Java‑Version?** JDK 16 oder höher  
- **Kann ich Farben und Beschriftungen anpassen?** Ja, die API bietet vollständige Formatierungssteuerung  

## Was ist ein Donut‑Diagramm und warum verwenden?

Ein Donut‑Diagramm ist eine Variante eines Kreisdiagramms mit einem leeren Zentrum, das mehrere Datenreihen als konzentrische Ringe darstellen lässt. **Es visualisiert Teile‑eines‑Ganzen über mehrere Kategorien hinweg, während es Platz für zusätzliche Informationen im Zentrum bewahrt.** Das macht es ideal für den Vergleich von Verkäufen nach Region über mehrere Quartale, Budgetzuweisungen nach Abteilungen oder jede Situation, in der hierarchische Proportionen dargestellt werden müssen.

## Warum Aspose.Slides für Java verwenden?

Sie können ein Donut‑Diagramm hinzufügen, ohne Microsoft Office zu installieren, und die Bibliothek verarbeitet **über 50 + Eingabe‑ und Ausgabeformate**, während sie Präsentationen mit mehr als 500 Folien handhabt. Aspose.Slides liefert **bis zu 3‑mal schnellere Render‑Leistung** im Vergleich zur nativen Office‑Automatisierung auf derselben Hardware und funktioniert auf Windows, Linux und macOS. Diese quantifizierten Vorteile bedeuten, dass Sie große Folienpräsentationen auf headless Servern mit vorhersehbarer Leistung erzeugen können.

## Voraussetzungen

- **Erforderliche Bibliotheken**  
  - Aspose.Slides for Java 25.4 oder höher (die Bibliothek, die das Hinzufügen von Donut‑Diagrammen ermöglicht).  

- **Umgebung**  
  - JDK 16 oder höher auf Ihrem Rechner installiert.  
  - Eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans.  

- **Kenntnisse**  
  - Grundlegende Java‑Syntax und objektorientierte Konzepte.  
  - Vertrautheit mit Maven oder Gradle für das Abhängigkeitsmanagement.  

## Maven Aspose Slides‑Abhängigkeit

Fügen Sie die folgende Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu. Dies ist die **Maven‑Aspose‑Slides‑Abhängigkeit**, die Sie benötigen, um die Bibliothek in Ihr Projekt zu integrieren.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Falls Sie Gradle bevorzugen, verwenden Sie das entsprechende Snippet unten.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Sie können das JAR auch direkt von der offiziellen Release‑Seite herunterladen:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Lizenz erwerben

Um das Evaluierungs‑Wasserzeichen zu entfernen und den vollen Funktionsumfang freizuschalten:

- **Kostenlose Testversion** – beginnen Sie mit einer temporären Lizenz.  
- **Temporäre Lizenz** – beantragen Sie eine über die [Aspose‑Website](https://purchase.aspose.com/temporary-license/).  
- **Kommerzielle Lizenz** – erwerben Sie sie für den Produktionseinsatz.  

Wenden Sie die Lizenz in Ihrem Code an:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Implementierungs‑Leitfaden

### Initialisierung einer Präsentation und Hinzufügen eines Donut‑Diagramms

Presentation ist die Aspose.Slides‑Klasse, die eine PowerPoint‑Präsentation repräsentiert.  
Laden Sie eine vorhandene PPTX‑Datei oder erstellen Sie ein neues `Presentation`‑Objekt und fügen Sie dann dem ersten Folie ein Donut‑Diagramm hinzu.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Konfiguration des Diagramm‑Daten‑Workbooks und Löschen vorhandener Daten

Das Workbook ist eine interne Tabelle, die die Diagrammdaten speichert.  
Holen Sie das Workbook, das dem Diagramm zugrunde liegt, und löschen Sie dann alle Standard‑Serien oder -Kategorien, damit Sie mit einer sauberen Basis beginnen können.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Hinzufügen von Serien zum Diagramm

Eine Serie stellt eine Sammlung von Datenpunkten dar, die im Diagramm geplottet werden.  
Sie können bis zu 15 Serien hinzufügen. Jede Serie kann angepasst werden – hier setzen wir die Explosion, die Donut‑Loch‑Größe und den Winkel des ersten Stücks.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Hinzufügen von Kategorien und Datenpunkten

Kategorien sind die Beschriftungen für jeden Datenpunkt entlang der Diagrammachse.  
Erstellen Sie 15 Kategorien und füllen Sie jede Serie mit einem Datenpunkt. Die letzte Serie erhält eine spezielle Beschriftungsformatierung.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Anpassen von Farben und Datenbeschriftungen

`FillType.Solid` gibt eine einfarbige Füllfarbe für Diagrammelemente an.  
Setzen Sie für jede Serie eine einfarbige Füllfarbe und aktivieren Sie Datenbeschriftungen. Für die letzte Serie ändern wir außerdem die Schriftfarbe der Beschriftung.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Speichern der Präsentation

`save` schreibt die Präsentation in eine Datei im gewählten Format.  
Speichern Sie die aktualisierte Präsentation auf dem Datenträger im PPTX‑Format oder exportieren Sie sie bei Bedarf nach PDF.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Häufige Probleme und Lösungen

- **Lizenz nicht gefunden** – Überprüfen Sie, ob der Pfad zu `license.lic` korrekt ist und die Datei lesbar ist.  
- **Diagramm erscheint leer** – Stellen Sie sicher, dass Sie vorhandene Serien/Kategorien gelöscht haben, bevor Sie neue hinzufügen.  
- **Falsche Farben** – Vergewissern Sie sich, dass `FillType.Solid` sowohl für die Füll‑ als auch für die Linienformate gesetzt ist.  
- **Leistung bei vielen Serien** – Begrenzen Sie die Anzahl der Serien/Kategorien oder verwenden Sie Workbook‑Zellen erneut, um den Speicherverbrauch im Griff zu behalten.  

## Häufig gestellte Fragen

**F: Kann ich ein Donut‑Diagramm ohne eine bereits vorhandene PPTX‑Datei erzeugen?**  
A: Ja, instanziieren Sie `new Presentation()`, um von einem leeren Foliendeck zu starten, und fügen Sie dann ein Diagramm wie oben gezeigt hinzu.

**F: Unterstützt Aspose.Slides den Export nach PDF?**  
A: Auf jeden Fall. Nachdem Sie das Diagramm erstellt haben, rufen Sie `pres.save("output.pdf", SaveFormat.Pdf);` auf, um eine PDF‑Version der Folie zu erhalten.

**F: Wie ändere ich die Größe des Donut‑Lochs?**  
A: Verwenden Sie `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, wobei `value` von 0 bis 100 reicht.

**F: Ist es möglich, Datenbeschriftungen zu allen Serien hinzuzufügen, nicht nur zur letzten?**  
A: Ja, verschieben Sie den Beschriftungs‑Formatierungsblock aus der Bedingung `if (i == ...)` heraus und wenden Sie ihn auf jeden `dataPoint` an.

**F: Welche Java‑Versionen werden unterstützt?**  
A: Aspose.Slides 25.4 unterstützt JDK 16 und neuer. Ältere JDKs benötigen den entsprechenden Klassifizierer in der Maven‑Abhängigkeit.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Verwandte Tutorials

- [Wie man ein Diagramm zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Wie man Kreisdiagramm‑Farben in Java mit Aspose.Slides anpasst – Ein vollständiger Leitfaden](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [PowerPoint‑Diagramm‑Kategorien mit Aspose.Slides für Java animieren | Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
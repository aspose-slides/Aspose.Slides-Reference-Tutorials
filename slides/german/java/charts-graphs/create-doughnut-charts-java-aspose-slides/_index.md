---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides beeindruckende Ringdiagramme in Java erstellen. Diese umfassende Anleitung behandelt Initialisierung, Datenkonfiguration und das Speichern von Präsentationen."
"title": "Erstellen Sie Donut-Diagramme in Java mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie Donut-Diagramme in Java mit Aspose.Slides: Eine Schritt-für-Schritt-Anleitung

## Einführung

In der heutigen datengetriebenen Umgebung ist die effektive Visualisierung von Informationen entscheidend für mehr Verständnis und Engagement. Die programmgesteuerte Erstellung professioneller Diagramme kann, insbesondere mit Java, eine Herausforderung darstellen. Diese Anleitung führt Sie durch die Verwendung von Aspose.Slides für Java zur mühelosen Erstellung von Ringdiagrammen.

Durch Befolgen dieser Schritte sammeln Entwickler praktische Erfahrungen in der Bearbeitung von Präsentationsfolien und der nahtlosen Integration der Datenvisualisierung.

**Wichtige Erkenntnisse:**
- Initialisieren Sie ein Präsentationsobjekt mit Aspose.Slides Java.
- Konfigurieren Sie Diagrammdaten und verwalten Sie vorhandene Reihen oder Kategorien.
- Fügen Sie Reihen und Kategorien für Ihre Diagramme hinzu und passen Sie diese an.
- Datenpunkte effektiv formatieren und anzeigen.
- Speichern Sie Ihre Präsentation problemlos in verschiedenen Formaten.

Bevor Sie mit der Implementierung beginnen, stellen Sie sicher, dass Sie über alles verfügen, was Sie für den Einstieg benötigen.

## Voraussetzungen

Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Erforderliche Bibliotheken:**
  - Aspose.Slides für Java Version 25.4 oder höher.
  
- **Umgebungs-Setup:**
  - Auf Ihrem System ist JDK 16 oder höher installiert.
  - Eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans.

- **Erforderliche Kenntnisse:**
  - Grundlegendes Verständnis der Konzepte der Java-Programmierung.
  - Vertrautheit mit der Verwaltung von Abhängigkeiten in Maven- oder Gradle-Projekten.

## Einrichten von Aspose.Slides für Java

Um Aspose.Slides in Ihr Projekt zu integrieren, befolgen Sie diese Schritte basierend auf Ihrem Build-Tool:

**Maven-Setup:**
Fügen Sie die folgende Abhängigkeit zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle-Setup:**
Nehmen Sie Folgendes in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktdownload:**
Alternativ können Sie die neueste Version direkt von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Erwerb einer Lizenz

So verwenden Sie Aspose.Slides ohne Auswertungsbeschränkungen:
- **Kostenlose Testversion:** Beginnen Sie mit einer temporären Lizenz, um alle Funktionen zu erkunden.
- **Temporäre Lizenz:** Erhalten Sie eine über die [Aspose-Website](https://purchase.aspose.com/temporary-license/).
- **Kaufen:** Erwägen Sie den Kauf für den fortlaufenden Gebrauch.

Wenden Sie Ihre Lizenz in Ihrer Java-Anwendung an, indem Sie:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementierungshandbuch

### Präsentation und Diagramm initialisieren

#### Überblick
Beginnen Sie mit der Initialisierung eines Präsentationsobjekts und fügen Sie der ersten Folie ein Ringdiagramm hinzu.

**Schritt 1: Präsentation initialisieren**
Laden Sie eine vorhandene PPTX-Datei oder erstellen Sie eine neue:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Schritt 2: Donut-Diagramm hinzufügen**
Erstellen Sie auf der ersten Folie an den angegebenen Koordinaten ein Diagramm:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurieren der Diagrammdaten-Arbeitsmappe und Löschen vorhandener Serien/Kategorien

#### Überblick
Konfigurieren Sie die Diagrammdaten-Arbeitsmappe und entfernen Sie alle bereits vorhandenen Reihen oder Kategorien.

**Schritt 1: Zugriff auf die Arbeitsmappe mit Diagrammdaten**
Rufen Sie die mit Ihrem Diagramm verknüpfte Arbeitsmappe ab:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Schritt 2: Vorhandene Serien und Kategorien löschen**
Stellen Sie sicher, dass keine Restdatenpunkte vorhanden sind:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Hinzufügen von Reihen zum Diagramm

#### Überblick
Füllen Sie Ihr Diagramm mit mehreren Reihen, die jeweils hinsichtlich Aussehen und Verhalten angepasst sind.

**Schritt 1: Serien iterativ hinzufügen**
Durchlaufen Sie Indizes, um Reihen hinzuzufügen:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Passen Sie die Serie an
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Hinzufügen von Kategorien und Datenpunkten zum Diagramm

#### Überblick
Konfigurieren Sie Kategorien und fügen Sie Datenpunkte mit spezifischer Formatierung für Beschriftungen hinzu.

**Schritt 1: Kategorien hinzufügen**
Durchlaufen Sie die Indizes für jede Kategorie:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Schritt 2: Datenpunkte zu jeder Reihe hinzufügen**
Durchlaufen Sie jede Serie für die aktuelle Kategorie:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Datenpunktformateinstellungen
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Beschriftungsformatierung für die letzte Serie
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

        // Anzeigeoptionen anpassen
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Passen Sie die Position des Etiketts an
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Speichern der Präsentation

#### Überblick
Nachdem Sie Ihr Diagramm konfiguriert haben, speichern Sie die Präsentation in einem angegebenen Verzeichnis.

**Schritt 1: Speichern Sie die Präsentation**
Verwenden Sie die `save` Methode zum Schreiben von Änderungen:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Abschluss

Sie haben nun gelernt, wie Sie mit Aspose.Slides Ringdiagramme in Java erstellen und anpassen. Diese Schritte bilden die Grundlage für die Integration anspruchsvoller Datenvisualisierungen in Ihre Präsentationen.

**Nächste Schritte:**
- Experimentieren Sie mit verschiedenen Diagrammtypen, die in Aspose.Slides verfügbar sind.
- Entdecken Sie zusätzliche Anpassungsoptionen wie Farben, Schriftarten und Stile, um Ihren Markenanforderungen gerecht zu werden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
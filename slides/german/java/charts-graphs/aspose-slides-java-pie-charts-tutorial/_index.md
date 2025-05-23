---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie Kreisdiagramme mit Aspose.Slides für Java erstellen und anpassen. Dieses Tutorial behandelt alles von der Einrichtung bis zur erweiterten Anpassung."
"title": "Erstellen von Kreisdiagrammen in Java mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Kreisdiagrammen mit Aspose.Slides für Java: Ein vollständiges Tutorial

## Einführung
Dynamische und optisch ansprechende Präsentationen sind entscheidend für die Vermittlung wirkungsvoller Informationen. Mit Aspose.Slides für Java können Sie komplexe Diagramme wie Kreisdiagramme nahtlos in Ihre Folien integrieren und so die Datenvisualisierung mühelos verbessern. Diese umfassende Anleitung führt Sie durch die Erstellung und Anpassung eines Kreisdiagramms mit Aspose.Slides Java und löst so mühelos gängige Präsentationsprobleme.

**Was Sie lernen werden:**
- Initialisieren einer Präsentation und Hinzufügen von Folien.
- Erstellen und Konfigurieren eines Kreisdiagramms auf Ihrer Folie.
- Festlegen von Diagrammtiteln, Datenbeschriftungen und Farben.
- Leistung optimieren und Ressourcen effektiv verwalten.
- Integration von Aspose.Slides in Java-Projekte mit Maven oder Gradle.

Stellen wir zunächst sicher, dass Sie über alle erforderlichen Werkzeuge und Kenntnisse verfügen, um mitmachen zu können!

## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie über die folgende Einrichtung verfügen:

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
- **Aspose.Slides für Java**: Stellen Sie sicher, dass Sie Version 25.4 oder höher haben.
- **Java Development Kit (JDK)**: Version 16 oder höher ist erforderlich.

### Anforderungen für die Umgebungseinrichtung
- Eine Entwicklungsumgebung mit installiertem und konfiguriertem Java.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA, Eclipse oder NetBeans.

### Voraussetzungen
- Grundlegende Kenntnisse der Java-Programmierung.
- Vertrautheit mit Maven oder Gradle für die Abhängigkeitsverwaltung.

## Einrichten von Aspose.Slides für Java
Um Aspose.Slides in Ihren Java-Projekten verwenden zu können, müssen Sie die Bibliothek als Abhängigkeit hinzufügen. So können Sie dies mit verschiedenen Build-Tools tun:

**Maven**
Fügen Sie diesen Ausschnitt zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Nehmen Sie Folgendes in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download**
Wenn Sie kein Build-Tool verwenden möchten, laden Sie die neueste Version herunter von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Schritte zum Lizenzerwerb
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen von Aspose.Slides zu erkunden.
- **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz für eine erweiterte Nutzung ohne Einschränkungen.
- **Kaufen**: Erwägen Sie einen Kauf, wenn Sie langfristigen Zugriff benötigen.

**Grundlegende Initialisierung und Einrichtung**
Um mit der Verwendung von Aspose.Slides zu beginnen, initialisieren Sie Ihr Projekt, indem Sie ein neues Präsentationsobjekt erstellen:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementierungshandbuch
Lassen Sie uns nun den Vorgang des Hinzufügens und Anpassens eines Kreisdiagramms in überschaubare Schritte unterteilen.

### Präsentation und Folie initialisieren
Beginnen Sie mit dem Einrichten einer neuen Präsentation und dem Aufrufen der ersten Folie. Dies ist Ihre Leinwand zum Erstellen von Diagrammen:
```java
import com.aspose.slides.*;

// Erstellen Sie eine neue Präsentationsinstanz.
Presentation presentation = new Presentation();
// Greifen Sie auf die erste Folie der Präsentation zu.
islide slides = presentation.getSlides().get_Item(0);
```

### Kreisdiagramm zur Folie hinzufügen
Fügen Sie an der angegebenen Position ein Kreisdiagramm mit einem Standarddatensatz ein:
```java
import com.aspose.slides.*;

// Fügen Sie an der Position (100, 100) ein Kreisdiagramm mit der Größe (400, 400) hinzu.
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagrammtitel festlegen
Passen Sie Ihr Diagramm an, indem Sie den Titel festlegen und zentrieren:
```java
import com.aspose.slides.*;

// Fügen Sie dem Kreisdiagramm einen Titel hinzu.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurieren von Datenbeschriftungen für Serien
Stellen Sie sicher, dass die Datenbeschriftungen aus Gründen der Übersichtlichkeit Werte anzeigen:
```java
import com.aspose.slides.*;

// Datenwerte der ersten Reihe anzeigen.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Arbeitsblatt „Diagrammdaten vorbereiten“
Richten Sie das Datenarbeitsblatt Ihres Diagramms ein, indem Sie vorhandene Reihen und Kategorien löschen:
```java
import com.aspose.slides.*;

// Bereiten Sie die Arbeitsmappe mit den Diagrammdaten vor.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategorien zum Diagramm hinzufügen
Definieren Sie Kategorien für Ihr Kreisdiagramm:
```java
import com.aspose.slides.*;

// Neue Kategorien hinzufügen.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Serien hinzufügen und Datenpunkte füllen
Erstellen Sie eine Reihe und füllen Sie sie mit Datenpunkten:
```java
import com.aspose.slides.*;

// Fügen Sie eine neue Serie hinzu und legen Sie ihren Namen fest.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Anpassen von Serienfarben und -rändern
Verbessern Sie die visuelle Attraktivität, indem Sie Farben festlegen und Ränder anpassen:
```java
import com.aspose.slides.*;

// Legen Sie für die Seriensektoren unterschiedliche Farben fest.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Wiederholen Sie den Vorgang für andere Datenpunkte mit unterschiedlichen Farben und Stilen.
```

### Konfigurieren benutzerdefinierter Datenbeschriftungen
Optimieren Sie die Beschriftungen für jeden Datenpunkt:
```java
import com.aspose.slides.*;

// Konfigurieren Sie benutzerdefinierte Beschriftungen.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Führungslinien für Beschriftungen aktivieren.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Drehwinkel einstellen und Präsentation speichern
Finalisieren Sie Ihr Kreisdiagramm, indem Sie einen Drehwinkel festlegen und die Präsentation speichern:
```java
import com.aspose.slides.*;

// Drehwinkel einstellen.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Speichern Sie die Präsentation in einer Datei.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie Kreisdiagramme mit Aspose.Slides für Java erstellen und anpassen. Mit diesen Schritten können Sie Ihre Präsentationen mit optisch ansprechenden Datenvisualisierungen aufwerten. Bei Fragen oder für weitere Unterstützung wenden Sie sich gerne an uns.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
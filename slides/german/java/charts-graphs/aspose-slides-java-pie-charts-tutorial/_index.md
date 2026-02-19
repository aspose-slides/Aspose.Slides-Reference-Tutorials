---
date: '2026-02-19'
description: Erfahren Sie, wie Sie in Java mit Aspose.Slides ein Kreisdiagramm erstellen,
  die Farben des Kreisdiagramms anpassen, Diagrammserien hinzufügen, mit dem Diagrammdaten‑Arbeitsblatt
  arbeiten und den Rotationswinkel festlegen.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Wie man die Farben von Kreisdiagrammen in Java mit Aspose.Slides anpasst –
  Ein vollständiger Leitfaden
url: /de/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Kreisdiagrammen mit Aspose.Slides für Java: Ein vollständiges Tutorial

## Einleitung
Das Erstellen dynamischer und optisch ansprechender Präsentationen ist entscheidend, um wirkungsvolle Informationen zu vermitteln. Mit Aspose.Slides für Java können Sie nahtlos komplexe Diagramme wie Kreisdiagramme in Ihre Folien integrieren, **customize pie chart colors** und die Datenvisualisierung mühelos verbessern. Dieses umfassende Handbuch führt Sie Schritt für Schritt durch das Erstellen und Anpassen eines Kreisdiagramms mit Aspose.Slides Java und löst gängige Präsentationsprobleme mit Leichtigkeit.

**Was Sie lernen werden:**
- Initialisieren einer Präsentation und Hinzufügen von Folien.
- Erstellen und Konfigurieren eines Kreisdiagramms auf Ihrer Folie.
- Festlegen von Diagrammtiteln, Datenbeschriftungen und **customize pie chart colors**.
- Optimieren der Leistung und effektives Ressourcenmanagement.
- Integration von Aspose.Slides in Java-Projekte mit Maven oder Gradle.

Lassen Sie uns beginnen, indem wir sicherstellen, dass Sie alle notwendigen Werkzeuge und das Wissen haben, um dem Tutorial zu folgen!

## Schnelle Antworten
- **Was ist die primäre Klasse zum Starten einer Präsentation?** `Presentation` aus `com.aspose.slides`.
- **Welche Methode fügt ein Kreisdiagramm zu einer Folie hinzu?** `addChart(ChartType.Pie, …)`.
- **Wie aktivieren Sie unterschiedliche Farben für jeden Abschnitt?** Setzen Sie `setColorVaried(true)` in der Seriengruppe.
- **Kann man das Kreisdiagramm drehen?** Ja, verwenden Sie `setRotationAngle(double)` am Diagrammobjekt.
- **Benötige ich eine Lizenz für den Produktionseinsatz?** Eine Aspose.Slides-Lizenz ist für kommerzielle Bereitstellungen erforderlich.

## Was bedeutet „customize pie chart colors“?
Customizing pie chart colors bedeutet, jedem Abschnitt des Kreisdiagramms eine eigene Füllfarbe zuzuweisen, um die Lesbarkeit und den visuellen Eindruck zu verbessern. In Aspose.Slides erreichen Sie dies, indem Sie unterschiedliche Farben aktivieren und anschließend für einzelne Datenpunkte feste Füllfarben festlegen.

## Warum Aspose.Slides für Java zum Erstellen von Kreisdiagrammen verwenden?
- **Vollständige Kontrolle** über das Aussehen des Diagramms, ohne Microsoft Office zu benötigen.
- **Plattformübergreifende** Kompatibilität – funktioniert unter Windows, Linux und macOS.
- **Umfangreiche API** für Datenbindung, Styling und Export nach PPTX, PDF oder Bildern.
- **Lizenzflexibilität** – beginnen Sie mit einer kostenlosen Testversion und upgraden Sie, wenn Sie das vollständige Funktionsset benötigen.

## Voraussetzungen

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
- **Aspose.Slides for Java**: Version 25.4 oder höher.
- **Java Development Kit (JDK)**: Version 16 oder höher.

### Anforderungen an die Umgebungseinrichtung
- Eine Entwicklungsumgebung mit installiertem und konfiguriertem Java.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA, Eclipse oder NetBeans.

### Wissensvoraussetzungen
- Grundlegendes Verständnis der Java-Programmierung.
- Vertrautheit mit Maven oder Gradle für das Abhängigkeitsmanagement.

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides in Ihren Java-Projekten zu verwenden, müssen Sie die Bibliothek als Abhängigkeit hinzufügen. So geht's mit verschiedenen Build-Tools:

**Maven**  
Fügen Sie diesen Ausschnitt zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Fügen Sie das Folgende in Ihre `build.gradle`‑Datei ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download**  
Wenn Sie kein Build‑Tool verwenden möchten, laden Sie das neueste Release von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunter.

### Schritte zum Erwerb einer Lizenz
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen von Aspose.Slides zu erkunden.  
- **Temporäre Lizenz**: Erhalten Sie eine temporäre Lizenz für erweiterten Gebrauch ohne Einschränkungen.  
- **Kauf**: Erwägen Sie den Kauf, wenn Sie langfristigen Zugriff benötigen.

**Grundlegende Initialisierung und Einrichtung**  
Um Aspose.Slides zu nutzen, initialisieren Sie Ihr Projekt, indem Sie ein neues Präsentationsobjekt erstellen:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementierungsleitfaden
Jetzt zerlegen wir den Prozess des Hinzufügens und Anpassen eines Kreisdiagramms in handhabbare Schritte.

### Präsentation und Folie initialisieren
Richten Sie zunächst eine neue Präsentation ein und greifen Sie auf die erste Folie zu. Dies ist Ihre Leinwand zum Erstellen von Diagrammen:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Kreisdiagramm zur Folie hinzufügen
Fügen Sie ein Kreisdiagramm an der angegebenen Position mit einem Standard‑Datensatz ein:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagrammtitel festlegen
Passen Sie Ihr Diagramm an, indem Sie den Titel setzen und zentrieren:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Datenbeschriftungen für die Serie konfigurieren
Stellen Sie sicher, dass Datenbeschriftungen Werte zur besseren Übersicht anzeigen:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Diagrammdaten-Arbeitsblatt vorbereiten
Richten Sie das Datenarbeitsblatt Ihres Diagramms ein, indem Sie vorhandene Serien und Kategorien löschen:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategorien zum Diagramm hinzufügen
Definieren Sie Kategorien für Ihr Kreisdiagramm:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Serie hinzufügen und Datenpunkte füllen
Erstellen Sie eine Serie und füllen Sie sie mit Datenpunkten – hier **add chart series**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Serienfarben und -rahmen anpassen
Verbessern Sie die Optik, indem Sie Farben setzen und Rahmen anpassen – das **customizes pie chart colors** direkt:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Benutzerdefinierte Datenbeschriftungen konfigurieren
Feinabstimmung der Beschriftungen für jeden Datenpunkt:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Rotationswinkel festlegen und Präsentation speichern
Schließen Sie Ihr Kreisdiagramm ab, indem Sie **set rotation angle** anwenden und die Datei speichern:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Alle Abschnitte haben dieselbe Farbe** | `setColorVaried(true)` nicht aufgerufen | Stellen Sie sicher, dass Sie unterschiedliche Farben in der Seriengruppe aktivieren. |
| **Datenbeschriftungen werden nicht angezeigt** | `showValue`-Flag deaktiviert | Rufen Sie `setShowValue(true)` im entsprechenden Beschriftungsformat auf. |
| **Rotation hat keine Wirkung** | Verwendung einer älteren Aspose.Slides-Version | Aktualisieren Sie auf Version 25.4 oder höher. |
| **Lizenzausnahme zur Laufzeit** | Fehlende oder ungültige Lizenzdatei | Laden Sie Ihre Lizenz mit `License license = new License(); license.setLicense("Aspose.Slides.lic");` bevor Sie das `Presentation`‑Objekt erstellen. |

## Häufig gestellte Fragen

**Q: Wie erhalte ich eine Aspose.Slides‑Lizenz für Java?**  
A: Sie können eine kostenlose Testversion auf der Aspose‑Website anfordern und anschließend eine permanente Lizenz erwerben. Laden Sie sie zur Laufzeit wie in der Tabelle „Häufige Probleme und Lösungen“ gezeigt.

**Q: Kann ich diesen Code mit älteren JDK‑Versionen verwenden?**  
A: Die API erfordert JDK 16 oder höher; ältere Versionen werden nicht unterstützt.

**Q: Ist es möglich, das Diagramm als Bild statt als PPTX zu exportieren?**  
A: Ja, rufen Sie nach dem Rendern `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` auf.

**Q: Was, wenn ich mehr als eine Serie zu einem Kreisdiagramm hinzufügen muss?**  
A: Kreisdiagramme zeigen typischerweise nur eine Serie; für mehrere Serien sollten Sie stattdessen ein Donut‑Diagramm verwenden.

**Q: Funktioniert die Bibliothek auf Linux‑Servern?**  
A: Absolut – Aspose.Slides für Java ist plattformunabhängig und läuft auf jedem Betriebssystem mit kompatiblem JDK.

---

**Last Updated:** 2026-02-19  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
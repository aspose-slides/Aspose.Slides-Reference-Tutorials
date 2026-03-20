---
date: '2026-03-20'
description: Erfahren Sie, wie Sie ein gruppiertes Säulendiagramm zu einer PowerPoint‑Präsentation
  hinzufügen, ein PowerPoint‑Diagramm anpassen und ein Datenreihen‑Diagramm mit Aspose.Slides
  für Java einfügen.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Wie man ein gruppiertes Säulendiagramm in PowerPoint mit Aspose.Slides für
  Java hinzufügt
url: /de/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein gruppiertes Säulendiagramm in PowerPoint mit Aspose.Slides für Java hinzufügt

## Einführung

Wenn Sie ein **grouped column chart** zu einer PowerPoint‑Präsentation hinzufügen müssen, kann eine klare Visualisierung rohe Zahlen in eine sofort verständliche Geschichte verwandeln. Das manuelle Erstellen in PowerPoint ist zeitaufwändig, besonders wenn Sie viele Folien programmgesteuert erzeugen müssen. **Aspose.Slides für Java** beseitigt die Reibung – es ermöglicht Ihnen, PowerPoint‑Diagramme zu erstellen, anzupassen und Datenreihen‑Diagramme mit nur wenigen Codezeilen einzufügen.

In diesem Tutorial lernen Sie, wie Sie:
- Eine neue PowerPoint‑Präsentation mit Aspose.Slides für Java initialisieren.
- **Diagramm zur Folie hinzufügen** und es als gruppiertes Säulendiagramm konfigurieren.
- **Gruppiertes Säulendiagramm** durch Definition von Gruppierungsebenen für Kategorien erstellen.
- **Datenreihen‑Diagramm einfügen**, sodass Ihre Daten korrekt angezeigt werden.
- Die fertige Präsentation als PPTX‑Datei speichern.

Stellen wir sicher, dass Sie alles haben, bevor wir in den Code eintauchen.

## Schnellantworten
- **Was ist die primäre Klasse?** `Presentation` aus `com.aspose.slides`.
- **Welcher Diagrammtyp wird verwendet?** `ChartType.ClusteredColumn`.
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert, aber eine Lizenz entfernt Evaluationsbeschränkungen.
- **Welche Java‑Version wird unterstützt?** JDK 16 oder neuer (das Beispiel verwendet JDK 16).
- **Wie führe ich das Beispiel aus?** Fügen Sie die Maven/Gradle‑Abhängigkeit hinzu, kompilieren Sie und führen Sie die `main`‑Methode aus.

## Was bedeutet „add clustered column chart“?

Ein *clustered column chart* (auch *grouped column chart* genannt) zeigt mehrere Datenreihen nebeneinander für jede Kategorie, sodass Werte über Gruppen hinweg leicht vergleichbar sind. In PowerPoint ist dieser Diagrammtyp ideal für Quartalsumsätze, Umfrageergebnisse oder jede Situation, in der Sie mehrere Datensätze innerhalb derselben Kategorie gegenüberstellen müssen.

## Warum Aspose.Slides zum Hinzufügen eines gruppierten Säulendiagramms verwenden?

- **Vollständige Automatisierung** – erzeugen Sie Dutzende von Folien ohne manuellen Aufwand.
- **Fein abgestimmte Anpassung** – steuern Sie Farben, Beschriftungen, Gruppierungsebenen und mehr.
- **Plattformübergreifend** – funktioniert auf jedem Betriebssystem, das Java unterstützt.
- **Keine Office‑Installation erforderlich** – erzeugen Sie PPTX‑Dateien auf Servern oder CI‑Pipelines.

## Voraussetzungen

- **Aspose.Slides für Java**‑Bibliothek (die neueste Version wird empfohlen).  
- JDK 16 oder höher.  
- Maven‑ oder Gradle‑Build‑Tool (oder Sie können das JAR manuell hinzufügen).  
- Eine IDE oder ein Texteditor zum Ausführen von Java‑Code.

## Einrichtung von Aspose.Slides für Java

Fügen Sie die Bibliothek Ihrem Projekt mit einem der folgenden Build‑Skripte hinzu.

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

Alternativ können Sie das neueste Release direkt von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung

Bevor Sie in die Produktion gehen, erhalten Sie eine Lizenz:
- **Kostenlose Testversion** – erkunden Sie alle Funktionen ohne Kauf.
- **Temporäre Lizenz** – bewerten Sie erweiterte Funktionen für einen kurzen Zeitraum.
- **Vollständige Lizenz** – schalten Sie unbegrenzte Nutzung frei. Erhalten Sie sie über die [Kaufseite von Aspose](https://purchase.aspose.com/buy).

## Implementierungsleitfaden

Wir gehen Schritt für Schritt durch, erklären **wie man ein Diagramm hinzufügt** und **wie man PowerPoint‑Diagramme** anpasst.

### Präsentation initialisieren

Zuerst erstellen Sie ein neues `Presentation`‑Objekt und holen die Standardfolie.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Diagramm zur Folie hinzufügen

Jetzt **fügen wir ein Diagramm zur Folie hinzu** und verwenden den Typ `ClusteredColumn`, wobei wir alle Standarddaten entfernen.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Diagrammdaten‑Workbook vorbereiten

Das Diagramm speichert seine Daten in einem internen Workbook. Wir leeren es, um neu zu beginnen.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Kategorien mit Gruppierungsebenen hinzufügen

Das Gruppieren von Kategorien erzeugt den **Gruppiertes‑Säulendiagramm**‑Effekt. Jede Kategorie kann zu einer logischen Gruppe gehören.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Datenreihen zum Diagramm hinzufügen

Hier **fügen wir Datenreihen‑Diagramm‑Einträge** ein, die als separate Säulen visualisiert werden.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Präsentation mit Diagramm speichern

Abschließend schreiben wir die PPTX‑Datei auf die Festplatte.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktische Anwendungen

- **Geschäftsberichte** – vergleichen Sie Quartalsumsätze nach Regionen.  
- **Akademische Forschung** – zeigen Sie experimentelle Ergebnisse, gruppiert nach Testbedingungen.  
- **Projektmanagement** – visualisieren Sie Abschlussraten von Aufgaben für mehrere Teams auf einer einzigen Folie.

## Leistungsüberlegungen

- **Speichermanagement** – geben Sie große Workbooks nach Gebrauch frei.  
- **Batch‑Operationen** – vermeiden Sie das Aktualisieren des Diagramms in engen Schleifen; sammeln Sie zuerst die Daten und wenden Sie sie dann an.  
- **Eingebaute Optimierungen** – Aspose.Slides bietet Methoden wie `Presentation.optimize()` für große Dateien.

## Häufige Fallstricke & Tipps

- **Fallstrick:** Das Vergessen, vorhandene Reihen/Kategorien zu leeren, kann zu doppelten Daten führen.  
  **Tipp:** Rufen Sie immer `clear()` auf, bevor Sie neue Daten einfügen.  
- **Fallstrick:** Verwendung einer falschen Zelladresse (z. B. `"c2"` statt `"C2"`).  
  **Tipp:** Zellreferenzen sind nicht case‑sensitiv, aber halten Sie sie aus Lesbarkeitsgründen konsistent.  
- **Tipp:** Verwenden Sie `setGroupingItem`, um sinnvolle Gruppenbezeichnungen zu erstellen; sie erscheinen automatisch in der Diagrammlegende.

## Häufig gestellte Fragen

**F1: Wie kann ich mehrere Reihen zu meinem Diagramm hinzufügen?**  
A1: Rufen Sie wiederholt `ch.getChartData().getSeries().add()` auf und übergeben Sie einen eindeutigen Namen sowie Datenpunkte für jede Reihe.

**F2: Welche häufigen Probleme gibt es bei Aspose.Slides‑Diagrammen?**  
A2: Probleme entstehen oft durch nicht übereinstimmende Datenbereiche oder fehlende Workbook‑Zellen. Vergewissern Sie sich, dass jede Kategorie und jeder Datenpunkt eine entsprechende Zelle hat.

**F3: Kann ich Aspose.Slides mit anderen Programmiersprachen verwenden?**  
A3: Ja, Aspose bietet äquivalente Bibliotheken für .NET, C++, Python und mehr.

**F4: Wie aktualisiere ich ein bestehendes Diagramm in einer Präsentation?**  
A4: Laden Sie die Präsentation, finden Sie das Diagramm über `slide.getShapes().get_Item(index)`, und ändern Sie dann seine Reihen oder Formatierungen nach Bedarf.

**F5: Gibt es Einschränkungen bei Diagrammtypen mit Aspose.Slides?**  
A5: Die Bibliothek unterstützt eine breite Palette von Diagrammtypen, prüfen Sie jedoch stets die aktuelle Dokumentation für neu hinzugefügte oder veraltete Typen.

## Ressourcen

- **Dokumentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Kauf**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Kostenlose Testversion**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporäre Lizenz**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support‑Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-20  
**Getestet mit:** Aspose.Slides für Java 25.4 (JDK 16)  
**Autor:** Aspose
---
date: '2026-03-02'
description: Erfahren Sie, wie Sie ein Box‑Plot in Java erstellen, ein Diagramm zur
  Folie hinzufügen und ein Box‑Whisker‑Diagramm in PowerPoint mit Aspose.Slides für
  Java erzeugen.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Boxplot in Java mit Aspose.Slides für PowerPoint erstellen
url: /de/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Box‑and‑Whisker‑Diagramme in PowerPoint mit Aspose.Slides für Java erstellt

In diesem Leitfaden werden Sie **create box plot java** mit Aspose.Slides erstellen und das Diagramm anschließend direkt in eine PowerPoint‑Folien einbetten. Das Erstellen visuell ansprechender Datenpräsentationen ist in der heutigen datengetriebenen Welt entscheidend, und Diagramme sind dafür unverzichtbare Werkzeuge. Wenn Sie Box‑and‑Whisker‑Diagramme in PowerPoint mit Java erzeugen möchten, bietet die Aspose.Slides‑Bibliothek eine robuste Lösung. Dieses Tutorial führt Sie Schritt für Schritt durch das Erstellen und Konfigurieren dieser Diagramme mit Aspose.Slides für Java.

## Was Sie lernen werden

- Einrichtung Ihrer Umgebung für Aspose.Slides für Java
- Schritte zum **add chart to slide** und zum Erzeugen eines Box‑Whisker‑Diagramms in PowerPoint mit Java
- Best Practices zur Optimierung der Leistung bei der Arbeit mit Aspose.Slides
- Praxisnahe Anwendungen von Box‑and‑Whisker‑Diagrammen

## Schnelle Antworten
- **Welche Bibliothek erstellt ein Box‑Plot in Java?** Aspose.Slides für Java.
- **Welcher Diagrammtyp wird verwendet?** `ChartType.BoxAndWhisker`.
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.
- **Kann ich mehrere Serien hinzufügen?** Ja – wiederholen Sie den Serien‑Erstellungsblock für jeden Datensatz.
- **Welches Format hat die endgültige Datei?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Voraussetzungen

Um diesem Tutorial zu folgen, stellen Sie sicher, dass Sie folgendes haben:

- **Java Development Kit (JDK)**: JDK 8 oder höher sollte installiert sein.
- **Aspose.Slides for Java Library**: Essenziell für die Verarbeitung von PowerPoint‑Präsentationen in Java.
- **IDE**: Eine integrierte Entwicklungsumgebung wie IntelliJ IDEA oder Eclipse zum Schreiben und Ausführen Ihres Codes.

## Einrichtung von Aspose.Slides für Java

Um Aspose.Slides zu verwenden, fügen Sie es als Abhängigkeit hinzu. Sie können dies über Maven, Gradle oder durch direkten Download verwalten.

### Maven

Fügen Sie die folgende Abhängigkeit in Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

In Ihrer `build.gradle` fügen Sie ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download

Alternativ können Sie die neueste Version von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

#### Lizenzbeschaffung

- **Free Trial**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.  
- **Temporary License**: Erhalten Sie eine temporäre Lizenz für Evaluierungszwecke.  
- **Purchase**: Für die volle Funktionalität sollten Sie den Kauf einer Lizenz in Betracht ziehen.

Um Aspose.Slides zu initialisieren, stellen Sie sicher, dass die Bibliothek in Ihrem Klassenpfad liegt und richten Sie bei Bedarf die Lizenzanforderungen ein.

## Implementierungs‑Leitfaden

Jetzt tauchen wir in den Schritt‑für‑Schritt‑Code ein. Jeder Block wird vor dem Snippet erklärt, damit Sie genau wissen, was er tut.

### Was ist ein Box‑Plot und warum ihn in Java verwenden?

Ein Box‑and‑Whisker‑Diagramm (oft *Box‑Plot* genannt) visualisiert die Datenverteilung – Median, Quartile und Ausreißer – in kompakter Form. In Java ermöglicht das programmatische Erzeugen dieses Diagramms, statistische Erkenntnisse direkt in PowerPoint‑Präsentationen einzubetten und manuelle Diagrammerstellung zu vermeiden.

### Warum ein Diagramm mit Aspose.Slides zur Folie hinzufügen?

Aspose.Slides abstrahiert die Low‑Level‑OpenXML‑Details und bietet Ihnen eine flüssige API zum Erstellen, Gestalten und Exportieren von Diagrammen. Das bedeutet, dass Sie die Berichtserstellung automatisieren, ein konsistentes Branding erzeugen und Diagramme in größere Java‑Workflows integrieren können.

### Schritt 1: Eine Präsentation erstellen oder öffnen

Zuerst öffnen Sie ein vorhandenes PPTX oder starten ein neues:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro Tipp:** Wenn die Datei nicht existiert, erstellt Aspose.Slides für Sie eine neue leere Präsentation.

### Schritt 2: Ein Box‑and‑Whisker‑Diagramm zur Folie hinzufügen

Platzieren Sie das Diagramm dort, wo Sie es benötigen, indem Sie Position und Größe (in Punkten) angeben:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Schritt 3: Vorhandene Daten löschen

Bevor Sie neue Daten einfügen, entfernen Sie alle Platzhalter‑Kategorien oder -Serien:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Schritt 4: Kategorien konfigurieren

Fügen Sie die Kategorien (X‑Achsen‑Beschriftungen) hinzu, die unter jedem Kasten angezeigt werden sollen:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Hinweis:** Passen Sie den Beschriftungstext an Ihre Daten‑Domäne an (z. B. „Q1“, „Produkt A“).

### Schritt 5: Serie erstellen und anpassen

Jetzt erstellen Sie eine Serie, setzen visuelle Optionen und fügen die numerischen Datenpunkte hinzu:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Sie können das `int[] data`‑Array durch Werte ersetzen, die aus einer Datenbank, einer CSV‑Datei oder einer anderen Quelle gelesen werden.

### Schritt 6: Präsentation speichern

Persistieren Sie die Änderungen in einer neuen PPTX‑Datei:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Schritt 7: Ressourcen bereinigen

Entsorgen Sie stets das `Presentation`‑Objekt, um native Ressourcen freizugeben:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktische Anwendungen

Box‑and‑Whisker‑Diagramme sind in der statistischen Analyse und Datenpräsentation von unschätzbarem Wert. Hier einige Szenarien, in denen sie glänzen:

1. **Financial Analysis** – Visualisieren Sie die Umsatzverteilung über Regionen.  
2. **Quality Control** – Erkennen Sie Ausreißer in Fertigungsmessungen.  
3. **Academic Research** – Zeigen Sie die Variabilität von Versuchsergebnissen.  
4. **Market Research** – Vergleichen Sie die Produktleistung über demografische Gruppen.

Durch die Integration dieser Diagramme in PowerPoint‑Präsentationen können Stakeholder komplexe Daten auf einen Blick erfassen.

## Leistungsüberlegungen

Bei der Arbeit mit Aspose.Slides in Java sollten Sie diese Tipps beachten:

- **Memory Management** – Entsorgen Sie `Presentation`‑Objekte umgehend.  
- **Data Handling** – Laden Sie nur die benötigten Daten; vermeiden Sie das direkte Einfügen riesiger Datensätze in das Diagramm‑Workbook.  
- **Lazy Loading** – Wenn Sie viele Folien erzeugen, überlegen Sie, Diagramme nur für die tatsächlich angezeigten Folien zu erstellen.

## Häufige Probleme und Lösungen

| Problem | Ursache | Lösung |
|-------|-------|----------|
| **Chart appears blank** | Datenzellen nicht korrekt befüllt | Überprüfen Sie, dass `wb.getCell` die richtige Zeile/Spalte referenziert und der Wert nicht `null` ist. |
| **Outliers not shown** | `setShowOutlierPoints` ist auf `false` gesetzt | Stellen Sie sicher, dass `series.setShowOutlierPoints(true)` aufgerufen wird. |
| **Memory leak** | Präsentation nicht entsorgt | Umschließen Sie die Nutzung immer mit try/finally und rufen Sie `dispose()` auf. |
| **Incorrect quartiles** | Verwendung der Standard‑`Inclusive`‑Methode | Wechseln Sie zu `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Häufig gestellte Fragen

**F1: Was ist ein Box‑and‑Whisker‑Diagramm?**  
Ein Box‑and‑Whisker‑Diagramm, auch als Box‑Plot bekannt, zeigt die Datenverteilung anhand von fünf Kennzahlen: Minimum, erstes Quartil, Median, drittes Quartil und Maximum sowie etwaige Ausreißer.

**F2: Kann ich das Aussehen des Box‑and‑Whisker‑Diagramms anpassen?**  
Ja. Aspose.Slides ermöglicht das Ändern von Farben, Linienstilen, Markersymbolen und sogar das Hinzufügen von Datenbeschriftungen über die Formatierungs‑API des Diagramms.

**F3: Ist es möglich, mehrere Serien in einem Diagramm zu verwenden?**  
Absolut. Wiederholen Sie den Serien‑Erstellungsblock für jeden Datensatz, den Sie visualisieren möchten.

**F4: Wie löse ich Probleme, wenn Daten nicht korrekt angezeigt werden?**  
Stellen Sie sicher, dass die Daten korrekt in die Workbook‑Zellen geschrieben werden und dass Sichtbarkeits‑Eigenschaften wie `setShowMeanLine` aktiviert sind.

**F5: Wo kann ich Unterstützung erhalten, wenn ich Probleme habe?**  
Besuchen Sie das [Aspose.Slides‑Forum](https://forum.aspose.com/c/slides/11) für Community‑Hilfe oder konsultieren Sie die offizielle Dokumentation.

**F6: Unterstützt Aspose.Slides weitere Diagrammtypen?**  
Ja, es unterstützt Linien-, Balken-, Kreis-, Streu‑, Radar‑ und viele weitere Diagrammtypen.

**F7: Kann ich Diagramme in einer headless Server‑Umgebung erzeugen?**  
Die Bibliothek funktioniert vollständig in serverseitigen Szenarien; eine UI ist nicht erforderlich.

## Ressourcen

- **Documentation**: Erkunden Sie detaillierte API‑Referenzen unter [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Greifen Sie auf Aspose.Slides‑Releases [hier](https://releases.aspose.com/slides/java/) zu  
- **Purchase**: Kaufen Sie eine Lizenz, um alle Funktionen freizuschalten, unter [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: Beginnen Sie mit einer kostenlosen Testversion oder fordern Sie eine temporäre Lizenz [hier](https://releases.aspose.com/slides/java/) an

Indem Sie diesem Leitfaden folgen, sind Sie nun in der Lage, programmgesteuert aussagekräftige Box‑and‑Whisker‑Diagramme in Ihren Java‑Anwendungen zu erzeugen und sie direkt in PowerPoint‑Präsentationen einzubetten. Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-03-02  
**Getestet mit:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose
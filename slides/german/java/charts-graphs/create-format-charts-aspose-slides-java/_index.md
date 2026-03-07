---
date: '2026-03-07'
description: Erfahren Sie, wie Sie ein Liniendiagramm in Java mit Aspose.Slides erstellen,
  einen Diagrammtitel hinzufügen, Gitternetzlinien einfügen, Diagrammbeschriftungen
  formatieren und professionelle Präsentationen speichern.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Wie man ein Liniendiagramm mit Aspose.Slides in Java erstellt – ein vollständiger
  Leitfaden
url: /de/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Liniendiagramm mit Aspose.Slides in Java erstellt

## Wie man ein Liniendiagramm in Java mit Aspose.Slides erstellt

### Einleitung
Visuell ansprechende Präsentationen zu erstellen ist entscheidend für eine effektive Kommunikation. Egal, ob Sie ein Business‑Professional oder ein Pädagoge sind, Sie müssen häufig **Liniendiagramme** erstellen, die sowohl informativ als auch ästhetisch ansprechend sind. In diesem Tutorial führen wir Sie durch die Verwendung von **Aspose.Slides für Java**, um ein Liniendiagramm zu erzeugen, einen Diagrammtitel hinzuzufügen, Rasterlinien einzufügen, Diagrammbeschriftungen zu formatieren und das Ergebnis als PowerPoint‑Datei zu speichern.

#### Schnelle Antworten
- **Welche Bibliothek ist am besten zum Erstellen von Diagrammen in Java?** Aspose.Slides for Java
- **Auf welchen Diagrammtyp konzentriert sich diese Anleitung?** Liniendiagramm mit Markern
- **Benötige ich eine Lizenz, um das Beispiel auszuführen?** Eine kostenlose temporäre Lizenz reicht für die Evaluierung
- **Welche IDE kann ich verwenden?** Jede Java‑IDE wie IntelliJ IDEA, Eclipse oder NetBeans
- **Wie werden Diagrammelemente formatiert?** Durch Fluent‑API‑Aufrufe für Titel, Achsen, Rasterlinien, Legenden und Hintergründe

### Was ist ein Liniendiagramm und warum Aspose.Slides verwenden?
Ein Liniendiagramm zeigt Datenpunkte, die durch gerade Linien verbunden sind, und eignet sich ideal, um Trends über die Zeit darzustellen. Aspose.Slides ermöglicht das programmatische Erstellen und vollständige Anpassen dieser Diagramme, sodass manuelle PowerPoint‑Bearbeitung entfällt.

### Voraussetzungen
- **Java Development Kit (JDK) 8+** installiert
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans usw.)
- **Aspose.Slides für Java**‑Bibliothek (via Maven oder Gradle hinzugefügt)

#### Erforderliche Bibliotheken und Abhängigkeiten
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

Alternativ können Sie das neueste JAR von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

#### Lizenzbeschaffung
- Holen Sie sich eine [kostenlose Testlizenz](https://purchase.aspose.com/temporary-license/) für Testzwecke.
- Kaufen Sie eine Voll‑Lizenz über die [offizielle Aspose‑Website](https://purchase.aspose.com/buy) für den Produktionseinsatz.

### Einrichtung von Aspose.Slides für Java
1. **Fügen Sie die oben gezeigte Abhängigkeit** zu Ihrem Projekt hinzu.
2. **Wenden Sie die Lizenz** (falls vorhanden) an, bevor Sie Präsentationsobjekte erstellen.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Schritt‑für‑Schritt-Implementierung

### Schritt 1: Erstelle das Ausgabeverzeichnis (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Warum das wichtig ist:* Das Vorhandensein des Ordners verhindert `FileNotFoundException`, wenn Sie die Präsentation später speichern.

### Schritt 2: Füge eine Folie hinzu und füge ein Liniendiagramm ein
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Erklärung:* Dies erstellt eine neue Folie und platziert ein **Liniendiagramm mit Markern** an den angegebenen Koordinaten.

### Schritt 3: Füge den Diagrammtitel hinzu (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Tipp:* Ein fetter, grauer Titel macht das Diagramm sofort erkennbar.

### Schritt 4: Formatiere Achsen und füge Rasterlinien hinzu (add grid lines)
#### Vertikale Achsenformatierung
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Horizontale Achsenformatierung
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Warum das wichtig ist:* Klare Rasterlinien und gedrehte Beschriftungen verbessern die Lesbarkeit, besonders bei dichten Datenpunkten.

### Schritt 5: Passe die Legende an (add chart title – bereits behandelt, aber die Legende ist Teil der Gesamtdarstellung)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Schritt 6: Setze Hintergrundfarben (format chart labels – Teil des gesamten visuellen Stylings)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Schritt 7: Speichere die Präsentation
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Ergebnis:* Sie haben nun eine PowerPoint‑Datei (`FormattedChart_out.pptx`) mit einem vollständig formatierten Liniendiagramm.

## Praktische Anwendungen
- **Business‑Reports:** Quartalsleistung mit Trendlinien darstellen.
- **Bildungsfolien:** Wissenschaftliche Daten für Vorlesungen visualisieren.
- **Projektvorschläge:** Meilensteine und Prognosen hervorheben.
- **Marketing‑Analyse:** ROI‑Trends von Kampagnen präsentieren.
- **Dashboard‑Integration:** Live‑Daten nach PowerPoint exportieren für Stakeholder‑Meetings.

## Leistungsüberlegungen
- **Speicherverwaltung:** Rufen Sie stets `dispose()` auf dem `Presentation`‑Objekt auf, um native Ressourcen sofort freizugeben.

## Häufige Probleme und Lösungen
| Problem | Lösung |
|---------|--------|
| **Lizenz nicht angewendet** | Laden Sie die Test‑/Voll‑Lizenz, bevor Sie irgendwelche `Presentation`‑Objekte erstellen. |
| **Diagramm erscheint leer** | Stellen Sie sicher, dass die Folie tatsächlich Datenreihen enthält; fügen Sie bei Bedarf Reihen hinzu. |
| **Datei nicht gespeichert** | Vergewissern Sie sich, dass das Ausgabeverzeichnis existiert (verwenden Sie den Schritt „create directory java“). |
| **Farben nicht angewendet** | Verwenden Sie `Color`‑Konstanten aus `java.awt.Color` oder `PresetColor`. |

## Häufig gestellte Fragen

**F: Kann ich neben Liniendiagrammen auch andere Diagrammtypen erstellen?**  
A: Ja, Aspose.Slides unterstützt Balken-, Kreis-, Streu‑ und viele weitere Diagrammtypen.

**F: Wie füge ich mehrere Datenreihen zum Liniendiagramm hinzu?**  
A: Verwenden Sie `chart.getChartData().getSeries().add(...)`, um vor der Formatierung zusätzliche Reihen einzufügen.

**F: Ist es möglich, das Diagramm als Bild zu exportieren?**  
A: Absolut. Rufen Sie `chart.getChartData().getChartDataWorkbook().save(...)` auf oder rendern Sie die Folie in ein Bildformat.

**F: Benötige ich eine kostenpflichtige Lizenz für die Entwicklung?**  
A: Eine kostenlose temporäre Lizenz reicht für die Evaluierung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.

**F: Welche Java‑Versionen werden unterstützt?**  
A: Die Bibliothek funktioniert mit JDK 8 bis JDK 22 (verwenden Sie den passenden Klassifizierer, z. B. `jdk16`).

---

**Zuletzt aktualisiert:** 2026-03-07  
**Getestet mit:** Aspose.Slides für Java 25.4 (jdk16‑Klassifizierer)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
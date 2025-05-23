---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java ein Kreisdiagramm erstellen und anpassen. Diese Anleitung behandelt Einrichtung, Implementierung und praktische Anwendungen."
"title": "Erstellen Sie ein Kreisdiagramm in Java mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie mit Aspose.Slides ein Kreisdiagramm in Java: Ein umfassender Leitfaden

## Diagramme und Grafiken

### Einführung

Kreisdiagramme bieten in der Datenvisualisierung eine intuitive Möglichkeit, Proportionen innerhalb eines Datensatzes darzustellen. Bei komplexen Datensätzen, bei denen einige Segmente deutlich kleiner sind als andere, können herkömmliche Kreisdiagramme jedoch unübersichtlich und schwer zu interpretieren sein. Kreisdiagramme lösen dieses Problem, indem sie kleine Segmente in ein sekundäres Diagramm aufteilen und so die Lesbarkeit verbessern.

In diesem Tutorial lernen Sie, wie Sie mit Aspose.Slides für Java ein Kreisdiagramm erstellen und bearbeiten. Sie lernen, wie Sie Ihre Umgebung einrichten, das Diagramm erstellen, Eigenschaften wie Datenbeschriftungen und Teilungspositionen anpassen und Ihre Präsentation im PPTX-Format speichern. Am Ende beherrschen Sie diese Funktionen mit praktischen Anwendungen und Performance-Tipps.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für Java
- Erstellen eines Kreisdiagramms
- Anpassen von Diagrammeigenschaften wie Datenbeschriftungen und Teilungskonfigurationen
- Speichern Ihrer Präsentation auf der Festplatte

Bereit loszulegen? Schauen wir uns zuerst die Voraussetzungen an!

## Voraussetzungen

Bevor Sie unser Kreisdiagramm erstellen, stellen Sie sicher, dass Sie über Folgendes verfügen:

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten:
- **Aspose.Slides für Java**: Unverzichtbar für die programmgesteuerte Verwaltung von PowerPoint-Präsentationen.

### Anforderungen für die Umgebungseinrichtung:
- Auf Ihrem Computer ist ein Java Development Kit (JDK) installiert. Wir empfehlen die Verwendung von JDK 16 oder höher.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA, Eclipse oder NetBeans.

### Erforderliche Kenntnisse:
- Grundlegende Kenntnisse der Java-Programmierung
- Vertrautheit mit Maven oder Gradle für das Abhängigkeitsmanagement

## Einrichten von Aspose.Slides für Java

### Informationen zur Installation:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download**: Sie können die neueste Version herunterladen von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Schritte zum Lizenzerwerb:
- **Kostenlose Testversion**: Beginnen Sie mit einer 30-tägigen Testversion, um alle Funktionen zu erkunden.
- **Temporäre Lizenz**Fordern Sie eine temporäre Lizenz zur erweiterten Evaluierung an.
- **Kaufen**: Erwägen Sie den Kauf einer Lizenz, wenn Aspose.Slides Ihren Anforderungen entspricht.

### Grundlegende Initialisierung und Einrichtung

Sobald Sie die Bibliothek in Ihrem Projekt eingerichtet haben, initialisieren Sie sie, indem Sie eine Instanz der `Presentation` Klasse:

```java
Presentation presentation = new Presentation();
```

Damit ist die Grundlage für das Hinzufügen verschiedener Diagramme zu Ihren Folien geschaffen. Als Nächstes implementieren wir unser Kreisdiagramm.

## Implementierungshandbuch

### Erstellen eines Kreisdiagramms

#### Überblick
Wir beginnen mit der Erstellung einer Instanz eines `Presentation` Fügen Sie auf der ersten Folie ein Kreisdiagramm hinzu. Dieses Diagramm visualisiert Daten effektiv, indem es kleinere Segmente in einen zweiten Kreis unterteilt und so die Lesbarkeit verbessert.

#### Schritt 1: Erstellen Sie eine Instanz der Präsentationsklasse
```java
// Erstellen einer neuen Präsentation
ePresentation presentation = new Presentation();
```
Dieser Code initialisiert Ihre Präsentation, in der wir unsere Diagramme hinzufügen.

#### Schritt 2: Fügen Sie auf der ersten Folie ein Kreisdiagramm hinzu
```java
// Fügen Sie der ersten Folie an Position (50, 50) ein Kreisdiagramm mit der Größe (500 x 400) hinzu.
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Hier geben wir den Diagrammtyp an (`PieOfPie`) und seine Position und Abmessungen auf der Folie.

#### Schritt 3: Datenbeschriftungen festlegen, um Werte für die Reihe anzuzeigen
```java
// Konfigurieren von Datenbeschriftungen zum Anzeigen von Werten
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Dieser Schritt stellt sicher, dass jedes Segment unseres Kreisdiagramms den entsprechenden Wert anzeigt, was eine schnelle Dateninterpretation ermöglicht.

#### Schritt 4: Konfigurieren Sie die Größe des zweiten Kreises und teilen Sie ihn nach Prozent auf
```java
// Legen Sie die Größe des sekundären Kreises fest
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Den Kuchen prozentual aufteilen
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Festlegen der Teilungsposition
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Mit diesen Konfigurationen können Sie die Aufteilung und Anzeige kleinerer Segmente in Ihrem Diagramm anpassen und so die Übersichtlichkeit für den Betrachter verbessern.

#### Schritt 5: Speichern Sie die Präsentation im PPTX-Format auf der Festplatte
```java
// Ausgabeverzeichnis definieren
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Speichern Sie die Präsentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
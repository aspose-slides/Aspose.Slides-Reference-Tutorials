---
date: '2026-07-17'
description: Erfahren Sie, wie Sie Sunburst-Diagramme in PowerPoint mit Aspose Slides
  for Java hinzufügen. Die Schritt‑für‑Schritt-Anleitung behandelt die Einrichtung,
  die Diagrammerstellung, die Anpassung und Praxisbeispiele.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: So fügen Sie Sunburst-Diagramme in PowerPoint mit Aspose Slides for
  Java hinzu. Folgen Sie diesem Tutorial, um die Bibliothek einzurichten, ein Diagramm
  zu erstellen, Datenpunkte anzupassen und es in realen Projekten anzuwenden.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: So fügen Sie Sunburst-Diagramme in PowerPoint mit Aspose (Java) hinzu
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: So fügen Sie Sunburst-Diagramme in PowerPoint mit Aspose (Java) hinzu
url: /de/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So fügen Sie Sunburst-Diagramme in PowerPoint mit Aspose (Java) hinzu

## Einführung

Das Hinzufügen eines Sunburst-Diagramms zu einer PowerPoint-Präsentation kann eine flache Datentabelle sofort in eine ansprechende visuelle Hierarchie verwandeln. In diesem Tutorial lernen Sie **wie man Sunburst**-Diagramme in PowerPoint mit Aspose.Slides für Java hinzufügt, von der Einrichtung der Umgebung bis zur Feinabstimmung von Farben und Beschriftungen. Egal, ob Sie ein Vertriebs‑Dashboard, eine Projekt‑Aufgaben‑Aufschlüsselung oder ein Lern‑Slide‑Deck erstellen, die nachfolgenden Schritte bieten Ihnen eine produktionsreife Lösung.

**Was Sie lernen werden**
- Wie Sie Aspose.Slides in einem Maven‑ oder Gradle‑Projekt konfigurieren  
- Wie Sie eine neue Präsentation erstellen und ein Sunburst‑Diagramm einfügen  
- Wie Sie Datenpunkte, Beschriftungen und Füllfarben anpassen  
- Praxisbeispiele, in denen Sunburst‑Diagramme glänzen  

Lassen Sie uns beginnen und sehen, wie einfach es ist, rohe Hierarchiedaten in ein poliertes PowerPoint‑Visual zu verwandeln.

## Schnelle Antworten
- **Primäre Bibliothek?** Aspose.Slides für Java  
- **Unterstützter Diagrammtyp?** Sunburst (radial hierarchisch)  
- **Mindest‑Java‑Version?** JDK 16  
- **Typische Implementierungszeit?** 10‑15 Minuten für ein Basis‑Diagramm  
- **Lizenz für Produktion erforderlich?** Ja, eine gültige Aspose‑Lizenz  

## Was ist ein Sunburst-Diagramm?
Ein Sunburst‑Diagramm ist ein radiales Diagramm, das hierarchische Daten visualisiert, indem Ringe vom Zentrum nach außen geschichtet werden. Es ist ideal, um mehrstufige Beziehungen wie Organisationsstrukturen, Produktkategorien oder Dateisystembäume darzustellen. Jeder konzentrische Ring repräsentiert eine Ebene der Hierarchie, und die Größe jedes Segments spiegelt dessen quantitativen Wert wider, sodass Betrachter sowohl Struktur als auch Umfang schnell erfassen können.

## Warum Aspose.Slides für Java verwenden?
Aspose.Slides unterstützt **mehr als 50 Diagrammtypen** und kann Präsentationen mit **bis zu 10.000 Folien** manipulieren, ohne die gesamte Datei in den Speicher zu laden, was hohe Leistung für unternehmensweite Berichte liefert. Es ist plattformübergreifend, bietet umfangreiche API‑Abdeckung und beinhaltet robuste Lizenzoptionen, die Evaluationsbeschränkungen entfernen – ideal für Produktionsumgebungen.

## Voraussetzungen
- **Java Development Kit (JDK)** 16 oder neuer  
- **IDE** – IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor  
- Grundlegende Kenntnisse der Java‑Syntax und von Maven/Gradle‑Build‑Tools  

## Einrichtung von Aspose.Slides für Java

### Maven-Abhängigkeit
Fügen Sie das Aspose.Slides‑Maven‑Artefakt zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle-Abhängigkeit
Wenn Sie Gradle bevorzugen, fügen Sie die folgende Zeile in `build.gradle` ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Sie können das neueste JAR auch direkt von der offiziellen Release‑Seite herunterladen: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lizenzbeschaffung
Um ohne Evaluationsbeschränkungen zu arbeiten, erhalten Sie eine Lizenz:
- **Kostenlose Testversion** – temporäre Lizenz für schnelle Evaluierung.  
- **Temporäre Lizenz** – beantragen Sie eine von der [Aspose‑Website](https://purchase.aspose.com/temporary-license).  
- **Vollkauf** – erwerben Sie ein Abonnement für uneingeschränkte Produktion.

### Grundlegende Initialisierung
Die Klasse `Presentation` ist der Einstiegspunkt zum Erstellen oder Öffnen von PowerPoint‑Dateien.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Implementierungsleitfaden

### Wie fügt man ein Sunburst‑Diagramm zu einer PowerPoint‑Präsentation mit Aspose.Slides für Java hinzu?

Laden Sie eine neue `Presentation`, fügen Sie eine Folie hinzu, setzen Sie ein `IChart` vom Typ `ChartType.Sunburst` ein und rufen Sie `save` auf. Dieses kompakte Drei‑Schritte‑Muster erzeugt ein voll funktionsfähiges Sunburst‑Diagramm, das weiter angepasst werden kann.

#### Schritt 1: Präsentation initialisieren
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Schritt 2: Sunburst‑Diagramm hinzufügen
Die `IChart`‑Schnittstelle definiert ein Diagrammobjekt, das auf jeder Folie platziert werden kann. Hier fügen wir ein Sunburst‑Diagramm bei den Koordinaten (100, 100) mit einer Größe von 450 × 400 Punkten hinzu.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Schritt 3: Präsentation speichern
Speichern Sie Ihre Änderungen stets durch Aufruf von `save`. Sie können PPTX, PDF oder eines der über 50 unterstützten Ausgabeformate wählen.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Datenpunkte im Diagramm ändern

#### Übersicht
Sie können jedes Segment des Sunburst‑Diagramms – Beschriftungen, Farben und Sichtbarkeit – über die Datenpunktesammlung des Diagramms anpassen.

#### Schritt 1: Zugriff auf die Datenpunktesammlung
Die erste Serie des Diagramms enthält eine Sammlung von `IChartDataPoint`‑Objekten, die jedes Segment repräsentieren.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Schritt 2: Wert für einen bestimmten Datenpunkt anzeigen
Setzen Sie `IsValueShown` auf `true` beim gewünschten Datenpunkt, um dessen numerischen Wert direkt im Segment anzuzeigen.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Schritt 3: Beschriftungsformate ändern
Passen Sie die Sichtbarkeit, Schriftfarbe und den Hintergrund der Beschriftungen an, um die Lesbarkeit zu verbessern.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Schritt 4: Füllfarbe für Datenpunkte festlegen
Gestalten Sie die Füllfarbe einzelner Segmente nach Ihrer Markenpalette oder zur Hervorhebung wichtiger Abschnitte.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Schritt 5: Geänderte Präsentation speichern
Speichern Sie das angepasste Diagramm erneut, indem Sie die Präsentation erneut sichern.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktische Anwendungen

1. **Business Analytics** – Visualisieren Sie Verkäufe nach Region → Produktlinie → SKU in einer einzigen radialen Ansicht.  
2. **Projektmanagement** – Zeigen Sie Work‑Breakdown‑Strukturen, von Phasen zu Aufgaben zu Unteraufgaben.  
3. **Bildung** – Abbilden Sie Curriculum‑Hierarchien, z. B. Fakultäten → Kurse → Module.  

## Leistungsüberlegungen

- **Speichereffizienz:** Aspose.Slides streamt Daten, sodass selbst ein 500‑seitiges Deck mit mehreren Diagrammen unter 200 MB RAM bleibt.  
- **Garbage Collection:** Geben Sie Folienobjekte (`slide.dispose()`) frei, wenn sie nicht mehr benötigt werden, um Speicherlecks zu vermeiden.  

## Häufig gestellte Fragen

**Q: Was ist ein Sunburst-Diagramm?**  
A: Ein Sunburst-Diagramm visualisiert hierarchische Daten in konzentrischen Ringen, wobei jeder Ring eine Ebene der Hierarchie darstellt.

**Q: Wie installiere ich Aspose.Slides für Java mit Maven?**  
A: Fügen Sie die im Abschnitt „Maven‑Abhängigkeit“ gezeigte Maven‑Abhängigkeit zu Ihrer `pom.xml` hinzu und führen Sie `mvn clean install` aus.

**Q: Kann ich andere Diagrammtypen mit Aspose.Slides anpassen?**  
A: Ja, die Bibliothek unterstützt über 50 Diagrammtypen, darunter Säulen-, Linien-, Kreis‑ und Radar‑Diagramme.

**Q: Meine Präsentation wird nicht gespeichert – was sollte ich überprüfen?**  
A: Prüfen Sie, ob der Dateipfad korrekt ist, das Verzeichnis existiert und Sie Schreibrechte besitzen. Stellen Sie außerdem sicher, dass die Methode `Presentation.save()` aufgerufen wird.

**Q: Wo kann ich weitere Hilfe oder Beispiele erhalten?**  
A: Besuchen Sie das [Aspose‑Forum](https://forum.aspose.com/c/slides/11) oder konsultieren Sie die offizielle [Aspose.Slides‑Referenz](https://reference.aspose.com/slides/java/).

## Ressourcen
- **Dokumentation:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referenz (kleingeschrieben):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Community‑Forum:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Downloads:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Zuletzt aktualisiert:** 2026-07-17  
**Getestet mit:** Aspose.Slides für Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Diagramme in PowerPoint mit Aspose.Slides für Java animieren – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Diagramm in Java mit Aspose.Slides erstellen – Diagramme hinzufügen & validieren](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
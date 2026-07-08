---
date: '2026-07-08'
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Kreisdiagrammen mithilfe
  von Aspose.Slides für Java hinzufügen. Folgen Sie dieser Schritt-für-Schritt-Anleitung,
  um professionelle Kreisdiagramme zu erstellen und anzupassen.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Kreisdiagramm zu PowerPoint mit Aspose.Slides für Java hinzufügen.
  Dieses Tutorial zeigt, wie man Kreisdiagramme programmgesteuert erzeugt und anpasst
  – ideal für automatisierte Berichte.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Kreisdiagramm in PowerPoint mit Aspose.Slides für Java hinzufügen – Schnell-Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Wie man ein Kreisdiagramm in PowerPoint mit Aspose.Slides für Java hinzufügt
url: /de/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kreisdiagramm-PowerPoint mit Aspose.Slides für Java hinzufügen

## Einleitung

Wenn Sie **Kreisdiagramm-PowerPoint hinzufügen** Folien benötigen, ohne PowerPoint manuell zu öffnen, sind Sie hier richtig. In diesem Leitfaden führen wir Sie durch die Einrichtung von Aspose.Slides für Java, das Erstellen eines Kreisdiagramms und die Anpassung jedes Segments – perfekt für automatisierte Berichte, Dashboards oder personalisierte Präsentationen. Am Ende haben Sie ein wiederverwendbares Java‑Snippet, das in Sekunden eine professionell aussehende Kreisdiagramm‑PowerPoint‑Datei erzeugt.

### Schnelle Antworten
- **Welche Bibliothek erstellt das Diagramm?** Aspose.Slides für Java (neueste Version).  
- **Kann ich es head‑less ausführen?** Ja – keine Office-Installation erforderlich.  
- **Welche Java-Version ist optimal?** JDK 16+ für beste Leistung und GC‑Verbesserungen.  
- **Wie kann ich ein Segment hervorheben?** Rufen Sie `setExplosion` auf dem `IDataPoint` auf und setzen Sie einen Pixel‑Versatz.  
- **Benötige ich eine Lizenz für die Produktion?** Eine Testversion funktioniert für die Entwicklung; eine permanente Lizenz entfernt alle Evaluationsbeschränkungen.

## Warum Kreisdiagramm-PowerPoint mit Aspose.Slides für Java hinzufügen?

Sie können aktuelle visuelle Berichte direkt aus Ihren Backend‑Diensten erzeugen, manuelle Kopier‑ und Einfügefehler vermeiden und ein markenkonformes Styling garantieren. Aspose.Slides unterstützt **70+ Diagrammtypen** und kann Präsentationen mit **10.000+ Folien** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, was es ideal für groß angelegte Automatisierung macht.

## Voraussetzungen

- **Aspose.Slides für Java** – das Tutorial bezieht sich auf Version 25.4 (die zum Zeitpunkt des Schreibens aktuelle Version).  
- **Java Development Kit** – JDK 16 oder neuer wird empfohlen.  
- **Maven** oder **Gradle** zur Verwaltung von Abhängigkeiten.  

## Einrichtung von Aspose.Slides für Java

### Maven
Fügen Sie diese Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie das Folgende in Ihre `build.gradle`‑Datei ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativ können Sie die neueste Version direkt von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzierung
Um Aspose.Slides ohne Einschränkungen zu nutzen:

- Beginnen Sie mit einer **kostenlosen Testversion**, um die API zu evaluieren.  
- Fordern Sie eine **temporäre Lizenz** für erweiterte Tests auf der Seite [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/) an.  
- Kaufen Sie ein vollständiges Abonnement über die [Kaufseite](https://purchase.aspose.com/buy).

## Wie man ein Kreisdiagramm-PowerPoint mit Aspose.Slides für Java hinzufügt

Laden Sie eine neue Präsentation, fügen Sie ein Kreisdiagramm ein und speichern Sie die Datei – alles in drei kurzen Schritten. Dieses Muster funktioniert für Datensätze jeder Größe und kann in einer Schleife verpackt werden, um Dutzende von Folien automatisch zu erzeugen. Der Ansatz ist leichtgewichtig, erfordert nur wenige Codezeilen und keine externen Ressourcen, wodurch er sowohl für kleine Hilfsprogramme als auch für große Batch‑Jobs geeignet ist.

### Schritt 1: Präsentation initialisieren
Die Klasse `Presentation` repräsentiert eine einzelne PowerPoint‑Datei im Speicher. Das Erstellen einer Instanz liefert Ihnen ein frisches, leeres Folienset zum Arbeiten.
```java
Presentation pres = new Presentation();
```

### Schritt 2: Kreisdiagramm hinzufügen
Fügen Sie ein Kreisdiagramm auf die erste Folie ein. Die Koordinaten (50, 50) und die Größe (600 × 400) passen zu einem Standard‑16:9‑Layout und lassen Platz für Titel.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Schritt 3: Präsentation speichern
Schreiben Sie die Präsentation auf die Festplatte. Ersetzen Sie `YOUR_OUTPUT_DIRECTORY` durch den Ordner, in dem Sie die Datei speichern möchten.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Schritt 4: Ressourcen bereinigen
Entsorgen Sie das `Presentation`‑Objekt, um native Ressourcen freizugeben und Speicherlecks zu vermeiden.
```java
if (pres != null) pres.dispose();
```

## Wie man die Hervorhebung und Farbe von Datenpunkten anpasst?

Laden Sie das Diagramm, finden Sie den Ziel‑Datenpunkt und wenden Sie dann einen Explosions‑Versatz sowie eine einfarbige Füllfarbe an. Dadurch hebt sich das Segment zur Betonung ab. Diese Anpassungen helfen, die Aufmerksamkeit des Publikums auf kritische Werte zu lenken und die Gesamtablesbarkeit des Diagramms zu verbessern.

### Schritt 1: Vorhandene Präsentation laden (oder die gerade erstellte wiederverwenden)
Das `Presentation`‑Objekt lädt eine vorhandene PowerPoint‑Datei in den Speicher, sodass Sie deren Inhalt ändern können.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Schritt 2: Auf das Diagramm und den Ziel‑Datenpunkt zugreifen
Das Interface `IDataPoint` repräsentiert einen einzelnen Datenpunkt (Segment) innerhalb einer Diagrammserie.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Schritt 3: Explosions‑ und Farb‑Anwendung
`setExplosion(int)` legt die Entfernung in Pixeln fest, um die ein Segment vom Diagrammmittelpunkt versetzt wird. Trennen Sie das Segment visuell mit `setExplosion(20)` und ändern Sie die Füllung zu Blau mittels `setFillType(FillType.Solid)` und `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Schritt 4: Speichern und Entsorgen
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktische Anwendungen
- **Verkaufsberichte:** Hervorhebung der meistverkauften Produkte mit hervorgehobenen Segmenten.  
- **Budgetanalyse:** Zuweisung unterschiedlicher Farben zu Abteilungen für schnellen visuellen Vergleich.  
- **Bildungsfolien:** Aufschlüsselung komplexer Konzepte in verdauliche Diagrammsegmente.  

## Leistungsüberlegungen
- **Objekte entsorgen** Sie umgehend, um Speicherlecks zu vermeiden, insbesondere beim Erzeugen vieler Folien in einer Schleife.  
- **Heap‑Nutzung überwachen** bei großen Präsentationen; verwenden Sie die `Save`‑Überladung, die einen `OutputStream` akzeptiert, um Daten zu streamen und den Speicherverbrauch gering zu halten.  
- Bleiben Sie bei **JDK 16+**, um von den neuesten Garbage‑Collection‑Verbesserungen zu profitieren, die die Verarbeitungszeit um bis zu 30 % für 1.000‑Folien‑Decks reduzieren können.

## Fazit
Sie haben nun einen vollständigen, produktionsbereiten Workflow, um **Kreisdiagramm-PowerPoint**‑Dateien mit Aspose.Slides für Java hinzuzufügen. Experimentieren Sie mit verschiedenen Explosionsabständen, Farben und Datensätzen, um Ihre Markenidentität zu treffen. Wenn Sie bereit sind, erkunden Sie weitere Diagrammtypen – Balken, Linien oder Streudiagramme –, um ein vollständiges Analyse‑Dashboard in PowerPoint zu erstellen.

## Häufig gestellte Fragen

**Q: Was ist der größte Vorteil der Verwendung von Aspose.Slides für Java?**  
A: Es ermöglicht Ihnen, PowerPoint‑Dateien programmgesteuert zu erstellen, zu bearbeiten und zu rendern, ohne dass Microsoft Office installiert sein muss, und unterstützt über 70 Diagrammtypen sowie mehr als 100 Dateiformate.

**Q: Kann ich eine PowerPoint‑Datei von Grund auf neu erzeugen?**  
A: Ja, instanziieren Sie ein `Presentation`‑Objekt, fügen Sie Folien, Diagramme oder Formen hinzu und rufen Sie anschließend `save` auf – alles in reinem Java‑Code.

**Q: Wie kann ich ein bestimmtes Kreisdiagramm‑Segment hervorheben?**  
A: Rufen Sie das `IDataPoint` für das Segment ab und rufen Sie `setExplosion(pixelOffset)` auf. Der Versatz definiert, wie weit das Segment nach außen verschoben wird.

**Q: Gibt es ein Limit für die Anzahl der Folien, die ich erstellen kann?**  
A: Aspose.Slides kann Präsentationen mit bis zu **10.000 Folien** in einer einzigen Datei verarbeiten, vorausgesetzt, Sie streamen die Ausgabe, um zu vermeiden, dass alles in den Speicher geladen wird.

**Q: Wo finde ich weiterführende Beispiele zur Diagramm‑Anpassung?**  
A: Sehen Sie sich die offizielle [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte API‑Referenzen und Beispielprojekte an.

## Ressourcen
- **Dokumentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Bibliothek herunterladen:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Lizenz erwerben:** [Aspose.Slides kaufen](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion:** [Aspose.Slides ausprobieren](https://releases.aspose.com/slides/java/)  
- **Temporäre Lizenz:** [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)  
- **Support-Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Zuletzt aktualisiert:** 2026-07-08  
**Getestet mit:** Aspose.Slides für Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Diagramme in PowerPoint mit Aspose.Slides für Java animieren – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Diagrammlayouts in PowerPoint mit Aspose.Slides für Java erstellen und validieren | SEO‑optimierte Anleitung](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-09-17'
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java ein Bubble-Chart in
  PowerPoint erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie ein Diagramm zur Folie
  hinzufügen, die Bubble-Größe konfigurieren und die PPTX effizient speichern.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Erfahren Sie, wie Sie mit Aspose.Slides für Java ein Bubble-Chart
  in PowerPoint erstellen. Dieses Tutorial erklärt, wie Sie ein Diagramm zur Folie
  hinzufügen, die Bubble-Größen anpassen und die Präsentation effizient speichern.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Bubble-Chart in PowerPoint mit Aspose.Slides für Java erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Bubble-Chart in PowerPoint mit Aspose.Slides für Java erstellen
url: /de/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstelle Bubble‑Diagramm‑PowerPoint mit Aspose.Slides für Java

## Einführung
Wenn Sie programmgesteuert **bubble chart powerpoint erstellen**‑Präsentationen erstellen müssen, bietet Aspose.Slides für Java eine saubere serverseitige API, die ohne Microsoft Office funktioniert. In diesem Tutorial lernen Sie, wie Sie ein Diagramm zu einer Folie hinzufügen, die Bubble‑Größen steuern und die endgültige PPTX speichern, während Sie Ressourcen effizient verwalten. Die Schritte sind aufgeteilt, sodass Sie den Code in jedes Java‑Projekt kopieren‑und‑einfügen können und sofort Ergebnisse sehen.

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Slides for Java
- **Welche Java‑Version ist erforderlich?** JDK 16 oder höher
- **Wie füge ich ein Bubble‑Diagramm hinzu?** Rufen Sie `addChart(ChartType.Bubble, …)` auf einer Folie auf
- **Kann ich die Bubble‑Größe ändern?** Ja, über `setBubbleSizeScale()`
- **Wie speichere ich die Datei?** Verwenden Sie `pres.save("Result.pptx", SaveFormat.Pptx)`

## Was ist das Erstellen eines bubble chart powerpoint?
Ein Bubble‑Diagramm in PowerPoint zu erstellen bedeutet, programmgesteuert ein Diagramm zu erzeugen, bei dem jeder Datenpunkt durch eine Blase dargestellt wird, deren X‑Position, Y‑Position und Größe drei Daten‑dimensionen kodieren. Aspose.Slides für Java übernimmt das Rendering, sodass Sie PowerPoint nicht installiert haben müssen.

## Warum Aspose.Slides für Java verwenden?
Aspose.Slides unterstützt **über 50 Diagrammtypen**, kann Präsentationen bis zu **2 GB** verarbeiten, ohne die gesamte Datei in den Speicher zu laden, und läuft auf jeder Plattform, die Java 16+ unterstützt. Diese quantifizierten Fähigkeiten machen es zu einer zuverlässigen Wahl für Unternehmens‑Reporting.

## Voraussetzungen
- **Java Development Kit** 16 oder neuer installiert.
- **Aspose.Slides for Java**‑Bibliothek (über Maven, Gradle oder direkten JAR‑Download hinzufügen).
- Grundlegende Kenntnisse der Java‑Syntax und objektorientierten Programmierung.

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides zu nutzen, binden Sie die Bibliothek in Ihr Build‑System ein.

### Maven
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml` hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie dies in Ihre `build.gradle` ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct download
Sie können das neueste JAR auch von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

#### License acquisition
- **Free trial** – alle Funktionen kostenlos testen.  
- **Temporary license** – erweiterte Evaluierung für größere Projekte.  
- **Full license** – erforderlich für den Produktionseinsatz.

### Basic initialization and setup
Die Klasse `Presentation` ist der Einstiegspunkt zum Erstellen oder Laden von PowerPoint‑Dateien.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Implementierungs‑Leitfaden
Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung zum Erstellen eines Bubble‑Diagramms und zum Verwalten von Ressourcen.

## Wie man ein bubble chart powerpoint erstellt
In diesem Abschnitt lernen Sie die genaue Reihenfolge der API‑Aufrufe, die zum Erzeugen eines Bubble‑Diagramms, zur Konfiguration seiner visuellen Eigenschaften und zum Speichern des Ergebnisses als PPTX‑Datei erforderlich sind. Der Ansatz funktioniert für jedes Java‑Projekt, das Aspose.Slides einbindet und bewährte Verfahren zur Ressourcenverwaltung befolgt.

Laden Sie die Präsentation, fügen Sie ein Bubble‑Diagramm hinzu, konfigurieren Sie dessen Erscheinungsbild und speichern Sie die Datei.

### Direct answer
Erstellen Sie eine neue `Presentation`, rufen Sie `addChart(ChartType.Bubble, …)` auf der gewünschten Folie auf, passen Sie die Bubble‑Größenskala mit `setBubbleSizeScale(150)` an und speichern Sie anschließend mit `pres.save("Result.pptx", SaveFormat.Pptx)`. Diese Sequenz fügt ein voll funktionsfähiges Bubble‑Diagramm in nur wenigen Java‑Zeilen hinzu.

- **`ChartType.Bubble`** stellt den Bubble‑Diagrammtyp dar.  
- **`addChart`** fügt ein neues Diagramm des angegebenen Typs in eine Folie ein.  
- **`setBubbleSizeScale`** passt die Gesamtabmessungen der Bubbles im Diagramm an.  
- **`SaveFormat.Pptx`** gibt das PPTX‑Dateiformat zum Speichern an.  

#### Step‑by‑step implementation
**1. Präsentation initialisieren** – Instanziieren Sie das Objekt `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Bubble‑Diagramm hinzufügen** – fügen Sie das Diagramm an den gewählten Koordinaten ein.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` weist Aspose.Slides an, ein Bubble‑Diagramm zu erstellen.  
- Die numerischen Parameter definieren die X/Y‑Position sowie Breite/Höhe in Punkten.

**3. Bubble‑Größenskala konfigurieren** – vergrößern Sie die Bubbles für bessere visuelle Wirkung.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Das Setzen der Skala auf **150 %** macht jede Bubble 1,5 × größer als der Standard.

**4. Präsentation speichern** – schreiben Sie die PPTX auf die Festplatte.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Troubleshooting tips
- Stellen Sie sicher, dass Schreibrechte für das Ausgabeverzeichnis vorhanden sind.  
- Bestätigen Sie, dass das Aspose.Slides‑JAR zur verwendeten JDK‑Version passt.

## Wie man PowerPoint‑Ressourcen effektiv verwaltet
Effizientes Ressourcenmanagement verhindert Speicherlecks und hält den JVM‑Fußabdruck gering, insbesondere beim Verarbeiten großer Präsentationen oder im Serverbetrieb. Befolgen Sie das untenstehende Muster, um sicherzustellen, dass native Ressourcen selbst bei Ausnahmen freigegeben werden.

Effizientes Ressourcenhandling verhindert Speicherlecks, insbesondere beim Verarbeiten großer Decks.

### Direct answer
Nachdem Sie die Arbeit mit einer `Presentation` abgeschlossen haben, rufen Sie stets `pres.dispose()` innerhalb eines `try‑finally`‑Blocks auf; dies gibt native Ressourcen frei und ermöglicht der JVM, den Speicher umgehend zurückzugewinnen.

- **`pres.dispose()`** gibt die von der Präsentation genutzten nativen Ressourcen frei.

**1. Erstellen und ändern** – arbeiten Sie nach Bedarf mit der Präsentation.  
```java
Presentation pres = new Presentation();
```

**2. Ressourcen freigeben** – Speicher freigeben, sobald die Verarbeitung abgeschlossen ist.  
```java
if (pres != null) pres.dispose();
```

## Praktische Anwendungen
Bubble‑Diagramme eignen sich hervorragend für Szenarien, in denen drei Daten‑dimensionen gleichzeitig visualisiert werden müssen:

1. **Marktanalyse** – die Bubble‑Größe stellt den Umsatz dar, während die X/Y‑Achsen Wachstum und Marktanteil zeigen.  
2. **Leistungskennzahlen** – vergleichen Sie die Produktivität von Mitarbeitern (X), Zufriedenheit (Y) und Einfluss (Größe).  
3. **Geodaten** – stellen Sie Städte dar, wobei die Bevölkerung in der Bubble‑Größe kodiert ist.  
4. **Projektmanagement** – visualisieren Sie Zeitplan (X), Kosten (Y) und Risiko (Größe) auf einer einzigen Folie.

## Leistungs‑Überlegungen
- **Ressourcennutzung** – geben Sie Präsentationen umgehend frei, um den Heap‑Verbrauch gering zu halten.  
- **Java‑Speicherverwaltung** – kapseln Sie die Arbeit mit Präsentationen in `try‑finally`, um die Freigabe auch bei Ausnahmen zu garantieren.  
- **Aktuell bleiben** – aktualisieren Sie auf die neueste Aspose.Slides‑Version, um von Leistungsoptimierungen und Fehlerbehebungen zu profitieren.

## Häufig gestellte Fragen

**Q: Was ist Aspose.Slides für Java?**  
A: Aspose.Slides für Java ist eine eigenständige Bibliothek, mit der Sie PowerPoint‑Dateien erstellen, bearbeiten und konvertieren können, ohne Microsoft Office zu benötigen.

**Q: Wie integriere ich Aspose.Slides in mein bestehendes Java‑Projekt?**  
A: Fügen Sie die zuvor gezeigte Maven‑ oder Gradle‑Abhängigkeit hinzu oder legen Sie das JAR in Ihren Klassenpfad, dann importieren Sie `com.aspose.slides.*`.

**Q: Kann ich Aspose.Slides für große Präsentationen verwenden?**  
A: Ja, die Bibliothek verarbeitet effizient Präsentationen bis zu **2 GB** und unterstützt Streaming, um das Laden der gesamten Datei in den Speicher zu vermeiden.

**Q: Welche Diagrammtypen stehen neben Bubble‑Diagrammen zur Verfügung?**  
A: Über **50 Diagrammtypen** werden unterstützt, darunter Balken-, Linien-, Kreis-, Radar‑ und Wasserfalldiagramme.

**Q: Gibt es integrierte Unterstützung für das Stylen von Diagrammelementen?**  
A: Auf jeden Fall. Sie können Farben, Schriftarten, Rahmen und Datenbeschriftungen über die `ChartSeries`‑ und `ChartTitle`‑Objekte des Diagramms anpassen.

## Ressourcen
- **Documentation**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Zuletzt aktualisiert:** 2026-09-17  
**Getestet mit:** Aspose.Slides für Java 25.4 (jdk16)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man ein Diagramm zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java PowerPoint‑Diagramm mit Aspose.Slides erstellen](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [PowerPoint‑Diagramm in Java erstellen – Präsentationen mit Diagrammen speichern mit Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
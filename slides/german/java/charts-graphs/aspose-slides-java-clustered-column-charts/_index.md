---
date: '2026-08-27'
description: Erfahren Sie, wie Sie ein clustered column chart in Java mit Aspose.Slides
  erstellen, das Diagramm hinzufügen, automatische Serienfarben festlegen und die
  Präsentation als PPTX speichern.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Erfahren Sie, wie Sie ein clustered column chart in Java mit Aspose.Slides
  erstellen, das Diagramm hinzufügen, automatische Serienfarben festlegen und die
  Präsentation als PPTX speichern – alles mit klaren Schritt‑für‑Schritt‑Anleitungen.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Erstellen Sie ein clustered column chart in Java mit Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Wie man ein clustered column chart in Java mit Aspose.Slides erstellt
url: /de/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein gruppiertes Säulendiagramm in Java mit Aspose.Slides erstellt

## Einleitung
Das programmgesteuerte Erstellen eines gruppierten Säulendiagramms spart Ihnen Stunden manueller Formatierung und garantiert Konsistenz über mehrere Präsentationen hinweg. In diesem Tutorial lernen Sie **wie man ein gruppiertes Säulendiagramm** in Java mit Aspose.Slides erstellt, **wie man ein Diagramm hinzufügt**, **wie man Farben festlegt** und **wie man die Präsentation als PPTX speichert**. Wir decken alles ab, von der Installation der Bibliothek bis zur Anpassung der Füllfarben von Serien und dem Persistieren der Datei, sodass Sie reichhaltige Datenvisualisierungen in jede PowerPoint‑Präsentation einbetten können.

## Schnelle Antworten
- **Welche Hauptklasse wird für die Arbeit mit Präsentationen verwendet?** `Presentation` aus dem Paket `com.aspose.slides`.  
- **Wie füge ich ein gruppiertes Säulendiagramm hinzu?** Rufen Sie `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)` auf.  
- **Können Serienfarben automatisch gesetzt werden?** Ja – aktivieren Sie `setAutomaticSeriesColor(true)` für jede Serie.  
- **Welches Format sollte ich zum Speichern der Datei verwenden?** `SaveFormat.Pptx` erzeugt eine Standard‑PowerPoint‑Datei.  
- **Ist für die Produktion eine Lizenz erforderlich?** Eine Testversion funktioniert für die Entwicklung; für den kommerziellen Einsatz ist eine Voll‑Lizenz nötig.

## Was ist ein gruppiertes Säulendiagramm?
Ein gruppiertes Säulendiagramm zeigt mehrere Datenreihen nebeneinander für jede Kategorie, sodass Werte über Gruppen hinweg leicht verglichen werden können. Aspose.Slides unterstützt diesen Diagrammtyp von Haus aus und ermöglicht die vollständige programmgesteuerte Steuerung aller visuellen Aspekte.

## Warum ein gruppiertes Säulendiagramm mit Aspose.Slides erstellen?
Aspose.Slides kann **mehr als 50 Eingabe‑ und Ausgabeformate** verarbeiten und Präsentationen mit **Hunderten von Folien** handhaben, ohne die gesamte Datei in den Speicher zu laden. Diese Effizienz bedeutet, dass Sie große Decks in einer serverseitigen Umgebung mit minimalem Ressourcenverbrauch erzeugen können.

## Voraussetzungen
- **Java Development Kit** 16 oder neuer.  
- **Maven** oder **Gradle** für das Abhängigkeitsmanagement.  
- Grundlegende Kenntnisse der Java‑Syntax und objektorientierter Konzepte.  

### Erforderliche Bibliotheken und Abhängigkeiten
Sie benötigen die Aspose.Slides for Java‑Bibliothek (Version 25.4 oder höher). Die Bibliothek ist vollständig kompatibel mit JDK 16 und bietet eine umfangreiche API zur Diagrammbearbeitung.

### Anforderungen an die Umgebung
Ihre IDE (IntelliJ IDEA, Eclipse, VS Code) muss so konfiguriert sein, dass Java 16‑Code kompiliert und Maven/Gradle‑Abhängigkeiten aufgelöst werden können.

### Erforderliche Vorkenntnisse
Ein Verständnis der PowerPoint‑Folienstruktur und grundlegender Diagrammbegriffe (Serien, Kategorien, Datenpunkte) erleichtert das schnelle Nachvollziehen der Beispiele.

## Einrichtung von Aspose.Slides für Java
Integrieren Sie die Bibliothek in Ihr Projekt mit einer der folgenden Methoden.

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

**Direkter Download** – holen Sie sich das JAR von der offiziellen Release‑Seite: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Schritte zum Erwerb einer Lizenz
- **Kostenlose Testversion** – registrieren Sie sich auf der Aspose‑Website, um eine temporäre Lizenzdatei zu erhalten.  
- **Temporäre Lizenz** – beantragen Sie eine 30‑tägige Lizenz für umfangreichere Tests.  
- **Voll‑Lizenz** – erwerben Sie sie für uneingeschränkte Produktion.

**Grundlegende Initialisierung und Einrichtung**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Wie fügt man ein gruppiertes Säulendiagramm hinzu?
`Presentation` repräsentiert eine PowerPoint‑Datei im Speicher.  

**Direkte Antwort:**  
Erzeugen Sie ein `Presentation`‑Objekt, das eine PowerPoint‑Datei im Speicher darstellt, holen Sie die erste Folie und rufen Sie `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)` auf. Dieser einzelne Aufruf fügt ein voll funktionsfähiges gruppiertes Säulendiagramm ein, das bereit für die Datenbefüllung ist, und positioniert es an den angegebenen Koordinaten auf der Folie.

### Funktion 1: gruppiertes Säulendiagramm erstellen
Die Klasse `Presentation` repräsentiert eine PowerPoint‑Datei im Speicher und bietet Zugriff auf Folien, Formen und Diagrammobjekte.

**Schritt 1: Präsentation initialisieren**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Schritt 2: gruppiertes Säulendiagramm hinzufügen**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Schritt 3: Ressourcen bereinigen**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Wie legt man Farben für das Diagramm fest?
`Series` stellt eine Sammlung von Datenpunkten innerhalb eines Diagramms dar.  

**Direkte Antwort:**  
Nachdem das Diagramm erstellt wurde, erhalten Sie über `chart.getChartData()` die Diagrammdaten und iterieren über jedes `Series`‑Objekt. Für jede Serie rufen Sie `setAutomaticSeriesColor(true)` auf der übergeordneten Serie auf. Aspose.Slides weist dann automatisch eine eindeutige, kontrastreiche Farbe aus seiner Palette jeder Serie zu, wodurch visuelle Klarheit ohne manuelle Farbauswahl entsteht.

### Funktion 2: automatische Füllfarbe für Reihen festlegen
`IChart` ist das Interface, das ein Diagramm‑Shape repräsentiert; es stellt `getChartData()` für die Manipulation von Serien bereit.

**Schritt 1: Diagramm zugreifen und Reihen durchlaufen**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Schritt 2: Ressourcenverwaltung**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Wie speichert man die Präsentation als PPTX?
`save` schreibt die Präsentation in eine Datei im gewählten Format.  

**Direkte Antwort:**  
Geben Sie einen Ausgabepfad wie `"output/ClusteredColumnChart.pptx"` an und rufen Sie `presentation.save(outputPath, SaveFormat.Pptx)` auf. Die `save`‑Methode serialisiert das gesamte Foliendeck, einschließlich aller Formen, Diagramme und Ressourcen, in eine standardkonforme PPTX‑Datei, die von PowerPoint 2010 oder neuer sowie vielen Online‑Viewern geöffnet werden kann.

### Funktion 3: Präsentation auf Festplatte speichern
Das Speichern mit `SaveFormat.Pptx` erzeugt eine Datei, die mit PowerPoint 2010 und neueren Versionen sowie den meisten Online‑Viewern kompatibel ist.

**Schritt 1: Ausgabepfad definieren**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Schritt 2: Präsentation speichern**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Praktische Anwendungen
- **Finanzberichte** – quartalsweise Umsätze über Produktlinien hinweg vergleichen.  
- **Marketing‑Analysen** – Kampagnenleistung nach Region visualisieren.  
- **Projektmanagement** – Sprint‑Velocity oder Ressourcenverteilung über Teams hinweg darstellen.  

## Leistungsüberlegungen
- `Presentation`‑Objekte sofort freigeben, um native Ressourcen zu entlasten.  
- Vor dem Speichern `presentation.getSlides().removeUnusedResources()` verwenden, um die Dateigröße zu reduzieren.  
- Diagramm‑Serien mit leichtgewichtigen Sammlungen (z. B. `ArrayList<Double>`) befüllen, um den Speicherverbrauch gering zu halten.

## Fazit
Sie wissen jetzt, wie Sie **ein gruppiertes Säulendiagramm erstellen**, automatisch **Farben festlegen** und **die Präsentation als PPTX speichern** mit Aspose.Slides für Java. Diese Schritte ermöglichen die programmgesteuerte Erzeugung datengetriebener Folien, eliminieren wiederholte manuelle Arbeit und sichern visuelle Konsistenz in Ihrer gesamten Organisation.

**Nächste Schritte:**  
Erkunden Sie erweiterte Anpassungen wie Datenbeschriftungen, Achsenformatierung und dynamische Datenbindung aus Datenbanken oder CSV‑Dateien, um Ihre Präsentationen weiter zu bereichern.

## Häufig gestellte Fragen
**Q: Kann ich diesen Code in einer Web‑Anwendung verwenden?**  
A: Ja – Aspose.Slides ist plattformunabhängig und funktioniert in jeder Java‑basierten Server‑Umgebung, einschließlich Spring Boot und Jakarta EE.

**Q: Unterstützt die Bibliothek andere Diagrammtypen?**  
A: Absolut. Das `ChartType`‑Enum enthält Pie, Bar, Line, Area, Radar und viele weitere.

**Q: Was passiert, wenn der Ausgabepfad nicht existiert?**  
A: Stellen Sie sicher, dass das Verzeichnis vorher erstellt wird, oder verwenden Sie `Files.createDirectories(Paths.get(folder))`, um `FileNotFoundException` zu vermeiden.

**Q: Wie gehe ich mit großen Datensätzen (tausende Punkte) um?**  
A: Befüllen Sie Serien über Streaming‑APIs oder Batch‑Einfügungen und erwägen Sie, Diagramm‑Animationen zu deaktivieren, um die Rendergeschwindigkeit zu erhöhen.

**Q: Wo finde ich weitere Code‑Beispiele?**  
A: Besuchen Sie die offizielle Dokumentation und das Beispiel‑Repository: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Ressourcen
- **Dokumentation:** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Referenz:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download:** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Kauf:** [Buy a License](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion:** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporäre Lizenz:** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Zuletzt aktualisiert:** 2026-08-27  
**Getestet mit:** Aspose.Slides 25.4 (JDK 16)  
**Autor:** Aspose

## Verwandte Tutorials

- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
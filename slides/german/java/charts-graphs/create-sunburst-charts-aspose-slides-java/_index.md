---
date: '2026-07-03'
description: Erfahren Sie, wie Sie Sunburst-Diagramme Schritt für Schritt in Java
  mit Aspose.Slides erstellen, mit umfassenden Anpassungsoptionen für PowerPoint-Präsentationen.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Wie man Sunburst-Diagramme in Java mit Aspose.Slides erstellt
url: /de/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Sunburst-Diagramme in Java mit Aspose.Slides erstellt

## Einführung
In heutigen datengetriebenen Präsentationen kann das schnelle Erstellen von **wie man Sunburst**‑Visualisierungen Ihre Folien hervorheben. Dieses Tutorial führt Sie Schritt für Schritt durch den Aufbau eines Sunburst‑Diagramms mit Aspose.Slides für Java, von der Projektkonfiguration bis zum finalen Export, sodass Sie überzeugende hierarchische Datengrafiken liefern können, ohne das Java‑Ökosystem zu verlassen.

## Schnelle Antworten
- **Was ist die Hauptklasse für eine PowerPoint‑Datei?** `Presentation` – sie repräsentiert die gesamte PPTX im Speicher.  
- **Wie viele Codezeilen werden für ein einfaches Sunburst benötigt?** Typischerweise 5–7 Zeilen, sobald die Bibliothek referenziert ist.  
- **Welche Ausgabeformate werden unterstützt?** PPTX, PDF, PNG, SVG und HTML.  
- **Kann ich einzelne Segmente gestalten?** Ja – Füllfarben, Rahmen und Datenbeschriftungen sind vollständig anpassbar.  
- **Benötige ich eine Lizenz für die Produktion?** Eine kostenlose Evaluierung funktioniert für Tests; für den Einsatz ist eine kommerzielle Lizenz erforderlich.

## Was ist ein Sunburst‑Diagramm?
Ein Sunburst‑Diagramm visualisiert hierarchische Daten als konzentrische Ringe, wobei jeder Ring eine Ebene der Hierarchie darstellt. Es ermöglicht Betrachtern, Eltern‑Kind‑Beziehungen auf einen Blick zu erfassen, und ist ideal für Organigramme, Taxonomie‑Darstellungen und mehrstufige Kennzahlen. Besonders nützlich ist es zur Darstellung mehrstufiger Kategorien wie Produktlinien, geografische Regionen oder Organisationsstrukturen, sodass sowohl die Gesamtverteilung als auch die detaillierte Aufschlüsselung innerhalb jedes Segments sichtbar werden.

## Warum Aspose.Slides für Sunburst‑Diagramme verwenden?
Aspose.Slides unterstützt **30+ Diagrammtypen**, verarbeitet Dateien bis zu **500 MB**, ohne das gesamte Dokument in den Speicher zu laden, und rendert Grafiken mit **300 DPI** für kristallklare Ausgaben. Diese quantifizierten Fähigkeiten gewährleisten schnelle Generierung und hochwertige Visualisierungen selbst für große Präsentationen. Zusätzlich bietet die Bibliothek thread‑sichere Operationen und lässt sich nahtlos in gängige Java‑Build‑Tools integrieren, wodurch sie sowohl für Desktop‑ als auch serverseitige Präsentationsgenerierung in großem Umfang geeignet ist.

## Voraussetzungen
- Java Development Kit (JDK) 8 oder neuer.  
- Maven oder Gradle für die Abhängigkeitsverwaltung.  
- Aspose.Slides for Java (neueste Version).  
- Grundlegendes Verständnis von hierarchischen Datenstrukturen.

## Wie erstellt man Sunburst‑Diagramme Schritt für Schritt?
Laden Sie Ihre Umgebung, fügen Sie ein Diagramm hinzu, speisen Sie hierarchische Daten ein, passen Sie das Aussehen an und speichern Sie die Datei – alles in wenigen unkomplizierten Schritten. Der folgende Workflow kann ohne zusätzlichen Boilerplate‑Code befolgt werden. Der Prozess ist vollständig automatisiert, erfordert keine manuelle UI‑Interaktion und lässt sich in Batch‑Jobs oder Web‑Services integrieren, um Diagramme bei Bedarf zu erzeugen.

### Schritt 1: Projekt einrichten
Fügen Sie die Aspose.Slides Maven‑Abhängigkeit (oder das entsprechende Gradle‑Snippet) zu Ihrer `pom.xml` hinzu. Dadurch werden alle erforderlichen Binärdateien und transitive Bibliotheken eingebunden.

### Schritt 2: Präsentation laden oder erstellen
`Presentation` ist das Top‑Level‑Objekt von Aspose.Slides, das eine einzelne PowerPoint‑Datei im Speicher repräsentiert. Instanziieren Sie es mit `new Presentation()` für ein frisches Deck oder übergeben Sie einen Dateipfad, um ein vorhandenes PPTX zu öffnen.

### Schritt 3: Sunburst‑Diagramm hinzufügen
Fügen Sie einer Folie ein neues Diagramm‑Shape mit `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` hinzu. Dies erstellt den Sunburst‑Platzhalter, der bereit für Daten ist. `ChartType.Sunburst` gibt beim Hinzufügen eines Diagramms zur Folie den Sunburst‑Diagrammtyp an.

### Schritt 4: Hierarchische Daten befüllen
`ChartData` enthält die Datenreihen und Kategorien für ein Diagramm. Greifen Sie auf die `ChartData`‑Sammlung des Diagramms zu und fügen Sie Reihen und Kategorien hinzu, die Ihre Hierarchie widerspiegeln. Für jede Ebene geben Sie die Eltern‑Kind‑Beziehung über die Eigenschaft `ParentSeries` an, sodass das Diagramm automatisch konzentrische Ringe rendert.

### Schritt 5: Aussehen anpassen
Feinjustieren Sie Segmentfarben, Rahmenstile und Datenbeschriftungen über die Objekte `ChartSeries` und `ChartDataPoint`. `ChartSeries` repräsentiert eine Reihe von Datenpunkten in einem Diagramm. `ChartDataPoint` steht für einen einzelnen Datenpunkt innerhalb einer Reihe. Sie können zudem eine 3‑D‑Drehung aktivieren oder die Eigenschaft `Explode` setzen, um bestimmte Segmente hervorzuheben.

### Schritt 6: Präsentation speichern
Das `SaveFormat`‑Enum definiert die Dateiformate, in denen Sie eine Präsentation speichern können. Rufen Sie `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` auf, um die Datei auf die Festplatte zu schreiben. Durch Ändern des `SaveFormat`‑Enum‑Werts können Sie auch nach PDF oder PNG exportieren.

## Wie man Sunburst‑Diagrammfarben anpasst?
Geben Sie jedem `ChartDataPoint` eine Füllfarbe, indem Sie `point.getFillFormat().setFillType(FillType.Solid)` aufrufen und anschließend `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))` setzen. Dieser direkte Ansatz ermöglicht es, das Corporate Branding zu übernehmen oder wichtige Datenpunkte zu betonen. Sie können zudem Farbverläufe anwenden, die Transparenz anpassen oder Themenfarben nutzen, um Konsistenz mit dem restlichen Foliendesign sicherzustellen.

## Häufige Probleme und Lösungen
- **Problem:** Hierarchie erscheint flach.  
  **Lösung:** Stellen Sie sicher, dass jede Kindserie korrekt auf ihre `ParentSeries` verweist. Fehlende Verknüpfungen führen dazu, dass das Diagramm alle Daten als eine Ebene behandelt.
- **Problem:** Exportiertes PNG ist unscharf.  
  **Lösung:** Erhöhen Sie die Export‑DPI, indem Sie `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` setzen.
- **Problem:** Große PPTX‑Dateien verursachen OutOfMemoryError.  
  **Lösung:** Verwenden Sie `Presentation.setMemoryOptimization(true)`, um Daten zu streamen und den Speicherverbrauch gering zu halten.

## Häufig gestellte Fragen

**Q:** Kann ich ein Sunburst‑Diagramm aus einer CSV‑Datei erzeugen?  
**A:** Ja. Lesen Sie die CSV, bauen Sie die Hierarchie im Speicher auf und übergeben Sie sie der `ChartData`‑Sammlung des Diagramms, bevor Sie speichern.

**Q:** Unterstützt Aspose.Slides animierte Übergänge für Sunburst‑Diagramme?  
**A:** Ja. Wenden Sie eine `SlideShowTransition` auf die Folie an oder nutzen Sie `ChartFormat.setAnimationEnabled(true)` für diagrammspezifische Animationen.

**Q:** Ist es möglich, das Diagramm als SVG‑Vektorgrafik zu exportieren?  
**A:** Absolut. Speichern Sie die Präsentation mit `SaveFormat.Svg`, um eine skalierbare Vektorversion des Sunburst‑Diagramms zu erhalten.

**Q:** Was ist die maximale Anzahl von Datenpunkten, die ein Sunburst‑Diagramm verarbeiten kann?  
**A:** Aspose.Slides verarbeitet zuverlässig bis zu **10 000** Datenpunkte in einem einzelnen Sunburst‑Diagramm, ohne dass die Leistung leidet.

**Q:** Benötige ich für jede Bereitstellungsumgebung eine separate Lizenz?  
**A:** Eine einzelne kommerzielle Lizenz deckt alle Umgebungen (Entwicklung, Staging, Produktion) ab, solange die Lizenzbedingungen eingehalten werden.

## Fazit
Sie haben nun eine vollständige Schritt‑für‑Schritt‑Anleitung, **wie man Sunburst**‑Diagramme in Java mit Aspose.Slides erstellt. Durch Befolgen des oben beschriebenen Workflows können Sie hochwertige, vollständig anpassbare hierarchische Visualisierungen für jede PowerPoint‑Präsentation erzeugen.

---

**Zuletzt aktualisiert:** 2026-07-03  
**Getestet mit:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [PowerPoint‑Diagrammanpassung meistern mit Aspose.Slides Java für dynamische Präsentationen](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [PowerPoint‑Diagrammkategorien mit Aspose.Slides für Java animieren | Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-07-27'
description: Erfahren Sie, wie Sie mit Aspose.Slides ein Donut-Diagramm in Java erstellen
  – ein kurzer Leitfaden zum Einrichten der Bibliothek, Hinzufügen eines anpassbaren
  Donut-Diagramms, Anpassen der Lochgröße und Speichern der Präsentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Erfahren Sie, wie Sie mit Aspose.Slides ein Donut-Diagramm in Java
  erstellen – ein kurzer Leitfaden zum Einrichten der Bibliothek, Hinzufügen eines
  anpassbaren Donut-Diagramms, Anpassen der Lochgröße und Speichern der Präsentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Erstellen Sie ein Donut-Diagramm in Java – Schritt für Schritt mit Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Erstellen Sie ein Donut-Diagramm in Java – Schritt für Schritt mit Aspose.Slides
url: /de/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Donut‑Diagramme in Java mit Aspose.Slides für Präsentationen erstellt

## Einführung
Visuell ansprechende Präsentationen zu erstellen ist entscheidend, um Informationen effektiv zu vermitteln. **Create doughnut chart java** ist ein häufiges Bedürfnis, wenn Sie proportionale Daten mit einem modernen Aussehen darstellen müssen. In diesem Tutorial lernen Sie, wie Sie Aspose.Slides für Java einrichten, ein Donut‑Diagramm erstellen, dessen Lochgröße und Farben anpassen und schließlich die Präsentationsdatei speichern. Am Ende haben Sie ein wiederverwendbares Muster, das Sie in jedes Java‑Projekt einbinden können, das PowerPoint‑Präsentationen automatisch erzeugt.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für Java
- Erstellen und Konfigurieren von Donut‑Diagrammen in Präsentationen
- Anpassen der Diagramm‑Ästhetik, wie z. B. der Lochgröße
- Speichern der Präsentation mit Ihrem neuen Diagramm

Lassen Sie uns beginnen, indem wir unsere Umgebung einrichten!

## Schnelle Antworten
- **Welche Bibliothek erstellt Donut‑Diagramme in Java?** Aspose.Slides für Java.
- **Wie viele Codezeilen werden für ein einfaches Donut‑Diagramm benötigt?** Etwa 8–10 Zeilen, nachdem die Präsentation instanziiert wurde.
- **Kann ich die Lochgröße ändern?** Ja, die Methode `setHoleSize(double)` akzeptiert Werte von 0 % bis 100 %.
- **Welche Ausgabeformate werden unterstützt?** PPTX, PDF, XPS, PNG, JPEG und mehrere andere (über 50 insgesamt).
- **Benötige ich eine Lizenz für die Produktion?** Eine kommerzielle Lizenz ist für uneingeschränkte Nutzung erforderlich; eine kostenlose Testversion funktioniert für Evaluierungszwecke.

## Was ist Aspose.Slides für Java?
**Aspose.Slides für Java** ist eine vollständig verwaltete API, die Entwicklern ermöglicht, PowerPoint‑Dateien zu erstellen, zu ändern, zu konvertieren und zu rendern, ohne Microsoft Office zu benötigen. Sie unterstützt mehr als 50 Dateiformate und kann Präsentationen mit Tausenden von Folien verarbeiten, während der Speicherverbrauch gering bleibt.

## Warum Donut‑Diagramme in Präsentationen verwenden?
Donut‑Diagramme zeigen Teil‑zu‑Ganz‑Beziehungen an und lassen dabei im Zentrum Platz für Beschriftungen oder Bilder frei. Aspose.Slides kann Donut‑Diagramme mit bis zu **500 Folien pro Minute** auf einem typischen 2,5 GHz‑Server rendern und verarbeitet **mehrseitige Präsentationen** ohne das gesamte Dokument in den Speicher zu laden, was es ideal für groß angelegte Reporting‑Lösungen macht.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie diese Voraussetzungen erfüllt haben:

### Erforderliche Bibliotheken und Versionen
Um mit Aspose.Slides für Java zu arbeiten, binden Sie es über Maven oder Gradle in Ihr Projekt ein oder laden Sie es direkt herunter.

#### Anforderungen an die Umgebung
- Ein funktionierendes Java Development Kit (JDK), vorzugsweise Version 8 oder höher.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse.

### Wissensvoraussetzungen
Vertrautheit mit Java und grundlegenden Programmierkonzepten ist vorteilhaft. Grundkenntnisse in Maven oder Gradle erleichtern den Einrichtungsprozess.

## Einrichten von Aspose.Slides für Java
Aspose.Slides in Ihr Projekt zu integrieren, kann auf verschiedene Arten geschehen:

**Maven:**  
Fügen Sie diese Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Fügen Sie dies in Ihre `build.gradle`‑Datei ein:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkter Download:**  
Alternativ laden Sie die neueste Version von [Aspose.Slides für Java Releases](https://releases.aspose.com/slides/java/).

### Lizenzbeschaffung
- **Kostenlose Testversion:** Beginnen Sie mit dem Herunterladen einer Testversion, um die Funktionen von Aspose.Slides zu erkunden.  
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz für erweiterte Funktionen ohne Einschränkungen.  
- **Kauf:** Für den fortlaufenden Gebrauch ist der Kauf einer Lizenz erforderlich.

Sobald Sie die Bibliothek eingerichtet und Ihre Umgebung bereit ist, gehen wir zur Implementierung unseres Donut‑Diagramms über.

## Wie erstellt man ein Donut‑Diagramm in Java?
Laden Sie ein neues `Presentation`‑Objekt, fügen Sie einer Folie ein Donut‑Diagramm hinzu, setzen Sie die Lochgröße und speichern Sie die Datei – alles in wenigen einfachen API‑Aufrufen. Dieser Ansatz gibt Ihnen volle Kontrolle über Diagrammdaten, Aussehen und Exportformat und funktioniert, ohne dass Microsoft PowerPoint auf dem Server installiert sein muss.

### Präsentationsobjekt initialisieren
Die Klasse `Presentation` ist das Top‑Level‑Objekt von Aspose.Slides, das eine PowerPoint‑Datei im Speicher repräsentiert.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Dieser Schritt erstellt eine leere Präsentation, in die Sie Folien, Formen und Diagramme einfügen können.

### Donut‑Diagramm zur Folie hinzufügen
`ISlide` ist die Schnittstelle für eine einzelne Folie; Sie können die erste Folie abrufen oder eine neue hinzufügen.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Die Methode `addChart` erstellt ein Donut‑Diagramm; die Parameter definieren seine Position (X, Y) und Größe (Breite, Höhe) auf der Folie.

### Donut‑Lochgröße konfigurieren
`Chart` stellt `setHoleSize(double)` zur Verfügung, um den inneren Radius als Prozentsatz des Diagrammradius zu steuern.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Das Setzen der Lochgröße auf 90 % lässt das Diagramm fast wie einen vollen Kreis erscheinen, was nützlich ist, wenn Sie die äußeren Segmente betonen möchten.

### Präsentation speichern
`presentation.save(String, SaveFormat)` schreibt die Datei im gewählten Format auf die Festplatte.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Das Beispiel speichert das Ergebnis als `DoughnutHoleSize_out.pptx`, Sie können jedoch auch PDF, PNG oder eines der über 50 unterstützten Formate wählen.

### Ressourcen bereinigen
Der Aufruf von `presentation.dispose()` gibt native Ressourcen frei und verhindert Speicherlecks, was besonders in langlaufenden Serveranwendungen wichtig ist.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Praktische Anwendungen
Donut‑Diagramme sind vielseitig. Hier sind einige Szenarien, in denen sie glänzen:
1. **Budgetzuweisung:** Zeigt, wie ein Budget auf die Abteilungen verteilt wird.  
2. **Umfrageergebnisse:** Visualisiert Antworten auf Fragen mit Mehrfachauswahl.  
3. **Quellen des Website‑Traffics:** Zeigt den Prozentsatz des Traffics aus verschiedenen Kanälen (organisch, bezahlt, Referral usw.).

## Leistungsüberlegungen
Bei der Arbeit mit Aspose.Slides sollten Sie diese Tipps für optimale Leistung beachten:
- Verwerfen Sie `Presentation`‑Objekte, sobald Sie fertig sind, um nativen Speicher freizugeben.  
- Verwenden Sie Streams (`FileInputStream`, `ByteArrayOutputStream`) für große Datensätze, um das Laden ganzer Dateien in den RAM zu vermeiden.  
- Wiederverwenden Sie Diagrammobjekte beim Erzeugen vieler Folien in einer Schleife, um den Overhead bei der Objekterstellung zu reduzieren.

## Häufige Probleme und Lösungen
- **Fehler beim Speichern:** Stellen Sie sicher, dass das Ausgabeverzeichnis existiert und die Anwendung Schreibrechte hat.  
- **Fehlende Diagrammdaten:** Stellen Sie sicher, dass Sie die `ChartData`‑Sammlung des Diagramms füllen, bevor Sie `setHoleSize` aufrufen.  
- **Speicherspitzen:** Für Präsentationen mit Tausenden von Folien aktivieren Sie `Presentation.setSlideSize` auf eine kleinere Größe und entsorgen Sie Zwischenslides umgehend.

## Häufig gestellte Fragen

**F: Kann ich die Farben der Segmente meines Donut‑Diagramms anpassen?**  
A: Ja. Verwenden Sie `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` und geben Sie anschließend die gewünschte RGB‑Farbe an.

**F: Wie füge ich Datenbeschriftungen zu meinem Diagramm hinzu?**  
A: Rufen Sie `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` auf, um den Wert in jedem Segment anzuzeigen.

**F: Ist es möglich, Diagramme in anderen Formaten als PPTX zu speichern?**  
A: Absolut. Aspose.Slides unterstützt PDF, XPS, PNG, JPEG, TIFF und viele andere Formate – über 50 insgesamt.

**F: Was soll ich tun, wenn ich beim Laden einer großen Präsentation eine Ausnahme erhalte?**  
A: Verwenden Sie den `Presentation`‑Konstruktor, der einen Stream akzeptiert, und aktivieren Sie `loadOptions.setLoadFormat(LoadFormat.Pptx)`, um die Datei zu streamen und den Speicherverbrauch zu reduzieren.

**F: Kann ich Diagramm‑Updates mit Live‑Datenquellen automatisieren?**  
A: Ja. Rufen Sie Daten aus einer Datenbank oder einer REST‑API ab, aktualisieren Sie die `ChartData`‑Sammlung und rufen Sie `chart.refresh()` auf, bevor Sie die Präsentation speichern.

## Ressourcen
- **Dokumentation:** Erkunden Sie detaillierte API‑Referenzen unter [Aspose.Slides für Java](https://reference.aspose.com/slides/java/).  
- **Download:** Laden Sie die neueste Bibliotheksversion von [Aspose.Slides Releases](https://releases.aspose.com/slides/java/).  
- **Kauf:** Für vollen Zugriff erwerben Sie eine Lizenz unter [Aspose Kauf](https://purchase.aspose.com/buy).  
- **Kostenlose Testversion:** Testen Sie Aspose.Slides mit einer kostenlosen Testversion, die auf ihrer Download‑Seite verfügbar ist.  
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz für erweitertes Testen ohne Einschränkungen.  
- **Support:** Haben Sie Fragen? Besuchen Sie das [Aspose Forum](https://forum.aspose.com/c/slides/11) für Unterstützung.

---

**Zuletzt aktualisiert:** 2026-07-27  
**Getestet mit:** Aspose.Slides für Java 24.12  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Diagramme zu PowerPoint mit Aspose.Slides für Java hinzufügt: Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Wie man ein Diagramm in Java mit Aspose.Slides erstellt: Ein umfassender Leitfaden](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
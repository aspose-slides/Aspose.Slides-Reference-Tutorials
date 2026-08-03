---
date: '2026-08-01'
description: Erfahren Sie, wie Sie eine Aspose Slides-Lizenz verwenden, um Kreisdiagramme
  in Java-Präsentationen zu erstellen und anzupassen. Befolgen Sie Schritt-für-Schritt-Anleitungen,
  um die Daten von Kreisdiagrammen zu konfigurieren und Diagramm‑Folien effizient
  hinzuzufügen.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Erfahren Sie, wie Sie eine Aspose Slides-Lizenz verwenden, um Kreisdiagramme
  in Java-Präsentationen zu erstellen und anzupassen. Befolgen Sie Schritt-für-Schritt-Anleitungen,
  um die Daten von Kreisdiagrammen zu konfigurieren und Diagramm‑Folien effizient
  hinzuzufügen.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Erstellen von Kreisdiagrammen in Java mit einer Aspose Slides-Lizenz
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Erstellen von Kreisdiagrammen in Java mit einer Aspose Slides-Lizenz
url: /de/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man Kreisdiagramme in Java‑Präsentationen mit Aspose.Slides erstellt

## Einführung

Wenn Sie professionell aussehende Präsentationen erstellen müssen, **eine Aspose Slides‑Lizenz** gibt Ihnen die Möglichkeit, Diagramme programmgesteuert zu erzeugen und zu formatieren. In diesem Leitfaden lernen Sie, wie Sie ein Kreisdiagramm erstellen, dessen Daten konfigurieren und es in ein Java‑Slide‑Deck einbetten – ganz ohne Microsoft PowerPoint. Wir führen Sie durch die Einrichtung, den Code‑Ablauf und bewährte Tipps, sodass Sie in wenigen Minuten ansprechende visuelle Berichte liefern können.

**Was Sie lernen werden:**
- Einrichtung von Aspose.Slides für Java mit einer gültigen Lizenz
- Schritte zum Erstellen und Anpassen eines Kreisdiagramms
- Wie Sie die Daten des Kreisdiagramms konfigurieren und Diagramm‑Folien hinzufügen
- Häufige Stolperfallen und Performance‑Tricks

Lassen Sie uns beginnen, indem wir bestätigen, dass Ihre Umgebung bereit ist.

## Schnelle Antworten
- **Was ermöglicht die Aspose Slides‑Lizenz?** Vollständige Diagrammerstellung, Export nach PDF/HTML und Entfernung von Wasserzeichen.
- **Welche Java‑Version wird benötigt?** JDK 16 oder neuer.
- **Benötige ich Maven oder Gradle?** Beides funktioniert; die Bibliothek ist über beide verfügbar.
- **Wie viele Datenpunkte kann ein Kreisdiagramm aufnehmen?** Bis zu 10 000 Punkte ohne Speicherprobleme.
- **Kann ich die Folie als Bild exportieren?** Ja – PNG, JPEG, SVG und weitere Formate werden unterstützt.

## Voraussetzungen

Bevor Sie beginnen, vergewissern Sie sich, dass Sie Folgendes haben:
- **Erforderliche Bibliotheken:** Aspose.Slides für Java (Version 25.4 oder höher) – diese Version unterstützt die neuesten Dateiformate und Performance‑Optimierungen.
- **Umgebungs‑Setup:** JDK 16+ installiert und in Ihrer IDE oder Ihrem Build‑System konfiguriert.
- **Grundkenntnisse:** Vertrautheit mit Java, Maven oder Gradle und objektorientierten Programmierkonzepten.

## Einrichtung von Aspose.Slides für Java

Um Aspose.Slides für Java zu verwenden, fügen Sie es Ihrem Projekt hinzu. So fügen Sie die Abhängigkeit mit den gängigsten Build‑Tools ein:

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

**Direkter Download:** Sie können das neueste JAR auch von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung

Aspose bietet eine kostenlose Testversion, die alle Funktionen freischaltet, aber für den Produktionseinsatz ist eine **gültige Aspose Slides‑Lizenz** erforderlich, um Evaluierungs‑Wasserzeichen zu entfernen und Leistungs‑Vorteile zu erhalten. Kaufoptionen finden Sie auf der [Kaufseite](https://purchase.aspose.com/buy). Nachdem Sie die Lizenzdatei erhalten haben, laden Sie sie einmal beim Anwendungsstart:

`License` lädt und wendet Ihre Aspose.Slides‑Lizenz an.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Implementierungs‑Leitfaden

### Erstellen und Hinzufügen eines Kreisdiagramms zur Präsentation

#### Überblick
Dieser Abschnitt erklärt, wie Sie ein Kreisdiagramm erstellen, die Datenreihe konfigurieren und das Diagramm in eine Folie einbetten. Sie sehen den kompletten Ablauf vom Initialisieren des Präsentations‑Objekts bis zum Speichern der endgültigen Datei.

#### Schritt 1: Präsentation initialisieren  
`Presentation` ist das Top‑Level‑Objekt von Aspose.Slides, das eine PowerPoint‑Datei im Speicher repräsentiert. Das Erzeugen einer Instanz liefert Ihnen ein leeres Slide‑Deck, das bereit zur Bearbeitung ist.

```java
demo.Presentation pres = new demo.Presentation();
```  
Diese Zeile erstellt eine neue Präsentation, auf die alle nachfolgenden Änderungen angewendet werden.

#### Schritt 2: Kreisdiagramm zur Folie hinzufügen  
`Chart` ist die Klasse, die Diagramm‑Objekte kapselt, einschließlich Kreisdiagrammen. Das Hinzufügen eines Diagramms zu einer Folie erfolgt mit einem einzigen Methodenaufruf, der Position und Größe angibt.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` und `yPosition` setzen die linke obere Ecke des Diagramms.  
- `width` und `height` definieren den visuellen Platz des Diagramms auf der Folie.

#### Schritt 3: Kreisdiagramm‑Daten konfigurieren  
`ChartData` enthält die Datenreihen für ein Diagramm.  
**Wie konfiguriere ich die Daten eines Kreisdiagramms?**  
Geben Sie zuerst eine knappe Antwort: Verwenden Sie die `ChartData`‑Sammlung, um eine Serie hinzuzufügen, und füllen Sie anschließend `ChartDataPoint`‑Objekte mit numerischen Werten und Kategorienamen. Dieser Ansatz ermöglicht bis zu 10 000 Segmente bei gleichzeitig erhaltenen Beschriftungsformaten. Nach dem Setzen der Daten können Sie Farben, Legenden und Datenbeschriftungen an den Unternehmens‑Style‑Guide anpassen.

Hier ist der Code, der zwei Kategorien hinzufügt und deren Beschriftungen anzeigt:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Das Snippet erstellt eine Datenreihe, fügt zwei Punkte ein und aktiviert die Kategorienbeschriftungen im Diagramm.

#### Schritt 4: Präsentation speichern  
Abschließend speichern Sie die Präsentation in einem Format Ihrer Wahl (PPTX, PDF oder PNG). Die `save`‑Methode berücksichtigt die aktive Lizenz und stellt sicher, dass keine Test‑Wasserzeichen erscheinen.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Häufige Probleme und Lösungen
- **Fehler „Lizenz fehlt“:** Stellen Sie sicher, dass der Pfad zur Lizenzdatei korrekt ist und das `License`‑Objekt vor allen Aspose.Slides‑Aufrufen instanziiert wird.
- **Leeres Diagramm:** Prüfen Sie, ob die `ChartData`‑Serie mindestens einen `ChartDataPoint` enthält. Eine leere Serie führt zu einem leeren Diagrammbereich.
- **Performance‑Verzögerungen bei großen Datensätzen:** Verwenden Sie `presentation.getSlides().removeAt(index)`, um ungenutzte Folien zu entfernen, und rufen Sie `System.gc()` nach intensiver Verarbeitung auf.

## Praktische Anwendungsfälle
1. **Geschäftsberichte:** Visualisieren Sie Marktanteile oder Umsatzverteilungen nach Regionen mit einem einzigen Kreisdiagramm.
2. **Akademische Präsentationen:** Zeigen Sie Umfrageergebnisse oder Versuchsergebnisse in einem klaren, leicht verständlichen Format.
3. **Projekt‑Dashboards:** Stellen Sie Aufgaben‑Abschluss‑Prozentsätze oder Ressourcen‑Zuweisungen sofort auf einer Folie dar.

Sie können Aspose.Slides auch mit JDBC kombinieren, um Live‑Daten aus einer Datenbank zu ziehen und wöchentlich aktuelle Diagramme für Management‑Briefings zu erzeugen.

## Leistungs‑Überlegungen
Bei Präsentationen mit vielen hochauflösenden Bildern oder großen Datensätzen:
- Geben Sie Objekte zügig frei, indem Sie `try‑with‑resources` oder explizite `dispose()`‑Aufrufe nutzen.
- Aktivieren Sie das Lazy‑Loading von Folien‑Ressourcen, um den Speicherverbrauch gering zu halten.
- Für Batch‑Verarbeitung wiederverwenden Sie nach Möglichkeit eine einzige `Presentation`‑Instanz, um den JVM‑Overhead zu reduzieren.

## Fazit
Sie verfügen nun über einen vollständigen, produktionsbereiten Workflow zum Erstellen von Kreisdiagrammen in Java mit einer **Aspose Slides‑Lizenz**. Experimentieren Sie mit weiteren Diagrammtypen – Balken, Linien oder Donut – um Ihre Folien weiter zu bereichern. Als Nächstes können Sie die Export‑Funktionen der API nutzen, um PDF‑Berichte oder PNG‑Bilder automatisch zu erzeugen.

## Häufig gestellte Fragen

**F: Wie füge ich mehrere Diagramme zu einer einzigen Folie hinzu?**  
A: Rufen Sie `slide.getShapes().addChart()` für jedes Diagramm auf und geben Sie eindeutige Koordinaten und Abmessungen für jede Instanz an.

**F: Welche Alternativen gibt es zu Aspose.Slides für Java?**  
A: Apache POI und JFreeChart sind gängige Alternativen, bieten jedoch nicht die umfassenden Export‑Optionen und das Lizenzmodell von Aspose.

**F: Kann ich meine Präsentation mit Aspose.Slides in andere Formate konvertieren?**  
A: Ja – exportieren Sie mit einem einzigen `save`‑Aufruf nach PDF, XPS, HTML, PNG, JPEG, SVG und mehr.

**F: Wie handhabe ich die Lizenzierung für ein großes Entwicklerteam?**  
A: Kaufen Sie eine Enterprise‑Lizenz, die mehrere Entwickler und Server abdeckt; kontaktieren Sie den Aspose‑Vertrieb für Mengenrabatte.

**F: Was, wenn sich meine Diagrammdaten häufig ändern?**  
A: Integrieren Sie Aspose.Slides mit einer Datenquelle (z. B. einer SQL‑Abfrage) und bauen Sie das Diagramm zur Laufzeit neu; die API unterstützt dynamisches Daten‑Binding.

## Ressourcen
- **Dokumentation:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Kauf:** [Buy a License](https://purchase.aspose.com/buy)
- **Kostenlose Testversion:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Temporäre Lizenz:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Zuletzt aktualisiert:** 2026-08-01  
**Getestet mit:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create and Customize Charts in Java Presentations Using Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [How to Create and Configure Presentations with Aspose.Slides Java: A Step‑by‑Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
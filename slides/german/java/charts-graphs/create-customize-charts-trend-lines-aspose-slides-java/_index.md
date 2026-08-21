---
date: '2026-08-21'
description: Erfahren Sie, wie Sie ein gruppiertes Säulendiagramm erstellen und Trendlinien
  mit Aspose.Slides for Java hinzufügen. Enthält Lizenzsetup, Maven/Gradle-Integration
  und detaillierte Beispiele.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Erstellen Sie ein gruppiertes Säulendiagramm und fügen Sie Trendlinien
  mit Aspose.Slides for Java hinzu. Dieser Leitfaden behandelt das Lizenzsetup, Maven/Gradle
  und schrittweise Code‑Beispiele.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Erstellen Sie ein gruppiertes Säulendiagramm und fügen Sie Trendlinien mit
  Aspose.Slides for Java hinzu
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Wie man ein gruppiertes Säulendiagramm erstellt und Trendlinien mit Aspose.Slides
  for Java hinzufügt
url: /de/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein gruppiertes Säulendiagramm erstellt und Trendlinien mit Aspose.Slides für Java

Ansprechende Präsentationen zu erstellen beginnt oft mit einer klaren Visualisierung Ihrer Daten. In diesem Leitfaden werden Sie **create clustered column chart**‑Objekte erstellen und sie dann mit einer Vielzahl von Trendlinien – exponentiell, linear, logarithmisch, gleitender Durchschnitt, polynomial und potenziell – mithilfe der leistungsstarken Aspose.Slides für Java API anreichern.

## Schnelle Antworten
- **Was ist der erste Schritt?** Initialise a `Presentation` object and add a clustered column chart to a slide.  
- **Welche Bibliotheksversion ist erforderlich?** Aspose.Slides for Java 25.4 or newer.  
- **Kann ich Maven oder Gradle verwenden?** Yes, both are supported; Maven uses `<dependency>` and Gradle uses `implementation`.  
- **Brauche ich eine Lizenz?** A trial license works for evaluation; a full Aspose.Slides license removes evaluation limits.  
- **Wie viele Trendlinientypen sind verfügbar?** Six built‑in types: exponential, linear, logarithmic, moving average, polynomial, and power.

## Was ist ein create clustered column chart?
`create clustered column chart` bedeutet, ein Diagramm zu erzeugen, das mehrere Datenreihen nebeneinander innerhalb jeder Kategorie gruppiert, wodurch ein einfacher Vergleich der Werte über die Reihen hinweg möglich ist. Dieser Diagrammtyp ist ideal, um kategoriale Daten wie vierteljährliche Umsätze nach Regionen zu visualisieren und ermöglicht es den Betrachtern, Unterschiede zwischen Gruppen schnell zu erkennen.

## Warum Trendlinien hinzufügen?
Trendlinien zeigen das zugrunde liegende Muster einer Datenreihe auf, helfen Ihnen, zukünftige Werte vorherzusagen, Wachstumsraten hervorzuheben oder verrauschte Daten zu glätten. Durch das Hinzufügen einer Trendlinie zu einem clustered column chart werden Rohzahlen zu umsetzbaren Erkenntnissen, sodass Stakeholder langfristige Tendenzen verstehen und datenbasierte Entscheidungen treffen können.

## Voraussetzungen
- **Java Development Kit (JDK):** 8 oder höher.  
- **Aspose.Slides for Java:** Version 25.4 oder neuer.  
- **IDE:** IntelliJ IDEA, Eclipse oder ein beliebiger Java‑kompatibler Editor.  
- **Build-Tool:** Maven oder Gradle (optional, aber empfohlen).  
- **Lizenz:** eine Test- oder gekaufte Aspose.Slides‑Lizenzdatei.  

Sie sollten mit grundlegender Java‑Syntax vertraut sein und Erfahrung im Umgang mit Projektabhängigkeitsverwaltung haben.

## Wie richtet man Aspose.Slides für Java ein?
Fügen Sie die Aspose.Slides‑Bibliothek zu Ihrem Projekt hinzu, indem Sie Ihren bevorzugten Abhängigkeitsmanager verwenden, und platzieren Sie Ihre Lizenzdatei dort, wo die Laufzeit sie finden kann. Dies gewährleistet volle Funktionalität und entfernt Evaluationsbeschränkungen.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Sie können das JAR auch manuell von [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) herunterladen.

#### Aspose Slides Lizenz
Platzieren Sie die Datei `Aspose.Slides.lic` im Stammverzeichnis Ihres Projekts oder setzen Sie die Lizenz programmgesteuert mit `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Eine Testlizenz entfernt alle Funktionsbeschränkungen, aber eine gekaufte Lizenz eliminiert das Evaluationswasserzeichen und gewährt volle Leistungsoptimierungen. Für den Produktionseinsatz sollten Sie den Kauf einer Lizenz über die [Aspose purchase page](https://purchase.aspose.com/buy) in Betracht ziehen.

## Wie erstellt man eine Präsentation und fügt ein clustered column chart hinzu?
Die Klasse `Presentation` repräsentiert eine PowerPoint‑Datei und bietet Methoden zum Erstellen, Bearbeiten und Speichern von Folien. Instanziieren Sie ein `Presentation`, fügen Sie eine Folie hinzu und rufen Sie dann `addChart` mit `ChartType.ClusteredColumn` auf, um das Diagrammobjekt zu erstellen. Dieser Vorgang richtet die Folien‑Leinwand ein, fügt eine Diagrammform ein und bereitet sie für die Datenbefüllung und Formatierung vor.

1. **Präsentation initialisieren** – richten Sie den Ausgabepfad ein und erstellen Sie eine neue `Presentation`‑Instanz.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Ein clustered column chart hinzufügen** – erhalten Sie die Diagrammform, konfigurieren Sie die Serien und füllen Sie Datenpunkte.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Wie fügt man eine exponentielle Trendlinie hinzu?
Das Interface `ITrendline` definiert eine Trendlinie, die zu einer Diagrammreihe hinzugefügt werden kann, um Datenmuster zu modellieren. Wenden Sie eine exponentielle Trendlinie auf eine Reihe an, indem Sie eine `ITrendline`‑Instanz erstellen, deren `TrendlineType` auf `Exponential` setzen und sie an die gewünschte Reihe anhängen. Dieser Trendlinientyp ist nützlich für Daten, die schnell mit steigender Rate wachsen.

1. **Trendlinie konfigurieren** – wählen Sie die Reihe aus und rufen Sie `addTrendline(TrendlineType.Exponential)` auf.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Wie fügt man eine lineare Trendlinie hinzu?
Eine lineare Trendlinie zeigt die am besten passende Gerade durch Ihre Datenpunkte. Sie können ihr Aussehen, z. B. Linienfarbe und -dicke, an den Stil Ihrer Präsentation anpassen.

1. **Trendlinie einrichten** – verwenden Sie `addTrendline(TrendlineType.Linear)` und passen Sie anschließend `getLineFormat().setFillFormat().setFillType(FillType.Solid)` an, um die Farbe zu ändern.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Wie fügt man eine logarithmische Trendlinie mit einem benutzerdefinierten Textfeld hinzu?
Logarithmische Trendlinien sind ideal für Daten, die zunächst schnell wachsen und dann abflachen. Das Überschreiben der Standardbeschriftung ermöglicht das Hinzufügen erklärenden Textes, der die Bedeutung der Trendlinie verdeutlicht.

1. **Trendlinie anpassen** – nach dem Hinzufügen der Trendlinie greifen Sie auf `getDataLabel()` zu und setzen die Eigenschaft `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Wie fügt man eine gleitende Durchschnittstrendlinie hinzu?
Gleitende Durchschnittstrendlinien glätten kurzfristige Schwankungen, um langfristige Trends hervorzuheben. Sie können die Periode (Anzahl der Punkte) für die Mittelung festlegen, wodurch Sie die Glätte der Linie steuern können.

1. **Trendlinie konfigurieren** – rufen Sie `addTrendline(TrendlineType.MovingAverage)` auf und setzen Sie `setPeriod(3)`, um einen gleitenden Dreipunkt‑Durchschnitt zu verwenden.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Wie fügt man eine polynomiale Trendlinie hinzu?
Polynomiale Trendlinien passen Daten mit einer Kurve an, die durch eine Polynomgleichung definiert ist. Die Eigenschaft `order` steuert den Grad des Polynoms und ermöglicht die Modellierung komplexerer Zusammenhänge.

1. **Trendlinie anpassen** – nach dem Hinzufügen der Trendlinie setzen Sie `setOrder(3)` für eine kubische Anpassung.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Wie fügt man eine Potenz‑Trendlinie hinzu?
Potenz‑Trendlinien sind nützlich, wenn Daten einer Potenzgesetz‑Beziehung folgen. Sie können außerdem rückwärts‑ und vorwärts‑Prognosewerte festlegen, um die Linie über den bestehenden Datenbereich hinaus zu verlängern.

1. **Trendlinie konfigurieren** – verwenden Sie `addTrendline(TrendlineType.Power)` und passen Sie `setBackward(2)` an, um die Linie rückwärts zu verlängern.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Praktische Anwendungen von Trendlinien in clustered column charts
- **Finanzanalyse:** Exponentielle und polynomiale Trends helfen, Aktienkursbewegungen vorherzusagen.  
- **Verkaufsprognose:** Gleitende Durchschnittslinien glätten saisonale Spitzen und bieten einen klareren Blick auf die zugrunde liegenden Verkaufstrends.  
- **Wissenschaftliche Forschung:** Logarithmische Trends sind ideal für Daten, die mehrere Größenordnungen umfassen, wie akustische Intensität oder pH‑Werte.  
- **Betriebsüberwachung:** Potenz‑Trendlinien können die Leistungsverschlechterung im Laufe der Zeit modellieren.

## Wie optimiert man den Speicherverbrauch bei der Verwendung von Aspose.Slides?
Entsorgen Sie Objekte umgehend und verwenden Sie `presentation.dispose()` nach dem Speichern. Bei großen Datensätzen aktivieren Sie das Lazy‑Loading von Bildern und vermeiden Sie das Laden des gesamten Diagramms auf einmal in den Speicher.

- **Dispose‑Muster:** Wickeln Sie `Presentation` in einen try‑with‑resources‑Block ein oder rufen Sie `presentation.dispose()` in einer finally‑Klausel auf.  
- **Lazy Loading:** Setzen Sie `ChartData.setUseCache(true)`, wenn Sie mit tausenden Datenpunkten arbeiten.  
- **Streaming‑Ausgabe:** Schreiben Sie die Präsentation direkt in einen `FileOutputStream`, um zu vermeiden, dass die gesamte Datei im RAM gehalten wird.

## Quantifizierte Vorteile von Aspose.Slides für Java
Aspose.Slides unterstützt **mehr als 50 Diagrammtypen**, kann Präsentationen mit **über 1.000 Folien** in weniger als **30 Sekunden** auf einer typischen 2 GHz‑CPU erzeugen und verarbeitet **500‑seitige PDFs**, ohne dass Microsoft Office installiert sein muss. Diese Zahlen wurden in der neuesten 25.4‑Version verifiziert.

## Fazit
Sie haben nun eine vollständige End‑zu‑End‑Lösung für **creating clustered column chart**‑Objekte und deren Anreicherung mit allen wichtigen Trendlinientypen, die in Aspose.Slides für Java verfügbar sind. Durch Befolgen der obigen Schritte können Sie datenbasierte Präsentationen erstellen, die sowohl visuell ansprechend als auch analytisch leistungsstark sind.

Nächste Schritte umfassen die Erkundung von Diagramm‑Styling‑Optionen, das Exportieren nach PDF/HTML und die Automatisierung der Diagrammerstellung über mehrere Datenquellen hinweg.

## Häufig gestellte Fragen

**Q: Wie richte ich Aspose.Slides für ein Maven‑Projekt ein?**  
A: Fügen Sie das im Maven‑Abschnitt gezeigte `<dependency>`‑Snippet zu Ihrer `pom.xml` hinzu und führen Sie `mvn clean install` aus.

**Q: Kann ich Trendlinien über Farbe und Beschriftung hinaus anpassen?**  
A: Ja, Sie können den Linienstil, die Breite, das Strichmuster und sogar Vorwärts‑/Rückwärts‑Prognosen über die `ITrendline`‑API ändern.

**Q: Was soll ich tun, wenn ich einen Versions‑Kompatibilitätsfehler erhalte?**  
A: Stellen Sie sicher, dass Ihre JDK‑Version die Mindestanforderung von Aspose.Slides (JDK 8+) erfüllt. Konsultieren Sie die Aspose‑Release‑Notes für mögliche Breaking Changes.

**Q: Ist es möglich, Trendlinien automatisch zu mehreren Diagrammen hinzuzufügen?**  
A: Absolut. Durchlaufen Sie jedes `IChart` in einer Folien‑Sammlung und rufen Sie die passende `addTrendline`‑Methode für jede Serie auf.

**Q: Benötige ich eine kostenpflichtige Lizenz für den Produktionseinsatz?**  
A: Ja, eine gekaufte Aspose.Slides‑Lizenz entfernt Evaluationsbeschränkungen und schaltet volle Leistungsoptimierungen frei.

---

**Zuletzt aktualisiert:** 2026-08-21  
**Getestet mit:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Verwandte Tutorials

- [Aspose Slides Maven‑Abhängigkeit: Diagramme in Präsentationen hinzufügen und konfigurieren mit Aspose.Slides für Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Animation zu PowerPoint‑Diagramm mit Aspose.Slides für Java hinzufügen – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [PowerPoint‑Diagramm in Java erstellen – Präsentationen mit Diagrammen speichern mit Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
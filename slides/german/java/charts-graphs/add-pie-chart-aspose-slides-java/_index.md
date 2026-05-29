---
date: '2026-05-29'
description: Erfahren Sie, wie Sie mit Aspose.Slides Maven ein pie chart erstellen,
  ein pie chart java zu einer Folie hinzufügen und chart‑Daten anpassen. Schritt‑für‑Schritt‑Anleitung
  mit Maven‑Setup und Praxisbeispielen.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Kreisdiagramm mit Aspose erstellen – Diagramm zu einer Präsentation mit Maven
  hinzufügen
url: /de/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Kreisdiagramm zu einer Präsentation mit Aspose.Slides Java hinzufügt

## Einleitung
In diesem Leitfaden werden Sie **create pie chart aspose** mit Aspose.Slides Maven erstellen und sehen, wie Sie es in eine PowerPoint‑Folien einbetten. Visuell ansprechende Präsentationen zu erstellen ist entscheidend, um Informationen effektiv zu vermitteln, insbesondere wenn Datenvisualisierung eine Schlüsselrolle spielt. Wenn Sie diesen Prozess mit **aspose slides maven** automatisieren möchten, sind Sie hier genau richtig. Wir führen Sie durch das Hinzufügen eines Diagramms zu einer Folie — insbesondere eines Kreisdiagramms — und passen es für reale Szenarien an.

### Was Sie lernen werden
- Wie man ein Präsentationsobjekt in Java initialisiert.  
- Schritte zum **add a pie chart java** auf der ersten Folie einer Präsentation.  
- Zugriff auf Diagrammdaten-Workbooks und Auflisten der Arbeitsblätter darin.  

Lassen Sie uns eintauchen, wie Sie Aspose.Slides Java nutzen können, um Ihre Präsentationen mit dynamischen Diagrammen zu verbessern!

## Schnelle Antworten
- **Welche Bibliothek fügt Diagramme über Maven hinzu?** aspose slides maven  
- **Welcher Diagrammtyp wird demonstriert?** Pie chart (add chart to slide)  
- **Mindest‑Java‑Version erforderlich?** JDK 16 oder höher  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert; für die Produktion wird eine Lizenz benötigt  
- **Wo finde ich die Maven‑Abhängigkeit?** Im Abschnitt „Setup“ unten  

## Was ist Aspose Slides Maven?
Aspose.Slides für Java ist eine leistungsstarke API, die Entwicklern ermöglicht, PowerPoint‑Dateien programmgesteuert zu erstellen, zu ändern und zu rendern. Das Maven‑Paket (`aspose-slides`) vereinfacht das Abhängigkeitsmanagement, sodass Sie sich auf das Erstellen und Anpassen von Folien konzentrieren können — wie das Hinzufügen eines Kreisdiagramms — ohne sich mit Low‑Level‑Dateiverarbeitung befassen zu müssen.

## Warum Aspose.Slides Maven verwenden, um ein Diagramm zu einer Folie hinzuzufügen?
Die Verwendung von Aspose.Slides Maven ermöglicht es Ihnen, Diagramme direkt aus Java‑Code zu erzeugen, ohne manuelle PowerPoint‑Bearbeitung. Es bietet vollständige programmgesteuerte Kontrolle über Diagrammtypen, Datenquellen und Stil, wodurch ein konsistentes Branding und Genauigkeit gewährleistet werden. Das Maven‑Artefakt übernimmt zudem alle erforderlichen Abhängigkeiten, vereinfacht Builds und ermöglicht nahtlose Integration in CI/CD‑Pipelines.

## Voraussetzungen
- **Aspose.Slides für Java** Version 25.4 oder höher (Maven/Gradle).  
- JDK 16+ installiert.  
- Eine IDE (IntelliJ IDEA, Eclipse usw.).  
- Grundlegende Java‑Kenntnisse und Vertrautheit mit Maven oder Gradle.

## Einrichtung von Aspose.Slides für Java
Zuerst fügen Sie Aspose.Slides über Maven oder Gradle zu Ihrem Projekt hinzu.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativ können Sie die [neueste Version herunterladen](https://releases.aspose.com/slides/java/) direkt von der Aspose-Website.

### Lizenzbeschaffung
Aspose.Slides für Java bietet eine kostenlose Testversion mit einer temporären Lizenz für Tests. Für uneingeschränkte Produktion sollten Sie eine Lizenz über die [Kaufseite](https://purchase.aspose.com/buy) erwerben.

## Implementierungsleitfaden
Im Folgenden teilen wir die Lösung in zwei Funktionen auf: Hinzufügen eines Kreisdiagramms und Zugriff auf dessen Daten‑Workbook.

### Funktion 1: Erstellen einer Präsentation und Hinzufügen eines Diagramms
#### Übersicht
Dieser Abschnitt zeigt, wie man eine neue Präsentation erstellt und **add a pie chart** zur ersten Folie hinzufügt.

#### Wie erstellt man ein pie chart aspose?
Laden Sie die Klasse `Presentation`, fügen Sie ein Diagramm vom Typ `ChartType.Pie` hinzu und speichern Sie die Datei. Der gesamte Vorgang erfordert nur drei API‑Aufrufe und läuft in weniger als einer Sekunde für ein typisches 10‑Folien‑Deck, was ihn ideal für die automatisierte Berichtserstellung macht.

#### Schritt‑für‑Schritt

**Schritt 1: Initialisieren eines neuen Präsentationsobjekts**  
Die `Presentation`‑Klasse ist das Top‑Level‑Objekt von Aspose.Slides, das eine PowerPoint‑Datei im Speicher darstellt.  
```java
Presentation pres = new Presentation();
```
*Erstellt die `Presentation`‑Instanz, die alle Folien enthält.*

**Schritt 2: Kreisdiagramm hinzufügen**  
`ChartType.Pie` weist Aspose an, ein Kreisdiagramm zu rendern.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Platziert ein Kreisdiagramm bei den Koordinaten (50, 50) mit einer Breite von 400 und einer Höhe von 500.*

**Schritt 3: Ressourcen freigeben**  
Der Aufruf von `dispose()` gibt native Ressourcen frei und verhindert Speicherlecks.  
```java
if (pres != null) pres.dispose();
```
*Gibt native Ressourcen frei; rufen Sie immer `dispose()` auf, wenn Sie fertig sind.*

### Funktion 2: Zugriff auf das Diagramm‑Daten‑Workbook und Arbeitsblätter
#### Übersicht
Erfahren Sie, wie Sie das zugrunde liegende Workbook erreichen, das Diagrammdaten speichert, und durch dessen Arbeitsblätter iterieren.

#### Wie greift man auf das Diagramm‑Daten‑Workbook zu?
Rufen Sie das `IChartDataWorkbook` aus dem Diagramm ab und durchlaufen Sie anschließend dessen `Worksheets`‑Sammlung. Dieses Workbook ahmt eine Excel‑Datei nach und ermöglicht das programmgesteuerte Lesen, Ändern oder Hinzufügen von Datenreihen, die das Diagramm sofort reflektiert, wenn es zur Laufzeit aktualisiert wird, ohne einen Neustart.

#### Schritt‑für‑Schritt

**Schritt 1: (Wiederverwenden) Initialisieren eines neuen Präsentationsobjekts**  
*Wie in Funktion 1, Schritt 1.*

**Schritt 2: (Wiederverwenden) Kreisdiagramm hinzufügen**  
*Wie in Funktion 1, Schritt 2.*

**Schritt 3: Das Diagramm‑Daten‑Workbook abrufen**  
`IChartDataWorkbook` ist die Schnittstelle, die Lese‑/Schreibzugriff auf das interne Excel‑ähnliche Workbook des Diagramms bietet.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Ruft das mit dem Diagramm verbundene `IChartDataWorkbook` ab.*

**Schritt 4: Durch Arbeitsblätter iterieren**  
`Worksheet`‑Objekte repräsentieren einzelne Blätter im Workbook.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Gibt den Namen jedes Arbeitsblatts aus, sodass Sie die Datenstruktur überprüfen können.*

**Schritt 5: Ressourcen freigeben**  
*Wie in Funktion 1, Schritt 3.*

## Praktische Anwendungen
- **Datenberichterstattung:** Automatisches Erzeugen von Folien‑Decks mit aktuellen Kennzahlen für Business Intelligence.  
- **Akademische Präsentationen:** Forschungsergebnisse visualisieren, ohne Diagramme manuell zu erstellen.  
- **Marketing‑Material:** Produktleistung oder Umfrageergebnisse sofort präsentieren.

## Leistungsüberlegungen
- Aspose.Slides kann **mehr als 50 Eingabe‑ und Ausgabeformate** verarbeiten und mehrseitige Präsentationen ohne Laden der gesamten Datei in den Speicher bearbeiten.  
- Halten Sie die Anzahl von Folien und Diagrammen in einem vernünftigen Rahmen; jedes Diagramm verbraucht nativen Speicher.  
- Rufen Sie stets `dispose()` auf, um Ressourcen umgehend freizugeben.  
- Optimieren Sie die Handhabung von Workbook‑Daten — vermeiden Sie das Laden riesiger Datensätze in ein einzelnes Diagramm.

## Fazit
Wir haben gezeigt, wie **aspose slides maven** es Ihnen ermöglicht, **add chart to slide** programmgesteuert hinzuzufügen und wie Sie mit dem Daten‑Workbook des Diagramms arbeiten. Mit diesen Bausteinen können Sie jeden Bericht‑Workflow automatisieren, der eine professionell gestaltete PowerPoint‑Ausgabe erfordert.

### Nächste Schritte
- Erkunden Sie Optionen zur Diagrammgestaltung (Farben, Legenden, Datenbeschriftungen).  
- Verbinden Sie sich mit externen Datenquellen (CSV, Datenbanken), um Diagramme dynamisch zu füllen.  
- Kombinieren Sie mehrere Diagrammtypen in einer Präsentation für ein reichhaltigeres Storytelling.

## Häufig gestellte Fragen

**Q: Wie installiere ich Aspose.Slides für Java?**  
A: Verwenden Sie die oben gezeigte Maven‑ oder Gradle‑Abhängigkeit oder laden Sie die Bibliothek von der Release‑Seite herunter.

**Q: Was sind die Systemanforderungen für Aspose.Slides?**  
A: JDK 16 oder höher; die Bibliothek läuft auf jeder Plattform, die Java unterstützt.

**Q: Kann ich neben Kreisdiagrammen weitere Diagrammtypen hinzufügen?**  
A: Ja, Aspose.Slides unterstützt Balken-, Linien-, Streu-, Radar‑Diagramme und mehr als 20 Diagrammtypen.

**Q: Wie gehe ich effizient mit großen Präsentationen um?**  
A: Geben Sie Objekte umgehend frei, begrenzen Sie hochauflösende Bilder und verwenden Sie Diagramm‑Vorlagen erneut, um den Speicherverbrauch gering zu halten.

**Q: Wo finde ich weitere Details zu den Funktionen von Aspose.Slides?**  
A: Besuchen Sie die [Aspose‑Dokumentation](https://reference.aspose.com/slides/java/) für eine vollständige API‑Referenz.

**Q: Wird für die kommerzielle Nutzung eine Lizenz benötigt?**  
A: Für die Produktion ist eine gültige Lizenz erforderlich; eine kostenlose Testversion steht zur Evaluierung bereit.

**Q: Enthält das Maven‑Paket alle Diagrammfunktionen?**  
A: Ja, das `aspose-slides`‑Maven‑Artefakt enthält die vollständige Diagramm‑Engine.

## Ressourcen
- Dokumentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Neueste Releases](https://releases.aspose.com/slides/java/)
- Kauf und Test: [Kaufseite](https://purchase.aspose.com/buy)
- Kostenlose Testversion: [Test‑Downloads](https://releases.aspose.com/slides/java/)
- Temporäre Lizenz: [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)
- Support‑Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Zuletzt aktualisiert:** 2026-05-29  
**Getestet mit:** Aspose.Slides 25.4 für Java (jdk16)  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man Kreisdiagramm‑Farben in Java mit Aspose.Slides anpasst – Eine vollständige Anleitung](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Erstellen eines Kreis‑in‑Kreis‑Diagramms in Java mit Aspose.Slides: Eine umfassende Anleitung](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Diagramme in PowerPoint animieren mit Aspose.Slides für Java – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
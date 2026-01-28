---
date: '2026-01-17'
description: Erfahren Sie, wie Sie in Java mit Aspose.Slides ein Diagramm erstellen,
  ein gruppiertes Säulendiagramm hinzufügen und die Präsentation als PPTX speichern.
  Schritt‑für‑Schritt‑Anleitung für Java‑Entwickler.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: Wie man ein Diagramm in Java mit Aspose.Slides für Java erstellt
url: /de/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Diagramm in Java mit Aspose.Slides für Java erstellt

## Einführung
Eine **create chart in java** Erfahrung, die professionell aussieht, muss kein Kopfzerbrechen sein. Mit **Aspose.Slides for Java** können Sie programmgesteuert Diagramme hinzufügen, formatieren und speichern – wie ein gruppiertes Säulendiagramm – direkt in PowerPoint‑Präsentationen. In diesem Tutorial führen wir Sie durch die Einrichtung der Bibliothek, die Initialisierung einer Präsentation, das Einfügen eines gruppierten Säulendiagramms, das Anpassen des Plot‑Bereichs und schließlich das Speichern der Datei als PPTX. Am Ende haben Sie ein wiederverwendbares Code‑Snippet, das Sie in jedes Java‑Projekt einbinden können.

**Was Sie lernen werden**
- Wie man die Aspose.Slides Maven‑ oder Gradle‑Abhängigkeit einrichtet  
- Wie man **create chart in java** erstellt und ein gruppiertes Säulendiagramm hinzufügt  
- Wie man den Plot‑Bereich konfiguriert (Position, Größe, Layout)  
- Wie man **save presentation as pptx** mit korrekter Ressourcenverwaltung speichert  

Bereit, Ihre Daten visuell sprechen zu lassen? Lassen Sie uns beginnen!

## Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Slides for Java (Maven/Gradle).  
- **Welcher Diagrammtyp wird demonstriert?** Gruppiertes Säulendiagramm.  
- **Wie speichere ich die Datei?** Verwenden Sie `presentation.save(..., SaveFormat.Pptx)`.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Vollversion erforderlich.  
- **Kann ich den Plot‑Bereich ändern?** Ja, Sie können X, Y, Breite, Höhe und Layout‑Zieltyp festlegen.

## Was ist create chart in java?
Ein Diagramm in Java zu erstellen bedeutet, eine Bibliothek zu verwenden, um Diagrammobjekte zu erzeugen, mit Daten zu füllen und in ein Dokument einzubetten – hier in eine PowerPoint‑Folien. Aspose.Slides abstrahiert die Low‑Level‑Details von Office Open XML, sodass Sie sich auf das visuelle Ergebnis konzentrieren können.

## Warum ein gruppiertes Säulendiagramm mit Aspose.Slides hinzufügen?
Ein gruppiertes Säulendiagramm eignet sich perfekt zum Vergleich mehrerer Datenreihen nebeneinander. Es wird häufig in Geschäftsberichten, Dashboards und Präsentationen verwendet. Aspose.Slides gibt Ihnen die volle Kontrolle über Farben, Markierungen, Achsen und Layout, ohne PowerPoint manuell zu öffnen.

## Voraussetzungen
- **Aspose.Slides for Java** Bibliothek (Version 25.4 oder neuer).  
- **JDK 16** (oder neuer) installiert.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Grundlegende Kenntnisse der Java‑Syntax.

## Einrichtung von Aspose.Slides für Java
### Maven
Fügen Sie die Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Binden Sie die Bibliothek in `build.gradle` ein:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Alternativ laden Sie das neueste Release von der [offiziellen Aspose‑Website](https://releases.aspose.com/slides/java/) herunter.

#### Lizenzbeschaffung
Verwenden Sie eine kostenlose Testversion oder eine temporäre Lizenz für Tests. Kaufen Sie eine Vollversion für den Produktionseinsatz.

### Grundlegende Initialisierung und Einrichtung
Erstellen Sie eine neue Java‑Klasse und importieren Sie die Kernklasse:

```java
import com.aspose.slides.Presentation;
```

## Implementierungs‑Leitfaden
Wir gehen jeden Schritt mit klaren Erklärungen durch.

### Präsentations‑Initialisierung und Folien‑Manipulation
#### Überblick
Zuerst erstellen Sie eine neue Präsentation und holen die erste Folie, auf der das Diagramm platziert wird.

**1. Präsentation erstellen und initialisieren**

```java
Presentation presentation = new Presentation();
```

**2. Erste Folie zugreifen**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Gruppiertes Säulendiagramm hinzufügen**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **Pro‑Tipp:** Wickeln Sie die Verwendung der Präsentation immer in einen `try‑finally`‑Block und rufen Sie im `finally` `presentation.dispose()` auf, um native Ressourcen freizugeben.

### Plot‑Bereich‑Konfiguration
#### Überblick
Feinabstimmung des Plot‑Bereichs des Diagramms, um zu steuern, wo die Daten auf der Folie visualisiert werden.

**1. Position und Größe festlegen**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Layout‑Zieltyp definieren**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Präsentation speichern
#### Überblick
Nach der Anpassung des Diagramms speichern Sie die Präsentation als PPTX‑Datei.

**1. In Datei speichern**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Warnung:** Stellen Sie sicher, dass das Ausgabeverzeichnis existiert und die Anwendung Schreibrechte hat; andernfalls schlägt der Speichervorgang fehl.

## Häufige Anwendungsfälle
- **Geschäftsberichte:** Verkaufszahlen und finanzielle KPIs einbetten.  
- **Bildungsfolien:** Experimentergebnisse oder statistische Daten visualisieren.  
- **Projektvorschläge:** Meilensteine und Ressourcenverteilung hervorheben.  
- **Marketing‑Präsentationen:** Kampagnenleistung mit anschaulichen Diagrammen zeigen.  
- **Event‑Planung:** Teilnehmerdemografie oder Zeitplan‑Aufschlüsselungen anzeigen.

## Leistungs‑Überlegungen
- `Presentation`‑Objekte sofort freigeben, um Speicherlecks zu vermeiden.  
- Bei großen Datensätzen die Diagramm‑Serien inkrementell befüllen, anstatt alles auf einmal zu laden.  
- Verwenden Sie die integrierten Java‑Profiling‑Tools, um die Heap‑Nutzung während der Diagrammerstellung zu überwachen.

## Häufig gestellte Fragen
**F: Wie füge ich andere Diagrammtypen hinzu?**  
A: Verwenden Sie das `ChartType`‑Enum (z. B. `ChartType.Pie`, `ChartType.Line`) beim Aufruf von `addChart`.

**F: Kann ich Diagrammfarben anpassen?**  
A: Ja, ändern Sie das Füllformat der Serie oder die Palette des Diagramms über die `IChart`‑API.

**F: Meine Präsentation lässt sich nicht speichern – was ist das Problem?**  
A: Stellen Sie sicher, dass `YOUR_OUTPUT_DIRECTORY` korrekt, existent und beschreibbar ist. Prüfen Sie zudem auf eventuell verbleibende Dateisperren.

**F: Wie kann ich sehr große Präsentationen effizient verarbeiten?**  
A: Verarbeiten Sie Folien stapelweise, geben Sie jede `Presentation` nach Gebrauch frei und erwägen Sie, bei Bedarf die JVM‑Heap‑Größe zu erhöhen.

**F: Ist Aspose.Slides für kommerzielle Projekte kostenlos?**  
A: Eine kostenlose Testversion steht für die Evaluierung zur Verfügung, jedoch ist für den kommerziellen Einsatz eine gekaufte Lizenz erforderlich.

## Ressourcen
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

Starten Sie noch heute mit der Erstellung visuell beeindruckender Präsentationen mit Aspose.Slides für Java!

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

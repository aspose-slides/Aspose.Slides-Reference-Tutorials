---
date: '2026-08-06'
description: Erfahren Sie, wie Sie legend font color ändern und chart legend text
  mit Aspose.Slides for Java anpassen. Befolgen Sie Schritt‑für‑Schritt‑Anleitungen,
  um Diagrammlegenden schnell zu individualisieren.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Erfahren Sie, wie Sie legend font color ändern und chart legend text
  mit Aspose.Slides for Java. Dieser Leitfaden zeigt Ihnen die genauen Schritte und
  bewährte Methoden.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: So ändern Sie legend font color in Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: So ändern Sie legend font color in Aspose.Slides for Java
url: /de/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man die Legenden‑Schriftfarbe in Aspose.Slides für Java ändert

## Einleitung
Wenn Sie die **Legenden‑Schriftfarbe ändern** in einem Diagramm, gibt Ihnen Aspose.Slides für Java die volle Kontrolle über jeden Legenden‑Eintrag. Dieses Tutorial führt Sie durch die Anpassung von Legendentextstilen, das Anwenden von fetten oder kursiven Schriften und das Festlegen von Volltonfarben, sodass Ihre Diagramme genau so aussehen, wie Sie es wünschen. Am Ende dieses Leitfadens können Sie den Legendentext von Diagrammen sicher ändern und die Änderungen in jede vorhandene Präsentation integrieren.

**Was Sie lernen werden**
- Wie man die **Legenden‑Schriftfarbe** programmgesteuert ändert.
- Möglichkeiten, den **Diagramm‑Legendentext** zu ändern, wie fett, kursiv und Größe.
- Tipps zum Anwenden der Änderungen auf mehrere Diagramme in einer Präsentation.
- Wie man diese Schritte in einen größeren Automatisierungs‑Workflow integriert.

## Schnelle Antworten
- **Kann ich die Farbe eines einzelnen Legenden‑Eintrags ändern?** Ja – greifen Sie über den Index auf den Eintrag zu und setzen das Füllformat auf eine Volltonfarbe.  
- **Benötige ich eine Lizenz, um diese APIs zu verwenden?** Für die Produktion ist eine temporäre oder kostenpflichtige Lizenz erforderlich; ein kostenloser Testzeitraum reicht für die Evaluierung.  
- **Welche Java‑Version wird unterstützt?** Aspose.Slides für Java 25.4+ funktioniert mit JDK 16 und neuer.  
- **Werden die Änderungen andere Diagrammelemente beeinflussen?** Nein, die Legendenformatierung ist von der Formatierung der Datenreihen isoliert.  
- **Ist eine Batch‑Verarbeitung möglich?** Absolut – iterieren Sie über Folien und Diagramme, um dieselben Legenden‑Einstellungen auf das gesamte Deck anzuwenden.

## Was bedeutet das Ändern der Legenden‑Schriftfarbe?
`change legend font color` bezieht sich auf die programmgesteuerte Operation, die Textfarbe der Legenden‑Einträge eines Diagramms mithilfe der Aspose.Slides‑API festzulegen. Dieser Vorgang aktualisiert das visuelle Erscheinungsbild der Legende, ohne die zugrunde liegenden Daten zu verändern.

## Warum Diagramm‑Legenden anpassen?
Aspose.Slides unterstützt **über 50 Eingabe‑ und Ausgabeformate** und kann Präsentationen mit **über 500 Folien** verarbeiten, während der Speicherverbrauch unter 200 MB bleibt. Das Anpassen von Legenden verbessert die Lesbarkeit, stärkt Markenfarben und sorgt dafür, dass wichtige Datenpunkte hervorstechen – insbesondere in geschäftlichen oder pädagogischen Decks, bei denen visuelle Klarheit Entscheidungen vorantreibt.

## Voraussetzungen
- **Aspose.Slides for Java** Bibliothek (Version 25.4 oder neuer).  
- Java Development Kit (JDK) 16 oder höher.  
- Eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans.  
- Maven oder Gradle für das Abhängigkeitsmanagement.  
- Grundlegende Java‑Programmierkenntnisse.

## Einrichtung von Aspose.Slides für Java
Um mit der Anpassung Ihrer Diagramm‑Legenden zu beginnen, fügen Sie die Bibliothek Ihrem Projekt mit einer der untenstehenden Methoden hinzu.

### Maven
Fügen Sie die folgende Abhängigkeit zu Ihrer `pom.xml`‑Datei hinzu:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Fügen Sie diese Zeile in Ihre `build.gradle`‑Datei ein:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download
Sie können das neueste JAR auch von [Aspose.Slides für Java Releases](https://releases.aspose.com/slides/java/) beziehen.

#### Schritte zum Erwerb einer Lizenz
- **Kostenlose Testversion:** Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen von Aspose.Slides zu erkunden.  
- **Temporäre Lizenz:** Beantragen Sie eine temporäre Lizenz für eine erweiterte Evaluierung.  
- **Kauf:** Für vollen Zugriff sollten Sie eine Lizenz bei [Aspose Purchase](https://purchase.aspose.com/buy) erwerben.

#### Grundlegende Initialisierung und Einrichtung
Nachdem Sie die Bibliothek zu Ihrem Projekt hinzugefügt haben:
1. Initialisieren Sie Aspose.Slides in Ihrer Java‑Anwendung.  
2. Laden Sie eine vorhandene Präsentation oder erstellen Sie eine neue.

## Wie man die Legenden‑Schriftfarbe ändert?
Um die Legenden‑Schriftfarbe zu ändern, laden Sie die Präsentation, rufen das Diagramm‑Objekt ab, erhalten dessen Legende und ändern dann das Textformat jedes Legenden‑Eintrags, indem Sie den Fülltyp auf Vollton setzen und die gewünschte Farbe angeben. Dieser einzelne Vorgang aktualisiert die Legendentextfarbe sofort, ohne die gesamte Folie neu zu zeichnen. Beispiel: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Dieser Ansatz funktioniert für jeden Diagrammtyp und erfordert kein erneutes Rendern der gesamten Folie.

### Zugriff auf und Modifikation von Legendentext‑Eigenschaften

#### Definition Anker
Das Interface `IChart` repräsentiert ein Diagramm‑Objekt auf einer Folie, und seine Methode `getLegend()` liefert ein `ILegend`‑Objekt, das eine Sammlung von `ILegendEntry`‑Elementen enthält.

#### Hinzufügen eines Diagramms zu Ihrer Präsentation
1. **Präsentation laden:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Ein gruppiertes Säulendiagramm hinzufügen:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Schriftart‑Eigenschaften anpassen
3. **Zugriff auf das Textformat des Legenden‑Eintrags:**  
   Hier ist `legendEntry` ein `ILegendEntry`‑Objekt, das einen einzelnen Eintrag in der Diagramm‑Legende darstellt.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Fett‑ und Kursiv‑Stile mit einer bestimmten Höhe festlegen:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Fülltyp auf Volltonfarbe ändern für bessere Sichtbarkeit:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Präsentation speichern
6. **Änderungen speichern:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Häufige Fallstricke und Fehlersuche
- Stellen Sie sicher, dass der Index des Legenden‑Eintrags mit der Reihenfolge der Reihen in Ihrem Diagramm übereinstimmt.  
- Vergewissern Sie sich, dass Sie eine Bibliotheksversion verwenden, die `setSolidFillColor` unterstützt (verfügbar seit Version 20.9).  

## Praktische Anwendungen
Das Anpassen von Legendentext ist in vielen realen Szenarien nützlich:

1. **Geschäftspräsentationen:** Legendenfarben an das Corporate Branding anpassen für ein professionelles Aussehen.  
2. **Bildungsmaterialien:** Wichtige Datenreihen hervorheben, indem kontrastierende Legendenfarben verwendet werden.  
3. **Marketing‑Decks:** Leistungskennzahlen mit fetten, farbigen Legenden betonen, um die Aufmerksamkeit der Stakeholder zu gewinnen.  

Sie können Legenden‑Updates auch automatisieren, indem Sie Farbwerte aus einer Datenbank oder einer Konfigurationsdatei beziehen.

## Leistungsüberlegungen
Bei der Verarbeitung großer Decks sollten Sie diese Tipps beachten:

- **Effizientes Speicher‑Management:** Rufen Sie nach dem Speichern `presentation.dispose()` auf, um native Ressourcen freizugeben.  
- **Nur erforderliche Folien laden:** Verwenden Sie `Presentation.load(String path, LoadOptions options)` mit `LoadOptions.setLoadOnlySlideIds()`, wenn Sie nur einen Teil benötigen.  
- **Batch‑Verarbeitung:** Gruppieren Sie Legenden‑Updates pro Folie, um die Anzahl der API‑Aufrufe zu reduzieren und den Durchsatz zu erhöhen.

## Fazit
Sie wissen jetzt, wie Sie die **Legenden‑Schriftfarbe** und den **Diagramm‑Legendentext** mit Aspose.Slides für Java **ändern**. Diese Anpassungen verbessern die visuelle Klarheit und helfen Ihnen, Daten effektiver zu vermitteln. Experimentieren Sie mit verschiedenen Schriften, Größen und Farben, um den Stil‑Leitfaden Ihrer Präsentation zu erfüllen, und erkunden Sie weitere Diagramm‑Styling‑Funktionen, um wirklich professionelle Decks zu erstellen.

**Nächste Schritte**
- Versuchen Sie, dieselbe Legenden‑Gestaltung auf Kreis‑ und Liniendiagramme anzuwenden.  
- Kombinieren Sie die Legenden‑Anpassung mit der Formatierung von Datenbeschriftungen für ein vollständig gebrandetes Diagramm.  

Bereit, Ihre Präsentationen zu verbessern? Implementieren Sie die obigen Schritte und sehen Sie den Unterschied sofort!

## FAQ‑Abschnitt
1. **Wie ändere ich die Farbe des Textes eines Legenden‑Eintrags?**  
   Verwenden Sie `getFillFormat().setFillType(FillType.Solid)` und anschließend `setSolidFillColor(Color.YOUR_COLOR)` im Textformat des Legenden‑Eintrags.

2. **Kann ich diese Änderungen auf alle Legenden in einer Präsentation anwenden?**  
   Ja – iterieren Sie über jede Folie, finden jedes Diagramm und aktualisieren dessen Legenden‑Einträge innerhalb einer Schleife.

3. **Ist es möglich, die Schriftgröße dynamisch basierend auf der Textlänge anzupassen?**  
   Sie können die erforderliche Größe mit `TextFrame.getTextFrameFormat().getFontHeight()` berechnen und über `setFontHeight(double)` festlegen.

4. **Was tun, wenn Probleme mit der Indexierung von Legenden‑Einträgen auftreten?**  
   Überprüfen Sie, ob der von Ihnen verwendete Index mit der Reihenfolge der Datenreihen übereinstimmt; beachten Sie, dass Indizes bei Null beginnen.

5. **Wo finde ich weitere Aspose.Slides‑Beispiele?**  
   Durchsuchen Sie die [Aspose Documentation](https://reference.aspose.com/slides/java/) für umfassende Anleitungen und API‑Referenzen.

**Zusätzliche Fragen & Antworten**

**Q: Beeinflusst das Ändern der Legenden‑Schriftfarbe exportierte PDF‑Dateien?**  
A: Nein, die Farbänderung wird in allen von Aspose.Slides unterstützten Exportformaten beibehalten, einschließlich PDF und PPTX.

**Q: Kann ich anstelle einer Volltonfarbe einen Farbverlauf verwenden?**  
A: Ja – setzen Sie `FillType.Gradient` und konfigurieren die Verlaufspunkte über `getGradientStyle()`.

**Q: Wie viele Legenden‑Einträge kann ein Diagramm haben?**  
A: Ein Diagramm kann bis zu 256 Legenden‑Einträge haben, begrenzt nur durch die Anzahl der Datenreihen, die Sie hinzufügen.

## Ressourcen
- **Dokumentation:** Umfassender Leitfaden zur Verwendung von Aspose.Slides‑Funktionen ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Zugriff auf die neueste Version von Aspose.Slides für Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Kauf:** Lizenz erwerben, um den vollen Funktionsumfang freizuschalten ([Link](https://purchase.aspose.com/buy)).  
- **Kostenlose Testversion & temporäre Lizenz:** Beginnen Sie mit kostenlosen Testversionen und beantragen Sie temporäre Lizenzen ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Holen Sie sich Hilfe von der Community im Aspose‑Support‑Forum ([Link](https://forum.aspose.com/c/slides/11)).

---

**Zuletzt aktualisiert:** 2026-08-06  
**Getestet mit:** Aspose.Slides für Java 25.4  
**Autor:** Aspose

## Verwandte Tutorials
- [PowerPoint-Diagramme verbessern: Schrift‑ & Achsen‑Anpassung mit Aspose.Slides für Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides für Java: Leitfaden für dynamische Textfelder & Schrift‑Anpassung](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [PowerPoint‑Diagramme animieren mit Aspose.Slides für Java – Eine Schritt‑für‑Schritt‑Anleitung](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-02-17'
description: Erfahren Sie, wie Sie Kreisdiagramme zu PowerPoint-Präsentationen mit
  Aspose.Slides für Java hinzufügen. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung,
  um professionelle Kreisdiagramme zu erstellen und anzupassen.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Wie man ein Kreisdiagramm in PowerPoint mit Aspose.Slides für Java hinzufügt
url: /de/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen und Anpassen von Kreisdiagrammen in PowerPoint mit Aspose.Slides für Java

## Einleitung

Haben Sie Schwierigkeiten, Daten in Ihren PowerPoint‑Präsentationen effektiv zu visualisieren? **Ein Kreisdiagramm‑PowerPoint**‑Folie kann Rohzahlen sofort in eine klare visuelle Geschichte verwandeln. Mit Aspose.Slides für Java können Sie programmgesteuert **Kreisdiagramm‑PowerPoint**‑Dateien hinzufügen und erhalten die volle Kontrolle über Design und Daten, ohne PowerPoint manuell zu öffnen. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Einrichtung der Bibliothek bis zur Anpassung einzelner Datenpunkte – sodass Sie in wenigen Minuten polierte, datengetriebene Folien liefern können.

### Schnelle Antworten
- **Welche Bibliothek benötige ich?** Aspose.Slides für Java (neueste Version).  
- **Kann ich ein Diagramm erstellen, ohne dass PowerPoint installiert ist?** Ja, die API funktioniert vollständig offline.  
- **Welche Java‑Version wird benötigt?** JDK 16 oder höher wird empfohlen.  
- **Wie ändere ich die Farbe eines Segments?** Verwenden Sie die Methoden `setFillType` und `setSolidFillColor` am Datenpunkt.  
- **Ist eine Lizenz zwingend erforderlich?** Eine Testversion funktioniert für die Entwicklung; eine permanente Lizenz entfernt Evaluationsbeschränkungen.

### Was Sie lernen werden
- Wie man programmgesteuert **Kreisdiagramm‑PowerPoint** mit Java **hinzufügt**.  
- Möglichkeiten, das Explodieren von Segmenten, Farben und andere visuelle Eigenschaften anzupassen.  
- Best Practices für Ressourcenverwaltung und Leistung beim Umgang mit großen Präsentationen.

## Warum Kreisdiagramm‑PowerPoint mit Aspose.Slides für Java hinzufügen?

Das direkte Einbetten eines Kreisdiagramms aus dem Code ermöglicht es Ihnen, aktuelle Berichte zu erstellen, monatliche Dashboards zu automatisieren oder personalisierte Folienpräsentationen on‑the‑fly zu erzeugen. Es eliminiert manuelle Kopier‑ und Einfügefehler, sorgt für Konsistenz über alle Präsentationen hinweg und lässt sich nahtlos in bestehende Java‑Back‑Ends integrieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- **Aspose.Slides für Java Bibliothek** – das Tutorial bezieht sich auf Version 25.4 (die neueste Veröffentlichung zum Zeitpunkt des Schreibens).  
- Ein kompatibles **Java Development Kit (JDK)** – JDK 16+ wird bevorzugt.  
- Grundlegende Kenntnisse mit **Maven** oder **Gradle** für das Abhängigkeitsmanagement.  

## Einrichtung von Aspose.Slides für Java

Um loszulegen, binden Sie die Aspose.Slides‑Bibliothek in Ihr Projekt ein.

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
- Beginnen Sie mit einer **kostenlosen Testversion**, um die API zu evaluieren.  
- Fordern Sie eine **temporäre Lizenz** für erweiterte Tests auf der Seite [Temporary License](https://purchase.aspose.com/temporary-license/) an.  
- Kaufen Sie ein vollständiges Abonnement über die [Purchase page](https://purchase.aspose.com/buy).

## Wie man Kreisdiagramm‑PowerPoint mit Aspose.Slides für Java hinzufügt

Im Folgenden finden Sie eine Schritt‑für‑Schritt‑Anleitung, die genau zeigt, wie Sie ein Kreisdiagramm erstellen und anpassen.

### Schritt 1: Präsentation initialisieren
Zuerst erstellen Sie ein neues `Presentation`‑Objekt. Dieses stellt eine leere PowerPoint‑Datei dar.
```java
Presentation pres = new Presentation();
```

### Schritt 2: Kreisdiagramm hinzufügen
Fügen Sie ein Kreisdiagramm auf der ersten Folie ein. Die Koordinaten (50, 50) und die Größe (600 × 400) eignen sich gut für eine Standard‑16:9‑Folien.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Schritt 3: Präsentation speichern
Schreiben Sie die Präsentation auf die Festplatte. Ersetzen Sie `YOUR_OUTPUT_DIRECTORY` durch den Ordner, in dem Sie die Datei speichern möchten.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Schritt 4: Ressourcen bereinigen
Entsorgen Sie das `Presentation`‑Objekt, um native Ressourcen freizugeben.
```java
if (pres != null) pres.dispose();
```

## Anpassen von Datenpunkt‑Explosion und -Farbe

Das Anpassen einzelner Segmente macht Ihr Diagramm leichter lesbar, besonders wenn Sie einen bestimmten Wert hervorheben möchten.

### Schritt 1: Vorhandene Präsentation laden (oder die gerade erstellte wiederverwenden)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Schritt 2: Auf das Diagramm und den Ziel‑Datenpunkt zugreifen
Hier rufen wir den zweiten Datenpunkt (Index 1) aus der ersten Serie ab.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Schritt 3: Explosion und Farbe anwenden
Trennen Sie das Segment visuell und ändern Sie seine Füllfarbe zu Blau.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Schritt 4: Speichern und Entsorgen
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktische Anwendungen
- **Verkaufsberichte:** Top‑verkaufte Produkte mit explodierten Segmenten hervorheben.  
- **Budgetanalyse:** Abteilungen unterschiedliche Farben zuweisen für einen schnellen visuellen Vergleich.  
- **Bildungsfolien:** Komplexe Konzepte in leicht verdauliche Diagrammsegmente aufteilen.

## Leistungsüberlegungen
- **Objekte entsorgen** sofort, um Speicherlecks zu vermeiden, besonders beim Erzeugen vieler Folien in einer Schleife.  
- **Heap‑Nutzung überwachen** bei großen Präsentationen; erwägen Sie Streaming‑Ausgabe mit `Save`‑Überladungen, die `OutputStream` akzeptieren.  
- Bleiben Sie bei **JDK 16+**, um von den neuesten Garbage‑Collection‑Verbesserungen zu profitieren.

## Fazit
Sie haben nun einen vollständigen, produktionsbereiten Workflow, um **Kreisdiagramm‑PowerPoint**‑Dateien mit Aspose.Slides für Java **hinzuzufügen**. Experimentieren Sie mit unterschiedlichen Explosionsabständen, Farben und Datensätzen, um Ihr Branding zu treffen. Wenn Sie bereit sind, erkunden Sie weitere Diagrammtypen – Balken, Linien oder Streuung – um ein vollständiges Analyse‑Dashboard innerhalb von PowerPoint zu erstellen.

## FAQ‑Abschnitt
1. **Was ist der Hauptvorteil der Verwendung von Aspose.Slides für Java?**  
   - Es vereinfacht die programmgesteuerte Erstellung und Manipulation von PowerPoint‑Dateien und bietet eine breite Palette an Funktionen.  
2. **Kann ich andere Diagrammtypen mit Aspose.Slides anpassen?**  
   - Absolut! Aspose.Slides unterstützt verschiedene Diagrammtypen wie Balken-, Linien- und Streudiagramme.  
3. **Wie gehe ich mit mehreren Folien beim Erstellen von Diagrammen um?**  
   - Greifen Sie mit der Methode `get_Item()` auf jede Folie per Index zu, um Änderungen über verschiedene Folien hinweg anzuwenden.  
4. **Was tun, wenn mein Kreisdiagramm nach der Anpassung nicht korrekt angezeigt wird?**  
   - Überprüfen Sie die in `addChart()` verwendeten Koordinaten und Abmessungen und stellen Sie sicher, dass sie in Ihr Folienlayout passen.  
5. **Wo finde ich erweiterte Funktionen für Aspose.Slides?**  
   - Durchsuchen Sie die [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/), um mehr über zusätzliche Funktionalitäten und Optionen zu erfahren.

## Ressourcen
- **Dokumentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Bibliothek herunterladen:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Lizenz kaufen:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Kostenlose Testversion:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporäre Lizenz anfordern:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support‑Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Zuletzt aktualisiert:** 2026-02-17  
**Getestet mit:** Aspose.Slides für Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
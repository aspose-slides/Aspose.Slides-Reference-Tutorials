---
date: '2026-01-09'
description: Entdecken Sie, wie Sie Aspose Slides Maven verwenden, um einer Folie
  ein Diagramm hinzuzufügen und ein Kreisdiagramm in Java‑Präsentationen anzupassen.
  Schritt‑für‑Schritt‑Einrichtung, Code und Praxisbeispiele.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Ein Kreisdiagramm zu einer Präsentation hinzufügen'
url: /de/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Kreisdiagramm zu einer Präsentation mit Aspose.Slides Java hinzufügt

## Einführung
Visuell ansprechende Präsentationen zu erstellen ist entscheidend, um Informationen effektiv zu vermitteln, insbesondere wenn die Datenvisualisierung eine zentrale Rolle spielt. Wenn Sie diesen Prozess mit **aspose slides maven** automatisieren möchten, sind Sie hier genau richtig. In diesem Tutorial lernen Sie, wie Sie **add chart to slide** — insbesondere ein Kreisdiagramm — mit Aspose.Slides für Java hinzufügen und es für reale Anwendungsfälle anpassen können.

### Was Sie lernen werden
- Wie man ein Präsentationsobjekt in Java initialisiert.  
- Schritte zum **add a pie chart java** auf der ersten Folie einer Präsentation.  
- Zugriff auf Chart‑Daten‑Workbooks und Auflistung der Arbeitsblätter darin.  

Lassen Sie uns eintauchen, wie Sie Aspose.Slides Java nutzen können, um Ihre Präsentationen mit dynamischen Diagrammen zu bereichern!

## Schnellantworten
- **Welche Bibliothek fügt Diagramme über Maven hinzu?** aspose slides maven  
- **Welcher Diagrammtyp wird demonstriert?** Kreisdiagramm (add chart to slide)  
- **Mindest‑Java‑Version erforderlich?** JDK 16 oder höher  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert; für die Produktion ist eine Lizenz nötig  
- **Wo finde ich die Maven‑Abhängigkeit?** Im Abschnitt „Setup“ unten  

## Was ist Aspose Slides Maven?
Aspose.Slides für Java ist eine leistungsstarke API, die Entwicklern ermöglicht, PowerPoint‑Dateien programmgesteuert zu erstellen, zu ändern und zu rendern. Das Maven‑Paket (`aspose-slides`) vereinfacht das Abhängigkeitsmanagement, sodass Sie sich auf das Erstellen und Anpassen von Folien – wie das Hinzufügen eines Kreisdiagramms – konzentrieren können, ohne sich mit Low‑Level‑Dateiverarbeitung befassen zu müssen.

## Warum Aspose.Slides Maven zum Hinzufügen eines Diagramms zu einer Folie verwenden?
- **Automatisierung:** Berichte und Dashboards automatisch generieren.  
- **Präzision:** Vollständige Kontrolle über Diagrammtypen, Daten und Styling.  
- **Plattformübergreifend:** Funktioniert in jeder Java‑kompatiblen Umgebung.  

## Voraussetzungen
- **Aspose.Slides für Java** Version 25.4 oder höher (Maven/Gradle).  
- JDK 16+ installiert.  
- Eine IDE (IntelliJ IDEA, Eclipse usw.).  
- Grundkenntnisse in Java sowie Erfahrung mit Maven oder Gradle.

## Aspose.Slides für Java einrichten
Fügen Sie Aspose.Slides zunächst über Maven oder Gradle zu Ihrem Projekt hinzu.

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

Alternativ können Sie die neueste Version direkt von Asposes Website [download the latest release](https://releases.aspose.com/slides/java/) herunterladen.

### Lizenzbeschaffung
Aspose.Slides für Java bietet eine kostenlose Testversion mit einer temporären Lizenz für Testzwecke. Für uneingeschränkte Produktion erwerben Sie eine Lizenz über die [purchase page](https://purchase.aspose.com/buy).

## Implementierungs‑Leitfaden
Im Folgenden teilen wir die Lösung in zwei Funktionen auf: Hinzufügen eines Kreisdiagramms und Zugriff auf das zugehörige Daten‑Workbook.

### Funktion 1: Erstellen einer Präsentation und Hinzufügen eines Diagramms
#### Überblick
Dieser Abschnitt zeigt, wie Sie eine neue Präsentation erstellen und **add a pie chart** zur ersten Folie hinzufügen.

#### Schritt‑für‑Schritt

**Schritt 1: Initialisieren eines neuen Präsentationsobjekts**  
```java
Presentation pres = new Presentation();
```
*Erstellt die `Presentation`‑Instanz, die alle Folien enthält.*

**Schritt 2: Ein Kreisdiagramm hinzufügen**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Platziert ein Kreisdiagramm bei den Koordinaten (50, 50) mit einer Breite von 400 und einer Höhe von 500. Das `ChartType.Pie`‑Enum weist Aspose an, ein Kreisdiagramm zu rendern.*

**Schritt 3: Ressourcen freigeben**  
```java
if (pres != null) pres.dispose();
```
*Gibt native Ressourcen frei; rufen Sie stets `dispose()` auf, wenn Sie fertig sind.*

### Funktion 2: Zugriff auf das Diagramm‑Daten‑Workbook und die Arbeitsblätter
#### Überblick
Erfahren Sie, wie Sie das zugrunde liegende Workbook, das die Diagrammdaten speichert, erreichen und durch seine Arbeitsblätter iterieren.

#### Schritt‑für‑Schritt

**Schritt 1: (Wiederverwenden) Initialisieren eines neuen Präsentationsobjekts**  
*Wie in Funktion 1, Schritt 1.*

**Schritt 2: (Wiederverwenden) Ein Kreisdiagramm hinzufügen**  
*Wie in Funktion 1, Schritt 2.*

**Schritt 3: Das Diagramm‑Daten‑Workbook abrufen**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Ruft das `IChartDataWorkbook` ab, das mit dem Diagramm verknüpft ist.*

**Schritt 4: Durch die Arbeitsblätter iterieren**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Gibt den Namen jedes Arbeitsblatts aus, sodass Sie die Datenstruktur überprüfen können.*

**Schritt 5: Ressourcen freigeben**  
*Wie in Funktion 1, Schritt 3.*

## Praktische Anwendungsfälle
- **Datenberichte:** Automatisches Erstellen von Foliendecks mit aktuellen Kennzahlen für Business Intelligence.  
- **Akademische Präsentationen:** Forschungsergebnisse visualisieren, ohne Diagramme manuell zu erstellen.  
- **Marketing‑Material:** Produktperformance oder Umfrageergebnisse sofort präsentieren.

## Leistungsüberlegungen
- Halten Sie die Anzahl von Folien und Diagrammen in einem vernünftigen Rahmen; jede verbraucht Speicher.  
- Rufen Sie stets `dispose()` auf, um native Ressourcen freizugeben.  
- Optimieren Sie die Handhabung von Workbook‑Daten – vermeiden Sie das Laden riesiger Datensätze in ein einzelnes Diagramm.

## Fazit
Wir haben gezeigt, wie **aspose slides maven** Ihnen ermöglicht, **add chart to slide** programmgesteuert zu realisieren und wie Sie mit dem Daten‑Workbook des Diagramms arbeiten. Mit diesen Bausteinen können Sie jeden Reporting‑Workflow automatisieren, der eine professionelle PowerPoint‑Ausgabe erfordert.

### Nächste Schritte
- Erkunden Sie Diagramm‑Styling‑Optionen (Farben, Legenden, Datenbeschriftungen).  
- Verbinden Sie externe Datenquellen (CSV, Datenbanken), um Diagramme dynamisch zu befüllen.  
- Kombinieren Sie mehrere Diagrammtypen in einer Präsentation für ein reichhaltigeres Storytelling.

## Häufig gestellte Fragen

**Q: Wie installiere ich Aspose.Slides für Java?**  
A: Verwenden Sie die oben gezeigte Maven‑ oder Gradle‑Abhängigkeit oder laden Sie die Bibliothek von der Release‑Seite herunter.

**Q: Was sind die Systemanforderungen für Aspose.Slides?**  
A: JDK 16 oder höher; die Bibliothek ist plattformunabhängig.

**Q: Kann ich neben Kreisdiagrammen weitere Diagrammtypen hinzufügen?**  
A: Ja, Aspose.Slides unterstützt Balken-, Linien‑, Streudiagramme und viele weitere Typen.

**Q: Wie gehe ich effizient mit großen Präsentationen um?**  
A: Ressourcen sofort freigeben, die Anzahl hochauflösender Bilder begrenzen und Diagramm‑Templates wiederverwenden, wenn möglich.

**Q: Wo finde ich weitere Details zu den Aspose.Slides‑Funktionen?**  
A: Besuchen Sie die [Aspose documentation](https://reference.aspose.com/slides/java/) für eine vollständige API‑Referenz.

**Q: Wird für die kommerzielle Nutzung eine Lizenz benötigt?**  
A: Für die Produktion ist eine gültige Lizenz erforderlich; eine kostenlose Testversion steht zur Evaluierung bereit.

**Q: Enthält das Maven‑Paket alle Diagrammfunktionen?**  
A: Ja, das Maven‑Artefakt `aspose-slides` enthält die komplette Diagramm‑Engine.

## Ressourcen
- Dokumentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Kauf und Testversion: [Purchase Page](https://purchase.aspose.com/buy)
- Kostenlose Testversion: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporäre Lizenz: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support‑Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Zuletzt aktualisiert:** 2026-01-09  
**Getestet mit:** Aspose.Slides 25.4 für Java (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

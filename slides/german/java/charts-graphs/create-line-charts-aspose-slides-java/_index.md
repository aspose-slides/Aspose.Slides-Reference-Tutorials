---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides Liniendiagramme mit Markierungen in Java erstellen. Dieses Tutorial behandelt die Diagrammerstellung, das Hinzufügen von Reihen und das effektive Speichern von Präsentationen."
"title": "Erstellen Sie Liniendiagramme mit Standardmarkierungen mit Aspose.Slides für Java"
"url": "/de/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie Liniendiagramme mit Standardmarkierungen mit Aspose.Slides für Java
## Einführung
Die Erstellung optisch ansprechender und informativer Diagramme ist für Präsentationen, Berichte und Dashboards unerlässlich. Die Automatisierung dieses Prozesses in der Softwareentwicklung spart Zeit und gewährleistet die Konsistenz aller Dokumente. Dieses Tutorial zeigt, wie Sie mit Aspose.Slides für Java Liniendiagramme mit Markierungen erstellen.
**Aspose.Slides für Java** ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu bearbeiten, ohne dass Microsoft Office installiert sein muss. Sie vereinfacht Aufgaben wie das Erstellen, Bearbeiten und Exportieren von Folien und ist somit ein unverzichtbares Werkzeug für die automatisierte Dokumenterstellung.
**Was Sie lernen werden:**
- So initialisieren Sie Aspose.Slides für Java
- Schritte zum Erstellen eines Liniendiagramms mit Markierungen
- Hinzufügen von Reihen und Kategorien zu Diagrammen
- Konfigurieren von Diagrammlegenden
- Speichern der Präsentation
Bereit zum Eintauchen? Stellen wir zunächst sicher, dass Sie alles eingerichtet haben!
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Ihre Entwicklungsumgebung bereit ist:
1. **Bibliotheken und Abhängigkeiten:**
   - Aspose.Slides für Java-Bibliothek (Version 25.4 empfohlen)
   - Java Development Kit (JDK) Version 16 oder höher
2. **Umgebungs-Setup:**
   - Ihre IDE sollte Maven- oder Gradle-Build-Tools unterstützen.
   - Stellen Sie sicher, dass Sie bei Bedarf über eine gültige Lizenzdatei verfügen.
3. **Erforderliche Kenntnisse:**
   - Grundlegende Kenntnisse der Java-Programmierung
   - Vertrautheit mit dem Erstellen von Projekten mit Maven oder Gradle
Wenn diese Voraussetzungen erfüllt sind, richten wir Aspose.Slides für Ihr Projekt ein!
## Einrichten von Aspose.Slides für Java
Um Aspose.Slides für Java zu verwenden, müssen Sie es als Abhängigkeit in Ihr Projekt einbinden. Je nachdem, ob Sie Maven oder Gradle verwenden, unterscheidet sich die Einrichtung geringfügig.
### Maven
Fügen Sie die folgende Abhängigkeit zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Nehmen Sie dies in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Direkter Download
Alternativ können Sie die neueste Version herunterladen von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).
**Schritte zum Lizenzerwerb:**
- Für eine kostenlose Testversion besuchen Sie die [Seite zur kostenlosen Testversion](https://releases.aspose.com/slides/java/).
- Um eine temporäre Lizenz zu erhalten, navigieren Sie zum [Seite mit temporärer Lizenz](https://purchase.aspose.com/temporary-license/).
- Erwerben Sie eine Volllizenz über deren [Einkaufsportal](https://purchase.aspose.com/buy).
**Grundlegende Initialisierung:**
So können Sie Aspose.Slides in Ihrer Java-Anwendung initialisieren:
```java
import com.aspose.slides.Presentation;
// Initialisieren eines neuen Präsentationsobjekts
Presentation pres = new Presentation();
```
Lassen Sie uns nun mit der Erstellung von Diagrammen beginnen!
## Implementierungshandbuch
### Funktion 1: Diagrammerstellung mit Standardmarkierungen
Dieser Abschnitt zeigt, wie Sie ein Liniendiagramm mit Markierungen erstellen. Diese Funktion ist für die effektive Visualisierung von Datentrends unerlässlich.
#### Hinzufügen eines Liniendiagramms
So fügen Sie ein Liniendiagramm mit Markierungen hinzu:
```java
import com.aspose.slides.*;
// Greifen Sie auf die erste Folie zu
ISlide slide = pres.getSlides().get_Item(0);
// Fügen Sie der Folie an Position (10, 10) und in der Größe (400, 400) ein Liniendiagramm mit Markierungen hinzu.
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Clearing-Serien und -Kategorien
So fangen Sie neu an:
```java
// Löschen Sie vorhandene Serien und Kategorien, um einen sauberen Start zu gewährleisten
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Holen Sie sich die Datenarbeitsmappe des Diagramms zur weiteren Bearbeitung
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Funktion 2: Hinzufügen von Serien und Kategorien
Das Hinzufügen von Reihen und Kategorien ist entscheidend, um Ihre Diagramme mit aussagekräftigen Daten zu füllen.
#### Erstellen einer neuen Serie
So fügen Sie eine neue Serie mit dem Namen „Serie 1“ hinzu:
```java
// Dem Diagramm eine neue Reihe hinzufügen
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Zugriff auf die erste Reihe zur Datenpopulation
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Auffüllen von Kategorien und Datenpunkten
So fügen Sie Kategorien und entsprechende Datenpunkte hinzu:
```java
// Fügen Sie Kategorienamen und die entsprechenden Datenpunkte hinzu
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Null-Datenpunkte ordnungsgemäß verarbeiten
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Funktion 3: Hinzufügen einer zweiten Reihe und Auffüllen von Datenpunkten
Durch das Hinzufügen zusätzlicher Reihen verleihen Sie Ihren Diagrammen mehr Tiefe.
#### Erstellen und Füllen einer zweiten Serie
So fügen Sie „Serie 2“ hinzu:
```java
// Fügen Sie eine weitere Serie mit dem Namen „Serie 2“ hinzu
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Zugriff auf die zweite Reihe zur Datenpopulation
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Datenpunkte für „Serie 2“ hinzufügen
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Funktion 4: Konfigurieren der Diagrammlegende
Durch die Konfiguration der Legende wird die Lesbarkeit des Diagramms verbessert.
#### Anpassen der Legendeneinstellungen
So konfigurieren Sie:
```java
// Aktivieren Sie die Legende und legen Sie fest, dass sie die Datenpunkte nicht überlagert.
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Funktion 5: Speichern der Präsentation
Sobald Ihr Diagramm fertig ist, speichern Sie die Präsentation in einer Datei.
```java
try {
    // Speichern Sie die geänderte Präsentation in einem angegebenen Verzeichnis
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Praktische Anwendungen
1. **Geschäftsberichterstattung:**
   - Verwenden Sie Diagramme in Finanzberichten, um Trends im Zeitverlauf darzustellen.
2. **Datenanalyse:**
   - Visualisieren Sie Datenmuster und Korrelationen während der Analysephasen.
3. **Lehrmaterialien:**
   - Erstellen Sie informative Folien für akademische Vorlesungen oder Präsentationen.
4. **Projektmanagement:**
   - Verbessern Sie Projektzeitpläne mit visuellen Diagrammelementen.
5. **Marketingpräsentationen:**
   - Präsentieren Sie Verkaufstrends und Kampagnenergebnisse effektiv mithilfe von Diagrammen.
## Abschluss
Sie haben gelernt, wie Sie mit Aspose.Slides Liniendiagramme mit Markierungen in Java erstellen, Serien und Kategorien hinzufügen, Legenden konfigurieren und Präsentationen speichern. Diese Kenntnisse sind wertvoll für die Erstellung dynamischer visueller Inhalte in verschiedenen professionellen Anwendungen.
Um mehr über die Funktionen von Aspose.Slides zu erfahren oder Community-Support zu suchen, besuchen Sie deren [offizielle Dokumentation](https://docs.aspose.com/slides/java/) oder treten Sie Foren wie Stack Overflow bei.
Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
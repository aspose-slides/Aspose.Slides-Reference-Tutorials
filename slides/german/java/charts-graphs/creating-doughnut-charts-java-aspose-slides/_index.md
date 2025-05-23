---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides Ringdiagramme in Java-Präsentationen erstellen und anpassen, einschließlich der Einrichtung Ihrer Umgebung und der Anpassung der Diagrammästhetik."
"title": "So erstellen Sie Ringdiagramme in Java mit Aspose.Slides für Präsentationen"
"url": "/de/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie Ringdiagramme in Java mit Aspose.Slides für Präsentationen

## Einführung
Visuell ansprechende Präsentationen sind für die effektive Informationsvermittlung unerlässlich. Diagramme sind wichtige Elemente, die das Verständnis von Datenverteilungen verbessern. Dieses Tutorial führt Sie durch die Erstellung anpassbarer Ringdiagramme mit Aspose.Slides für Java und ermöglicht Ihnen eine mühelose Diagrammerstellung mit umfangreichen Anpassungsmöglichkeiten wie Lochgröße und -positionierung.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für Java
- Erstellen und Konfigurieren von Ringdiagrammen in Präsentationen
- Anpassen der Diagrammästhetik, z. B. der Lochgröße
- Speichern der Präsentation mit Ihrem neuen Diagramm

Beginnen wir mit der Einrichtung unserer Umgebung!

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

### Erforderliche Bibliotheken und Versionen
Um mit Aspose.Slides für Java zu arbeiten, binden Sie es über Maven oder Gradle in Ihr Projekt ein oder laden Sie es direkt herunter.

#### Anforderungen für die Umgebungseinrichtung
- Ein funktionierendes Java Development Kit (JDK), vorzugsweise Version 8 oder höher.
- Eine integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse.

### Voraussetzungen
Kenntnisse in Java und grundlegenden Programmierkonzepten sind von Vorteil. Grundkenntnisse in Maven oder Gradle erleichtern die Einrichtung.

## Einrichten von Aspose.Slides für Java
Die Einbindung von Aspose.Slides in Ihr Projekt kann auf verschiedene Arten erfolgen:

**Maven:**
Fügen Sie diese Abhängigkeit zu Ihrem `pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Nehmen Sie dies in Ihre `build.gradle` Datei:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktdownload:**
Alternativ können Sie die neueste Version von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Lizenzerwerb
- **Kostenlose Testversion**: Laden Sie zunächst eine Testversion herunter, um die Funktionen von Aspose.Slides zu erkunden.
- **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz für erweiterte Funktionalität ohne Einschränkungen.
- **Kaufen**: Für die dauerhafte Nutzung ist der Erwerb einer Lizenz erforderlich.

Sobald Sie die Bibliothek eingerichtet und Ihre Umgebung bereit haben, können wir mit der Implementierung unseres Ringdiagramms fortfahren.

## Implementierungshandbuch

### Erstellen eines Ringdiagramms
Das Erstellen einer Präsentation mit einem benutzerdefinierten Ringdiagramm mit Aspose.Slides umfasst mehrere Schritte. Wir schlüsseln sie der Übersichtlichkeit halber auf:

#### Präsentationsobjekt initialisieren
Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse, die Ihr PowerPoint-Dokument darstellt.
```java
// Erstellen Sie eine Instanz der Präsentationsklasse, um ein PPTX-Dokument darzustellen
Presentation presentation = new Presentation();
```
Dieser Schritt initialisiert Ihre Präsentation und Sie können Folien und Diagramme hinzufügen.

#### Ringdiagramm zur Folie hinzufügen
Greifen Sie auf die erste Folie zu (oder erstellen Sie bei Bedarf eine) und fügen Sie ein Ringdiagramm hinzu:
```java
// Greifen Sie auf die erste Folie der Präsentation zu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position bei (50, 50) mit Größe 400x400
```
Dieser Codeausschnitt fügt der ersten Folie ein Ringdiagramm hinzu. Die Parameter definieren dessen Position und Abmessungen auf der Folie.

#### Donut-Lochgröße konfigurieren
Um Ihrem Ringdiagramm ein einzigartiges Aussehen zu verleihen, passen Sie die Lochgröße an:
```java
// Stellen Sie die Lochgröße für das Ringdiagramm auf 90 % ein
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Hier stellen wir die Lochgröße auf 90 % ein, sodass es fast ein vollständiger Kreis ist. Passen Sie diesen Wert Ihren Designanforderungen an.

#### Präsentation speichern
Nachdem Sie Ihr Diagramm konfiguriert haben, speichern Sie die Präsentation:
```java
// Speichern Sie die Präsentation im PPTX-Format im angegebenen Verzeichnis auf der Festplatte
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Diese Zeile schreibt Ihre Änderungen in eine Datei namens `DoughnutHoleSize_out.pptx` in Ihrem angegebenen Verzeichnis.

#### Ressourcen bereinigen
Stellen Sie abschließend sicher, dass Sie das Präsentationsobjekt entsorgen:
```java
// Entsorgen Sie das Präsentationsobjekt, um Ressourcen freizugeben
if (presentation != null) presentation.dispose();
```
Dieser Schritt ist für die Ressourcenverwaltung und die Vermeidung von Speicherlecks von entscheidender Bedeutung.

### Praktische Anwendungen
Ringdiagramme sind vielseitig einsetzbar. Hier sind einige Szenarien, in denen sie überzeugen:
1. **Budgetzuweisung**: Zeigen Sie an, wie ein Budget auf die Abteilungen verteilt ist.
2. **Umfrageergebnisse**: Visualisieren Sie Antworten auf Fragen mit Multiple-Choice-Antworten.
3. **Website-Verkehrsquellen**: Zeigt den Prozentsatz des Datenverkehrs an, der aus verschiedenen Quellen stammt.

### Überlegungen zur Leistung
Beachten Sie beim Arbeiten mit Aspose.Slides diese Tipps für eine optimale Leistung:
- Verwalten Sie den Speicher, indem Sie Objekte entsorgen, wenn sie nicht mehr benötigt werden.
- Verwenden Sie Streams für große Datensätze, um den Speicherverbrauch zu minimieren.
- Optimieren Sie Ihren Code, indem Sie, wo möglich, Instanzen wiederverwenden.

## Abschluss
Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.Slides für Java ein Ringdiagramm erstellen und anpassen. Dieses Tutorial behandelte die Einrichtung der Bibliothek, das Hinzufügen von Diagrammen zu Präsentationen und die Anpassung ihres Erscheinungsbilds.

Um die Möglichkeiten von Aspose.Slides weiter zu erkunden, können Sie mit anderen Diagrammtypen experimentieren oder tiefer in die Funktionen zur Präsentationsautomatisierung eintauchen.

**Nächste Schritte:**
- Experimentieren Sie mit verschiedenen Diagrammkonfigurationen.
- Entdecken Sie die zusätzliche Aspose.Slides-Dokumentation für erweiterte Funktionen.

Bereit, Ihre eigenen Ringdiagramme zu erstellen? Versuchen Sie diese Lösung in Ihrem nächsten Projekt zu implementieren!

## FAQ-Bereich
1. **Kann ich die Farben meiner Ringdiagrammsegmente anpassen?**
   Ja, Sie können Segmentfarben anpassen mit `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` , um einen einfarbigen Fülltyp festzulegen und die gewünschte Farbe anzugeben.

2. **Wie füge ich meinem Diagramm Datenbeschriftungen hinzu?**
   Verwenden `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` und ähnliche Methoden zum programmgesteuerten Hinzufügen von Datenpunkten und Beschriftungen.

3. **Ist es möglich, Diagramme in anderen Formaten als PPTX zu speichern?**
   Absolut! Aspose.Slides unterstützt verschiedene Ausgabeformate wie PDF, XPS und Bildformate wie PNG oder JPEG.

4. **Was passiert, wenn beim Speichern der Präsentation ein Fehler auftritt?**
   Stellen Sie sicher, dass Ihr Verzeichnispfad korrekt ist und Sie über Schreibberechtigungen für den angegebenen Speicherort verfügen. Überprüfen Sie, ob die von Ihnen verwendete Version von Aspose.Slides das Dateiformat unterstützt, in dem Sie speichern möchten.

5. **Kann ich Diagrammaktualisierungen mit Live-Datenquellen automatisieren?**
   Ja, durch die Integration von APIs oder Datenbanken in Ihre Java-Anwendung können Sie Diagrammdaten dynamisch aktualisieren und Präsentationen nach Bedarf auffrischen.

## Ressourcen
- **Dokumentation**: Entdecken Sie detaillierte API-Referenzen unter [Aspose.Slides für Java](https://reference.aspose.com/slides/java/).
- **Herunterladen**: Holen Sie sich die neueste Bibliotheksversion von [Aspose.Slides-Versionen](https://releases.aspose.com/slides/java/).
- **Kaufen**: Für den vollständigen Zugriff erwerben Sie eine Lizenz unter [Aspose Kauf](https://purchase.aspose.com/buy).
- **Kostenlose Testversion**: Testen Sie Aspose.Slides mit einer kostenlosen Testversion, die auf der Download-Seite verfügbar ist.
- **Temporäre Lizenz**Erwerben Sie eine temporäre Lizenz für erweiterte Tests ohne Einschränkungen.
- **Unterstützung**: Haben Sie Fragen? Besuchen Sie die [Aspose Forum](https://forum.aspose.com/c/slides/11) um Hilfe.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
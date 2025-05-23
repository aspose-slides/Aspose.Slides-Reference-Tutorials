---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides dynamische Diagramme in .NET-Präsentationen erstellen. Diese Anleitung behandelt die Einrichtung, Diagrammerstellung und Anpassung."
"title": "So erstellen und passen Sie Diagramme in .NET-Präsentationen mit Aspose.Slides für .NET an"
"url": "/de/net/charts-graphs/create-customize-charts-net-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und passen Sie Diagramme in .NET-Präsentationen mit Aspose.Slides für .NET an

## Einführung
In der heutigen datengetriebenen Welt ist die effektive Visualisierung von Informationen für Geschäftspräsentationen und akademische Berichte unerlässlich. Diagramme sind wichtige Werkzeuge, um komplexe Daten klar und prägnant zu vermitteln. Dieses Tutorial führt Sie durch die Erstellung dynamischer Diagramme in .NET-Präsentationen mit Aspose.Slides für .NET – einer leistungsstarken Bibliothek, die die Dokumentenautomatisierung vereinfacht.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für .NET
- Erstellen einer Präsentation mit einem gruppierten Säulendiagramm
- Formatieren von Datenpunkten in Ihren Diagrammen

Am Ende dieses Tutorials verfügen Sie über praktische Erfahrung beim Erstellen und Anpassen von Diagrammen in .NET-Präsentationen mit Aspose.Slides.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:

- **Erforderliche Bibliotheken:**
  - Aspose.Slides für .NET (Version 23.x oder höher)

- **Umgebungs-Setup:**
  - Eine Entwicklungsumgebung mit installiertem .NET Framework oder .NET Core
  - Visual Studio oder eine andere IDE, die C#-Projekte unterstützt

- **Erforderliche Kenntnisse:**
  - Grundlegende Kenntnisse in C#
  - Vertrautheit mit Microsoft Office-Präsentationen und Diagrammen

## Einrichten von Aspose.Slides für .NET

### Installationsschritte:

#### Verwenden der .NET-CLI:
```bash
dotnet add package Aspose.Slides
```

#### Verwenden der Paketmanager-Konsole:
```powershell
Install-Package Aspose.Slides
```

#### NuGet-Paket-Manager-Benutzeroberfläche:
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb
Um alle Funktionen von Aspose.Slides nutzen zu können, benötigen Sie eine Lizenz. Diese erhalten Sie über:
- **Kostenlose Testversion:** Beginnen Sie mit einer vorübergehenden kostenlosen Testversion, um die grundlegenden Funktionen kennenzulernen.
- **Temporäre Lizenz:** Erwerben Sie eine temporäre Lizenz für den vollständigen Zugriff ohne Einschränkungen während der Evaluierung.
- **Kaufen:** Erwägen Sie für laufende Projekte den Kauf eines Abonnements.

### Grundlegende Initialisierung
Um Aspose.Slides in Ihrem Projekt zu initialisieren, schließen Sie den Namespace ein und instanziieren Sie ein `Presentation` Objekt:

```csharp
using Aspose.Slides;
// Instanziieren Sie die Präsentationsklasse, die eine PPTX-Datei darstellt
Presentation pres = new Presentation();
```

## Implementierungshandbuch
Wir werden das Erstellen von Präsentationen und das Hinzufügen von Diagrammen mit Aspose.Slides für .NET durchgehen.

### Funktion 1: Präsentationserstellung und Diagrammergänzung

#### Überblick:
Diese Funktion zeigt, wie Sie eine Präsentation erstellen und der ersten Folie ein gruppiertes Säulendiagramm hinzufügen. Diagramme sind für die effektive Visualisierung von Datentrends unerlässlich.

#### Schrittweise Implementierung:

##### 1. Pfad zum Speichern von Dokumenten festlegen
Geben Sie zunächst an, wo Ihre Dateien gespeichert werden sollen.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

##### 2. Instanziieren Sie ein neues Präsentationsobjekt
Erstellen Sie eine Instanz des `Presentation` Klasse, um mit der Erstellung Ihrer Präsentation zu beginnen.

```csharp
Presentation pres = new Presentation();
```

##### 3. Greifen Sie auf die erste Folie zu
Erhalten Sie Zugriff auf die erste Folie Ihrer Präsentation mit:

```csharp
ISlide slide = pres.Slides[0];
```

##### 4. Fügen Sie ein gruppiertes Säulendiagramm hinzu
Fügen Sie an der gewünschten Position auf der Folie ein Diagramm hinzu.

```csharp
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
```
Dadurch wird ein gruppiertes Säulendiagramm an den Koordinaten (50, 50) mit den Abmessungen 500 x 400 Pixel hinzugefügt.

##### 5. Speichern Sie die Präsentation
Speichern Sie Ihre Präsentation abschließend im angegebenen Verzeichnis.

```csharp
pres.Save(dataDir + "CreatePresentationWithChart_out.pptx", SaveFormat.Pptx);
```

### Funktion 2: Festlegen eines voreingestellten Zahlenformats für Diagrammdatenpunkte

#### Überblick:
Erfahren Sie, wie Sie für Datenpunkte in Diagrammreihen ein voreingestelltes Zahlenformat (z. B. Prozent) festlegen und so die Lesbarkeit Ihrer Diagramme verbessern.

#### Schrittweise Implementierung:

##### 1. Zugriff auf und Durchlaufen von Serien
Greifen Sie nach dem Hinzufügen Ihres Diagramms auf die Seriensammlung zu.

```csharp
IChartSeriesCollection series = chart.ChartData.Series;
```

##### 2. Formatieren Sie jeden Datenpunkt
Legen Sie für jeden Datenpunkt in der Reihe ein Zahlenformat von „0,00 %“ fest.

```csharp
foreach (ChartSeries ser in series)
{
    foreach (IChartDataPoint cell in ser.DataPoints)
    {
        // Zahlenformat für bessere Lesbarkeit festlegen
        cell.Value.AsCell.PresetNumberFormat = 10; // Formatieren als 0,00 %
    }
}
```

##### 3. Speichern Sie die Präsentation mit formatierten Zahlen

```csharp
pres.Save(dataDir + "SetPresetNumberFormat_out.pptx", SaveFormat.Pptx);
```

## Praktische Anwendungen
- **Geschäftsberichte:** Verwenden Sie Diagramme, um Verkaufsdatentrends über ein Quartal darzustellen.
- **Akademische Projekte:** Visualisieren Sie die Ergebnisse statistischer Analysen in Forschungsarbeiten.
- **Marketingpräsentationen:** Zeigen Sie Kennzahlen zur Kundensegmentierung und Kundenbindung an.

Aspose.Slides lässt sich nahtlos in andere Systeme integrieren und ermöglicht die Automatisierung von Dokumenten-Workflows in Unternehmensumgebungen.

## Überlegungen zur Leistung
So gewährleisten Sie eine optimale Leistung bei der Verwendung von Aspose.Slides:
- **Optimieren Sie die Datenverarbeitung:** Beschränken Sie Datenpunkte auf die notwendigen Informationen.
- **Ressourcenmanagement:** Entsorgen Sie Objekte entsprechend, um Speicher freizugeben.
- **Bewährte Methoden:** Nutzen `using` Anweisungen für die Ressourcenverwaltung und berücksichtigen Sie nach Möglichkeit asynchrone Vorgänge.

## Abschluss
Sie haben nun gelernt, wie Sie mit Aspose.Slides Diagramme in .NET-Präsentationen erstellen und anpassen. Diese Anleitung soll Ihnen helfen, diese Funktionen effektiv in Ihren Projekten zu implementieren. Entdecken Sie weitere Funktionen wie das Hinzufügen verschiedener Diagrammtypen oder die Integration von Aspose.Slides in andere Microsoft Office-Komponenten für mehr Produktivität.

### Nächste Schritte:
- Experimentieren Sie mit verschiedenen Diagrammstilen und Datensätzen.
- Integrieren Sie Aspose.Slides in vorhandene .NET-Anwendungen zur automatischen Berichterstellung.

## FAQ-Bereich
1. **Was ist der Hauptzweck von Aspose.Slides?**
   - Es wird zum programmgesteuerten Erstellen, Ändern und Verwalten von Präsentationen in .NET-Umgebungen verwendet.
2. **Kann ich Diagrammtypen mit Aspose.Slides anpassen?**
   - Ja, Sie können verschiedene Diagrammtypen hinzufügen, darunter Balken-, Linien-, Kreisdiagramme usw., wobei Anpassungsoptionen verfügbar sind.
3. **Wie gehe ich mit großen Datensätzen in Diagrammen um?**
   - Optimieren Sie Ihre Datenpunkte und ziehen Sie in Erwägung, Daten für eine bessere Leistung zusammenzufassen.
4. **Gibt es Unterstützung für andere Microsoft Office-Formate?**
   - Ja, Aspose.Slides unterstützt die Konvertierung zwischen verschiedenen Office-Formaten wie PowerPoint zu PDF.
5. **Wo bekomme ich Hilfe, wenn ich auf Probleme stoße?**
   - Der [Aspose.Slides Forum](https://forum.aspose.com/c/slides/11) ist eine großartige Ressource für Unterstützung und Diskussionen.

## Ressourcen
- **Dokumentation:** [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/net/)
- **Herunterladen:** [Neuerscheinungen](https://releases.aspose.com/slides/net/)
- **Kaufen:** [Aspose.Slides kaufen](https://purchase.aspose.com/buy)
- **Kostenlose Testversion:** [Kostenlose Testversion starten](https://releases.aspose.com/slides/net/)
- **Temporäre Lizenz:** [Beantragung einer temporären Lizenz](https://purchase.aspose.com/temporary-license/)
- **Unterstützung:** [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

Mit diesem Leitfaden sind Sie bestens gerüstet, um mit Aspose.Slides professionelle Präsentationen mit dynamischen Diagrammen in .NET zu erstellen. Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
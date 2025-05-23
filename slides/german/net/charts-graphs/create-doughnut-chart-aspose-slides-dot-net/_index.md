---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET mühelos Ringdiagramme in PowerPoint-Präsentationen erstellen und anpassen. Optimieren Sie Ihre visuelle Datenpräsentation mit diesem umfassenden Leitfaden."
"title": "So erstellen Sie ein Ringdiagramm in PowerPoint mit Aspose.Slides für .NET – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein Ringdiagramm in PowerPoint mit Aspose.Slides für .NET: Eine Schritt-für-Schritt-Anleitung

## Einführung

Die Erweiterung Ihrer PowerPoint-Präsentationen mit optisch ansprechenden Ringdiagrammen kann die Datendarstellung deutlich verbessern. Aspose.Slides für .NET bietet eine effiziente Möglichkeit, diese Diagramme zu erstellen und anzupassen. Dieses Tutorial führt Sie Schritt für Schritt durch die Verwendung von Aspose.Slides für .NET, um Ihren PowerPoint-Folien ein anpassbares Ringdiagramm hinzuzufügen, einschließlich der Anpassung der Lochgrößen.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für .NET
- Schritte zum Hinzufügen eines Ringdiagramms zu Ihrer Folie
- Techniken zum Konfigurieren der Lochgröße Ihres Ringdiagramms
- Praktische Anwendungen und Leistungsüberlegungen

Beginnen wir mit dem, was Sie brauchen, bevor wir eintauchen!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### Erforderliche Bibliotheken und Versionen
- Aspose.Slides für .NET (neueste Version)
- Visual Studio oder jede kompatible IDE, die .NET-Entwicklung unterstützt

### Anforderungen für die Umgebungseinrichtung
- Eine Windows-Umgebung mit installiertem .NET Framework
- Grundkenntnisse der C#-Programmierung

## Einrichten von Aspose.Slides für .NET

Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek installieren. So können Sie dies mit verschiedenen Methoden tun:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Verwenden der Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version direkt über die NuGet-Schnittstelle Ihrer IDE.

### Schritte zum Lizenzerwerb
1. **Kostenlose Testversion:** Laden Sie zunächst eine kostenlose Testversion herunter, um die Funktionen zu testen.
2. **Temporäre Lizenz:** Wenn Sie mehr Zeit benötigen, fordern Sie bei Aspose eine temporäre Lizenz an.
3. **Kaufen:** Für eine langfristige Nutzung sollten Sie den Kauf der Vollversion in Erwägung ziehen.

Initialisieren Sie Ihr Projekt nach der Installation mit diesem Grund-Setup:
```csharp
using Aspose.Slides;

// Initialisieren Sie ein neues Präsentationsobjekt
Presentation presentation = new Presentation();
```

## Implementierungshandbuch

Lassen Sie uns den Prozess der Erstellung eines Ringdiagramms mit Aspose.Slides für .NET in überschaubare Schritte unterteilen.

### Erstellen Sie ein Ringdiagramm

#### Überblick
Wir beginnen damit, Ihrer PowerPoint-Folie ein Ringdiagramm hinzuzufügen und dessen Position und Größe festzulegen.

**Hinzufügen des Diagramms:**
```csharp
using Aspose.Slides.Charts;

// Greifen Sie auf die erste Folie der Präsentation zu (standardmäßig wird eine erstellt)
ISlide slide = presentation.Slides[0];

// Fügen Sie der Folie an Position (50, 50) ein Ringdiagramm mit einer Breite und Höhe von 400 Einheiten hinzu
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parameter:** `ChartType.Doughnut`, x-Position: 50, y-Position: 50, Breite: 400, Höhe: 400.

### Legen Sie die Lochgröße fest

#### Überblick
Als Nächstes konfigurieren wir die Lochgröße des Ringdiagramms, um es optisch ansprechend zu gestalten.

**Lochgröße konfigurieren:**
```csharp
// Stellen Sie die Lochgröße für das Ringdiagramm auf 90 % ein
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Tastenkonfiguration:** `DoughnutHoleSize` bestimmt, wie viel von der Mitte „ausgeschnitten“ wird. Ein Wert zwischen 0 und 100 stellt den Prozentsatz dar.

### Speichern Sie Ihre Präsentation

Speichern Sie abschließend Ihre Änderungen in einer neuen PowerPoint-Datei:
```csharp
// Definieren Sie den Pfad, in dem die Präsentation gespeichert wird
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Speichern Sie die geänderte Präsentation im PPTX-Format
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Notiz:** Ersetzen `YOUR_OUTPUT_DIRECTORY` mit Ihrem gewünschten Dateispeicherort.

### Tipps zur Fehlerbehebung

- Stellen Sie sicher, dass Aspose.Slides korrekt installiert und importiert ist.
- Überprüfen Sie vor dem Speichern der Präsentation, ob Ihr Ausgabeverzeichnispfad vorhanden ist.

## Praktische Anwendungen

Mit Aspose.Slides für .NET erstellte Ringdiagramme können in verschiedenen Szenarien verwendet werden:

1. **Geschäftsberichte:** Veranschaulichen Sie Finanzdaten wie Budgetzuweisungen oder Umsatzverteilungen.
2. **Marketinganalyse:** Zeigen Sie die Marktanteile verschiedener Marken in Prozent an.
3. **Lehrmaterial:** Verwenden Sie es, um statistische Konzepte auf visuell ansprechende Weise zu erklären.

Integrieren Sie Aspose.Slides mit anderen Systemen zur automatischen Berichterstellung und -verteilung innerhalb von Unternehmensumgebungen.

## Überlegungen zur Leistung

Beachten Sie beim Arbeiten mit großen Präsentationen oder zahlreichen Diagrammen die folgenden Tipps:

- Optimieren Sie die Datenverarbeitung, bevor Sie sie zu Folien hinzufügen.
- Um Speicherplatz zu sparen, verwenden Sie Präsentationsobjekte nach Möglichkeit wieder.
- Aktualisieren Sie Ihre Aspose.Slides-Bibliothek regelmäßig, um von Leistungsverbesserungen zu profitieren.

## Abschluss

Sie haben gelernt, wie Sie mit Aspose.Slides für .NET ein Ringdiagramm erstellen und anpassen. Dieses vielseitige Tool verbessert die visuelle Attraktivität Ihrer Präsentationen und macht Daten auf einen Blick leichter verständlich.

**Nächste Schritte:**
Entdecken Sie andere in Aspose.Slides verfügbare Diagrammtypen oder vertiefen Sie sich in erweiterte Funktionen wie Animationen.

Bereit zum Ausprobieren? Gehen Sie zum Ressourcenbereich unten und fangen Sie an zu experimentieren!

## FAQ-Bereich

1. **Wofür wird Aspose.Slides für .NET verwendet?**  
   Es handelt sich um eine Bibliothek zum programmgesteuerten Erstellen, Ändern und Konvertieren von PowerPoint-Präsentationen.

2. **Wie kann ich die Farbe der Donutsegmente ändern?**  
   Verwenden `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` um die Fülleigenschaften anzupassen.

3. **Kann ich mehrere Diagramme in einer Präsentation erstellen?**  
   Ja, fügen Sie so viele Diagramme wie nötig hinzu, indem Sie die Schritte zur Diagrammerstellung auf verschiedenen Folien oder Positionen wiederholen.

4. **Wie lizenziere ich Aspose.Slides für .NET für die kommerzielle Nutzung?**  
   Erwerben Sie eine Lizenz über die offizielle Aspose-Website, um es kommerziell zu nutzen.

5. **Was soll ich tun, wenn meine Präsentation nicht richtig gespeichert wird?**  
   Überprüfen Sie die Dateipfadberechtigungen und stellen Sie sicher, dass Ihre Projektreferenzen auf dem neuesten Stand sind.

## Ressourcen

- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/net/)
- [Laden Sie Aspose.Slides für .NET herunter](https://releases.aspose.com/slides/net/)
- [Erwerben Sie eine Lizenz](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/slides/net/)
- [Antrag auf eine temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Support-Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
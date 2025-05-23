---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie Präsentationen durch die Verknüpfung externer Excel-Daten mit Aspose.Slides für .NET verbessern. Diese Anleitung führt Sie durch die Einrichtung, Konfiguration und Implementierung dynamischer Diagramme."
"title": "So legen Sie eine externe Arbeitsmappe für ein Diagramm in Aspose.Slides .NET fest&#58; Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/data-integration/set-external-workbook-chart-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie eine externe Arbeitsmappe für ein Diagramm in Aspose.Slides .NET fest: Eine Schritt-für-Schritt-Anleitung

## Einführung

Die direkte Einbindung von Daten aus externen Quellen in Ihre Präsentationen steigert deren Wert erheblich. Mit Aspose.Slides für .NET können Sie nahtlos eine externe Arbeitsmappe für Diagramme in Folien einrichten und so dynamische und aktuelle Visualisierungen ermöglichen. Dieses Tutorial führt Sie durch die Verknüpfung einer netzwerkbasierten Excel-Datei mit einem Diagramm in Ihrer Präsentation.

**Was Sie lernen werden:**
- Konfigurieren einer Aspose.Slides .NET-Umgebung.
- Einrichten einer externen Arbeitsmappe von einem Netzwerkspeicherort für Diagramme.
- Implementieren eines benutzerdefinierten Handlers zum Laden von Ressourcen in C#.
- Praktische Anwendungen zur Integration externer Datenquellen in Präsentationen.

Lass uns anfangen!

## Voraussetzungen

Bevor Sie mit der Codierung beginnen, stellen Sie sicher, dass Sie diese Anforderungen erfüllen:

- **Erforderliche Bibliotheken und Abhängigkeiten**: Installieren Sie Aspose.Slides für .NET in Ihrem Projekt.
- **Anforderungen für die Umgebungseinrichtung**: Richten Sie eine C#-Entwicklungsumgebung ein (z. B. Visual Studio).
- **Voraussetzungen**: Grundkenntnisse der C#-Programmierung und Vertrautheit mit Aspose.Slides.

## Einrichten von Aspose.Slides für .NET

Installieren Sie zunächst die Aspose.Slides-Bibliothek in Ihrem Projekt. Sie können eine der folgenden Methoden verwenden:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paket-Manager-Konsole**
```bash
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**: Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb

Um Aspose.Slides zu nutzen, starten Sie mit einer kostenlosen Testversion oder fordern Sie eine temporäre Lizenz an. Für eine langfristige Nutzung können Sie eine Volllizenz auf der offiziellen Website erwerben.

### Grundlegende Initialisierung

So initialisieren Sie Aspose.Slides in Ihrer Anwendung:
```csharp
using Aspose.Slides;

// Initialisieren Sie das Präsentationsobjekt
Presentation pres = new Presentation();
```

## Implementierungshandbuch

Lassen Sie uns die Implementierung in die wichtigsten Funktionen aufschlüsseln.

### Einrichten einer externen Arbeitsmappe vom Netzwerk

Mit dieser Funktion können Sie eine netzwerkbasierte Excel-Datei als externe Arbeitsmappe für ein Diagramm in Ihrer Präsentation verknüpfen.

#### Schritt 1: Geben Sie den externen Arbeitsmappenpfad an
Geben Sie den Pfad Ihrer externen Arbeitsmappe auf einem Netzlaufwerk an:
```csharp
string externalWbPath = "http://IHR_DOKUMENTENVERZEICHNIS/styles/2.xlsx";
```
Ersetzen `YOUR_DOCUMENT_DIRECTORY` mit dem tatsächlichen Verzeichnis, in dem Ihre Excel-Datei gehostet wird.

#### Schritt 2: Ladeoptionen konfigurieren
Richten Sie Ladeoptionen ein und geben Sie einen benutzerdefinierten Rückruf zum Laden von Ressourcen an:
```csharp
LoadOptions opts = new LoadOptions();
opts.ResourceLoadingCallback = new WorkbookLoadingHandler();
```

#### Schritt 3: Präsentation erstellen und Diagramm hinzufügen
Erstellen Sie eine Präsentationsinstanz und fügen Sie der ersten Folie ein Diagramm hinzu:
```csharp
using (Presentation pres = new Presentation(opts))
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
    IChartData chartData = chart.ChartData;
    
    // Festlegen des externen Arbeitsmappenpfads für die Diagrammdaten
    (chartData as ChartData).SetExternalWorkbook(externalWbPath);
}
```

### Handler zum Laden von Arbeitsmappen

Diese Funktion beinhaltet das Erstellen eines benutzerdefinierten Handlers zum Laden von Ressourcen, um die Excel-Datei von Ihrem angegebenen Netzwerkspeicherort abzurufen.

#### Schritt 1: Implementieren des Rückrufs zum Laden von Ressourcen
Erstellen Sie eine Klasse, die implementiert `IResourceLoadingCallback`:
```csharp
class WorkbookLoadingHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(IResourceLoadingArgs args)
    {
        string workbookPath = args.OriginalUri;
        
        // Überprüfen Sie, ob der Pfad ein Netzwerkspeicherort ist (kein lokaler Dateipfad).
        if (workbookPath.IndexOf(':') > 1 && !workbookPath.StartsWith("file:///"))
        {
            try
            {
                WebRequest request = WebRequest.Create(workbookPath);
                request.Credentials = new NetworkCredential("testuser", "testuser");
                
                using (WebResponse response = request.GetResponse())
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Stellen Sie die abgerufenen Daten Aspose.Slides zur Verfügung
                    return ResourceLoadingAction.UserProvided;
                }
            }
            catch (Exception ex)
            {
                throw new InvalidOperationException(ex.ToString());
            }
        }
        else
        {
            return ResourceLoadingAction.Default;
        }
    }
}
```

## Praktische Anwendungen

Hier sind einige Anwendungsfälle aus der Praxis für die Integration externer Datenquellen in Ihre Aspose.Slides-Präsentationen:
1. **Dynamisches Reporting**: Aktualisieren Sie Diagramme in Finanz- oder Leistungsberichten automatisch basierend auf den neuesten Netzwerkdaten.
2. **Geschäfts-Dashboards**: Erstellen Sie interaktive Dashboards, die Livedaten aus Unternehmensdatenbanken oder Remoteservern abrufen.
3. **Bildungsinhalte**: Entwickeln Sie Lehrmaterialien mit aktuellen statistischen Daten zu Themen wie Wirtschaft oder Demografie.

## Überlegungen zur Leistung

Beachten Sie beim Arbeiten mit externen Arbeitsmappen die folgenden Leistungstipps:
- **Netzwerkanforderungen optimieren**: Minimieren Sie die Häufigkeit von Netzwerkanforderungen, um Latenz und Bandbreitennutzung zu reduzieren.
- **Ressourcenmanagement**Sorgen Sie für eine effiziente Speichernutzung, indem Sie Streams umgehend freigeben, wenn sie nicht mehr benötigt werden.
- **Fehlerbehandlung**: Implementieren Sie eine robuste Fehlerbehandlung für Netzwerkprobleme, um einen reibungslosen Anwendungsbetrieb zu gewährleisten.

## Abschluss

Sie sollten nun gut verstehen, wie Sie mit Aspose.Slides für .NET eine externe Arbeitsmappe von einem Netzwerkstandort aus einrichten. Diese Funktion kann die Interaktivität und Datenrelevanz Ihrer Präsentation deutlich verbessern. Für weitere Informationen können Sie weitere Aspose-Bibliotheken integrieren oder zusätzliche von Aspose.Slides unterstützte Diagrammtypen ausprobieren. Setzen Sie diese Lösung in einem Ihrer Projekte ein, um die Vorteile selbst zu erleben!

## FAQ-Bereich

**1. Was ist Aspose.Slides für .NET?**
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, bearbeiten und konvertieren können.

**2. Kann ich Aspose.Slides mit anderen Programmiersprachen verwenden?**
Ja, Aspose bietet ähnliche Bibliotheken für Java, C++, Python und mehr.

**3. Wie gehe ich mit Netzwerkfehlern beim Laden einer externen Arbeitsmappe um?**
Implementieren Sie eine robuste Ausnahmebehandlung in Ihrem `WorkbookLoadingHandler` um potenzielle Netzwerkprobleme elegant zu bewältigen.

**4. Ist es möglich, lokale Dateien anstelle von Netzwerkspeicherorten zu verwenden?**
Ja, Sie können den Pfad ändern in `externalWbPath` um bei Bedarf auf eine lokale Datei zu verweisen.

**5. Kann ich Diagramme automatisch mit neuen Daten aktualisieren?**
Ja, durch das regelmäßige erneute Abrufen und Einrichten der externen Arbeitsmappe spiegeln Ihre Diagramme alle an den Quelldaten vorgenommenen Aktualisierungen wider.

## Ressourcen
- **Dokumentation**: [Aspose.Slides .NET-Dokumentation](https://reference.aspose.com/slides/net/)
- **Herunterladen**: [Aspose.Slides-Releases für .NET](https://releases.aspose.com/slides/net/)
- **Kaufen**: [Aspose.Slides kaufen](https://purchase.aspose.com/buy)
- **Kostenlose Testversion**: [Kostenlose Testversion von Aspose.Slides](https://releases.aspose.com/slides/net/)
- **Temporäre Lizenz**: [Holen Sie sich eine temporäre Lizenz für Aspose.Slides](https://purchase.aspose.com/temporary-license/)
- **Unterstützung**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

Mit diesen Ressourcen sind Sie bestens gerüstet, um das volle Potenzial von Aspose.Slides in Ihren .NET-Projekten auszuschöpfen. Viel Spaß beim Programmieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
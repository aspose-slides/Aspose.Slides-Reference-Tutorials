---
"description": "Erfahren Sie, wie Sie Präsentationen mit Aspose.Slides für .NET in das XAML-Format exportieren. Erstellen Sie mühelos interaktive Inhalte!"
"linktitle": "Präsentation ins XAML-Format exportieren"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Präsentation ins XAML-Format exportieren"
"url": "/de/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Präsentation ins XAML-Format exportieren


In der Softwareentwicklung sind Tools zur Vereinfachung komplexer Aufgaben unerlässlich. Aspose.Slides für .NET ist ein solches Tool, mit dem Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie eine Präsentation mit Aspose.Slides für .NET ins XAML-Format exportieren. 

## Einführung in Aspose.Slides für .NET

Bevor wir mit dem Tutorial beginnen, stellen wir kurz Aspose.Slides für .NET vor. Es handelt sich um eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen erstellen, bearbeiten, konvertieren und verwalten können, ohne Microsoft PowerPoint selbst zu benötigen. Mit Aspose.Slides für .NET können Sie verschiedene Aufgaben im Zusammenhang mit PowerPoint-Präsentationen automatisieren und so Ihren Entwicklungsprozess effizienter gestalten.

## Voraussetzungen

Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

1. Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für .NET installiert und zur Verwendung in Ihrem .NET-Projekt bereit haben.

2. Quellpräsentation: Sie verfügen über eine PowerPoint-Präsentation (PPTX), die Sie in das XAML-Format exportieren möchten. Stellen Sie sicher, dass Sie den Pfad zu dieser Präsentation kennen.

3. Ausgabeverzeichnis: Wählen Sie ein Verzeichnis, in dem Sie die generierten XAML-Dateien speichern möchten.

## Schritt 1: Richten Sie Ihr Projekt ein

In diesem ersten Schritt richten wir unser Projekt ein und stellen sicher, dass alle erforderlichen Komponenten bereit sind. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides für .NET-Bibliothek hinzugefügt haben.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Pfad zur Quellpräsentation
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

Ersetzen `"Your Document Directory"` mit dem Pfad zum Verzeichnis, das Ihre PowerPoint-Quellpräsentation enthält. Geben Sie außerdem das Ausgabeverzeichnis an, in dem die generierten XAML-Dateien gespeichert werden.

## Schritt 2: Präsentation nach XAML exportieren

Exportieren wir nun die PowerPoint-Präsentation in das XAML-Format. Dazu verwenden wir Aspose.Slides für .NET. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Konvertierungsoptionen erstellen
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Definieren Sie Ihren eigenen Output-sparenden Service
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Folien konvertieren
    pres.Save(xamlOptions);

    // Speichern von XAML-Dateien in einem Ausgabeverzeichnis
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

In diesem Codeausschnitt laden wir die Quellpräsentation, erstellen XAML-Konvertierungsoptionen und definieren einen benutzerdefinierten Ausgabespeicherdienst mit `NewXamlSaver`. Anschließend speichern wir die XAML-Dateien im angegebenen Ausgabeverzeichnis.

## Schritt 3: Benutzerdefinierte XAML Saver-Klasse

Um den benutzerdefinierten XAML-Saver zu implementieren, erstellen wir eine Klasse namens `NewXamlSaver` das implementiert die `IXamlOutputSaver` Schnittstelle.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Diese Klasse übernimmt das Speichern von XAML-Dateien im Ausgabeverzeichnis.

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie eine PowerPoint-Präsentation mit Aspose.Slides für .NET in das XAML-Format exportieren. Dies kann eine wertvolle Fähigkeit bei der Arbeit an Projekten sein, bei denen Präsentationen bearbeitet werden.

Entdecken Sie weitere Funktionen und Möglichkeiten von Aspose.Slides für .NET, um Ihre PowerPoint-Automatisierungsaufgaben zu verbessern.

## FAQs

1. ### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine .NET-Bibliothek für die programmgesteuerte Arbeit mit PowerPoint-Präsentationen.

2. ### Wo bekomme ich Aspose.Slides für .NET?
Sie können Aspose.Slides für .NET herunterladen von [Hier](https://purchase.aspose.com/buy).

3. ### Gibt es eine kostenlose Testversion?
Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten. [Hier](https://releases.aspose.com/).

4. ### Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
Sie können eine vorübergehende Lizenz erhalten [Hier](https://purchase.aspose.com/temporary-license/).

5. ### Wo erhalte ich Support für Aspose.Slides für .NET?
Sie finden Support und Community-Diskussionen [Hier](https://forum.aspose.com/).

Weitere Tutorials und Ressourcen finden Sie im [Aspose.Slides API-Dokumentation](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie beim Konvertieren von Präsentationen in HTML mit Aspose.Slides für .NET durch direktes Einbetten von Schriftarten eine konsistente Schriftartwiedergabe sicherstellen."
"title": "So verknüpfen Sie Schriftarten in HTML mit Aspose.Slides für .NET – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So verknüpfen Sie Schriftarten in HTML mit Aspose.Slides für .NET

## Einführung

Das Konvertieren von Präsentationen in HTML unter Beibehaltung einer konsistenten Schriftartdarstellung auf allen Plattformen kann eine Herausforderung sein. **Aspose.Slides für .NET** bietet eine nahtlose Lösung, indem Sie alle in einer Präsentation verwendeten Schriftarten über eingebettete Schriftartdateien direkt in der HTML-Ausgabe verknüpfen können.

In diesem Tutorial erfahren Sie, wie Sie die Schriftartverknüpfung mit Aspose.Slides für .NET implementieren und die Designkonsistenz über verschiedene Plattformen hinweg sicherstellen. 

**Was Sie lernen werden:**
- Einrichten Ihrer Umgebung mit Aspose.Slides für .NET
- Verknüpfen von Schriftarten bei der HTML-Konvertierung
- Schreiben benutzerdefinierter Controller zum Einbetten von Schriftarten
- Praktische Anwendungen und Leistungsüberlegungen

Lassen Sie uns einen Blick auf die Schritte werfen, die erforderlich sind, um dies zu erreichen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

### Erforderliche Bibliotheken und Abhängigkeiten
- **Aspose.Slides für .NET** Bibliothek: Die Kernkomponente für unsere Implementierung.

### Anforderungen für die Umgebungseinrichtung
- Eine Entwicklungsumgebung mit installiertem .NET Framework oder .NET Core.

### Voraussetzungen
- Grundlegende Kenntnisse der C#-Programmierung.
- Vertrautheit mit HTML und CSS, insbesondere mit `@font-face` Regel.

## Einrichten von Aspose.Slides für .NET

Um Aspose.Slides in Ihrem .NET-Projekt zu verwenden, müssen Sie die Bibliothek installieren. Hier sind mehrere Methoden:

### Verwenden der .NET-CLI
```bash
dotnet add package Aspose.Slides
```

### Verwenden der Package Manager-Konsole
```powershell
Install-Package Aspose.Slides
```

### Über die NuGet-Paket-Manager-Benutzeroberfläche
- Öffnen Sie Ihr Projekt in Visual Studio.
- Navigieren Sie zum „NuGet-Paket-Manager“.
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Schritte zum Lizenzerwerb
Sie können eine kostenlose Testlizenz erhalten, um alle Funktionen ohne Einschränkungen zu testen, indem Sie die folgenden Schritte ausführen:
1. **Kostenlose Testversion**: Laden Sie eine temporäre Lizenz herunter [Hier](https://releases.aspose.com/slides/net/).
2. **Temporäre Lizenz**: Beantragen Sie einen erweiterten Zugang [Hier](https://purchase.aspose.com/temporary-license/).
3. **Kaufen**: Für die volle Funktionalität erwerben Sie eine Lizenz [Hier](https://purchase.aspose.com/buy).

### Grundlegende Initialisierung und Einrichtung
```csharp
// Erstellen Sie eine Instanz der Lizenzklasse
easpose.slides.License license = new aspose.slides.License();

// Wenden Sie die Lizenz aus dem Dateipfad an
license.SetLicense("Aspose.Slides.lic");
```

## Implementierungshandbuch

Lassen Sie uns nun die Schriftverknüpfung in der HTML-Konvertierung implementieren, indem wir **Aspose.Slides für .NET**.

### Funktionsübersicht: Verknüpfen von Schriftarten bei der HTML-Konvertierung
Diese Funktion stellt sicher, dass alle in einer Präsentation verwendeten Schriftarten durch Einbettung der Schriftdateien direkt in der resultierenden HTML-Datei verknüpft sind. Diese Methode bietet eine robuste Lösung für die Gewährleistung der Designkonsistenz über verschiedene Browser und Plattformen hinweg.

#### Schritt 1: Erstellen des benutzerdefinierten Controllers
Erstellen einer benutzerdefinierten Controllerklasse `LinkAllFontsHtmlController` welches erbt von `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Legen Sie das Verzeichnis fest, in dem die Schriftdateien gespeichert werden
    }
}
```
#### Schritt 2: Implementieren Sie die Methode zum Schreiben von Schriftarten
Der `WriteFont` Die Methode schreibt die Schriftdaten in eine Datei und generiert entsprechenden HTML-Code zum Einbetten:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Bestimmen Sie den zu verwendenden Schriftartnamen und bevorzugen Sie, sofern verfügbar, Ersatzschriftarten.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Erstellen Sie einen Dateipfad für die .woff-Schriftdatei.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Schreiben Sie die Schriftdaten in den angegebenen Dateipfad.
    File.WriteAllBytes(path, fontData);

    // Generieren Sie einen HTML-Stilblock, der die Schriftart mithilfe der Regel @font-face einbettet.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
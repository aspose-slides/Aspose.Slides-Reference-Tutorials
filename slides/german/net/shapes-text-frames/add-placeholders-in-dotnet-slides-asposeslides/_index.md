---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET effizient Inhalte, vertikalen Text, Diagramme und Tabellenplatzhalter zu Ihren PowerPoint-Folien hinzufügen."
"title": "So fügen Sie Platzhalter in .NET-Folien mit Aspose.Slides hinzu"
"url": "/de/net/shapes-text-frames/add-placeholders-in-dotnet-slides-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So fügen Sie mit Aspose.Slides Platzhalter in .NET-Folien hinzu

## Einführung

Suchen Sie nach einer effizienten Möglichkeit, Platzhalter wie Inhalte, vertikalen Text, Diagramme und Tabellen in Ihren Präsentationen zu automatisieren? Mit Aspose.Slides für .NET wird dieser Prozess nahtlos. Dieses Tutorial führt Sie durch die Verwendung von Aspose.Slides, um das Hinzufügen von Platzhaltern in PowerPoint-Folien in einer .NET-Umgebung zu optimieren.

In diesem umfassenden Leitfaden untersuchen wir:
- Einrichten von Aspose.Slides für .NET
- Schritt-für-Schritt-Anleitung zum Hinzufügen verschiedener Platzhalter
- Reale Anwendungen dieser Funktionen
- Leistungsüberlegungen für eine optimale Nutzung

## Voraussetzungen

### Erforderliche Bibliotheken und Versionen
Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Aspose.Slides für .NET-Bibliotheksversion 22.x oder höher.
- Eine kompatible .NET-Umgebung (z. B. .NET Core 3.1 oder höher).

### Anforderungen für die Umgebungseinrichtung
Stellen Sie sicher, dass Ihre Entwicklungsumgebung mit Visual Studio oder einer anderen IDE eingerichtet ist, die .NET-Projekte unterstützt.

### Voraussetzungen
Grundkenntnisse in C# und Vertrautheit mit .NET-Programmierkonzepten sind von Vorteil, aber nicht erforderlich, da wir im Laufe des Kurses alle Grundlagen behandeln.

## Einrichten von Aspose.Slides für .NET
Um Aspose.Slides in Ihrem Projekt verwenden zu können, müssen Sie es installieren. So geht's:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Verwenden der Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb
Um Aspose.Slides auszuprobieren, können Sie eine kostenlose Testversion wählen oder eine temporäre Lizenz erwerben. Für den produktiven Einsatz empfiehlt sich der Erwerb einer Volllizenz. Besuchen Sie [Asposes Kaufseite](https://purchase.aspose.com/buy) um mehr über Lizenzierungsoptionen zu erfahren.

#### Grundlegende Initialisierung
Initialisieren Sie Ihr Projekt, indem Sie eine Instanz des `Presentation` Klasse:
```csharp
using Aspose.Slides;
// ...
var presentation = new Presentation();
```

## Implementierungshandbuch

### Platzhalter für Inhalte hinzufügen
Durch Hinzufügen eines Inhaltsplatzhalters können Sie Text, Bilder und andere Medien in Folien einfügen. So geht's mit Aspose.Slides für .NET.

#### Überblick
Dieser Abschnitt führt Sie durch den Vorgang zum Hinzufügen eines Inhaltsplatzhalters zu einem leeren Folienlayout mit Aspose.Slides für .NET.

#### Implementierungsschritte
**1. Richten Sie Ihr Projekt ein**
Beginnen Sie mit der Erstellung eines neuen C#-Projekts und der Installation der Aspose.Slides-Bibliothek, wie zuvor erwähnt.

**2. Präsentation initialisieren**
Erstellen Sie eine Instanz von `Presentation` So arbeiten Sie mit Folien:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "content_placeholder.pptx");

using (var pres = new Presentation())
{
    // Der Code wird hier hinzugefügt.
}
```
**3. Zugriff auf die Layoutfolie**
Rufen Sie die leere Layoutfolie ab, auf der Sie Ihren Platzhalter hinzufügen:
```csharp
// Abrufen der leeren Layoutfolie.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
Dieser Schritt greift auf ein vordefiniertes leeres Layout zu, das sich ideal für benutzerdefinierte Designs eignet.

**4. Platzhalter für Inhalte hinzufügen**
Verwenden Sie die `PlaceholderManager` So fügen Sie einen Inhaltsplatzhalter an den angegebenen Koordinaten und in der angegebenen Größe ein:
```csharp
// Abrufen des Platzhalter-Managers der Layoutfolie.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Hinzufügen eines Inhaltsplatzhalters an Position (10, 10) mit der Größe (300 x 200).
placeholderManager.AddContentPlaceholder(10, 10, 300, 200);
```
Die Parameter definieren die Position `(x, y)` und Abmessungen `(width x height)` des Platzhalters.

**5. Präsentation speichern**
Speichern Sie abschließend Ihre Präsentationsdatei:
```csharp
// Speichern der Präsentation mit hinzugefügtem Inhaltsplatzhalter.
pres.Save(outFilePath, SaveFormat.Pptx);
```
Dadurch wird das geänderte Layout in einem angegebenen Verzeichnis gespeichert.

### Platzhalter für vertikalen Text hinzufügen
Vertikale Textplatzhalter eignen sich perfekt für Seitenleisten oder einzigartige Designelemente, bei denen eine Änderung der Textausrichtung erforderlich ist.

#### Überblick
In diesem Abschnitt erfahren Sie, wie Sie einen vertikalen Textplatzhalter hinzufügen, um die Ästhetik Ihrer Folie zu verbessern.

#### Implementierungsschritte
**1. Präsentation initialisieren**
Erstellen Sie eine neue Instanz von `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "vertical_text_placeholder.pptx");

using (var pres = new Presentation())
{
    // Der Code wird hier hinzugefügt.
}
```
**2. Zugriff auf die Layoutfolie**
Rufen Sie die leere Layoutfolie ab:
```csharp
// Abrufen der leeren Layoutfolie.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Vertikalen Textplatzhalter hinzufügen**
Fügen Sie einen vertikalen Textplatzhalter hinzu, indem Sie `PlaceholderManager`:
```csharp
// Abrufen des Platzhalter-Managers der Layoutfolie.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Hinzufügen eines vertikalen Textplatzhalters an Position (350, 10) mit der Größe (200 x 300).
placeholderManager.AddVerticalTextPlaceholder(350, 10, 200, 300);
```
**4. Präsentation speichern**
Speichern Sie Ihre Präsentation:
```csharp
// Speichern der Präsentation mit hinzugefügtem vertikalen Textplatzhalter.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Diagrammplatzhalter hinzufügen
Diagramme sind für die Datendarstellung in Präsentationen unerlässlich. So fügen Sie mit Aspose.Slides einen Diagrammplatzhalter hinzu.

#### Überblick
Dieser Abschnitt hilft Ihnen, mit Aspose.Slides einen Diagrammplatzhalter in Ihre PowerPoint-Folien zu integrieren.

#### Implementierungsschritte
**1. Präsentation initialisieren**
Erstellen Sie eine Instanz von `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "chart_placeholder.pptx");

using (var pres = new Presentation())
{
    // Der Code wird hier hinzugefügt.
}
```
**2. Zugriff auf die Layoutfolie**
Rufen Sie die leere Layoutfolie ab:
```csharp
// Abrufen der leeren Layoutfolie.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Diagrammplatzhalter hinzufügen**
Verwenden `PlaceholderManager` So fügen Sie einen Diagrammplatzhalter hinzu:
```csharp
// Abrufen des Platzhalter-Managers der Layoutfolie.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Hinzufügen eines Diagrammplatzhalters an Position (10, 350) mit der Größe (300 x 300).
placeholderManager.AddChartPlaceholder(10, 350, 300, 300);
```
**4. Präsentation speichern**
Speichern Sie Ihre Präsentation:
```csharp
// Speichern der Präsentation mit hinzugefügtem Diagrammplatzhalter.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Tabellenplatzhalter hinzufügen
Tabellen organisieren Daten effektiv und werden in Präsentationen häufig zur Verdeutlichung verwendet.

#### Überblick
Erfahren Sie, wie Sie mit Aspose.Slides einen Tabellenplatzhalter hinzufügen, um die Informationen auf Ihren Folien übersichtlich zu strukturieren.

#### Implementierungsschritte
**1. Präsentation initialisieren**
Erstellen Sie eine Instanz von `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "table_placeholder.pptx");

using (var pres = new Presentation())
{
    // Der Code wird hier hinzugefügt.
}
```
**2. Zugriff auf die Layoutfolie**
Rufen Sie die leere Layoutfolie ab:
```csharp
// Abrufen der leeren Layoutfolie.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Tabellenplatzhalter hinzufügen**
Verwenden `PlaceholderManager` So fügen Sie einen Tabellenplatzhalter hinzu:
```csharp
// Abrufen des Platzhalter-Managers der Layoutfolie.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Hinzufügen eines Tabellenplatzhalters an Position (350, 350) mit der Größe (300 x 200).
placeholderManager.AddTablePlaceholder(350, 350, 300, 200);
```
**4. Präsentation speichern**
Speichern Sie Ihre Präsentation:
```csharp
// Speichern der Präsentation mit hinzugefügtem Tabellenplatzhalter.
pres.Save(outFilePath, SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
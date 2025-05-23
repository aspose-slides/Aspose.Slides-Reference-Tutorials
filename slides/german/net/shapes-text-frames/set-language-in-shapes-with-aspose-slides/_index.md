---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Sprachattribute für Text in Formen festlegen. Diese Anleitung behandelt das Hinzufügen automatischer Formen, das Festlegen von Sprach-IDs und das Speichern von Präsentationen."
"title": "So legen Sie die Sprache in PowerPoint-Formen mit Aspose.Slides für .NET fest"
"url": "/de/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie die Sprache in PowerPoint-Formen mit Aspose.Slides für .NET fest

In der Welt digitaler Präsentationen kann es eine Herausforderung sein, sicherzustellen, dass Ihre Inhalte in verschiedenen Sprachen barrierefrei und korrekt formatiert sind. Mit Aspose.Slides für .NET können Sie mühelos Sprachattribute für Text in Formen in PowerPoint-Folien festlegen. Diese Funktion ist besonders nützlich bei der Erstellung mehrsprachiger Dokumente oder zur Gewährleistung der Konsistenz in der globalen Kommunikation.

**Was Sie lernen werden:**
- Automatische Formen hinzufügen und Text darin einfügen.
- Festlegen der Sprach-ID für Textabschnitte mithilfe von Aspose.Slides.
- Speichern von Präsentationen mit benutzerdefinierten Konfigurationen.

Lassen Sie uns einen Blick darauf werfen, wie Sie diese Funktion nahtlos implementieren können.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Bibliotheken und Abhängigkeiten**: Sie müssen Aspose.Slides für .NET installiert haben. Diese Bibliothek ist für die Bearbeitung von PowerPoint-Präsentationen in C# unerlässlich.
  
- **Umgebungs-Setup**: Eine Entwicklungsumgebung mit .NET Core oder .NET Framework ist erforderlich.

- **Voraussetzungen**: Kenntnisse der grundlegenden C#-Programmierkonzepte und ein Verständnis der Prinzipien der objektorientierten Programmierung sind hilfreich.

## Einrichten von Aspose.Slides für .NET

Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek installieren. Sie können dies mit einer der folgenden Methoden tun:

**.NET-CLI**
```shell
dotnet add package Aspose.Slides
```

**Paketmanager**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb

Sie können mit einer kostenlosen Testversion beginnen, indem Sie eine temporäre Lizenz herunterladen von [Hier](https://purchase.aspose.com/temporary-license/). Für die dauerhafte Nutzung erwägen Sie den Erwerb einer Lizenz über [dieser Link](https://purchase.aspose.com/buy).

Sobald Ihr Setup fertig ist, initialisieren Sie Aspose.Slides in Ihrem Projekt:

```csharp
using Aspose.Slides;
```

## Implementierungshandbuch

Nachdem wir nun alles eingerichtet haben, implementieren wir die Funktion zum Festlegen der Sprache für Formtext.

### Funktionsübersicht: Sprache für Shape-Text festlegen

Mit dieser Funktion können Sie die Sprache des Textes in einer PowerPoint-Form festlegen. Durch Festlegen der Sprach-ID stellen Sie sicher, dass die Rechtschreibprüfung und andere sprachspezifische Funktionen korrekt angewendet werden.

#### Schritt 1: Präsentation initialisieren

Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse.

```csharp
using (Presentation pres = new Presentation())
{
    // Ihr Code hier
}
```

Dadurch wird ein neues PowerPoint-Präsentationsobjekt initialisiert, das wir bearbeiten werden.

#### Schritt 2: Automatische Form und Textrahmen hinzufügen

Fügen Sie Ihrer Folie eine rechteckige Form hinzu und fügen Sie Text ein:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Hier, `AddAutoShape` Fügt der ersten Folie ein Rechteck hinzu. Die Parameter definieren dessen Position und Größe.

#### Schritt 3: Sprach-ID festlegen

Legen Sie die Sprache für den Textteil innerhalb der Form fest:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Dadurch wird Englisch (UK) als Sprache für die Rechtschreibprüfung zugewiesen.

#### Schritt 4: Speichern Sie die Präsentation

Speichern Sie Ihre Präsentation abschließend in einem angegebenen Pfad:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
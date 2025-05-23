---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Miniaturansichten für PowerPoint-Folien erstellen. Optimieren Sie Ihre Präsentationen ganz einfach."
"linktitle": "Miniaturansicht aus Folie generieren"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Generieren Sie Folienminiaturen mit Aspose.Slides für .NET"
"url": "/de/net/slide-thumbnail-generation/generate-thumbnail-from-slide/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generieren Sie Folienminiaturen mit Aspose.Slides für .NET


In der Welt digitaler Präsentationen ist die Erstellung ansprechender und informativer Folienvorschaubilder unerlässlich, um die Aufmerksamkeit Ihres Publikums zu gewinnen. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie in Ihren .NET-Anwendungen Vorschaubilder aus Folien erstellen können. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie dies mit Aspose.Slides für .NET erreichen.

## Voraussetzungen

Bevor wir mit dem Generieren von Miniaturansichten aus Folien beginnen, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für die .NET-Bibliothek

Stellen Sie sicher, dass die Bibliothek Aspose.Slides für .NET installiert ist. Sie können sie von der [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) oder verwenden Sie den NuGet-Paket-Manager in Visual Studio.

### 2. .NET-Entwicklungsumgebung

Auf Ihrem System sollte eine funktionierende .NET-Entwicklungsumgebung, einschließlich Visual Studio, installiert sein.

## Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces für Aspose.Slides importieren. So gehen Sie dazu vor:

### Schritt 1: Öffnen Sie Ihr Projekt

Öffnen Sie Ihr .NET-Projekt in Visual Studio.

### Schritt 2: Using-Direktiven hinzufügen

Fügen Sie in der Codedatei, in der Sie mit Aspose.Slides arbeiten möchten, die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Slides;
using System.Drawing;
```

Nachdem Sie Ihre Umgebung eingerichtet haben, ist es an der Zeit, mit Aspose.Slides für .NET Miniaturansichten aus Folien zu generieren.

## Miniaturansicht aus Folie generieren

In diesem Abschnitt unterteilen wir den Vorgang zum Erstellen einer Miniaturansicht aus einer Folie in mehrere Schritte.

### Schritt 1: Definieren Sie das Dokumentverzeichnis

Geben Sie das Verzeichnis an, in dem sich Ihre Präsentationsdatei befindet. Ersetzen Sie `"Your Document Directory"` mit dem tatsächlichen Pfad.

```csharp
string dataDir = "Your Document Directory";
```

### Schritt 2: Öffnen Sie die Präsentation

Verwenden Sie die `Presentation` Klasse, um Ihre PowerPoint-Präsentation zu öffnen. Stellen Sie sicher, dass Sie den richtigen Dateipfad haben.

```csharp
using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlide.pptx"))
{
    // Greifen Sie auf die erste Folie zu
    ISlide sld = pres.Slides[0];

    // Erstellen Sie ein Bild in Originalgröße
    Bitmap bmp = sld.GetThumbnail(1f, 1f);

    // Speichern Sie das Bild im JPEG-Format auf der Festplatte
    bmp.Save(dataDir + "Thumbnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
}
```

Hier ist eine kurze Erklärung, was jeder Schritt bewirkt:

1. Sie öffnen Ihre PowerPoint-Präsentation über das `Presentation` Klasse.
2. Zur ersten Folie gelangen Sie über das `ISlide` Schnittstelle.
3. Sie erstellen ein Vollbild der Folie mit dem `GetThumbnail` Verfahren.
4. Sie speichern das generierte Bild im JPEG-Format in Ihrem angegebenen Verzeichnis.

Das war's! Sie haben mit Aspose.Slides für .NET erfolgreich eine Miniaturansicht aus einer Folie erstellt.

## Abschluss

Aspose.Slides für .NET vereinfacht die Erstellung von Folienvorschauen in Ihren .NET-Anwendungen. Mit den in dieser Anleitung beschriebenen Schritten erstellen Sie ganz einfach ansprechende Folienvorschauen, die Ihr Publikum begeistern.

Egal, ob Sie ein Präsentationsmanagementsystem erstellen oder Ihre Geschäftspräsentationen optimieren – Aspose.Slides für .NET ermöglicht Ihnen die effiziente Arbeit mit PowerPoint-Dokumenten. Probieren Sie es aus und erweitern Sie die Möglichkeiten Ihrer Anwendung.

Wenn Sie Fragen haben oder weitere Hilfe benötigen, können Sie sich jederzeit an die [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die Aspose-Community auf ihrer [Support-Forum](https://forum.aspose.com/).

---

## FAQs (Häufig gestellte Fragen)

### Ist Aspose.Slides für .NET mit den neuesten .NET Framework-Versionen kompatibel?
Ja, Aspose.Slides für .NET wird regelmäßig aktualisiert, um die neuesten .NET Framework-Versionen zu unterstützen.

### Kann ich mit Aspose.Slides für .NET Miniaturansichten von bestimmten Folien innerhalb einer Präsentation erstellen?
Natürlich können Sie von jeder Folie innerhalb einer Präsentation Miniaturansichten erstellen, indem Sie den entsprechenden Folienindex auswählen.

### Gibt es Lizenzierungsoptionen für Aspose.Slides für .NET?
Ja, Aspose bietet verschiedene Lizenzoptionen an, darunter auch temporäre Lizenzen für Testzwecke. Sie können diese auf der [Aspose-Kaufseite](https://purchase.aspose.com/buy).

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten von der [Aspose-Veröffentlichungsseite](https://releases.aspose.com/).

### Wie erhalte ich Support für Aspose.Slides für .NET, wenn ich auf Probleme stoße oder Fragen habe?
Sie können Hilfe suchen und an Diskussionen im Aspose Community Support Forum teilnehmen [Hier](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
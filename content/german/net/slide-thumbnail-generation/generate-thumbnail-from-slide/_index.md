---
title: Generieren Sie Folienminiaturansichten mit Aspose.Slides für .NET
linktitle: Miniaturansicht aus Folie generieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET PowerPoint-Folienminiaturansichten generieren. Verbessern Sie Ihre Präsentationen ganz einfach.
type: docs
weight: 11
url: /de/net/slide-thumbnail-generation/generate-thumbnail-from-slide/
---

In der Welt der digitalen Präsentationen ist die Erstellung ansprechender und informativer Miniaturansichten von Folien ein wesentlicher Bestandteil, um die Aufmerksamkeit Ihres Publikums zu erregen. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie Miniaturansichten von Folien in Ihren .NET-Anwendungen generieren können. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie dies mit Aspose.Slides für .NET erreichen.

## Voraussetzungen

Bevor wir uns mit dem Generieren von Miniaturansichten aus Folien befassen, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für .NET-Bibliothek

 Stellen Sie sicher, dass die Aspose.Slides für .NET-Bibliothek installiert ist. Sie können es hier herunterladen[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) oder verwenden Sie NuGet Package Manager in Visual Studio.

### 2. .NET-Entwicklungsumgebung

Auf Ihrem System sollte eine funktionierende .NET-Entwicklungsumgebung, einschließlich Visual Studio, installiert sein.

## Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces für Aspose.Slides importieren. Hier sind die Schritte dazu:

### Schritt 1: Öffnen Sie Ihr Projekt

Öffnen Sie Ihr .NET-Projekt in Visual Studio.

### Schritt 2: Using-Anweisungen hinzufügen

Fügen Sie in der Codedatei, in der Sie mit Aspose.Slides arbeiten möchten, die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Slides;
using System.Drawing;
```

Nachdem Sie nun Ihre Umgebung eingerichtet haben, ist es an der Zeit, mit Aspose.Slides für .NET Miniaturansichten von Folien zu generieren.

## Miniaturansicht aus Folie generieren

In diesem Abschnitt unterteilen wir den Prozess der Generierung einer Miniaturansicht aus einer Folie in mehrere Schritte.

### Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Sie sollten das Verzeichnis angeben, in dem sich Ihre Präsentationsdatei befindet. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad.

```csharp
string dataDir = "Your Document Directory";
```

### Schritt 2: Öffnen Sie die Präsentation

 Benutzen Sie die`Presentation` Klasse, um Ihre PowerPoint-Präsentation zu öffnen. Stellen Sie sicher, dass Sie den richtigen Dateipfad haben.

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

1.  Sie öffnen Ihre PowerPoint-Präsentation mit dem`Presentation` Klasse.
2.  Auf die erste Folie gelangen Sie mit`ISlide` Schnittstelle.
3.  Mit dem erstellen Sie ein maßstabsgetreues Bild der Folie`GetThumbnail` Methode.
4. Sie speichern das generierte Bild im JPEG-Format in Ihrem angegebenen Verzeichnis.

Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich eine Miniaturansicht einer Folie generiert.

## Abschluss

Aspose.Slides für .NET vereinfacht die Erstellung von Folienminiaturansichten in Ihren .NET-Anwendungen. Indem Sie die in diesem Leitfaden beschriebenen Schritte befolgen, können Sie ganz einfach ansprechende Folienvorschauen erstellen, um Ihr Publikum anzusprechen.

Ob Sie ein Präsentationsverwaltungssystem aufbauen oder Ihre Geschäftspräsentationen verbessern, Aspose.Slides für .NET ermöglicht Ihnen die effiziente Arbeit mit PowerPoint-Dokumenten. Probieren Sie es aus und erweitern Sie die Fähigkeiten Ihrer Anwendung.

 Wenn Sie Fragen haben oder weitere Hilfe benötigen, können Sie sich jederzeit an die wenden[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) oder wenden Sie sich an die Aspose-Community[Hilfeforum](https://forum.aspose.com/).

---

## FAQs (häufig gestellte Fragen)

### Ist Aspose.Slides für .NET mit den neuesten .NET Framework-Versionen kompatibel?
Ja, Aspose.Slides für .NET wird regelmäßig aktualisiert, um die neuesten .NET Framework-Versionen zu unterstützen.

### Kann ich mit Aspose.Slides für .NET Miniaturansichten von bestimmten Folien innerhalb einer Präsentation generieren?
Sie können auf jeden Fall Miniaturansichten von jeder Folie innerhalb einer Präsentation erstellen, indem Sie den entsprechenden Folienindex auswählen.

### Gibt es Lizenzoptionen für Aspose.Slides für .NET?
Ja, Aspose bietet verschiedene Lizenzierungsoptionen an, darunter auch temporäre Lizenzen für Testzwecke. Sie können sie auf der erkunden[Aspose-Kaufseite](https://purchase.aspose.com/buy).

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET unter erhalten[Aspose-Veröffentlichungsseite](https://releases.aspose.com/).

### Wie kann ich Unterstützung für Aspose.Slides für .NET erhalten, wenn ich auf Probleme stoße oder Fragen habe?
 Im Aspose-Community-Supportforum können Sie Hilfe suchen und an Diskussionen teilnehmen[Hier](https://forum.aspose.com/).

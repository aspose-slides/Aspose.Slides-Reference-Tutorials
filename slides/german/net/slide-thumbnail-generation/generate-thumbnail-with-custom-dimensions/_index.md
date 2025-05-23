---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Miniaturbilder aus PowerPoint-Präsentationen erstellen. Verbessern Sie Benutzerfreundlichkeit und Funktionalität."
"linktitle": "Miniaturansicht mit benutzerdefinierten Abmessungen generieren"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Miniaturansichten in Folien mit benutzerdefinierten Abmessungen generieren"
"url": "/de/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Miniaturansichten in Folien mit benutzerdefinierten Abmessungen generieren


Das Erstellen benutzerdefinierter Miniaturbilder Ihrer PowerPoint-Präsentationen kann von großem Nutzen sein, egal ob Sie eine interaktive Anwendung erstellen, die Benutzerfreundlichkeit verbessern oder Inhalte für verschiedene Plattformen optimieren. In diesem Tutorial führen wir Sie durch die Erstellung benutzerdefinierter Miniaturbilder aus PowerPoint-Präsentationen mithilfe der Bibliothek Aspose.Slides für .NET. Mit dieser leistungsstarken Bibliothek können Sie PowerPoint-Dateien programmgesteuert in .NET-Anwendungen bearbeiten, konvertieren und optimieren.

## Voraussetzungen

Bevor wir mit der Generierung benutzerdefinierter Miniaturbilder beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für .NET

Sie müssen die Bibliothek Aspose.Slides für .NET in Ihrem Projekt installiert haben. Falls noch nicht geschehen, finden Sie hier die erforderliche Dokumentation und Download-Links. [Hier](https://reference.aspose.com/slides/net/).

### 2. Eine PowerPoint-Präsentation

Stellen Sie sicher, dass Sie die PowerPoint-Präsentation haben, aus der Sie ein benutzerdefiniertes Miniaturbild erstellen möchten. Diese Präsentation sollte in Ihrem Projektverzeichnis verfügbar sein.

### 3. Entwicklungsumgebung

Um diesem Lernprogramm folgen zu können, sollten Sie über Grundkenntnisse der .NET-Programmierung mit C# und einer eingerichteten Entwicklungsumgebung wie Visual Studio verfügen.

Nachdem wir nun die Voraussetzungen geklärt haben, wollen wir den Vorgang zum Generieren benutzerdefinierter Miniaturansichten in schrittweise Anweisungen unterteilen.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code einbinden. Diese Namespaces ermöglichen Ihnen die Arbeit mit Aspose.Slides und die Bearbeitung von PowerPoint-Präsentationen.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Schritt 1: Laden Sie die Präsentation

Laden Sie zunächst die PowerPoint-Präsentation, aus der Sie ein benutzerdefiniertes Miniaturbild erstellen möchten. Dies wird mithilfe der Bibliothek Aspose.Slides erreicht.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instanziieren Sie eine Präsentationsklasse, die die Präsentationsdatei darstellt
using (Presentation pres = new Presentation(srcFileName))
{
    // Ihr Code zur Miniaturbildgenerierung wird hier eingefügt
}
```

## Schritt 2: Zugriff auf die Folie

Innerhalb der geladenen Präsentation müssen Sie auf die Folie zugreifen, von der Sie das benutzerdefinierte Miniaturbild erstellen möchten. Sie können die Folie über ihren Index auswählen.

```csharp
// Greifen Sie auf die erste Folie zu (Sie können den Index nach Bedarf ändern)
ISlide sld = pres.Slides[0];
```

## Schritt 3: Benutzerdefinierte Miniaturansicht-Abmessungen definieren

Geben Sie die gewünschten Abmessungen für Ihr benutzerdefiniertes Miniaturbild an. Sie können die Breite und Höhe in Pixeln entsprechend den Anforderungen Ihrer Anwendung definieren.

```csharp
int desiredX = 1200; // Breite
int desiredY = 800;  // Höhe
```

## Schritt 4: Skalierungsfaktoren berechnen

Um das Seitenverhältnis der Folie beizubehalten, berechnen Sie die Skalierungsfaktoren für die X- und Y-Abmessungen basierend auf der Größe der Folie und Ihren gewünschten Abmessungen.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Schritt 5: Generieren Sie das Miniaturbild

Erstellen Sie ein maßstabsgetreues Bild der Folie mit den angegebenen benutzerdefinierten Abmessungen und speichern Sie es im JPEG-Format auf der Festplatte.

```csharp
// Erstellen Sie ein Bild in Originalgröße
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Speichern Sie das Bild im JPEG-Format auf der Festplatte
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nachdem Sie diese Schritte ausgeführt haben, sollten Sie erfolgreich ein benutzerdefiniertes Miniaturbild aus Ihrer PowerPoint-Präsentation generiert haben.

## Abschluss

Das Erstellen benutzerdefinierter Miniaturansichten aus PowerPoint-Präsentationen mit Aspose.Slides für .NET ist eine wertvolle Fähigkeit, die das Benutzererlebnis und die Funktionalität Ihrer Anwendungen verbessern kann. Mit den in diesem Tutorial beschriebenen Schritten erstellen Sie ganz einfach benutzerdefinierte Miniaturansichten, die Ihren spezifischen Anforderungen entsprechen.

---

## FAQs (Häufig gestellte Fragen)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen in .NET-Anwendungen zu arbeiten.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
Die Dokumentation finden Sie [Hier](https://reference.aspose.com/slides/net/).

### Ist die Nutzung von Aspose.Slides für .NET kostenlos?
Aspose.Slides für .NET ist eine kommerzielle Bibliothek. Preis- und Lizenzinformationen finden Sie hier [Hier](https://purchase.aspose.com/buy).

### Benötige ich fortgeschrittene Programmierkenntnisse, um Aspose.Slides für .NET zu verwenden?
Während einige Kenntnisse der .NET-Programmierung von Vorteil sind, bietet Aspose.Slides für .NET eine benutzerfreundliche API, die die Arbeit mit PowerPoint-Präsentationen vereinfacht.

### Ist technischer Support für Aspose.Slides für .NET verfügbar?
Ja, Sie können auf technischen Support und Community-Foren zugreifen [Hier](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Erstellen Sie Miniaturansichten in Folien mit benutzerdefinierten Abmessungen
linktitle: Erstellen Sie eine Miniaturansicht mit benutzerdefinierten Abmessungen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Miniaturbilder aus PowerPoint-Präsentationen generieren. Verbessern Sie Benutzererfahrung und Funktionalität.
type: docs
weight: 13
url: /de/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

Das Erstellen benutzerdefinierter Miniaturbilder Ihrer PowerPoint-Präsentationen kann von großem Nutzen sein, unabhängig davon, ob Sie eine interaktive Anwendung erstellen, das Benutzererlebnis verbessern oder Inhalte für verschiedene Plattformen optimieren. In diesem Tutorial führen wir Sie durch den Prozess der Generierung benutzerdefinierter Miniaturbilder aus PowerPoint-Präsentationen mithilfe der Aspose.Slides für .NET-Bibliothek. Mit dieser leistungsstarken Bibliothek können Sie PowerPoint-Dateien programmgesteuert in .NET-Anwendungen bearbeiten, konvertieren und verbessern.

## Voraussetzungen

Bevor wir mit der Erstellung benutzerdefinierter Miniaturbilder beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für .NET

 In Ihrem Projekt muss die Aspose.Slides for .NET-Bibliothek installiert sein. Falls noch nicht geschehen, finden Sie hier die erforderliche Dokumentation und Download-Links[Hier](https://reference.aspose.com/slides/net/).

### 2. Eine PowerPoint-Präsentation

Stellen Sie sicher, dass Sie über die PowerPoint-Präsentation verfügen, aus der Sie ein benutzerdefiniertes Miniaturbild erstellen möchten. Diese Präsentation sollte in Ihrem Projektverzeichnis zugänglich sein.

### 3. Entwicklungsumgebung

Um diesem Tutorial folgen zu können, sollten Sie über praktische Kenntnisse der .NET-Programmierung mit C# und einer eingerichteten Entwicklungsumgebung wie Visual Studio verfügen.

Nachdem wir nun die Voraussetzungen abgedeckt haben, unterteilen wir den Prozess der Generierung benutzerdefinierter Miniaturansichten in Schritt-für-Schritt-Anleitungen.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code aufnehmen. Mit diesen Namespaces können Sie mit Aspose.Slides arbeiten und PowerPoint-Präsentationen bearbeiten.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Schritt 1: Laden Sie die Präsentation

Laden Sie zunächst die PowerPoint-Präsentation, aus der Sie ein benutzerdefiniertes Miniaturbild erstellen möchten. Dies wird mithilfe der Aspose.Slides-Bibliothek erreicht.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instanziieren Sie eine Präsentationsklasse, die die Präsentationsdatei darstellt
using (Presentation pres = new Presentation(srcFileName))
{
    // Hier finden Sie Ihren Code für die Miniaturbildgenerierung
}
```

## Schritt 2: Greifen Sie auf die Folie zu

Innerhalb der geladenen Präsentation müssen Sie auf die spezifische Folie zugreifen, aus der Sie das benutzerdefinierte Miniaturbild erstellen möchten. Sie können die Folie anhand ihres Index auswählen.

```csharp
// Greifen Sie auf die erste Folie zu (Sie können den Index nach Bedarf ändern)
ISlide sld = pres.Slides[0];
```

## Schritt 3: Definieren Sie benutzerdefinierte Miniaturbildabmessungen

Geben Sie die gewünschten Abmessungen für Ihr benutzerdefiniertes Miniaturbild an. Sie können die Breite und Höhe in Pixel entsprechend den Anforderungen Ihrer Anwendung festlegen.

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

## Schritt 5: Erstellen Sie das Miniaturbild

Erstellen Sie ein maßstabsgetreues Bild der Folie mit den angegebenen benutzerdefinierten Abmessungen und speichern Sie es im JPEG-Format auf der Festplatte.

```csharp
// Erstellen Sie ein Bild in Originalgröße
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Speichern Sie das Bild im JPEG-Format auf der Festplatte
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nachdem Sie diese Schritte ausgeführt haben, sollten Sie erfolgreich ein benutzerdefiniertes Miniaturbild aus Ihrer PowerPoint-Präsentation erstellt haben.

## Abschluss

Das Generieren benutzerdefinierter Miniaturbilder aus PowerPoint-Präsentationen mit Aspose.Slides für .NET ist eine wertvolle Fähigkeit, die das Benutzererlebnis und die Funktionalität Ihrer Anwendungen verbessern kann. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie ganz einfach benutzerdefinierte Miniaturansichten erstellen, die Ihren spezifischen Anforderungen entsprechen.

---

## FAQs (häufig gestellte Fragen)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen in .NET-Anwendungen zu arbeiten.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation finden Sie hier[Hier](https://reference.aspose.com/slides/net/).

### Ist die Nutzung von Aspose.Slides für .NET kostenlos?
 Aspose.Slides für .NET ist eine kommerzielle Bibliothek. Hier finden Sie Preis- und Lizenzinformationen[Hier](https://purchase.aspose.com/buy).

### Benötige ich fortgeschrittene Programmierkenntnisse, um Aspose.Slides für .NET zu verwenden?
Während einige Kenntnisse der .NET-Programmierung von Vorteil sind, bietet Aspose.Slides für .NET eine benutzerfreundliche API, die die Arbeit mit PowerPoint-Präsentationen vereinfacht.

### Ist technischer Support für Aspose.Slides für .NET verfügbar?
 Ja, Sie können auf technischen Support und Community-Foren zugreifen[Hier](https://forum.aspose.com/).
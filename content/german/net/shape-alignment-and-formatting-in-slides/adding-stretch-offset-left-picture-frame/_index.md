---
title: Hinzufügen eines Streckungsversatzes nach links für den Bilderrahmen in Aspose.Slides
linktitle: Hinzufügen eines Streckungsversatzes nach links für den Bilderrahmen in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET einen Streckungsversatz nach links für einen Bildrahmen in PowerPoint hinzufügen. Schritt-für-Schritt-Anleitung mit vollständigem Quellcode-Beispiel.
type: docs
weight: 14
url: /de/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine umfassende Bibliothek, die es .NET-Entwicklern ermöglicht, mit PowerPoint-Präsentationen zu arbeiten, ohne Microsoft Office zu benötigen. Es bietet eine Vielzahl von Funktionen, darunter das Erstellen, Bearbeiten und Bearbeiten von Folien, Formen, Text, Bildern und mehr.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio ist auf Ihrem Computer installiert.
2. Grundlegendes Verständnis von C# und .NET Framework.
3.  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten des Projekts

Beginnen wir mit der Einrichtung eines neuen C#-Projekts in Visual Studio:

1. Öffnen Sie Visual Studio.
2. Klicken Sie auf „Neues Projekt erstellen“.
3. Wählen Sie „Konsolen-App (.NET Framework/Core)“ aus.
4. Wählen Sie einen passenden Namen und Ort für Ihr Projekt.
5. Klicken Sie auf „Erstellen“.

Fügen Sie als Nächstes einen Verweis auf die Aspose.Slides for .NET-Bibliothek in Ihrem Projekt hinzu. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf „Referenzen“, wählen Sie „NuGet-Pakete verwalten“, suchen Sie nach „Aspose.Slides“ und installieren Sie das Paket.

## Hinzufügen eines Streckungsversatzes nach links für den Bilderrahmen

Gehen Sie folgendermaßen vor, um mit Aspose.Slides für .NET einen Streckungsversatz nach links für einen Bilderrahmen hinzuzufügen:

1.  Laden Sie die Präsentationsdatei mit`Presentation` Klasse.
2. Suchen Sie die Folie mit dem Bildrahmen, den Sie ändern möchten.
3. Greifen Sie auf die Bilderrahmenform zu, indem Sie die Formen auf der Folie durchlaufen.
4.  Wenden Sie den Streckungsversatz nach links mit an`PictureFrame` Klasse.

## Beispielcode

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Laden Sie die Präsentation
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // Holen Sie sich die erste Folie
                ISlide slide = presentation.Slides[0];

                // Durchlaufen Sie die Formen auf der Folie
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // Wenden Sie den Streckungsversatz nach links an
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // Speichern Sie die geänderte Präsentation
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

In diesem Beispiel laden wir eine Präsentation, durchlaufen die Formen auf der ersten Folie und wenden, wenn wir eine Bilderrahmenform finden, einen Streckungsversatz von -10 nach links an.

## Testen der Anwendung

Um die Anwendung zu testen, gehen Sie folgendermaßen vor:

1. Stellen Sie sicher, dass Sie über eine Beispiel-PowerPoint-Präsentation verfügen (`sample.pptx`) mit mindestens einem Bilderrahmen.
2. Führen Sie die Anwendung aus.
3.  Die geänderte Präsentation mit dem hinzugefügten Dehnungsversatz wird gespeichert unter`output.pptx`.

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit .NET einen Streckungsversatz nach links für einen Bilderrahmen in Aspose.Slides hinzufügen. Aspose.Slides für .NET bietet leistungsstarke Tools zur programmgesteuerten Bearbeitung von PowerPoint-Präsentationen und ermöglicht Entwicklern die nahtlose Erstellung dynamischer und benutzerdefinierter Diashows.

## FAQs

### Wie kann ich Aspose.Slides für .NET installieren?

 Sie können Aspose.Slides für .NET von der Website herunterladen[Hier](https://releases.aspose.com/slides/net/).

### Kann ich Aspose.Slides für andere PowerPoint-Manipulationsaufgaben verwenden?

Absolut! Aspose.Slides für .NET bietet eine Vielzahl von Funktionen, darunter das Erstellen, Bearbeiten und Konvertieren von PowerPoint-Präsentationen. Weitere Details und Beispiele finden Sie in der Dokumentation.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Formaten kompatibel?

Ja, Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPTX, PPT, POTX und mehr. Es unterstützt auch die Konvertierung zwischen verschiedenen Formaten.

### Wie kann ich andere Eigenschaften von Formen in einer Präsentation anpassen?

Mithilfe der Aspose.Slides-Bibliothek können Sie auf verschiedene Eigenschaften von Formen zugreifen und diese ändern, darunter Text, Position, Größe, Formatierung und mehr. Ausführliche Informationen und Beispiele finden Sie in der Dokumentation.

### Kann ich Aspose.Slides mit anderen Programmiersprachen verwenden?

Ja, Aspose.Slides bietet Bibliotheken für verschiedene Programmiersprachen, darunter Java, Python und mehr. Sie können diejenige auswählen, die zu Ihrer Entwicklungsumgebung passt.
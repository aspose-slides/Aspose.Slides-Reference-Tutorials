---
title: Hinzufügen eines Dehnungsversatzes für die Bildfüllung in Folien mit Aspose.Slides
linktitle: Hinzufügen eines Dehnungsversatzes für die Bildfüllung in Folien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationsfolien mit Aspose.Slides für .NET verbessern. Diese Schritt-für-Schritt-Anleitung behandelt das Hinzufügen von Stretch-Offset für die Bildfüllung, das Erstellen dynamischer Grafiken und die Optimierung des Designs.
type: docs
weight: 18
url: /de/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

In modernen Präsentationen spielen visuelle Elemente eine entscheidende Rolle bei der effektiven Vermittlung von Botschaften. Aspose.Slides, eine leistungsstarke API für die Arbeit mit Präsentationsdateien in .NET, bietet eine Funktion namens „Stretch Offset“, mit der Sie genau steuern können, wie Bilder in Formen gefüllt werden. Dieser Artikel führt Sie durch den Prozess des Hinzufügens eines Dehnungsversatzes für die Bildfüllung in Präsentationsfolien mithilfe von Aspose.Slides für .NET.

## Einführung in den Stretch-Offset

Stretch Offset ist eine wertvolle Technik, wenn Sie die Darstellung von Bildern in Formen anpassen müssen. Damit können Sie die Position und Ausrichtung des Bildes innerhalb einer Form steuern und so kreative und optisch ansprechende Foliendesigns erstellen. Mithilfe der Aspose.Slides-API können Sie den Stretch-Offset programmgesteuert implementieren und Ihre Präsentationen zum Leben erwecken.

## Einrichten Ihrer Entwicklungsumgebung

 Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass Aspose.Slides für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können es von der Aspose-Website herunterladen[Download-Link](https://releases.aspose.com/slides/net/)Befolgen Sie nach dem Herunterladen die Installationsanweisungen, um die API für Ihr Projekt einzurichten.

## Ein Bild zu einer Folie hinzufügen

Um die Stretch-Offset-Funktion zu demonstrieren, beginnen wir damit, mit Aspose.Slides ein Bild zu einer Folie hinzuzufügen. Der folgende Codeausschnitt zeigt, wie dies erreicht wird:

```csharp
// Instanziieren Sie ein Präsentationsobjekt
Presentation presentation = new Presentation();

// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.Slides[0];

// Definieren Sie den Pfad der Bilddatei
string imagePath = "path_to_your_image.jpg";

// Fügen Sie der Folie ein Bild hinzu
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// Speichern Sie die Präsentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Anwenden eines Streckungsversatzes auf Bilder

 Nachdem wir nun ein Bild zu einer Folie hinzugefügt haben, wollen wir untersuchen, wie man einen Streckungsversatz darauf anwendet. Der Dehnungsversatz wird durch zwei Eigenschaften gesteuert:`StretchX` Und`StretchY`. Diese Eigenschaften bestimmen den horizontalen bzw. vertikalen Versatz des Bildes innerhalb der Form.

So können Sie einen Stretch-Offset mit Aspose.Slides implementieren:

```csharp
// Greifen Sie auf das Bildfüllformat zu
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Dehnungsversatz anwenden
pictureFill.StretchX = 0.5; // Horizontaler Versatz von 50 %
pictureFill.StretchY = -0.2; // Vertikaler Versatz von -20 %
```

In diesem Beispiel haben wir einen horizontalen Versatz von 50 % und einen vertikalen Versatz von -20 % festgelegt. Der negative Wert für den vertikalen Versatz verschiebt das Bild innerhalb der Form nach oben.

## Anpassen der Stretch-Offset-Werte

 Das Finden der perfekten Werte für den Dehnungsversatz erfordert möglicherweise einige Versuche, um den gewünschten visuellen Effekt zu erzielen. Passen Sie die Werte an`StretchX` Und`StretchY` passend zu Ihren Design- und Ausrichtungsvorlieben. Experimentieren Sie mit positiven und negativen Werten, um zu sehen, wie sich die Bildplatzierung ändert.

## Verwenden von Stretch-Offset mit verschiedenen Formen

 Der Dehnungsversatz kann auf verschiedene Formtypen angewendet werden, darunter Rechtecke, Ellipsen und mehr. Die Methode für den Zugriff auf`PictureFillFormat` bleibt über alle Formen hinweg konsistent. Fühlen Sie sich frei, verschiedene Formen zu erkunden und mit ihnen zu experimentieren, um einzigartige Folienkompositionen zu erstellen.

## Fortgeschrittene Techniken und Tipps

- Kombinieren Sie Stretch-Offset mit anderen Formatierungsfunktionen für komplizierte Designs.
- Verwenden Sie den Streckungsversatz, um bestimmte Teile eines Bildes innerhalb einer Form hervorzuheben.
-  Nutzen Sie die`PictureFillFormat.TileAsTexture`Eigenschaft, um Bilder innerhalb von Formen anzuordnen, anstatt sie zu strecken.

## Abschluss

Die Integration von Stretch-Offset zum Ausfüllen von Bildern in Präsentationsfolien mit Aspose.Slides eröffnet eine Welt voller kreativer Möglichkeiten. Durch die präzise Kontrolle der Bildpositionierung können Sie die visuelle Wirkung Ihrer Präsentationen verbessern. Indem Sie die in diesem Artikel beschriebenen Schritte befolgen, haben Sie gelernt, wie Sie diese Funktion effektiv nutzen können.

## FAQs

### Wie kann ich Aspose.Slides für .NET herunterladen?

 Sie können Aspose.Slides für .NET von der Aspose-Website herunterladen[Download-Link](https://releases.aspose.com/slides/net/).

### Kann ich den Stretch-Offset für jeden Bildtyp verwenden?

Ja, der Stretch-Offset kann auf Bilder in verschiedenen Formaten angewendet werden, darunter JPG, PNG und mehr.

###  Was passiert, wenn ich beides einstelle?`StretchX` and `StretchY` to the same value?

Wenn Sie beide Eigenschaften auf denselben Wert festlegen, bleibt das Seitenverhältnis des Bildes erhalten, während seine Position innerhalb der Form verschoben wird.

### Ist Stretch-Offset mit Animationen kompatibel?

Ja, Stretch Offset funktioniert nahtlos mit Folienanimationen und ermöglicht Ihnen die Erstellung dynamischer Präsentationen.

### Wie kann ich auf erweiterte Stretch-Offset-Optionen zugreifen?

In der Aspose.Slides-Dokumentation finden Sie ausführliche Informationen zu erweiterten Stretch-Offset-Techniken und -Eigenschaften.
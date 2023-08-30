---
title: Hinzufügen von Bilderrahmen mit relativer Skalierungshöhe in Aspose.Slides
linktitle: Hinzufügen von Bilderrahmen mit relativer Skalierungshöhe in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationen verbessern, indem Sie mit Aspose.Slides für .NET Bilderrahmen mit relativer Skalenhöhe hinzufügen. Erstellen Sie mühelos optisch ansprechende Folien.
type: docs
weight: 17
url: /de/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

## Einführung

In der dynamischen Welt der Präsentationen spielen visuelle Elemente eine entscheidende Rolle für die effektive Vermittlung von Informationen. Mit Aspose.Slides für .NET können Sie über die Grundlagen hinausgehen und Ihre Präsentationen durch die Einbindung von Bilderrahmen mit relativer Skalenhöhe aufwerten. Dieser Leitfaden führt Sie Schritt für Schritt durch den Prozess und vermittelt Ihnen die Fähigkeiten, visuell fesselnde Folien zu erstellen, die auffallen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Aspose.Slides beginnen, dieser Leitfaden hilft Ihnen dabei, die Kunst des Hinzufügens von Bilderrahmen mit relativer Skalierungshöhe zu meistern.

## Hinzufügen von Bilderrahmen mit relativer Skalierungshöhe in Aspose.Slides

Wenn es darum geht, Bilderrahmen mit relativer Skalenhöhe in Aspose.Slides hinzuzufügen, ist der Vorgang bemerkenswert intuitiv. Befolgen Sie diese Schritte, um Ihre Präsentationen zu verbessern:

### Schritt 1: Initialisieren Sie die Präsentation

Beginnen Sie mit der Initialisierung des Präsentationsobjekts mit dem folgenden Code:

```csharp
Presentation presentation = new Presentation();
```

### Schritt 2: Fügen Sie eine Folie hinzu

Um eine neue Folie hinzuzufügen, verwenden Sie den folgenden Codeausschnitt:

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

### Schritt 3: Fügen Sie ein Bild ein

Jetzt ist es an der Zeit, das Bild in die Folie einzufügen. Der folgende Code zeigt, wie dies erreicht wird:

```csharp
byte[] imageBytes = File.ReadAllBytes("image.jpg");
IPPImage image = presentation.Images.AddImage(imageBytes);
slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, image.Width, image.Height, image);
```

### Schritt 4: Skalenhöhe anpassen

Um eine relative Skalenhöhe für den Bilderrahmen zu erstellen, verwenden Sie den folgenden Codeausschnitt:

```csharp
IPictureFrame pictureFrame = (IPictureFrame)slide.Shapes[0];
pictureFrame.PictureFormat.Picture.ImageScale.HeightScale = 50; // Passen Sie den Skalierungsprozentsatz wie gewünscht an
```

## FAQs

### Wie kann ich die Skalenhöhe des Bilderrahmens ändern?

 Um die Skalierungshöhe des Bilderrahmens zu ändern, können Sie die verwenden`PictureFormat.Picture.ImageScale.HeightScale` Eigenschaft und weisen Sie ihr einen gewünschten Prozentwert zu.

### Kann ich einer einzelnen Folie mehrere Bilderrahmen hinzufügen?

Ja, Sie können einer einzelnen Folie mehrere Bilderrahmen hinzufügen, indem Sie die zuvor genannten Schritte für jeden Bilderrahmen ausführen, den Sie einfügen möchten.

### Ist es möglich, die Bilderrahmen in einer Präsentation zu animieren?

Absolut! Aspose.Slides bietet leistungsstarke Animationsfunktionen. Sie können Animationen auf Bilderrahmen anwenden, indem Sie verschiedene in der Bibliothek verfügbare Animationseffekte verwenden.

### Welche Bildformate werden zum Einfügen unterstützt?

Aspose.Slides unterstützt eine Vielzahl von Bildformaten, darunter JPEG, PNG, GIF, BMP und mehr. Sie können Bilder dieser Formate nahtlos in Ihre Folien einfügen.

### Wie kann ich die Position des Bilderrahmens auf der Folie festlegen?

 Sie können die Position des Bildrahmens festlegen, indem Sie beim Hinzufügen des Bildrahmens die X- und Y-Koordinaten angeben`slide.Shapes.AddPictureFrame` Methode.

### Ist es möglich, das Aussehen des Bilderrahmens individuell anzupassen?

Ja, Sie können das Erscheinungsbild des Bilderrahmens mithilfe von Eigenschaften wie Rahmenfarbe, Füllfarbe und mehr anpassen. Ausführliche Informationen finden Sie in der Aspose.Slides-Dokumentation.

## Abschluss

Durch die Einbindung von Bilderrahmen mit relativer Skalenhöhe in Ihre Präsentationen können Sie deren visuelle Attraktivität und Engagement erheblich steigern. Mit Aspose.Slides für .NET wird der Prozess unkompliziert und anpassbar, sodass Sie beeindruckende Folien erstellen können, die einen bleibenden Eindruck hinterlassen. Egal, ob Sie Bildungsinhalte, Geschäftspräsentationen oder kreative Präsentationen erstellen, die Beherrschung dieser Funktion wird Ihre Präsentationsfähigkeiten zweifellos verbessern.

Denken Sie daran, der Schlüssel liegt im Experimentieren und in der Kreativität. Indem Sie die Leistungsfähigkeit von Aspose.Slides nutzen, erstellen Sie nicht nur Folien; Sie schaffen immersive Erlebnisse für Ihr Publikum.
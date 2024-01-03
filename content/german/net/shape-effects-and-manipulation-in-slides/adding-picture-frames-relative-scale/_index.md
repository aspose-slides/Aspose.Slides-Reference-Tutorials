---
title: Tutorial zum Hinzufügen von Bilderrahmen mit Aspose.Slides .NET
linktitle: Hinzufügen von Bilderrahmen mit relativer Skalierungshöhe in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Slides für .NET Bilderrahmen mit relativer Skalierungshöhe hinzufügen. Befolgen Sie diese Schritt-für-Schritt-Anleitung für reibungslose Präsentationen.
type: docs
weight: 17
url: /de/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## Einführung
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler mühelos PowerPoint-Präsentationen in ihren .NET-Anwendungen erstellen, bearbeiten und konvertieren können. In diesem Tutorial befassen wir uns mit dem Prozess des Hinzufügens von Bilderrahmen mit relativer Skalierungshöhe mithilfe von Aspose.Slides für .NET. Befolgen Sie diese Schritt-für-Schritt-Anleitung, um Ihre Fähigkeiten beim Erstellen von Präsentationen zu verbessern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio oder eine andere bevorzugte C#-Entwicklungsumgebung installiert.
- Aspose.Slides für .NET-Bibliothek zu Ihrem Projekt hinzugefügt.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihren C#-Code. Dieser Schritt stellt sicher, dass Sie Zugriff auf die Klassen und Funktionen haben, die von der Aspose.Slides-Bibliothek bereitgestellt werden.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Stellen Sie sicher, dass Sie die Aspose.Slides for .NET-Bibliothek zu Ihrem Projekt hinzufügen, indem Sie darauf verweisen.
## Schritt 2: Präsentation und Bild laden
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Laden Sie das Bild, um es der Präsentationsbildsammlung hinzuzufügen
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
In diesem Schritt erstellen wir ein neues Präsentationsobjekt und laden das Bild, das wir der Präsentation hinzufügen möchten.
## Schritt 3: Bilderrahmen zur Folie hinzufügen
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Fügen Sie nun der ersten Folie der Präsentation einen Bilderrahmen hinzu. Passen Sie die Parameter wie Formtyp, Position und Abmessungen entsprechend Ihren Anforderungen an.
## Schritt 4: Legen Sie die Breite und Höhe der relativen Skala fest
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Stellen Sie die relative Skalierungshöhe und -breite für den Bilderrahmen ein, um den gewünschten Skalierungseffekt zu erzielen.
## Schritt 5: Präsentation speichern
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Abschließend speichern Sie die Präsentation mit dem hinzugefügten Bildrahmen im angegebenen Ausgabeformat.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Bilderrahmen mit relativer Skalierungshöhe hinzufügen. Experimentieren Sie mit verschiedenen Bildern, Positionen und Maßstäben, um optisch ansprechende Präsentationen zu erstellen, die auf Ihre Bedürfnisse zugeschnitten sind.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides unterstützt hauptsächlich .NET-Sprachen, Sie können jedoch auch andere Aspose-Produkte auf Kompatibilität mit anderen Plattformen prüfen.
### Wo finde ich eine ausführliche Dokumentation zu Aspose.Slides für .NET?
 Siehe die[Dokumentation](https://reference.aspose.com/slides/net/) Ausführliche Informationen und Beispiele finden Sie hier.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine bekommen[Kostenlose Testphase](https://releases.aspose.com/) um die Leistungsfähigkeit der Bibliothek zu bewerten.
### Wie erhalte ich Unterstützung für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) um Unterstützung von der Community und den Aspose-Experten zu erhalten.
### Wo kann ich Aspose.Slides für .NET kaufen?
 Sie können Aspose.Slides für .NET bei kaufen[Kaufseite](https://purchase.aspose.com/buy).
---
"description": "Erfahren Sie, wie Sie in Aspose.Slides für .NET Bilderrahmen mit relativer Skalierungshöhe hinzufügen. Folgen Sie dieser Schritt-für-Schritt-Anleitung für nahtlose Präsentationen."
"linktitle": "Hinzufügen von Bilderrahmen mit relativer Skalierungshöhe in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Tutorial zum Hinzufügen von Bilderrahmen mit Aspose.Slides .NET"
"url": "/de/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial zum Hinzufügen von Bilderrahmen mit Aspose.Slides .NET

## Einführung
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen mühelos in ihren .NET-Anwendungen erstellen, bearbeiten und konvertieren können. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für .NET Bilderrahmen mit relativer Skalierung hinzufügen. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um Ihre Präsentationsfähigkeiten zu verbessern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio oder eine andere bevorzugte C#-Entwicklungsumgebung installiert.
- Aspose.Slides für die .NET-Bibliothek zu Ihrem Projekt hinzugefügt.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihren C#-Code. Dieser Schritt stellt sicher, dass Sie Zugriff auf die Klassen und Funktionen der Aspose.Slides-Bibliothek haben.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Fügen Sie die Bibliothek Aspose.Slides für .NET Ihrem Projekt hinzu, indem Sie darauf verweisen.
## Schritt 2: Präsentation und Bild laden
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Laden Sie das Bild, das der Präsentationsbildsammlung hinzugefügt werden soll
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
Fügen Sie nun der ersten Folie der Präsentation einen Bilderrahmen hinzu. Passen Sie die Parameter wie Formtyp, Position und Abmessungen Ihren Anforderungen entsprechend an.
## Schritt 4: Relative Skalenbreite und -höhe festlegen
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Legen Sie die relative Skalierungshöhe und -breite für den Bilderrahmen fest, um den gewünschten Skalierungseffekt zu erzielen.
## Schritt 5: Präsentation speichern
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Abschließend speichern Sie die Präsentation mit dem hinzugefügten Bilderrahmen im angegebenen Ausgabeformat.
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Bilderrahmen mit relativer Skalierungshöhe hinzufügen. Experimentieren Sie mit verschiedenen Bildern, Positionen und Maßstäben, um optisch ansprechende Präsentationen zu erstellen, die auf Ihre Bedürfnisse zugeschnitten sind.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides unterstützt hauptsächlich .NET-Sprachen, Sie können jedoch auch andere Aspose-Produkte auf Kompatibilität mit verschiedenen Plattformen prüfen.
### Wo finde ich eine ausführliche Dokumentation zu Aspose.Slides für .NET?
Weitere Informationen finden Sie im [Dokumentation](https://reference.aspose.com/slides/net/) für umfassende Informationen und Beispiele.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
Ja, Sie können eine [kostenlose Testversion](https://releases.aspose.com/) um die Fähigkeiten der Bibliothek zu bewerten.
### Wie erhalte ich Support für Aspose.Slides für .NET?
Besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) um Hilfe von der Community und Aspose-Experten zu suchen.
### Wo kann ich Aspose.Slides für .NET kaufen?
Sie können Aspose.Slides für .NET kaufen von der [Kaufseite](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
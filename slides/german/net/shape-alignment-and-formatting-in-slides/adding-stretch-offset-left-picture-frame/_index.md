---
"description": "Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET optimieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung, um Bilderrahmen mit einem Streckungsversatz nach links zu versehen."
"linktitle": "Hinzufügen eines Dehnungsversatzes nach links für den Bilderrahmen in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Hinzufügen eines Dehnungsversatzes nach links in PowerPoint mit Aspose.Slide"
"url": "/de/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hinzufügen eines Dehnungsversatzes nach links in PowerPoint mit Aspose.Slide

## Einführung
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen mühelos bearbeiten können. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für .NET einen Streckungsversatz nach links für einen Bilderrahmen hinzufügen. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um Ihre Fähigkeiten im Umgang mit Bildern und Formen in PowerPoint-Präsentationen zu verbessern.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass die Bibliothek installiert ist. Falls nicht, laden Sie sie von der [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
- Entwicklungsumgebung: Verfügen Sie über eine funktionierende Entwicklungsumgebung mit .NET-Funktionen.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr .NET-Projekt:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues Projekt oder öffnen Sie ein vorhandenes. Stellen Sie sicher, dass in Ihrem Projekt auf die Bibliothek Aspose.Slides verwiesen wird.
## Schritt 2: Präsentationsobjekt erstellen
Instanziieren Sie die `Presentation` Klasse, die die PPTX-Datei darstellt:
```csharp
using (Presentation pres = new Presentation())
{
    // Ihr Code für die nachfolgenden Schritte wird hier eingefügt.
}
```
## Schritt 3: Holen Sie sich die erste Folie
Rufen Sie die erste Folie aus der Präsentation ab:
```csharp
ISlide slide = pres.Slides[0];
```
## Schritt 4: Instanziieren des Bildes
Laden Sie das Bild, das Sie verwenden möchten:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Schritt 5: Rechteck-AutoForm hinzufügen
Erstellen Sie eine AutoForm vom Typ „Rechteck“:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Schritt 6: Fülltyp und Bildfüllmodus festlegen
Konfigurieren Sie den Fülltyp und den Bildfüllmodus der Form:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Schritt 7: Bild so einstellen, dass es die Form ausfüllt
Geben Sie das Bild an, mit dem die Form gefüllt werden soll:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Schritt 8: Streckungsversätze festlegen
Definieren Sie den Bildversatz von den entsprechenden Kanten des Begrenzungsrahmens der Form:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Schritt 9: Speichern Sie die Präsentation
Schreiben Sie die PPTX-Datei auf die Festplatte:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich einen Streckungsversatz nach links für einen Bilderrahmen hinzugefügt.
## Abschluss
In diesem Tutorial haben wir die Bearbeitung von Bildrahmen in PowerPoint-Präsentationen mit Aspose.Slides für .NET untersucht. Durch die Schritt-für-Schritt-Anleitung haben Sie Einblicke in die Arbeit mit Bildern, Formen und Offsets gewonnen.
## Häufig gestellte Fragen
### F: Kann ich Streckungsversätze auf andere Formen als Rechtecke anwenden?
A: Während sich dieses Tutorial auf Rechtecke konzentriert, können Streckungsversätze auf verschiedene von Aspose.Slides unterstützte Formen angewendet werden.
### F: Wie kann ich die Dehnungsoffsets für verschiedene Effekte anpassen?
A: Experimentieren Sie mit verschiedenen Offset-Werten, um die gewünschte visuelle Wirkung zu erzielen. Passen Sie die Werte Ihren spezifischen Anforderungen an.
### F: Ist Aspose.Slides mit dem neuesten .NET-Framework kompatibel?
A: Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Framework-Versionen sicherzustellen.
### F: Wo finde ich zusätzliche Beispiele und Ressourcen für Aspose.Slides?
A: Erkunden Sie die [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) für umfassende Beispiele und Anleitungen.
### F: Kann ich mehrere Streckungsversätze auf eine einzelne Form anwenden?
A: Ja, Sie können mehrere Streckungsversätze kombinieren, um komplexe und individuelle visuelle Effekte zu erzielen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
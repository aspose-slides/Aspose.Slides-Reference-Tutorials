---
title: Hinzufügen eines Streckungsversatzes nach links in PowerPoint mit Aspose.Slide
linktitle: Hinzufügen eines Streckungsversatzes nach links für den Bilderrahmen in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET verbessern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung, um den Streckungsversatz nach links für Bilderrahmen hinzuzufügen.
type: docs
weight: 14
url: /de/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Einführung
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die einfache Bearbeitung von PowerPoint-Präsentationen ermöglicht. In diesem Tutorial untersuchen wir den Prozess des Hinzufügens eines Streckungsversatzes nach links für einen Bilderrahmen mithilfe von Aspose.Slides für .NET. Befolgen Sie diese Schritt-für-Schritt-Anleitung, um Ihre Fähigkeiten im Umgang mit Bildern und Formen in PowerPoint-Präsentationen zu verbessern.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Wenn nicht, laden Sie es herunter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
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
Erstellen Sie ein neues Projekt oder öffnen Sie ein bestehendes. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Slides-Bibliothek verwiesen wird.
## Schritt 2: Präsentationsobjekt erstellen
 Instanziieren Sie die`Presentation` Klasse, die die PPTX-Datei darstellt:
```csharp
using (Presentation pres = new Presentation())
{
    // Hier finden Sie Ihren Code für die weiteren Schritte.
}
```
## Schritt 3: Holen Sie sich die erste Folie
Rufen Sie die erste Folie aus der Präsentation ab:
```csharp
ISlide slide = pres.Slides[0];
```
## Schritt 4: Instanziieren Sie das Bild
Laden Sie das Bild, das Sie verwenden möchten:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Schritt 5: Rechteck-AutoForm hinzufügen
Erstellen Sie eine AutoForm vom Typ Rechteck:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Schritt 6: Fülltyp und Bildfüllmodus festlegen
Konfigurieren Sie den Fülltyp und den Bildfüllmodus der Form:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Schritt 7: Stellen Sie das Bild so ein, dass es die Form ausfüllt
Geben Sie das Bild an, um die Form zu füllen:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Schritt 8: Dehnungsversätze angeben
Definieren Sie die Bildversätze von den entsprechenden Kanten des Begrenzungsrahmens der Form:
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
Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich einen Streckungsversatz nach links für einen Bilderrahmen hinzugefügt.
## Abschluss
In diesem Tutorial haben wir den Prozess der Bearbeitung von Bildrahmen in PowerPoint-Präsentationen mit Aspose.Slides für .NET untersucht. Durch Befolgen der Schritt-für-Schritt-Anleitung haben Sie Einblicke in die Arbeit mit Bildern, Formen und Versätzen gewonnen.
## Häufig gestellte Fragen
### F: Kann ich Dehnungsversätze auch auf andere Formen als Rechtecke anwenden?
A: Während sich dieses Tutorial auf Rechtecke konzentriert, können Dehnungsversätze auf verschiedene Formen angewendet werden, die von Aspose.Slides unterstützt werden.
### F: Wie kann ich die Dehnungsversätze für verschiedene Effekte anpassen?
A: Experimentieren Sie mit verschiedenen Offset-Werten, um die gewünschte visuelle Wirkung zu erzielen. Passen Sie die Werte entsprechend Ihren spezifischen Anforderungen an.
### F: Ist Aspose.Slides mit dem neuesten .NET Framework kompatibel?
A: Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET Framework-Versionen sicherzustellen.
### F: Wo finde ich zusätzliche Beispiele und Ressourcen für Aspose.Slides?
 A: Entdecken Sie die[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) Ausführliche Beispiele und Anleitungen finden Sie hier.
### F: Kann ich mehrere Dehnungsversätze auf eine einzelne Form anwenden?
A: Ja, Sie können mehrere Dehnungsversätze kombinieren, um komplexe und individuelle visuelle Effekte zu erzielen.
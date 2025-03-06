---
title: Hinzufügen eines Streckungsversatzes zum Ausfüllen von Bildern in PowerPoint-Präsentationen
linktitle: Hinzufügen eines Streckungsversatzes zum Ausfüllen von Bildern in Folien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET verbessern. Folgen Sie einer Schritt-für-Schritt-Anleitung, um einen Streckungsoffset für die Bildfüllung hinzuzufügen.
weight: 18
url: /de/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hinzufügen eines Streckungsversatzes zum Ausfüllen von Bildern in PowerPoint-Präsentationen

## Einführung
In der dynamischen Welt der Präsentationen spielen visuelle Elemente eine entscheidende Rolle, um die Aufmerksamkeit des Publikums zu fesseln. Aspose.Slides für .NET ermöglicht Entwicklern, ihre PowerPoint-Präsentationen durch eine Reihe robuster Funktionen zu verbessern. Eine dieser Funktionen ist die Möglichkeit, einen Streckungsoffset für die Bildfüllung hinzuzufügen, wodurch kreative und optisch ansprechende Folien erstellt werden können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von der[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET-Entwicklungsumgebung eingerichtet haben.
Beginnen wir nun mit der Schritt-für-Schritt-Anleitung.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces, um die Aspose.Slides-Funktionalität in Ihrer .NET-Anwendung zu nutzen.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues .NET-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Stellen Sie sicher, dass Aspose.Slides für .NET ordnungsgemäß referenziert wird.
## Schritt 2: Präsentationsklasse initialisieren
 Instanziieren Sie den`Presentation` Klasse zur Darstellung der PowerPoint-Datei.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ihr Code kommt hier rein
}
```
## Schritt 3: Holen Sie sich die erste Folie
Rufen Sie die erste Folie aus der Präsentation ab, mit der Sie arbeiten möchten.
```csharp
ISlide sld = pres.Slides[0];
```
## Schritt 4: ImageEx-Klasse instantiieren
 Erstellen Sie eine Instanz des`ImageEx`Klasse zum Verarbeiten des Bildes, das Sie der Folie hinzufügen möchten.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Schritt 5: Bilderrahmen hinzufügen
 Nutzen Sie die`AddPictureFrame` Methode, um der Folie einen Bilderrahmen hinzuzufügen. Geben Sie die Abmessungen und die Position des Rahmens an.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation auf der Festplatte.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich einen Streckungsversatz für die Bildfüllung in Folien hinzugefügt.
## Abschluss
Mit Aspose.Slides für .NET ist das Verbessern Ihrer PowerPoint-Präsentationen jetzt einfacher als je zuvor. In diesem Tutorial haben Sie gelernt, wie Sie Stretch-Offset für die Bildfüllung integrieren und Ihren Folien so ein neues Maß an Kreativität verleihen.
## FAQs
### Kann ich Aspose.Slides für .NET in meinen Webanwendungen verwenden?
Ja, Aspose.Slides für .NET ist sowohl für Desktop- als auch für Webanwendungen geeignet.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung der Community.
### Wo finde ich die vollständige Dokumentation für Aspose.Slides für .NET?
 Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/net/) für detaillierte Informationen.
### Kann ich Aspose.Slides für .NET kaufen?
 Ja, Sie können das Produkt kaufen[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Tutorial zum Formatieren von Ellipsenformen mit Aspose.Slides für .NET
linktitle: Formatieren der Ellipsenform in Folien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie mit Aspose.Slides für .NET beeindruckende Ellipsenformen in PowerPoint. Folgen Sie unserer Schritt-für-Schritt-Anleitung für professionelle Präsentationen.
type: docs
weight: 11
url: /de/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---
## Einführung
Um Ihr Publikum zu fesseln, ist es wichtig, Ihre PowerPoint-Präsentationen mit optisch ansprechenden Formen aufzuwerten. Eine solche Form ist die Ellipse, die Ihren Folien einen Hauch von Eleganz und Professionalität verleihen kann. In diesem Tutorial führen wir Sie durch den Prozess der Formatierung von Ellipsenformen in PowerPoint mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Slides für .NET-Bibliothek, die Sie herunterladen können von[Hier](https://releases.aspose.com/slides/net/).
- Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen zum Erstellen und Speichern von Dateien auf Ihrem System verfügen.
## Namespaces importieren
Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. Dadurch wird sichergestellt, dass Sie Zugriff auf die Klassen und Methoden haben, die für die Arbeit mit Aspose.Slides erforderlich sind.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
Lassen Sie uns das Beispiel nun in mehrere Schritte aufteilen, um eine umfassende Anleitung zum Formatieren von Ellipsenformen in PowerPoint mit Aspose.Slides für .NET zu erhalten.
## Schritt 1: Richten Sie Ihr Projekt ein
 Erstellen Sie ein neues C#-Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.Slides-Bibliothek hinzu. Wenn Sie es noch nicht heruntergeladen haben, finden Sie den Download-Link[Hier](https://releases.aspose.com/slides/net/).
## Schritt 2: Definieren Sie Ihr Dokumentverzeichnis
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Stellen Sie sicher, dass das angegebene Verzeichnis vorhanden ist, oder erstellen Sie es, wenn nicht.
## Schritt 3: Präsentationsklasse instanziieren
```csharp
using (Presentation pres = new Presentation())
{
    // Ihr Code für die Formatierung der Ellipsenform kommt hier hin
}
```
 Erstellen Sie eine Instanz des`Presentation` Klasse, die die PowerPoint-Datei darstellt.
## Schritt 4: Holen Sie sich die erste Folie
```csharp
ISlide sld = pres.Slides[0];
```
Greifen Sie auf die erste Folie Ihrer Präsentation zu.
## Schritt 5: Ellipsen-AutoForm hinzufügen
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Fügen Sie eine Ellipsen-AutoForm in die Folie ein und geben Sie ihre Position und Abmessungen an.
## Schritt 6: Ellipsenform formatieren
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
Wenden Sie eine Formatierung auf die Ellipsenform an und legen Sie die Füllfarbe und Linieneigenschaften fest.
## Schritt 7: Speichern Sie die Präsentation
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation auf der Festplatte.
Befolgen Sie diese Schritte sorgfältig, und Ihre PowerPoint-Präsentation enthält eine schön formatierte Ellipsenform.
## Abschluss
Durch die Einbindung optisch ansprechender Formen wie Ellipsen können Sie die Ästhetik Ihrer PowerPoint-Präsentationen deutlich steigern. Aspose.Slides für .NET macht diesen Prozess nahtlos und ermöglicht Ihnen die mühelose Erstellung professionell aussehender Folien.

## FAQs
### Ist Aspose.Slides mit den neuesten Versionen von PowerPoint kompatibel?
Aspose.Slides gewährleistet die Kompatibilität mit verschiedenen PowerPoint-Versionen, einschließlich der neuesten. Weitere Informationen finden Sie in der[Dokumentation](https://reference.aspose.com/slides/net/) für spezifische Details.
### Kann ich eine kostenlose Testversion von Aspose.Slides für .NET herunterladen?
 Ja, Sie können eine kostenlose Testversion ausprobieren[Hier](https://releases.aspose.com/).
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Besuchen[dieser Link](https://purchase.aspose.com/temporary-license/) um eine vorläufige Lizenz zu erwerben.
### Wo finde ich Unterstützung für Aspose.Slides-bezogene Fragen?
 Bitten Sie die Community um Hilfe bei der[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Gibt es eine direkte Kaufoption für Aspose.Slides für .NET?
 Ja, Sie können die Bibliothek direkt kaufen[Hier](https://purchase.aspose.com/buy).
---
title: Erstellen Sie mit Aspose.Slides atemberaubende Farbverläufe in PowerPoint
linktitle: Füllen von Formen mit Farbverlauf in Präsentationsfolien mithilfe von Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Verbessern Sie Ihre Präsentationen mit Aspose.Slides für .NET! Lernen Sie Schritt für Schritt, wie Sie Formen mit Farbverläufen füllen. Laden Sie jetzt Ihre kostenlose Testversion herunter!
type: docs
weight: 21
url: /de/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## Einführung
Das Erstellen visuell fesselnder Präsentationsfolien ist wichtig, um die Aufmerksamkeit Ihres Publikums zu gewinnen und zu erhalten. In diesem Tutorial führen wir Sie durch den Prozess der Verbesserung Ihrer Folien, indem Sie mithilfe von Aspose.Slides für .NET eine Ellipsenform mit einem Farbverlauf füllen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem Computer installiert.
-  Aspose.Slides für .NET-Bibliothek. Laden Sie es herunter[Hier](https://releases.aspose.com/slides/net/).
- Ein Projektverzeichnis zum Organisieren Ihrer Dateien.
## Namespaces importieren
Fügen Sie in Ihr C#-Projekt die erforderlichen Namespaces für Aspose.Slides ein:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Erstellen Sie eine Präsentation
Beginnen Sie mit der Erstellung einer neuen Präsentation mithilfe der Aspose.Slides-Bibliothek:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ihr Code kommt hier hin...
}
```
## Schritt 2: Fügen Sie eine Ellipsenform hinzu
Fügen Sie in die erste Folie Ihrer Präsentation eine Ellipsenform ein:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Schritt 3: Verlaufsformatierung anwenden
Geben Sie an, dass die Form mit einem Farbverlauf gefüllt werden soll, und definieren Sie die Verlaufseigenschaften:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Schritt 4: Farbverlaufsstopps hinzufügen
Definieren Sie die Farben und Positionen der Farbverlaufsstopps:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie Ihre Präsentation mit der neu hinzugefügten, mit Farbverlauf gefüllten Form:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Wiederholen Sie diese Schritte in Ihrem C#-Code und achten Sie dabei auf die richtige Reihenfolge und Parameterwerte. Das Ergebnis ist eine Präsentationsdatei mit einer optisch ansprechenden Ellipsenform, die mit einem Farbverlauf gefüllt ist.
## Abschluss
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## FAQs
### F: Kann ich Farbverläufe auch auf andere Formen als Ellipsen anwenden?
A: Natürlich! Aspose.Slides für .NET unterstützt Farbverlaufsfüllungen für verschiedene Formen wie Rechtecke, Polygone und mehr.
### F: Wo finde ich weitere Beispiele und ausführliche Dokumentation?
 A: Erkunden Sie die[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) für umfassende Anleitungen und Beispiele.
### F: Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 A: Ja, Sie können auf eine kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### F: Wie kann ich Support für Aspose.Slides für .NET erhalten?
A: Suchen Sie Hilfe und engagieren Sie sich in der Community auf der[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### F: Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 A: Natürlich können Sie eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
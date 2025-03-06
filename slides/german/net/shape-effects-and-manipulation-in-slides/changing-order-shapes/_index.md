---
title: Neugestaltung von Präsentationsfolien mit Aspose.Slides für .NET
linktitle: Ändern der Reihenfolge von Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Präsentationsfolien mit Aspose.Slides für .NET neu gestalten. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um Formen neu anzuordnen und die visuelle Attraktivität zu verbessern.
weight: 26
url: /de/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Neugestaltung von Präsentationsfolien mit Aspose.Slides für .NET

## Einführung
Das Erstellen optisch ansprechender Präsentationsfolien ist ein entscheidender Aspekt effektiver Kommunikation. Aspose.Slides für .NET ermöglicht Entwicklern die programmgesteuerte Bearbeitung von Folien und bietet eine breite Palette an Funktionen. In diesem Tutorial werden wir uns mit dem Prozess der Änderung der Reihenfolge von Formen in Präsentationsfolien mithilfe von Aspose.Slides für .NET befassen.
## Voraussetzungen
Bevor wir uns auf diese Reise begeben, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek in Ihr .NET-Projekt integriert haben. Wenn nicht, können Sie sie von der[Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie mit Visual Studio oder einem anderen .NET-Entwicklungstool eine funktionierende Entwicklungsumgebung ein.
- Grundlegende Kenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
Fügen Sie in Ihr C#-Projekt die erforderlichen Namespaces ein, um auf die Aspose.Slides-Funktionalität zuzugreifen:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues Projekt in Visual Studio oder Ihrer bevorzugten .NET-Entwicklungsumgebung. Stellen Sie sicher, dass in Ihrem Projekt auf Aspose.Slides für .NET verwiesen wird.
## Schritt 2: Laden Sie die Präsentation
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Schritt 3: Zugriff auf die Folie und die Formen
```csharp
ISlide slide = presentation.Slides[0];
```
## Schritt 4: Eine neue Form hinzufügen
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Schritt 5: Ändern Sie den Text in der Form
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Schritt 6: Eine weitere Form hinzufügen
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Schritt 7: Ändern Sie die Reihenfolge der Formen
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Schritt 8: Speichern Sie die geänderte Präsentation
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Damit ist die Schritt-für-Schritt-Anleitung zum Ändern der Reihenfolge von Formen in Präsentationsfolien mit Aspose.Slides für .NET abgeschlossen.
## Abschluss
Aspose.Slides für .NET vereinfacht die programmgesteuerte Bearbeitung von Präsentationsfolien. In diesem Tutorial haben Sie gelernt, wie Sie Formen neu anordnen und so die visuelle Attraktivität Ihrer Präsentationen verbessern können.
## FAQs
### F: Kann ich Aspose.Slides für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?
A: Ja, Aspose.Slides für .NET ist sowohl mit Windows- als auch mit Linux-Umgebungen kompatibel.
### F: Gibt es Lizenzüberlegungen für die Verwendung von Aspose.Slides in einem kommerziellen Projekt?
 A: Ja, Lizenzdetails und Kaufoptionen finden Sie auf der[Aspose.Slides-Kaufseite](https://purchase.aspose.com/buy).
### F: Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 A: Ja, Sie können die Funktionen erkunden mit dem[Kostenlose Testphase](https://releases.aspose.com/) verfügbar auf der Aspose.Slides-Website.
### F: Wo kann ich Support finden oder Fragen zu Aspose.Slides für .NET stellen?
 A: Besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) um Unterstützung zu erhalten und sich in der Community zu engagieren.
### F: Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
 A: Sie können erwerben eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) zu Auswertungszwecken.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

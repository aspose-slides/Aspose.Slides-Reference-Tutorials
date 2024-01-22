---
title: Beherrschen der Formausrichtung mit Aspose.Slides für .NET
linktitle: Ausrichten von Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Formen mit Aspose.Slides für .NET mühelos in Präsentationsfolien ausrichten. Verbessern Sie die optische Attraktivität durch präzise Ausrichtung. Jetzt downloaden!
type: docs
weight: 10
url: /de/net/shape-alignment-and-formatting-in-slides/aligning-shapes/
---
## Einführung
Die Erstellung optisch ansprechender Präsentationsfolien erfordert oft eine präzise Ausrichtung der Formen. Aspose.Slides für .NET bietet eine leistungsstarke Lösung, um dies problemlos zu erreichen. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für .NET Formen in Präsentationsfolien ausrichten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides for .NET-Bibliothek installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung auf Ihrem Computer ein.
## Namespaces importieren
Importieren Sie in Ihrer .NET-Anwendung die erforderlichen Namespaces für die Arbeit mit Aspose.Slides:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Schritt 1: Initialisieren Sie die Präsentation
Beginnen Sie mit der Initialisierung eines Präsentationsobjekts und dem Hinzufügen einer Folie:
```csharp
string dataDir = "Your Document Directory";
string outpptxFile = Path.Combine(dataDir, "ShapesAlignment_out.pptx");
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
    // Erstellen Sie einige Formen
    // ...
}
```
## Schritt 2: Formen innerhalb einer Folie ausrichten
 Fügen Sie der Folie Formen hinzu und richten Sie sie mit aus`SlideUtil.AlignShapes` Methode:
```csharp
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 200, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
// Ausrichten aller Formen in IBaseSlide.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignBottom, true, pres.Slides[0]);
```
## Schritt 3: Formen innerhalb einer Gruppe ausrichten
Erstellen Sie eine Gruppenform, fügen Sie ihr Formen hinzu und richten Sie sie innerhalb der Gruppe aus:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
IGroupShape groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// Ausrichten aller Formen innerhalb von IGroupShape.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape);
```
## Schritt 4: Bestimmte Formen innerhalb einer Gruppe ausrichten
Richten Sie bestimmte Formen innerhalb einer Gruppe aus, indem Sie ihre Indizes angeben:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// Ausrichten von Formen mit angegebenen Indizes innerhalb von IGroupShape.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape, new int[] { 0, 2 });
```
## Abschluss
Verbessern Sie mühelos die visuelle Attraktivität Ihrer Präsentationsfolien, indem Sie Aspose.Slides für .NET nutzen, um Formen präzise auszurichten. Diese Schritt-für-Schritt-Anleitung vermittelt Ihnen das Wissen, um den Ausrichtungsprozess zu optimieren und professionell aussehende Präsentationen zu erstellen.
## FAQs
### Kann ich Formen in einer vorhandenen Präsentation mit Aspose.Slides für .NET ausrichten?
 Ja, Sie können eine vorhandene Präsentation mit laden`Presentation.Load` und fahren Sie dann mit dem Ausrichten der Formen fort.
### Gibt es in Aspose.Slides weitere Ausrichtungsoptionen?
Aspose.Slides bietet verschiedene Ausrichtungsoptionen, darunter AlignTop, AlignRight, AlignBottom, AlignLeft und mehr.
### Kann ich Formen anhand ihrer Verteilung auf einer Folie ausrichten?
Absolut! Aspose.Slides bietet Methoden zum gleichmäßigen Verteilen von Formen sowohl horizontal als auch vertikal.
### Ist Aspose.Slides für die plattformübergreifende Entwicklung geeignet?
Aspose.Slides für .NET ist in erster Linie für Windows-Anwendungen konzipiert, Aspose bietet jedoch auch Bibliotheken für Java und andere Plattformen.
### Wie kann ich weitere Hilfe oder Unterstützung erhalten?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
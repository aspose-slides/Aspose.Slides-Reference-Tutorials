---
title: Erstellen Sie atemberaubende skizzierte Formen mit Aspose.Slides
linktitle: Erstellen skizzierter Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET kreative skizzierte Formen zu Ihren Präsentationsfolien hinzufügen. Verbessern Sie mühelos die visuelle Attraktivität!
weight: 13
url: /de/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie atemberaubende skizzierte Formen mit Aspose.Slides

## Einführung
Willkommen zu unserer Schritt-für-Schritt-Anleitung zum Erstellen skizzierter Formen in Präsentationsfolien mit Aspose.Slides für .NET. Wenn Sie Ihren Präsentationen einen Hauch von Kreativität verleihen möchten, bieten skizzierte Formen eine einzigartige und handgezeichnete Ästhetik. In diesem Tutorial führen wir Sie durch den Prozess und unterteilen ihn in einfache Schritte, um ein reibungsloses Erlebnis zu gewährleisten.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für .NET installiert haben. Sie können sie herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung mit Ihrer bevorzugten IDE ein.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr .NET-Projekt. Dieser Schritt stellt sicher, dass Sie Zugriff auf die Klassen und Funktionen haben, die für die Arbeit mit Aspose.Slides erforderlich sind.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
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
## Schritt 1: Einrichten des Projekts
Beginnen Sie mit der Erstellung eines neuen .NET-Projekts oder dem Öffnen eines vorhandenen. Achten Sie darauf, Aspose.Slides in Ihre Projektreferenzen aufzunehmen.
## Schritt 2: Aspose.Slides initialisieren
Initialisieren Sie Aspose.Slides, indem Sie den folgenden Codeausschnitt hinzufügen. Dadurch wird die Präsentation eingerichtet und die Ausgabepfade für die Präsentationsdatei und das Miniaturbild angegeben.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Fahren Sie mit den nächsten Schritten fort ...
}
```
## Schritt 3: Skizzierte Form hinzufügen
Fügen wir der Folie nun eine skizzierte Form hinzu. In diesem Beispiel fügen wir ein Rechteck mit einem Freihand-Skizzeneffekt hinzu.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformieren Sie die Form in eine Skizze im Freihandstil
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Schritt 4: Miniaturansicht generieren
Erstellen Sie eine Miniaturansicht der Folie, um die skizzierte Form zu visualisieren. Speichern Sie die Miniaturansicht als PNG-Datei.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Schritt 5: Präsentation speichern
Speichern Sie die Präsentationsdatei mit der skizzierten Form.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Das ist es! Sie haben erfolgreich eine Präsentation mit skizzierten Formen mit Aspose.Slides für .NET erstellt.
## Abschluss
Das Hinzufügen skizzierter Formen zu Ihren Präsentationsfolien kann die visuelle Attraktivität steigern und Ihr Publikum fesseln. Mit Aspose.Slides für .NET wird der Prozess unkompliziert und Sie können Ihrer Kreativität mühelos freien Lauf lassen.
## FAQs
### 1. Kann ich den Skizzeneffekt anpassen?
 Ja, Aspose.Slides für .NET bietet verschiedene Anpassungsoptionen für skizzierte Effekte. Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/net/) für detaillierte Informationen.
### 2. Gibt es eine kostenlose Testversion?
 Sicher! Sie können eine kostenlose Testversion von Aspose.Slides für .NET ausprobieren[Hier](https://releases.aspose.com/).
### 3. Wo bekomme ich Unterstützung?
 Wenn Sie Hilfe benötigen oder Fragen haben, besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### 4. Wie kann ich Aspose.Slides für .NET kaufen?
 Um Aspose.Slides für .NET zu kaufen, besuchen Sie die[Kaufseite](https://purchase.aspose.com/buy).
### 5. Bieten Sie temporäre Lizenzen an?
 Ja, es sind temporäre Lizenzen verfügbar[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

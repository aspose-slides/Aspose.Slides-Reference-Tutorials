---
title: Beherrschen geometrischer Formen mit ShapeUtil - Aspose.Slides .NET
linktitle: Verwenden von ShapeUtil für Geometrieformen in Präsentationsfolien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Slides für .NET mit ShapeUtil für dynamische Geometrieformen. Erstellen Sie mühelos ansprechende Präsentationen. Jetzt herunterladen! Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides verbessern. Entdecken Sie ShapeUtil für die Bearbeitung von Geometrieformen. Schritt-für-Schritt-Anleitung mit .NET-Quellcode. Präsentationen effektiv optimieren.
type: docs
weight: 17
url: /de/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
## Einführung
Das Erstellen optisch ansprechender und dynamischer Präsentationsfolien ist eine wesentliche Fähigkeit, und Aspose.Slides für .NET bietet ein leistungsstarkes Toolkit, um dies zu erreichen. In diesem Tutorial untersuchen wir die Verwendung von ShapeUtil zum Umgang mit Geometrieformen in Präsentationsfolien. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Aspose.Slides beginnen, führt Sie dieser Leitfaden durch den Prozess der Verwendung von ShapeUtil zur Verbesserung Ihrer Präsentationen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegendes Verständnis der C#- und .NET-Programmierung.
-  Installierte Aspose.Slides für .NET-Bibliothek. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine Entwicklungsumgebung, die für die Ausführung von .NET-Anwendungen eingerichtet ist.
## Namespaces importieren
Stellen Sie in Ihrem C#-Code sicher, dass Sie die erforderlichen Namespaces importieren, um auf die Aspose.Slides-Funktionen zuzugreifen. Fügen Sie am Anfang Ihres Skripts Folgendes hinzu:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um eine Schritt-für-Schritt-Anleitung für die Verwendung von ShapeUtil für Geometrieformen in Präsentationsfolien zu erstellen.
## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad ersetzen, in dem Sie Ihre Präsentation speichern möchten.
## Schritt 2: Definieren Sie den Namen der Ausgabedatei
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
Geben Sie den gewünschten Namen der Ausgabedatei einschließlich der Dateierweiterung an.
## Schritt 3: Erstellen Sie eine Präsentation
```csharp
using (Presentation pres = new Presentation())
```
Initialisieren Sie ein neues Präsentationsobjekt mithilfe der Aspose.Slides-Bibliothek.
## Schritt 4: Fügen Sie eine Geometrieform hinzu
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
Fügen Sie der ersten Folie der Präsentation eine Rechteckform hinzu.
## Schritt 5: Erhalten Sie den ursprünglichen Geometriepfad
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
Rufen Sie den Geometriepfad der Form ab und legen Sie den Füllmodus fest.
## Schritt 6: Erstellen Sie einen Grafikpfad mit Text
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
Erzeugen Sie einen Grafikpfad mit Text, der der Form hinzugefügt werden soll.
## Schritt 7: Konvertieren Sie den Grafikpfad in den Geometriepfad
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
Verwenden Sie ShapeUtil, um den Grafikpfad in einen Geometriepfad umzuwandeln und den Füllmodus festzulegen.
## Schritt 8: Legen Sie kombinierte Geometriepfade für die Form fest
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
Kombinieren Sie den neuen Geometriepfad mit dem ursprünglichen Pfad und stellen Sie ihn auf die Form ein.
## Schritt 9: Speichern Sie die Präsentation
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation mit der neuen Geometrieform.
## Abschluss
Glückwunsch! Sie haben die Verwendung von ShapeUtil zum Umgang mit Geometrieformen in Präsentationsfolien mit Aspose.Slides für .NET erfolgreich untersucht. Mit dieser leistungsstarken Funktion können Sie ganz einfach dynamische und ansprechende Präsentationen erstellen.
## FAQs
### Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Aspose.Slides unterstützt hauptsächlich .NET-Sprachen. Aspose bietet jedoch ähnliche Bibliotheken für andere Plattformen und Sprachen.
### Wo finde ich eine ausführliche Dokumentation zu Aspose.Slides für .NET?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/slides/net/).
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können die kostenlose Testversion finden[Hier](https://releases.aspose.com/).
### Wie erhalte ich Unterstützung für Aspose.Slides für .NET?
 Besuchen Sie das Community-Supportforum[Hier](https://forum.aspose.com/c/slides/11).
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
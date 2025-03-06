---
title: Erstellen benutzerdefinierter Geometrie in C# mit Aspose.Slides für .NET
linktitle: Erstellen benutzerdefinierter Geometrie in Geometrieformen mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Slides für .NET benutzerdefinierte Geometrie erstellen. Werten Sie Ihre Präsentationen mit einzigartigen Formen auf. Schritt-für-Schritt-Anleitung für C#-Entwickler.
weight: 15
url: /de/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In der dynamischen Welt der Präsentationen können Sie Ihren Inhalt durch das Hinzufügen einzigartiger Formen und Geometrien aufwerten und ihn ansprechender und optisch ansprechender gestalten. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zum Erstellen benutzerdefinierter Geometrien innerhalb von Formen, sodass Sie sich von herkömmlichen Designs lösen können. Dieses Tutorial führt Sie durch den Prozess zum Erstellen benutzerdefinierter Geometrie in einem GeometryShape mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegende Kenntnisse der Programmiersprache C#.
- Aspose.Slides für die .NET-Bibliothek, die in Ihrer Entwicklungsumgebung installiert ist.
- Visual Studio oder eine beliebige bevorzugte C#-Entwicklungsumgebung eingerichtet.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Stellen Sie sicher, dass Aspose.Slides für .NET ordnungsgemäß installiert ist.
## Schritt 2: Definieren Sie Ihr Dokumentverzeichnis
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Schritt 3: Äußeren und inneren Sternradius festlegen
```csharp
float R = 100, r = 50; // Äußerer und innerer Sternradius
```
## Schritt 4: Sterngeometriepfad erstellen
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Schritt 5: Erstellen Sie eine Präsentation
```csharp
using (Presentation pres = new Presentation())
{
    // Neue Form erstellen
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Neuen Geometriepfad für die Form festlegen
    shape.SetGeometryPath(starPath);
    // Speichern der Präsentation
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Schritt 6: Definieren Sie die Methode CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Geometrie in einem GeometryShape erstellen. Dies eröffnet eine Welt voller Möglichkeiten zum Erstellen einzigartiger und visuell beeindruckender Präsentationen.
## FAQs
### 1. Kann ich Aspose.Slides für .NET mit anderen Programmiersprachen verwenden?
Ja, Aspose.Slides unterstützt verschiedene Programmiersprachen, aber dieses Tutorial konzentriert sich auf C#.
### 2. Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Besuche den[Dokumentation](https://reference.aspose.com/slides/net/) für detaillierte Informationen.
### 3. Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können erkunden eine[Kostenlose Testphase](https://releases.aspose.com/) um die Funktionen kennenzulernen.
### 4. Wie kann ich Support für Aspose.Slides für .NET erhalten?
 Suchen Sie Hilfe und engagieren Sie sich in der Community bei[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### 5. Wo kann ich Aspose.Slides für .NET kaufen?
 Sie können Aspose.Slides für .NET kaufen[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Visuals beherrschen – Segmente mit Aspose.Slides in .NET hinzufügen
linktitle: Hinzufügen von Segmenten zur Geometrieform in der Präsentation mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre .NET-Anwendungen mit Aspose.Slides verbessern. Dieses Tutorial führt Sie durch das Hinzufügen von Segmenten zu Geometrieformen für fesselnde Präsentationen.
type: docs
weight: 13
url: /de/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---
## Einführung
In der Welt der .NET-Entwicklung ist die Erstellung optisch ansprechender Präsentationen eine häufige Anforderung. Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die die nahtlose Integration robuster Funktionen zur Präsentationserstellung in Ihre .NET-Anwendungen ermöglicht. Dieses Tutorial konzentriert sich auf einen bestimmten Aspekt des Präsentationsdesigns – das Hinzufügen von Segmenten zu Geometrieformen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio ist auf Ihrem Computer installiert.
- Aspose.Slides für .NET-Bibliothek heruntergeladen und in Ihrem Projekt referenziert.
## Namespaces importieren
Stellen Sie in Ihrem C#-Code sicher, dass Sie die erforderlichen Namespaces importieren, um auf die Aspose.Slides-Funktionen zuzugreifen. Fügen Sie Ihrem Code die folgenden Zeilen hinzu:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Lassen Sie uns das Beispiel nun in mehrere Schritte unterteilen.
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Slides-Bibliothek verwiesen wird.
## Schritt 2: Erstellen Sie eine Präsentation
Initialisieren Sie ein neues Präsentationsobjekt mithilfe der Aspose.Slides-Bibliothek. Dies dient als Leinwand für Ihre Geometrieform.
```csharp
using (Presentation pres = new Presentation())
{
    // Hier finden Sie Ihren Code zum Erstellen einer Präsentation
}
```
## Schritt 3: Fügen Sie eine Geometrieform hinzu
Erstellen Sie eine Geometrieform innerhalb der Präsentation. Fügen wir beispielsweise der ersten Folie ein Rechteck hinzu.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Schritt 4: Geometriepfad abrufen
Rufen Sie den Geometriepfad der erstellten Form ab, um ihre Segmente zu bearbeiten.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Schritt 5: Segmente hinzufügen
Fügen Sie dem Geometriepfad Segmente (Linien) hinzu. In diesem Beispiel werden dem Pfad zwei Zeilen hinzugefügt.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Schritt 6: Bearbeiteten Geometriepfad zuweisen
Weisen Sie den geänderten Geometriepfad wieder der Form zu, um die Änderungen zu übernehmen.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation an einem gewünschten Ort.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Mit diesen Schritten haben Sie mit Aspose.Slides für .NET erfolgreich Segmente zu einer Geometrieform in einer Präsentation hinzugefügt.
## Abschluss
Mit Aspose.Slides für .NET können Entwickler ihre Anwendungen mit erweiterten Funktionen zur Präsentationserstellung erweitern. Durch das Hinzufügen von Segmenten zu Geometrieformen können Sie die visuellen Elemente Ihrer Präsentationen anpassen.
### Häufig gestellte Fragen
### Kann ich mit Aspose.Slides verschiedene Arten von Formen hinzufügen?
Ja, Aspose.Slides unterstützt verschiedene Formtypen, darunter Rechtecke, Kreise und benutzerdefinierte Geometrieformen.
### Ist für die Verwendung von Aspose.Slides in meinem Projekt eine Lizenz erforderlich?
Ja, eine gültige Lizenz ist erforderlich. Sie können eine temporäre Lizenz zu Testzwecken erwerben oder eine Volllizenz für die Produktion erwerben.
### Wie kann ich Unterstützung für Aspose.Slides-bezogene Abfragen erhalten?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
### Gibt es weitere Tutorials für Aspose.Slides?
 Entdecke die[Dokumentation](https://reference.aspose.com/slides/net/) Ausführliche Anleitungen und Beispiele finden Sie hier.
### Kann ich Aspose.Slides vor dem Kauf kostenlos testen?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
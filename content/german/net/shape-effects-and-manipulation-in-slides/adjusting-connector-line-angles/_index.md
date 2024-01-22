---
title: Passen Sie die Winkel der Verbindungslinien in PowerPoint mit Aspose.Slides an
linktitle: Anpassen der Verbindungslinienwinkel in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie die Winkel der Verbindungslinien in PowerPoint-Folien mit Aspose.Slides für .NET anpassen. Verbessern Sie Ihre Präsentationen mit Präzision und Leichtigkeit.
type: docs
weight: 28
url: /de/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---
## Einführung
Die Erstellung optisch ansprechender Präsentationsfolien erfordert häufig eine präzise Anpassung der Verbindungslinien. In diesem Tutorial erfahren Sie, wie Sie die Verbindungslinienwinkel in Präsentationsfolien mithilfe von Aspose.Slides für .NET anpassen. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Dateien zu arbeiten und umfangreiche Funktionen zum Erstellen, Ändern und Bearbeiten von Präsentationen bietet.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse der Programmiersprache C#.
- Visual Studio oder eine andere C#-Entwicklungsumgebung installiert.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine PowerPoint-Präsentationsdatei mit Verbindungslinien, die Sie anpassen möchten.
## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihren C#-Code aufnehmen:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues C#-Projekt in Visual Studio und installieren Sie das Aspose.Slides NuGet-Paket. Richten Sie die Projektstruktur mit einem Verweis auf die Aspose.Slides-Bibliothek ein.
## Schritt 2: Laden Sie die Präsentation
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 Laden Sie Ihre PowerPoint-Präsentationsdatei in das`Presentation`Objekt. Ersetzen Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad zu Ihrer Datei.
## Schritt 3: Greifen Sie auf die Folie und die Formen zu
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Greifen Sie auf die erste Folie in der Präsentation zu und initialisieren Sie eine Variable, um Formen auf der Folie darzustellen.
## Schritt 4: Durch Formen iterieren
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Code für die Handhabung von Verbindungslinien
}
```
Durchlaufen Sie jede Form auf der Folie, um Verbindungslinien zu identifizieren und zu verarbeiten.
## Schritt 5: Passen Sie die Winkel der Verbindungslinien an
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Code für die Handhabung von AutoShapes
}
else if (shape is Connector)
{
    // Code für die Handhabung von Konnektoren
}
Console.WriteLine(dir);
```
 Identifizieren Sie, ob es sich bei der Form um eine AutoForm oder einen Verbinder handelt, und passen Sie die Winkel der Verbindungslinien mithilfe der bereitgestellten Optionen an`getDirection` Methode.
##  Schritt 6: Definieren Sie die`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Code zur Richtungsberechnung
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 Implementieren Sie die`getDirection` Methode zur Berechnung des Winkels der Verbindungslinie anhand ihrer Abmessungen und Ausrichtung.
## Abschluss
Mit diesen Schritten können Sie die Winkel der Verbindungslinien in Ihrer PowerPoint-Präsentation mithilfe von Aspose.Slides für .NET programmgesteuert anpassen. Dieses Tutorial bietet eine Grundlage für die Verbesserung der visuellen Attraktivität Ihrer Folien.
## FAQs
### Ist Aspose.Slides sowohl für Windows- als auch für Webanwendungen geeignet?
Ja, Aspose.Slides kann sowohl in Windows- als auch in Webanwendungen verwendet werden.
### Kann ich vor dem Kauf eine kostenlose Testversion von Aspose.Slides herunterladen?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo finde ich eine umfassende Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/slides/net/).
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Gibt es ein Support-Forum für Aspose.Slides?
 Ja, Sie können das Support-Forum besuchen[Hier](https://forum.aspose.com/c/slides/11).
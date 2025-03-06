---
title: 3D-Rotation in Präsentationen meistern mit Aspose.Slides für .NET
linktitle: Anwenden eines 3D-Rotationseffekts auf Formen in Präsentationsfolien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Verbessern Sie Ihre Präsentationen mit Aspose.Slides für .NET! Lernen Sie in diesem Tutorial, 3D-Rotationseffekte auf Formen anzuwenden. Erstellen Sie dynamische und visuell beeindruckende Präsentationen.
weight: 23
url: /de/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 3D-Rotation in Präsentationen meistern mit Aspose.Slides für .NET

## Einführung
Das Erstellen ansprechender und dynamischer Präsentationsfolien ist ein wichtiger Aspekt effektiver Kommunikation. Aspose.Slides für .NET bietet eine Reihe leistungsstarker Tools zur Verbesserung Ihrer Präsentationen, darunter die Möglichkeit, 3D-Rotationseffekte auf Formen anzuwenden. In diesem Tutorial werden wir den Prozess der Anwendung eines 3D-Rotationseffekts auf Formen in Präsentationsfolien mithilfe von Aspose.Slides für .NET durchgehen.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für .NET installiert haben. Sie können sie von der[Webseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung wie Visual Studio ein, um Ihren Code zu schreiben und auszuführen.
## Namespaces importieren
Importieren Sie in Ihr .NET-Projekt die erforderlichen Namespaces, um die Funktionalität von Aspose.Slides zu nutzen. Fügen Sie am Anfang Ihres Codes die folgenden Namespaces ein:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung. Stellen Sie sicher, dass Sie Ihrem Projekt den Aspose.Slides-Verweis hinzugefügt haben.
## Schritt 2: Präsentation initialisieren
Instanziieren Sie eine Präsentationsklasse, um mit der Arbeit mit Folien zu beginnen:
```csharp
Presentation pres = new Presentation();
```
## Schritt 3: AutoForm hinzufügen
Fügen Sie der Folie eine AutoForm hinzu und geben Sie deren Typ, Position und Abmessungen an:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Schritt 4: 3D-Rotationseffekt einstellen
Konfigurieren Sie den 3D-Rotationseffekt für die AutoForm:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation mit dem angewendeten 3D-Rotationseffekt:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Schritt 6: Wiederholen Sie den Vorgang für andere Formen
Wenn Sie weitere Formen haben, wiederholen Sie die Schritte 3 bis 5 für jede Form.
## Abschluss
Das Hinzufügen von 3D-Rotationseffekten zu Formen in Ihren Präsentationsfolien kann deren visuelle Attraktivität deutlich steigern. Mit Aspose.Slides für .NET wird dieser Prozess unkompliziert und ermöglicht Ihnen die Erstellung fesselnder Präsentationen.
## FAQs
### Kann ich in Aspose.Slides für .NET eine 3D-Rotation auf Textfelder anwenden?
Ja, Sie können mit Aspose.Slides 3D-Rotationseffekte auf verschiedene Formen, einschließlich Textfelder, anwenden.
### Gibt es eine Testversion von Aspose.Slides für .NET?
 Ja, Sie können auf die Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 Ja, Sie können eine vorübergehende Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich eine ausführliche Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation ist verfügbar[Hier](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

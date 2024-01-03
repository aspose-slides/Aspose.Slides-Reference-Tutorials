---
title: Verknüpfen von Videos über ActiveX-Steuerelement in PowerPoint
linktitle: Verknüpfen von Videos über ActiveX-Steuerelement
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mithilfe von Aspose.Slides für .NET Videos mit PowerPoint-Folien verknüpfen. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Tipps zum Erstellen interaktiver und ansprechender Präsentationen mit verknüpften Videos.
type: docs
weight: 12
url: /de/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
Verknüpfen eines Videos über ActiveX-Steuerelement in einer Präsentation mit Aspose.Slides für .NET

In Aspose.Slides für .NET können Sie mithilfe des ActiveX-Steuerelements ein Video programmgesteuert mit einer Präsentationsfolie verknüpfen. Dadurch können Sie interaktive Präsentationen erstellen, bei denen der Videoinhalt direkt in der Folie abgespielt werden kann. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Verknüpfung eines Videos mit einer Präsentationsfolie mithilfe von Aspose.Slides für .NET.

## Voraussetzungen:
- Visual Studio (oder eine andere .NET-Entwicklungsumgebung)
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Schritt 1: Erstellen Sie ein neues Projekt
Erstellen Sie ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung (z. B. Visual Studio) und fügen Sie Verweise auf die Aspose.Slides für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Importieren Sie in Ihr Projekt die notwendigen Namespaces für die Arbeit mit Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Schritt 3: Präsentation laden
Laden Sie die PowerPoint-Präsentation dort, wo Sie das verlinkte Video hinzufügen möchten:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Hier finden Sie Ihren Code zum Hinzufügen des verlinkten Videos
}
```

## Schritt 4: ActiveX-Steuerelement hinzufügen
 Erstellen Sie eine Instanz von`IOleObjectFrame` Schnittstelle zum Hinzufügen des ActiveX-Steuerelements zur Folie:

```csharp
ISlide slide = presentation.Slides[0]; // Wählen Sie die Folie aus, zu der Sie das Video hinzufügen möchten
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Im obigen Code fügen wir der Folie einen ActiveX-Steuerrahmen mit den Abmessungen 640 x 480 hinzu. Wir geben die ProgID für das ShockwaveFlash ActiveX-Steuerelement an, das häufig zum Einbetten von Videos verwendet wird.

## Schritt 5: Legen Sie die Eigenschaften des ActiveX-Steuerelements fest
Legen Sie die Eigenschaften des ActiveX-Steuerelements fest, um die verknüpfte Videoquelle anzugeben:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Ersetzen Sie es durch den tatsächlichen Videodateipfad
oleObjectFrame.AlternativeText = "Linked Video";
```

 Ersetzen`"YourVideoPathHere"` mit dem tatsächlichen Pfad zu Ihrer Videodatei. Der`AlternativeText` Die Eigenschaft stellt eine Beschreibung für das verlinkte Video bereit.

## Schritt 6: Präsentation speichern
Speichern Sie die geänderte Präsentation:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## FAQs:

### Wie kann ich die Größe und Position des verlinkten Videos auf der Folie festlegen?
 Sie können die Abmessungen und Position des ActiveX-Steuerrahmens mithilfe der Parameter anpassen`AddOleObjectFrame` Methode. Die vier numerischen Argumente repräsentieren die X- und Y-Koordinaten der oberen linken Ecke sowie die Breite und Höhe des Rahmens.

### Kann ich mit diesem Ansatz Videos unterschiedlicher Formate verknüpfen?
Ja, Sie können Videos verschiedener Formate verknüpfen, sofern das entsprechende ActiveX-Steuerelement für dieses Format verfügbar ist. Das in diesem Handbuch verwendete ActiveX-Steuerelement ShockwaveFlash ist beispielsweise für Flash-Videos (SWF) geeignet. Für andere Formate müssen Sie möglicherweise andere ProgIDs verwenden.

### Gibt es eine Größenbeschränkung für das verlinkte Video?
Die Größe des verlinkten Videos kann sich auf die Gesamtgröße und Leistung Ihrer Präsentation auswirken. Es wird empfohlen, Ihre Videos für die Webwiedergabe zu optimieren, bevor Sie sie mit der Präsentation verknüpfen.

### Abschluss:
Wenn Sie die in dieser Anleitung beschriebenen Schritte befolgen, können Sie mit Aspose.Slides für .NET ganz einfach ein Video per ActiveX-Steuerung in einer Präsentation verknüpfen. Mit dieser Funktion können Sie ansprechende und interaktive Präsentationen erstellen, die Multimedia-Inhalte nahtlos integrieren.

 Weitere Einzelheiten und erweiterte Optionen finden Sie im[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
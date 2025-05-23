---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Videos mit PowerPoint-Folien verknüpfen. Diese Schritt-für-Schritt-Anleitung enthält Quellcode und Tipps zum Erstellen interaktiver und ansprechender Präsentationen mit verknüpften Videos."
"linktitle": "Verknüpfen von Videos über ActiveX-Steuerelement"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Verknüpfen von Videos über ActiveX-Steuerelemente in PowerPoint"
"url": "/de/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Verknüpfen von Videos über ActiveX-Steuerelemente in PowerPoint

Verknüpfen eines Videos über ActiveX-Steuerelement in einer Präsentation mit Aspose.Slides für .NET

In Aspose.Slides für .NET können Sie mithilfe des ActiveX-Steuerelements ein Video programmgesteuert mit einer Präsentationsfolie verknüpfen. So erstellen Sie interaktive Präsentationen, bei denen der Videoinhalt direkt auf der Folie abgespielt werden kann. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Verknüpfung eines Videos mit einer Präsentationsfolie mithilfe von Aspose.Slides für .NET.

## Voraussetzungen:
- Visual Studio (oder eine andere .NET-Entwicklungsumgebung)
- Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen von [Hier](https://releases.aspose.com/slides/net/).

## Schritt 1: Neues Projekt erstellen
Erstellen Sie ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung (z. B. Visual Studio) und fügen Sie Verweise auf die Aspose.Slides-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Importieren Sie in Ihr Projekt die erforderlichen Namespaces für die Arbeit mit Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Schritt 3: Präsentation laden
Laden Sie die PowerPoint-Präsentation, in der Sie das verknüpfte Video einfügen möchten:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Ihr Code zum Hinzufügen des verknüpften Videos wird hier eingefügt
}
```

## Schritt 4: ActiveX-Steuerelement hinzufügen
Erstellen Sie eine Instanz des `IOleObjectFrame` Schnittstelle zum Hinzufügen des ActiveX-Steuerelements zur Folie:

```csharp
ISlide slide = presentation.Slides[0]; // Wählen Sie die Folie aus, auf der Sie das Video hinzufügen möchten
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Im obigen Code fügen wir der Folie einen ActiveX-Steuerelementrahmen mit den Abmessungen 640 x 480 hinzu. Wir geben die ProgID für das ShockwaveFlash-ActiveX-Steuerelement an, das häufig zum Einbetten von Videos verwendet wird.

## Schritt 5: Eigenschaften des ActiveX-Steuerelements festlegen
Legen Sie die Eigenschaften des ActiveX-Steuerelements fest, um die verknüpfte Videoquelle anzugeben:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Ersetzen Sie es durch den tatsächlichen Videodateipfad
oleObjectFrame.AlternativeText = "Linked Video";
```

Ersetzen `"YourVideoPathHere"` mit dem tatsächlichen Pfad zu Ihrer Videodatei. Die `AlternativeText` Die Eigenschaft bietet eine Beschreibung für das verknüpfte Video.

## Schritt 6: Präsentation speichern
Speichern Sie die geänderte Präsentation:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Häufig gestellte Fragen:

### Wie kann ich die Größe und Position des verknüpften Videos auf der Folie festlegen?
Sie können die Abmessungen und die Position des ActiveX-Steuerrahmens über die Parameter des `AddOleObjectFrame` Methode. Die vier numerischen Argumente stellen die X- und Y-Koordinaten der oberen linken Ecke bzw. die Breite und Höhe des Rahmens dar.

### Kann ich mit diesem Ansatz Videos unterschiedlicher Formate verknüpfen?
Ja, Sie können Videos verschiedener Formate verknüpfen, sofern das entsprechende ActiveX-Steuerelement für das jeweilige Format verfügbar ist. Beispielsweise ist das in dieser Anleitung verwendete ShockwaveFlash-ActiveX-Steuerelement für Flash-Videos (SWF) geeignet. Für andere Formate müssen Sie möglicherweise andere ProgIDs verwenden.

### Gibt es eine Größenbeschränkung für das verlinkte Video?
Die Größe des verknüpften Videos kann sich auf die Gesamtgröße und Leistung Ihrer Präsentation auswirken. Es wird empfohlen, Ihre Videos für die Webwiedergabe zu optimieren, bevor Sie sie mit der Präsentation verknüpfen.

### Abschluss:
Mit den in dieser Anleitung beschriebenen Schritten können Sie mithilfe von Aspose.Slides für .NET ganz einfach ein Video per ActiveX-Steuerelement in eine Präsentation einbinden. Mit dieser Funktion erstellen Sie ansprechende und interaktive Präsentationen, die nahtlos Multimedia-Inhalte integrieren.

Weitere Einzelheiten und erweiterte Optionen finden Sie im [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
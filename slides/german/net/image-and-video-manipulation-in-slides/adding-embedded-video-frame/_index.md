---
"description": "Verbessern Sie Ihre Präsentationen mit eingebetteten Videos mithilfe von Aspose.Slides für .NET. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine nahtlose Integration."
"linktitle": "Aspose.Slides – Eingebettete Videos in .NET-Präsentationen hinzufügen"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Aspose.Slides – Eingebettete Videos in .NET-Präsentationen hinzufügen"
"url": "/de/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides – Eingebettete Videos in .NET-Präsentationen hinzufügen

## Einführung
In der dynamischen Welt der Präsentationen kann die Integration multimedialer Elemente das Engagement deutlich steigern. Aspose.Slides für .NET bietet eine leistungsstarke Lösung für die Einbindung eingebetteter Videoframes in Ihre Präsentationsfolien. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess und sorgt so für ein nahtloses Erlebnis.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von der [Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- Medieninhalt: Sie verfügen über eine Videodatei (z. B. „Wildlife.mp4“), die Sie in Ihre Präsentation einbetten möchten.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihr .NET-Projekt:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Verzeichnisse einrichten
Stellen Sie sicher, dass Ihr Projekt über die erforderlichen Verzeichnisse für Dokument- und Mediendateien verfügt:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Schritt 2: Präsentationsklasse instanziieren
Erstellen Sie eine Instanz der Klasse „Presentation“, um die PPTX-Datei darzustellen:
```csharp
using (Presentation pres = new Presentation())
{
    // Holen Sie sich die erste Folie
    ISlide sld = pres.Slides[0];
```
## Schritt 3: Video in Präsentation einbetten
Verwenden Sie den folgenden Code, um ein Video in die Präsentation einzubetten:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Schritt 4: Videoframe hinzufügen
Fügen Sie der Folie nun einen Videorahmen hinzu:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Schritt 5: Videoeigenschaften festlegen
Stellen Sie das Video auf den Video-Frame ein und konfigurieren Sie den Abspielmodus und die Lautstärke:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie abschließend die PPTX-Datei auf der Festplatte:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Wiederholen Sie diese Schritte für jedes Video, das Sie in Ihre Präsentation einbetten möchten.
## Abschluss
Herzlichen Glückwunsch! Sie haben Ihrer Präsentation mit Aspose.Slides für .NET erfolgreich einen eingebetteten Videorahmen hinzugefügt. Diese dynamische Funktion verleiht Ihren Präsentationen neue Dimensionen und fesselt Ihr Publikum mit nahtlos in Ihre Folien integrierten Multimedia-Elementen.
## FAQs
### Kann ich Videos in jede Folie der Präsentation einbetten?
Ja, Sie können jede Folie auswählen, indem Sie den Index in ändern `pres.Slides[index]`.
### Welche Videoformate werden unterstützt?
Aspose.Slides unterstützt eine Vielzahl von Videoformaten, darunter MP4, AVI und WMV.
### Kann ich die Größe und Position des Videorahmens anpassen?
Absolut! Passen Sie die Parameter in `AddVideoFrame(x, y, width, height, video)` nach Bedarf.
### Gibt es eine Begrenzung für die Anzahl der Videos, die ich einbetten kann?
Die Anzahl der eingebetteten Videos wird normalerweise durch die Kapazität Ihrer Präsentationssoftware begrenzt.
### Wie kann ich weitere Hilfe erhalten oder meine Erfahrungen teilen?
Besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Support und Diskussionen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
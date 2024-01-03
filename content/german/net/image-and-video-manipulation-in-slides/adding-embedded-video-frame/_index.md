---
title: Aspose.Slides – Eingebettete Videos in .NET-Präsentationen hinzufügen
linktitle: Aspose.Slides – Eingebettete Videos in .NET-Präsentationen hinzufügen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Verbessern Sie Ihre Präsentationen mit eingebetteten Videos mit Aspose.Slides für .NET. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 19
url: /de/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Einführung
In der dynamischen Welt der Präsentationen kann die Integration multimedialer Elemente das Engagement deutlich steigern. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zum Einbinden eingebetteter Videobilder in Ihre Präsentationsfolien. Dieses Tutorial führt Sie durch den Prozess und schlüsselt jeden Schritt auf, um ein nahtloses Erlebnis zu gewährleisten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
-  Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek von herunter und installieren Sie sie[Release-Seite](https://releases.aspose.com/slides/net/).
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
## Schritt 2: Instanziieren Sie die Präsentationsklasse
Erstellen Sie eine Instanz der Presentation-Klasse, um die PPTX-Datei darzustellen:
```csharp
using (Presentation pres = new Presentation())
{
    // Holen Sie sich die erste Folie
    ISlide sld = pres.Slides[0];
```
## Schritt 3: Video in die Präsentation einbetten
Verwenden Sie den folgenden Code, um ein Video in die Präsentation einzubetten:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Schritt 4: Videorahmen hinzufügen
Fügen Sie nun der Folie einen Videorahmen hinzu:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Schritt 5: Videoeigenschaften festlegen
Stellen Sie das Video auf den Videorahmen ein und konfigurieren Sie Wiedergabemodus und Lautstärke:
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
Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich einen eingebetteten Videorahmen zu Ihrer Präsentation hinzugefügt. Diese dynamische Funktion kann Ihre Präsentationen auf ein neues Niveau heben und Ihr Publikum mit Multimedia-Elementen fesseln, die nahtlos in Ihre Folien integriert sind.
## FAQs
### Kann ich Videos in jede Folie der Präsentation einbetten?
 Ja, Sie können eine beliebige Folie auswählen, indem Sie den Index in ändern`pres.Slides[index]`.
### Welche Videoformate werden unterstützt?
Aspose.Slides unterstützt eine Vielzahl von Videoformaten, darunter MP4, AVI und WMV.
### Kann ich die Größe und Position des Videobilds anpassen?
 Absolut! Passen Sie die Parameter an`AddVideoFrame(x, y, width, height, video)` wie benötigt.
### Gibt es eine Begrenzung für die Anzahl der Videos, die ich einbetten kann?
Die Anzahl der eingebetteten Videos ist normalerweise durch die Kapazität Ihrer Präsentationssoftware begrenzt.
### Wie kann ich weitere Hilfe suchen oder meine Erfahrungen teilen?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
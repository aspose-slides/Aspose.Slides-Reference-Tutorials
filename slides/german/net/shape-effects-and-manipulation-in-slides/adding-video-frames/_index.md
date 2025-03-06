---
title: Tutorial zum Hinzufügen von Video-Frames mit Aspose.Slides für .NET
linktitle: Hinzufügen von Videoframes zu Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Beleben Sie Präsentationen mit dynamischen Video-Frames mithilfe von Aspose.Slides für .NET. Folgen Sie unserer Anleitung für eine nahtlose Integration und erstellen Sie ansprechende Präsentationen.
type: docs
weight: 19
url: /de/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---
## Einführung
In der dynamischen Landschaft der Präsentationen kann die Einbindung von Multimedia-Elementen die Gesamtwirkung und das Engagement steigern. Das Hinzufügen von Video-Frames zu Ihren Folien kann bahnbrechend sein und die Aufmerksamkeit Ihres Publikums auf eine Weise fesseln, die statische Inhalte nicht können. Aspose.Slides für .NET bietet eine robuste Lösung für die nahtlose Integration von Video-Frames in Ihre Präsentationsfolien.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegende Kenntnisse der C#- und .NET-Programmierung.
-  Aspose.Slides für .NET-Bibliothek installiert. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine geeignete Entwicklungsumgebung einrichten.
## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Präsentationsobjekt erstellen
 Beginnen Sie mit der Erstellung einer Instanz des`Presentation` Klasse, die die PPTX-Datei darstellt:
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    // Ihr Code hier
}
```
## Schritt 2: Zugriff auf die Folie
Rufen Sie die erste Folie aus der Präsentation ab:
```csharp
ISlide sld = pres.Slides[0];
```
## Schritt 3: Video-Frame hinzufügen
Fügen Sie der Folie nun einen Video-Frame hinzu:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
Passen Sie die Parameter (links, oben, Breite, Höhe) entsprechend Ihren Layoutvorlieben an.
## Schritt 4: Wiedergabemodus und Lautstärke einstellen
Konfigurieren Sie den Wiedergabemodus und die Lautstärke des eingefügten Videobildes:
```csharp
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Sie können diese Einstellungen entsprechend Ihren Präsentationsanforderungen anpassen.
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation auf der Festplatte:
```csharp
pres.Save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
Jetzt enthält Ihre Präsentation einen nahtlos integrierten Videorahmen!
## Abschluss
Das Einfügen von Videoframes in Präsentationsfolien mit Aspose.Slides für .NET ist ein unkomplizierter Vorgang, der Ihren Inhalten eine dynamische Note verleiht. Verbessern Sie Ihre Präsentationen, indem Sie Multimedia-Elemente nutzen, Ihr Publikum fesseln und ein unvergessliches Erlebnis bieten.
## FAQs
### F1: Kann ich einer einzelnen Folie mehrere Video-Frames hinzufügen?
Ja, Sie können einer einzelnen Folie mehrere Videobilder hinzufügen, indem Sie den im Lernprogramm beschriebenen Vorgang für jedes Videobild wiederholen.
### F2: Welche Videoformate werden von Aspose.Slides für .NET unterstützt?
Aspose.Slides für .NET unterstützt verschiedene Videoformate, darunter AVI, WMV und MP4.
### F3: Kann ich die Wiedergabeoptionen für das eingefügte Video steuern?
Auf jeden Fall! Sie haben die volle Kontrolle über die Wiedergabeoptionen, wie z. B. Wiedergabemodus und Lautstärke, wie im Tutorial gezeigt.
### F4: Gibt es eine Testversion von Aspose.Slides für .NET?
 Ja, Sie können die Funktionen von Aspose.Slides für .NET erkunden, indem Sie die Testversion herunterladen[Hier](https://releases.aspose.com/).
### F5: Wo finde ich Unterstützung für Aspose.Slides für .NET?
 Bei Fragen oder für Hilfe besuchen Sie die[Aspose.Slides Forum](https://forum.aspose.com/c/slides/11).
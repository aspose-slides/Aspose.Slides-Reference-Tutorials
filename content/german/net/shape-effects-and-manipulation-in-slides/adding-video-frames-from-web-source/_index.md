---
title: Tutorial zum Einbetten von Videorahmen mit Aspose.Slides für .NET
linktitle: Hinzufügen von Videobildern aus einer Webquelle in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Videobilder nahtlos in PowerPoint-Folien einbetten. Werten Sie Präsentationen mühelos mit Multimedia auf.
type: docs
weight: 20
url: /de/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---
## Einführung
In der dynamischen Welt der Präsentationen kann die Einbindung multimedialer Elemente das Engagement erheblich steigern und wirkungsvolle Botschaften vermitteln. Eine wirkungsvolle Möglichkeit, dies zu erreichen, besteht darin, Videobilder in Präsentationsfolien einzubetten. In diesem Tutorial erfahren Sie, wie Sie dies mit Aspose.Slides für .NET nahtlos erreichen können. Aspose.Slides ist eine robuste Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu bearbeiten und umfangreiche Funktionen zum Erstellen, Bearbeiten und Verbessern von Folien bietet.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Folgendes vorhanden ist:
1.  Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek von herunter und installieren Sie sie[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
2. Beispielvideodatei: Bereiten Sie eine Videodatei vor, die Sie in Ihre Präsentation einbetten möchten. Sie können das bereitgestellte Beispiel mit einem Video namens „Wildlife.mp4“ verwenden.
## Namespaces importieren
Fügen Sie in Ihr .NET-Projekt die erforderlichen Namespaces ein, um die Funktionalitäten von Aspose.Slides zu nutzen:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Lassen Sie uns den Prozess des Einbettens von Videobildern in Präsentationsfolien mithilfe von Aspose.Slides für .NET in überschaubare Schritte unterteilen:
## Schritt 1: Verzeichnisse einrichten
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ und „Ihr Medienverzeichnis“ durch die entsprechenden Pfade in Ihrem Projekt ersetzen.
## Schritt 2: Präsentationsobjekt erstellen
```csharp
using (Presentation pres = new Presentation())
{
    // Holen Sie sich die erste Folie
    ISlide sld = pres.Slides[0];
```
Initialisieren Sie eine neue Präsentation und greifen Sie auf die erste Folie zum Einbetten des Videobilds zu.
## Schritt 3: Video in Präsentation einbetten
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Nutzen Sie die`AddVideo` Methode zum Einbetten des Videos in die Präsentation unter Angabe des Dateipfads und des Ladeverhaltens.
## Schritt 4: Videorahmen hinzufügen
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Erstellen Sie einen Videorahmen auf der Folie und definieren Sie dessen Position und Abmessungen.
## Schritt 5: Videoeinstellungen konfigurieren
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Ordnen Sie den Videorahmen dem eingebetteten Video zu, legen Sie den Wiedergabemodus fest und passen Sie die Lautstärke nach Ihren Wünschen an.
## Schritt 6: Präsentation speichern
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation mit dem eingebetteten Videoframe.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Videobilder in Präsentationsfolien einbetten. Diese Funktion eröffnet spannende Möglichkeiten für die Erstellung dynamischer und ansprechender Präsentationen, die Ihr Publikum fesseln.
## FAQs
### Kann ich mit Aspose.Slides Videos verschiedener Formate einbetten?
Ja, Aspose.Slides unterstützt eine Vielzahl von Videoformaten und sorgt so für Flexibilität bei Ihren Präsentationen.
### Wie kann ich die Wiedergabeeinstellungen des eingebetteten Videos steuern?
 Verstelle die`PlayMode` Und`Volume` Eigenschaften des Videobilds, um das Wiedergabeverhalten anzupassen.
### Ist Aspose.Slides mit den neuesten Versionen von .NET kompatibel?
Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Frameworks zu gewährleisten.
### Kann ich mit Aspose.Slides mehrere Videos in eine einzige Folie einbetten?
Ja, Sie können mehrere Videos einbetten, indem Sie einer Folie zusätzliche Videobilder hinzufügen.
### Wo finde ich Unterstützung für Aspose.Slides-bezogene Abfragen?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
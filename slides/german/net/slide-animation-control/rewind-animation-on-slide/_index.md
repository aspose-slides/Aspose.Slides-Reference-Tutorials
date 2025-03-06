---
title: Beherrschen von Rückspulanimationen in Präsentationen mit Aspose.Slides
linktitle: Animation auf Folie zurückspulen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Animationen auf PowerPoint-Folien mit Aspose.Slides für .NET zurückspulen. Folgen Sie dieser Schritt-für-Schritt-Anleitung mit vollständigen Quellcodebeispielen.
type: docs
weight: 13
url: /de/net/slide-animation-control/rewind-animation-on-slide/
---
## Einführung
In der dynamischen Welt der Präsentationen kann die Einbindung fesselnder Animationen das Engagement erheblich steigern. Aspose.Slides für .NET bietet ein leistungsstarkes Toolset, um Ihren Präsentationen Leben einzuhauchen. Eine interessante Funktion ist die Möglichkeit, Animationen auf Folien zurückzuspulen. In dieser umfassenden Anleitung führen wir Sie Schritt für Schritt durch den Prozess, sodass Sie das volle Potenzial des Zurückspulens von Animationen mit Aspose.Slides für .NET nutzen können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Wenn nicht, laden Sie sie von der[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
- .NET-Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET-Entwicklungsumgebung eingerichtet haben.
- Grundlegende C#-Kenntnisse: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
In Ihrem C#-Code müssen Sie die erforderlichen Namespaces importieren, um die von Aspose.Slides für .NET bereitgestellte Funktionalität nutzen zu können. Hier ist ein Codeausschnitt, der Ihnen dabei hilft:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues Projekt in Ihrer bevorzugten .NET-Entwicklungsumgebung. Richten Sie ein Verzeichnis für Ihre Dokumente ein, falls es noch nicht vorhanden ist.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Schritt 2: Laden Sie die Präsentation
 Instanziieren Sie den`Presentation` Klasse zur Darstellung Ihrer Präsentationsdatei.
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // Ihr Code für die nachfolgenden Schritte kommt hier hin
}
```
## Schritt 3: Zugriff auf die Effektsequenz
Rufen Sie die Effektsequenz für die erste Folie ab.
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## Schritt 4: Effekt-Timing ändern
Greifen Sie auf den ersten Effekt der Hauptsequenz zu und ändern Sie dessen Timing, um das Zurückspulen zu ermöglichen.
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## Schritt 6: Rückspuleffekt in der Zielpräsentation prüfen
Laden Sie die geänderte Präsentation und prüfen Sie, ob der Rückspuleffekt angewendet wird.
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
Wiederholen Sie diese Schritte für weitere Folien oder passen Sie den Vorgang entsprechend der Struktur Ihrer Präsentation an.
## Abschluss
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## FAQs
### Ist Aspose.Slides für .NET mit der neuesten Version des .NET-Frameworks kompatibel?
 Aspose.Slides für .NET wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Framework-Versionen sicherzustellen. Überprüfen Sie die[Dokumentation](https://reference.aspose.com/slides/net/) für Kompatibilitätsdetails.
### Kann ich eine Rückspulanimation auf bestimmte Objekte innerhalb einer Folie anwenden?
Ja, Sie können den Code anpassen, um die Rückspulanimation selektiv auf bestimmte Objekte oder Elemente innerhalb einer Folie anzuwenden.
### Gibt es eine Testversion für Aspose.Slides für .NET?
 Ja, Sie können die Funktionen erkunden, indem Sie eine kostenlose Testversion erhalten von[Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) um Hilfe zu suchen und sich in der Community zu engagieren.
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz erwerben bei[Hier](https://purchase.aspose.com/temporary-license/).
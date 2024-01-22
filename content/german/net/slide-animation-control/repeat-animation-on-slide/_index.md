---
title: Beherrschen von PowerPoint-Animationen mit Aspose.Slides .NET
linktitle: Wiederholen Sie die Animation auf der Folie
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Verbessern Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET. Steuern Sie Animationen mühelos, fesseln Sie Ihr Publikum und hinterlassen Sie einen bleibenden Eindruck.
type: docs
weight: 12
url: /de/net/slide-animation-control/repeat-animation-on-slide/
---
## Einführung
In der dynamischen Welt der Präsentationen spielt die Fähigkeit, Animationen zu steuern, eine entscheidende Rolle, um die Aufmerksamkeit des Publikums zu fesseln und zu fesseln. Mit Aspose.Slides für .NET können Entwickler die Animationstypen innerhalb von Folien selbst steuern und so eine interaktivere und optisch ansprechendere Präsentation ermöglichen. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie Animationstypen auf einer Folie mit Aspose.Slides für .NET steuern.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/slides/net/).
2. .NET-Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung auf Ihrem Computer ein.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces, um die von Aspose.Slides bereitgestellten Funktionen zu nutzen:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie das Projekt ein
Erstellen Sie ein neues Verzeichnis für Ihr Projekt und instanziieren Sie die Präsentationsklasse, um die Präsentationsdatei darzustellen.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Ihr Code kommt hierher
}
```
## Schritt 2: Zugriff auf die Effektsequenz
Rufen Sie die Effektsequenz für die erste Folie mithilfe der MainSequence-Eigenschaft ab.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Schritt 3: Greifen Sie auf den ersten Effekt zu
Erhalten Sie den ersten Effekt der Hauptsequenz, um ihre Eigenschaften zu manipulieren.
```csharp
IEffect effect = effectsSequence[0];
```
## Schritt 4: Ändern Sie die Wiederholungseinstellungen
Ändern Sie die Eigenschaft „Timing/Repeat“ des Effekts in „Bis zum Ende der Folie“.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation, um die Änderungen zu visualisieren.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Wiederholen Sie diese Schritte für weitere Effekte oder passen Sie sie entsprechend Ihren Präsentationsanforderungen an.
## Abschluss
Mit Aspose.Slides für .NET war es noch nie so einfach, dynamische Animationen in Ihre PowerPoint-Präsentationen zu integrieren. Diese Schritt-für-Schritt-Anleitung vermittelt Ihnen das Wissen zur Steuerung von Animationstypen und stellt sicher, dass Ihre Folien einen bleibenden Eindruck bei Ihrem Publikum hinterlassen.
## Häufig gestellte Fragen
### Kann ich diese Animationen auf bestimmte Objekte innerhalb einer Folie anwenden?
Ja, Sie können bestimmte Objekte anvisieren, indem Sie auf deren individuelle Effekte innerhalb der Sequenz zugreifen.
### Ist Aspose.Slides mit den neuesten PowerPoint-Versionen kompatibel?
Aspose.Slides bietet Unterstützung für eine Vielzahl von PowerPoint-Versionen und gewährleistet so die Kompatibilität mit alten und neuen Versionen.
### Wo finde ich zusätzliche Beispiele und Ressourcen?
 Entdecke die[Dokumentation](https://reference.aspose.com/slides/net/) Ausführliche Beispiele und ausführliche Erklärungen finden Sie hier.
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Besuchen[Hier](https://purchase.aspose.com/temporary-license/) Informationen zum Erhalt einer befristeten Lizenz.
### Benötigen Sie Hilfe oder haben Sie weitere Fragen?
 Engagieren Sie sich mit der Aspose.Slides-Community auf der[Hilfeforum](https://forum.aspose.com/c/slides/11).
---
"description": "Optimieren Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET. Steuern Sie Animationen mühelos, fesseln Sie Ihr Publikum und hinterlassen Sie einen bleibenden Eindruck."
"linktitle": "Animation auf Folie wiederholen"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "PowerPoint-Animationen mit Aspose.Slides .NET meistern"
"url": "/de/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint-Animationen mit Aspose.Slides .NET meistern

## Einführung
In der dynamischen Welt der Präsentationen spielt die Steuerung von Animationen eine entscheidende Rolle, um die Aufmerksamkeit des Publikums zu fesseln. Aspose.Slides für .NET ermöglicht Entwicklern die Steuerung von Animationstypen innerhalb von Folien und ermöglicht so eine interaktivere und optisch ansprechendere Präsentation. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie Animationstypen auf einer Folie mit Aspose.Slides für .NET steuern.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Aspose.Slides für .NET-Bibliothek: Laden Sie die Bibliothek herunter und installieren Sie sie von [Hier](https://releases.aspose.com/slides/net/).
2. .NET-Entwicklungsumgebung: Richten Sie auf Ihrem Computer eine .NET-Entwicklungsumgebung ein.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces, um die von Aspose.Slides bereitgestellten Funktionen zu nutzen:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Schritt 1: Einrichten des Projekts
Erstellen Sie ein neues Verzeichnis für Ihr Projekt und instanziieren Sie die Präsentationsklasse, um die Präsentationsdatei darzustellen.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Ihr Code kommt hier hin
}
```
## Schritt 2: Zugriff auf die Effektsequenz
Rufen Sie die Effektsequenz für die erste Folie mithilfe der MainSequence-Eigenschaft ab.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Schritt 3: Zugriff auf den ersten Effekt
Erhalten Sie den ersten Effekt der Hauptreihe, um ihre Eigenschaften zu manipulieren.
```csharp
IEffect effect = effectsSequence[0];
```
## Schritt 4: Wiederholungseinstellungen ändern
Ändern Sie die Eigenschaft „Timing/Wiederholung“ des Effekts in „Bis zum Ende der Folie“.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation, um die Änderungen zu visualisieren.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Wiederholen Sie diese Schritte für zusätzliche Effekte oder passen Sie sie entsprechend Ihren Präsentationsanforderungen an.
## Abschluss
Mit Aspose.Slides für .NET ist es so einfach, dynamische Animationen in Ihre PowerPoint-Präsentationen zu integrieren. Diese Schritt-für-Schritt-Anleitung vermittelt Ihnen das Wissen zur Steuerung verschiedener Animationsarten und sorgt dafür, dass Ihre Folien einen bleibenden Eindruck bei Ihrem Publikum hinterlassen.
## Häufig gestellte Fragen
### Kann ich diese Animationen auf bestimmte Objekte innerhalb einer Folie anwenden?
Ja, Sie können bestimmte Objekte anvisieren, indem Sie innerhalb der Sequenz auf ihre einzelnen Effekte zugreifen.
### Ist Aspose.Slides mit den neuesten PowerPoint-Versionen kompatibel?
Aspose.Slides bietet Unterstützung für eine Vielzahl von PowerPoint-Versionen und gewährleistet die Kompatibilität sowohl mit alten als auch mit neuen Versionen.
### Wo finde ich weitere Beispiele und Ressourcen?
Entdecken Sie die [Dokumentation](https://reference.aspose.com/slides/net/) für umfassende Beispiele und detaillierte Erklärungen.
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
Besuchen [Hier](https://purchase.aspose.com/temporary-license/) Informationen zum Erhalt einer vorläufigen Lizenz.
### Benötigen Sie Hilfe oder haben Sie weitere Fragen?
Engagieren Sie sich mit der Aspose.Slides-Community auf der [Support-Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
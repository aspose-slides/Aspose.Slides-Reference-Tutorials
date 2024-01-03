---
title: Beherrschen Sie Nachanimationseffekte in PowerPoint mit Aspose.Slides
linktitle: Steuerung nach Animationstyp in Folie
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Nachanimationseffekte in PowerPoint-Folien mit Aspose.Slides für .NET steuern. Werten Sie Ihre Präsentationen mit dynamischen visuellen Elementen auf.
type: docs
weight: 11
url: /de/net/slide-animation-control/control-after-animation-type/
---
## Einführung
Die Aufwertung Ihrer Präsentationen durch dynamische Animationen ist ein entscheidender Aspekt für die Einbindung Ihres Publikums. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zur Steuerung der Nachanimationseffekte in Folien. In diesem Tutorial führen wir Sie durch den Prozess der Verwendung von Aspose.Slides für .NET zum Bearbeiten des Nachanimationstyps auf Folien. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie interaktivere und optisch ansprechendere Präsentationen erstellen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
- Grundkenntnisse in C#- und .NET-Programmierung.
-  Aspose.Slides für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces, um auf die Aspose.Slides-Funktionen zuzugreifen. Fügen Sie Ihrem Code die folgenden Zeilen hinzu:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Lassen Sie uns nun den bereitgestellten Code zum besseren Verständnis in mehrere Schritte aufteilen:
## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Stellen Sie sicher, dass das angegebene Verzeichnis vorhanden ist, oder erstellen Sie es, wenn dies nicht der Fall ist.
## Schritt 2: Definieren Sie den Ausgabedateipfad
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Geben Sie den Ausgabedateipfad für die geänderte Präsentation an.
## Schritt 3: Laden Sie die Präsentation
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Instanziieren Sie die Presentation-Klasse und laden Sie die vorhandene Präsentation.
## Schritt 4: Ändern Sie die Nachanimationseffekte auf Folie 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Klonen Sie die erste Folie, greifen Sie auf ihre Zeitleistensequenz zu und stellen Sie den Nachanimationseffekt auf „Bei nächstem Mausklick ausblenden“ ein.
## Schritt 5: Ändern Sie die Nachanimationseffekte auf Folie 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Klonen Sie die erste Folie erneut und ändern Sie dieses Mal den Nachanimationseffekt in „Farbe“ mit einer grünen Farbe.
## Schritt 6: Ändern Sie die Nachanimationseffekte auf Folie 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Klonen Sie die erste Folie noch einmal und stellen Sie den Nachanimationseffekt auf „Nach Animation ausblenden“ ein.
## Schritt 7: Speichern Sie die geänderte Präsentation
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Speichern Sie die geänderte Präsentation unter dem angegebenen Ausgabedateipfad.
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Nachanimationseffekte auf Folien steuern. Experimentieren Sie mit verschiedenen Nachanimationstypen, um dynamischere und ansprechendere Präsentationen zu erstellen.
## FAQs
### Kann ich auf einzelne Elemente innerhalb einer Folie unterschiedliche Nachanimationseffekte anwenden?
Ja, du kannst. Durchlaufen Sie die Elemente und passen Sie ihre Nachanimationseffekte entsprechend an.
### Ist Aspose.Slides mit den neuesten Versionen von .NET kompatibel?
Ja, Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET Framework-Versionen sicherzustellen.
### Wie kann ich mit Aspose.Slides benutzerdefinierte Animationen zu Folien hinzufügen?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/slides/net/) Ausführliche Informationen zum Hinzufügen benutzerdefinierter Animationen finden Sie hier.
### Welche Dateiformate unterstützt Aspose.Slides zum Speichern von Präsentationen?
Aspose.Slides unterstützt verschiedene Formate, darunter PPTX, PPT, PDF und mehr. Die vollständige Liste finden Sie in der Dokumentation.
### Wo kann ich Unterstützung erhalten oder Fragen zu Aspose.Slides stellen?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Unterstützung und Community-Interaktion.
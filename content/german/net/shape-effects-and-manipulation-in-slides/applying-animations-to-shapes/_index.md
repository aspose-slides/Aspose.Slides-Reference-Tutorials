---
title: Formanimationen leicht gemacht mit Aspose.Slides
linktitle: Anwenden von Animationen auf Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie beeindruckende Präsentationen mit Aspose.Slides für .NET. Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Animationen auf Formen anwenden. Verbessern Sie jetzt Ihre Folien!
type: docs
weight: 21
url: /de/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---
## Einführung
In der Welt der dynamischen Präsentationen kann das Hinzufügen von Animationen zu Formen die visuelle Attraktivität und das Engagement Ihrer Folien erheblich verbessern. Aspose.Slides für .NET bietet ein leistungsstarkes Toolkit, um dies nahtlos zu erreichen. In diesem Tutorial führen wir Sie durch den Prozess der Anwendung von Animationen auf Formen mit Aspose.Slides, sodass Sie fesselnde Präsentationen erstellen können, die einen bleibenden Eindruck hinterlassen.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
1.  Aspose.Slides für .NET: Stellen Sie sicher, dass die Bibliothek installiert und einsatzbereit ist. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung mit den erforderlichen Konfigurationen ein.
3. Dokumentverzeichnis: Erstellen Sie ein Verzeichnis zum Speichern Ihrer Präsentationsdateien.
## Namespaces importieren
Beginnen Sie in Ihrer .NET-Anwendung mit dem Importieren der erforderlichen Namespaces:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## Schritt 1: Erstellen Sie eine Präsentation
 Beginnen Sie mit der Erstellung einer neuen Präsentation mit`Presentation` Klasse:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    //Hier finden Sie Ihren Code zum Erstellen einer Präsentation.
}
```
## Schritt 2: Animierte Form hinzufügen
Fügen wir nun der ersten Folie Ihrer Präsentation eine animierte Form hinzu:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## Schritt 3: Animationseffekt anwenden
Fügen Sie der erstellten Form den Animationseffekt „PathFootball“ hinzu:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Schritt 4: Trigger-Schaltfläche erstellen
Erstellen Sie eine Schaltfläche, die die Animation auslöst:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Schritt 5: Definieren Sie einen benutzerdefinierten Benutzerpfad
Definieren Sie einen benutzerdefinierten Benutzerpfad für die Animation:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// Speichern Sie die Präsentation als PPTX auf der Festplatte
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
Damit ist die Schritt-für-Schritt-Anleitung zum Anwenden von Animationen auf Formen mit Aspose.Slides für .NET abgeschlossen.
## Abschluss
Die Einbindung von Animationen in Ihre Präsentationen fügt ein dynamisches Element hinzu, das die Aufmerksamkeit Ihres Publikums fesselt. Mit Aspose.Slides verfügen Sie über ein robustes Tool, mit dem Sie diese Effekte nahtlos integrieren und Ihre Präsentationen auf die nächste Ebene heben können.
## Häufig gestellte Fragen
### Kann ich mehrere Animationen auf eine einzelne Form anwenden?
Ja, mit Aspose.Slides können Sie einer einzelnen Form mehrere Animationseffekte hinzufügen und so komplexe Animationen flexibel erstellen.
### Ist Aspose.Slides mit verschiedenen PowerPoint-Versionen kompatibel?
Aspose.Slides gewährleistet die Kompatibilität mit verschiedenen PowerPoint-Versionen und stellt sicher, dass Ihre Präsentationen nahtlos auf verschiedenen Plattformen funktionieren.
### Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Slides?
 Entdecke die[Dokumentation](https://reference.aspose.com/slides/net/) und suchen Sie Hilfe bei der[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Benötige ich eine Lizenz für Aspose.Slides, um die Bibliothek nutzen zu können?
 Ja, Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy) um das volle Potenzial von Aspose.Slides auszuschöpfen.
### Kann ich Aspose.Slides vor dem Kauf ausprobieren?
 Sicherlich! Nutzen Sie die[Kostenlose Testphase](https://releases.aspose.com/) um die Möglichkeiten von Aspose.Slides kennenzulernen, bevor Sie eine Verpflichtung eingehen.
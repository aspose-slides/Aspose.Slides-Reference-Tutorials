---
title: Formanimationen leicht gemacht mit Aspose.Slides
linktitle: Anwenden von Animationen auf Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie beeindruckende Präsentationen mit Aspose.Slides für .NET. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie Animationen auf Formen anwenden. Verbessern Sie jetzt Ihre Folien!
weight: 21
url: /de/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Formanimationen leicht gemacht mit Aspose.Slides

## Einführung
In der Welt dynamischer Präsentationen kann das Hinzufügen von Animationen zu Formen die visuelle Attraktivität und Wirkung Ihrer Folien erheblich steigern. Aspose.Slides für .NET bietet ein leistungsstarkes Toolkit, um dies nahtlos zu erreichen. In diesem Tutorial führen wir Sie durch den Prozess des Anwendens von Animationen auf Formen mit Aspose.Slides, sodass Sie fesselnde Präsentationen erstellen können, die einen bleibenden Eindruck hinterlassen.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
1.  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Bibliothek installiert und einsatzbereit haben. Sie können sie herunterladen[Hier](https://releases.aspose.com/slides/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung mit den erforderlichen Konfigurationen ein.
3. Dokumentverzeichnis: Erstellen Sie ein Verzeichnis zum Speichern Ihrer Präsentationsdateien.
## Namespaces importieren
Importieren Sie in Ihrer .NET-Anwendung zunächst die erforderlichen Namespaces:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## Schritt 1: Erstellen Sie eine Präsentation
 Erstellen Sie zunächst eine neue Präsentation mit dem`Presentation` Klasse:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ihr Code zum Erstellen einer Präsentation kommt hierhin.
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
## Schritt 4: Trigger-Button erstellen
Erstellen Sie eine Schaltfläche, die die Animation auslöst:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Schritt 5: Benutzerdefinierten Benutzerpfad definieren
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
Durch die Einbindung von Animationen in Ihre Präsentationen fügen Sie ein dynamisches Element hinzu, das die Aufmerksamkeit Ihres Publikums fesselt. Mit Aspose.Slides verfügen Sie über ein robustes Tool, um diese Effekte nahtlos zu integrieren und Ihre Präsentationen auf die nächste Ebene zu heben.
## Häufig gestellte Fragen
### Kann ich auf eine einzelne Form mehrere Animationen anwenden?
Ja, mit Aspose.Slides können Sie einer einzelnen Form mehrere Animationseffekte hinzufügen und haben so Flexibilität beim Erstellen komplexer Animationen.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides gewährleistet die Kompatibilität mit verschiedenen PowerPoint-Versionen und sorgt dafür, dass Ihre Präsentationen reibungslos auf verschiedenen Plattformen funktionieren.
### Wo finde ich zusätzliche Ressourcen und Support für Aspose.Slides?
 Entdecke die[Dokumentation](https://reference.aspose.com/slides/net/) und suchen Sie Hilfe in der[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### Benötige ich eine Lizenz für Aspose.Slides, um die Bibliothek zu verwenden?
 Ja, Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy) um das volle Potenzial von Aspose.Slides auszuschöpfen.
### Kann ich Aspose.Slides vor dem Kauf ausprobieren?
 Sicherlich! Nutzen Sie die[Kostenlose Testphase](https://releases.aspose.com/) um die Funktionen von Aspose.Slides kennenzulernen, bevor Sie eine Verpflichtung eingehen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

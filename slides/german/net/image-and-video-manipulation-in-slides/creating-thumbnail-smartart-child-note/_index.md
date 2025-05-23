---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET ansprechende SmartArt-Miniaturansichten für untergeordnete Notizen erstellen. Werten Sie Ihre Präsentationen mit dynamischen Visualisierungen auf!"
"linktitle": "Erstellen einer Miniaturansicht für eine untergeordnete SmartArt-Notiz in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Erstellen einer Miniaturansicht für eine untergeordnete SmartArt-Notiz in Aspose.Slides"
"url": "/de/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen einer Miniaturansicht für eine untergeordnete SmartArt-Notiz in Aspose.Slides

## Einführung
Im Bereich dynamischer Präsentationen ist Aspose.Slides für .NET ein leistungsstarkes Tool, das Entwicklern die Möglichkeit bietet, PowerPoint-Präsentationen programmgesteuert zu bearbeiten und zu verbessern. Eine interessante Funktion ist die Möglichkeit, Miniaturansichten für SmartArt-Unternotizen zu generieren, um Ihre Präsentationen optisch ansprechender zu gestalten. Diese Schritt-für-Schritt-Anleitung führt Sie durch die Erstellung von Miniaturansichten für SmartArt-Unternotizen mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass die Aspose.Slides-Bibliothek in Ihr .NET-Projekt integriert ist. Falls nicht, laden Sie sie von der [Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine funktionierende .NET-Entwicklungsumgebung ein und verfügen Sie über grundlegende Kenntnisse der C#-Programmierung.
- Beispielpräsentation: Erstellen oder besorgen Sie sich eine PowerPoint-Präsentation mit SmartArt und untergeordneten Notizen zum Testen.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt. Diese Namespaces ermöglichen den Zugriff auf die Klassen und Methoden, die für die Arbeit mit Aspose.Slides erforderlich sind.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Schritt 1: Präsentationsklasse instanziieren
Beginnen Sie mit der Instanziierung des `Presentation` Klasse, die die PPTX-Datei darstellt, mit der Sie arbeiten werden.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Schritt 2: SmartArt hinzufügen
Fügen Sie nun SmartArt zu einer Folie innerhalb der Präsentation hinzu. In diesem Beispiel verwenden wir die `BasicCycle` Layout.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Schritt 3: Knotenreferenz abrufen
Um mit einem bestimmten Knoten im SmartArt zu arbeiten, erhalten Sie dessen Referenz mithilfe seines Index.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Schritt 4: Miniaturansicht erhalten
Rufen Sie das Miniaturbild der untergeordneten Notiz im SmartArt-Knoten ab.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Schritt 5: Miniaturansicht speichern
Speichern Sie das generierte Miniaturbild in einem angegebenen Verzeichnis.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Wiederholen Sie diese Schritte für jeden SmartArt-Knoten in Ihrer Präsentation und passen Sie das Layout und die Stile nach Bedarf an.
## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Slides für .NET Entwicklern die einfache Erstellung ansprechender Präsentationen ermöglicht. Die Möglichkeit, Miniaturansichten für SmartArt-Unternotizen zu generieren, steigert die visuelle Attraktivität Ihrer Präsentationen und sorgt für ein dynamisches und interaktives Benutzererlebnis.
## Häufig gestellte Fragen
### F: Kann ich die Größe und das Format des generierten Miniaturbilds anpassen?
A: Ja, Sie können die Abmessungen und das Format der Miniaturansicht anpassen, indem Sie die entsprechenden Parameter im Code ändern.
### F: Unterstützt Aspose.Slides andere SmartArt-Layouts?
A: Absolut! Aspose.Slides bietet eine Vielzahl von SmartArt-Layouts, sodass Sie dasjenige auswählen können, das Ihren Präsentationsanforderungen am besten entspricht.
### F: Ist eine temporäre Lizenz zu Testzwecken verfügbar?
A: Ja, Sie können eine temporäre Lizenz erhalten von [Hier](https://purchase.aspose.com/temporary-license/) zum Testen und Auswerten.
### F: Wo kann ich Hilfe suchen oder Kontakt zur Aspose.Slides-Community aufnehmen?
A: Besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) um mit der Community zu interagieren, Fragen zu stellen und Lösungen zu finden.
### F: Kann ich Aspose.Slides für .NET kaufen?
A: Natürlich! Entdecken Sie die Kaufoptionen [Hier](https://purchase.aspose.com/buy) um das volle Potenzial von Aspose.Slides in Ihren Projekten auszuschöpfen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
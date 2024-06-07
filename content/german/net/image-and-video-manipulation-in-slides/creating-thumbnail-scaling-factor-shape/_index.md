---
title: Erstellen einer Miniaturansicht mit Skalierungsfaktor für die Form in Aspose.Slides
linktitle: Erstellen einer Miniaturansicht mit Skalierungsfaktor für die Form in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET PowerPoint-Miniaturbilder mit bestimmten Begrenzungen erstellen. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 12
url: /de/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---
## Einführung
Willkommen zu unserem umfassenden Leitfaden zum Erstellen von Miniaturansichten mit Begrenzungen für Formen in Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, nahtlos mit PowerPoint-Präsentationen in ihren .NET-Anwendungen zu arbeiten. In diesem Tutorial werden wir uns eingehend mit dem Prozess des Generierens von Miniaturansichten mit bestimmten Begrenzungen für Formen innerhalb einer Präsentation mithilfe von Aspose.Slides befassen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie auf Ihrem Computer eine geeignete Entwicklungsumgebung für .NET ein, beispielsweise Visual Studio.
## Namespaces importieren
Importieren Sie in Ihrer .NET-Anwendung zunächst die erforderlichen Namespaces, um auf die Aspose.Slides-Funktionen zuzugreifen:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Schritt 1: Präsentation vorbereiten
Beginnen Sie mit der Instanziierung einer Präsentationsklasse, die die PowerPoint-Präsentationsdatei darstellt, mit der Sie arbeiten möchten:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Ihr Code zum Generieren von Miniaturansichten kommt hier hin
}
```
## Schritt 2: Erstellen Sie ein Bild im Originalmaßstab
Erstellen Sie im Präsentationsblock ein maßstabsgetreues Bild der Form, für die Sie eine Miniaturansicht generieren möchten:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    //Hier kommt Ihr Code zum Speichern des Bildes hin
}
```
## Schritt 3: Speichern Sie das Image auf der Festplatte
Speichern Sie das generierte Bild auf der Festplatte und geben Sie das Format an (in diesem Fall PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Miniaturansichten mit Begrenzungen für Formen erstellen. Diese Funktion kann unglaublich nützlich sein, wenn Sie in Ihren PowerPoint-Präsentationen programmgesteuert Bilder von Formen in bestimmten Größen erstellen müssen.
## Häufig gestellte Fragen
### F1: Kann ich Aspose.Slides mit anderen .NET-Frameworks verwenden?
Ja, Aspose.Slides ist mit verschiedenen .NET-Frameworks kompatibel und bietet Flexibilität für die Integration in verschiedene Arten von Anwendungen.
### F2: Gibt es eine Testversion für Aspose.Slides?
 Ja, Sie können die Funktionalität von Aspose.Slides erkunden, indem Sie die Testversion herunterladen[Hier](https://releases.aspose.com/).
### F3: Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Sie können eine temporäre Lizenz für Aspose.Slides erwerben, indem Sie[dieser Link](https://purchase.aspose.com/temporary-license/).
### F4: Wo finde ich zusätzliche Unterstützung für Aspose.Slides?
Bei Fragen oder für Hilfe besuchen Sie bitte das Aspose.Slides-Supportforum[Hier](https://forum.aspose.com/c/slides/11).
### F5: Kann ich Aspose.Slides für .NET kaufen?
 Natürlich! Um Aspose.Slides für .NET zu kaufen, besuchen Sie bitte die Kaufseite[Hier](https://purchase.aspose.com/buy).
---
title: Extrahieren Sie Audio aus PowerPoint-Hyperlinks mit Aspose.Slides
linktitle: Audio aus Hyperlink extrahieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Extrahieren Sie Audio aus Hyperlinks in PowerPoint-Präsentationen mit Aspose.Slides für .NET. Verbessern Sie Ihre Multimediaprojekte mühelos.
weight: 12
url: /de/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


In der Welt der Multimediapräsentationen spielt Audio eine entscheidende Rolle bei der Verbesserung der Gesamtwirkung Ihrer Folien. Sind Sie schon einmal auf eine PowerPoint-Präsentation mit Audio-Hyperlinks gestoßen und haben sich gefragt, wie Sie den Ton für andere Zwecke extrahieren können? Mit Aspose.Slides für .NET können Sie diese Aufgabe mühelos erledigen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Extrahierens von Audio aus einem Hyperlink in einer PowerPoint-Präsentation.

## Voraussetzungen

Bevor wir mit dem Extraktionsprozess beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für .NET-Bibliothek

Sie müssen die Bibliothek Aspose.Slides für .NET in Ihrer Entwicklungsumgebung installiert haben. Falls noch nicht geschehen, können Sie sie von der Website unter herunterladen.[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

### 2. PowerPoint-Präsentation mit Audio-Hyperlinks

Stellen Sie sicher, dass Sie eine PowerPoint-Präsentation (PPTX) haben, die Hyperlinks mit zugehörigem Audio enthält. Dies ist die Quelle, aus der Sie das Audio extrahieren.

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces in Ihr C#-Projekt, um Aspose.Slides für .NET effektiv nutzen zu können. Diese Namespaces sind für die Arbeit mit PowerPoint-Präsentationen und das Extrahieren von Audio aus Hyperlinks unerlässlich.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

Nachdem wir nun unsere Voraussetzungen geschaffen und die erforderlichen Namespaces importiert haben, unterteilen wir den Extraktionsprozess in mehrere Schritte.

## Schritt 1: Definieren Sie das Dokumentverzeichnis

 Geben Sie zunächst das Verzeichnis an, in dem sich Ihre PowerPoint-Präsentation befindet. Sie können ersetzen`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

 Laden Sie die PowerPoint-Präsentation (PPTX), die den Audio-Hyperlink enthält, mit Aspose.Slides. Ersetzen Sie`"HyperlinkSound.pptx"`durch den tatsächlichen Dateinamen Ihrer Präsentation.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Fahren Sie mit dem nächsten Schritt fort.
}
```

## Schritt 3: Holen Sie sich den Hyperlink-Sound

Holen Sie sich den Hyperlink der ersten Form aus der PowerPoint-Folie. Wenn dem Hyperlink ein Sound zugeordnet ist, extrahieren wir ihn.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // Fahren Sie mit dem nächsten Schritt fort.
}
```

## Schritt 4: Audio aus Hyperlink extrahieren

Wenn dem Hyperlink ein Ton zugeordnet ist, können wir ihn als Byte-Array extrahieren und als Mediendatei speichern.

```csharp
// Extrahiert den Hyperlink-Sound in ein Byte-Array
byte[] audioData = link.Sound.BinaryData;

// Geben Sie den Pfad an, in dem Sie das extrahierte Audio speichern möchten
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// Speichern Sie das extrahierte Audio in einer Mediendatei
File.WriteAllBytes(outMediaPath, audioData);
```

Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich Audio aus einem Hyperlink in einer PowerPoint-Präsentation extrahiert. Dieses extrahierte Audio kann jetzt für andere Zwecke in Ihren Multimediaprojekten verwendet werden.

## Abschluss

Aspose.Slides für .NET bietet eine leistungsstarke und benutzerfreundliche Lösung zum Extrahieren von Audio aus Hyperlinks in PowerPoint-Präsentationen. Mit den in diesem Handbuch beschriebenen Schritten können Sie Ihre Multimediaprojekte mühelos verbessern, indem Sie den Audioinhalt Ihrer Präsentationen wiederverwenden.

### Häufig gestellte Fragen (FAQs)

### Ist Aspose.Slides für .NET eine kostenlose Bibliothek?
 Nein, Aspose.Slides für .NET ist eine kommerzielle Bibliothek, aber Sie können ihre Funktionen und Dokumentation erkunden, indem Sie eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).

### Kann ich Audio aus Hyperlinks in älteren PowerPoint-Formaten wie PPT extrahieren?
Ja, Aspose.Slides für .NET unterstützt sowohl PPTX- als auch PPT-Formate zum Extrahieren von Audio aus Hyperlinks.

### Gibt es ein Community-Forum für Aspose.Slides-Support?
 Ja, Sie können Hilfe erhalten und Ihre Erfahrungen mit Aspose.Slides teilen im[Aspose.Slides-Community-Forum](https://forum.aspose.com/).

### Kann ich für ein kurzfristiges Projekt eine temporäre Lizenz für Aspose.Slides erwerben?
Ja, Sie können eine temporäre Lizenz für Aspose.Slides für .NET erwerben, um Ihren kurzfristigen Projektbedarf zu decken. Besuchen Sie dazu[dieser Link](https://purchase.aspose.com/temporary-license/).

### Werden für die Extraktion außer MPG noch andere Audioformate unterstützt?
Mit Aspose.Slides für .NET können Sie Audio in verschiedenen Formaten extrahieren, nicht nur in MPG. Sie können es nach der Extraktion in Ihr bevorzugtes Format konvertieren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

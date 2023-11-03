---
title: Miniaturansicht aus Folie in Notizen erstellen
linktitle: Miniaturansicht aus Folie in Notizen erstellen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Miniaturansichten von Folien im Notizenbereich Ihrer Präsentation generieren. Verbessern Sie Ihre visuellen Inhalte!
type: docs
weight: 12
url: /de/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

In der Welt moderner Präsentationen sind visuelle Inhalte das A und O. Für eine effektive Kommunikation ist die Erstellung ansprechender Folien unerlässlich. Eine Möglichkeit, Ihre Präsentationen zu verbessern, besteht darin, Miniaturansichten von Folien zu erstellen, insbesondere wenn Sie bestimmte Details hervorheben oder einen Überblick geben möchten. Aspose.Slides für .NET ist ein leistungsstarkes Tool, mit dem Sie dies nahtlos erreichen können. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Erstellung von Miniaturansichten aus Folien im Notizenbereich einer Präsentation mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor wir uns mit den Details befassen, sollten Sie die folgenden Voraussetzungen erfüllen:

### 1. Aspose.Slides für .NET

 Stellen Sie sicher, dass Aspose.Slides für .NET installiert und eingerichtet ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

### 2. .NET-Umgebung

Auf Ihrem System sollte eine .NET-Entwicklungsumgebung bereitstehen.

### 3. Eine Präsentationsdatei

 Haben Sie eine Präsentationsdatei (z. B.`ThumbnailFromSlideInNotes.pptx`), aus dem Sie Miniaturansichten erstellen möchten.

Lassen Sie uns den Prozess nun in Schritte unterteilen:

## Schritt 1: Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Slides arbeiten zu können. Fügen Sie den folgenden Code am Anfang Ihres C#-Skripts hinzu:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Schritt 2: Laden Sie die Präsentation

 Als Nächstes müssen Sie die Präsentationsdatei laden, die die Folien mit Notizen enthält. Verwenden Sie den folgenden Code, um a zu instanziieren`Presentation` Klasse:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Ihr Code kommt hierher
}
```

## Schritt 3: Greifen Sie auf die Folie zu

Sie können auswählen, für welche Folie in der Präsentation Sie ein Miniaturbild erstellen möchten. In diesem Beispiel greifen wir auf die erste Folie zu:

```csharp
ISlide sld = pres.Slides[0];
```

## Schritt 4: Gewünschte Abmessungen definieren

Geben Sie die Abmessungen (Breite und Höhe) für die Miniaturansicht an, die Sie erstellen möchten. Zum Beispiel:

```csharp
int desiredX = 1200; // Breite
int desiredY = 800;  // Höhe
```

## Schritt 5: Skalierungsfaktoren berechnen

Um sicherzustellen, dass das Miniaturbild den gewünschten Abmessungen entspricht, berechnen Sie die Skalierungsfaktoren wie folgt:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Schritt 6: Erstellen Sie ein Miniaturbild

Erstellen Sie nun mit den berechneten Skalierungsfaktoren eine Miniaturansicht des Bildes in Originalgröße:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Schritt 7: Speichern Sie das Miniaturbild

Speichern Sie abschließend das generierte Miniaturbild als JPEG-Bild:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich eine Miniaturansicht einer Folie im Notizenbereich Ihrer Präsentation generiert.

## Abschluss

Durch die Einbindung von Miniaturansichten in Ihre Präsentationen können Sie deren visuelle Attraktivität und Effektivität deutlich verbessern. Aspose.Slides für .NET vereinfacht diesen Vorgang und ermöglicht Ihnen das einfache Erstellen benutzerdefinierter Miniaturansichten Ihrer Folien.

## FAQs (häufig gestellte Fragen)

### In welchen Formaten kann ich die generierten Miniaturansichten speichern?
Sie können die Miniaturansichten je nach Ihren Anforderungen in verschiedenen Formaten speichern, darunter JPEG, PNG und mehr.

### Kann ich Miniaturansichten für mehrere Folien gleichzeitig erstellen?
Ja, Sie können die Folien Ihrer Präsentation in einer Schleife durchgehen und für jede einzelne Miniaturansichten erstellen.

### Ist Aspose.Slides für .NET mit verschiedenen .NET-Frameworks kompatibel?
Ja, Aspose.Slides für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Framework.

### Kann ich das Erscheinungsbild der generierten Miniaturansichten anpassen?
Absolut! Aspose.Slides für .NET bietet Optionen zum Anpassen des Erscheinungsbilds der Miniaturansichten, z. B. Abmessungen, Qualität und mehr.

### Wo kann ich Unterstützung oder weitere Hilfe zu Aspose.Slides für .NET erhalten?
 Hilfe und Kontakt zur Aspose-Community finden Sie unter[Aspose-Supportforum](https://forum.aspose.com/).
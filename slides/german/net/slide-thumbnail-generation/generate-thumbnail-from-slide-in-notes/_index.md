---
title: Miniaturansicht aus Folie in Notizen generieren
linktitle: Miniaturansicht aus Folie in Notizen generieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Miniaturansichten von Folien im Notizenbereich Ihrer Präsentation erstellen. Verbessern Sie Ihren visuellen Inhalt!
weight: 12
url: /de/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Miniaturansicht aus Folie in Notizen generieren


In der Welt moderner Präsentationen ist visueller Inhalt das A und O. Das Erstellen ansprechender Folien ist für eine effektive Kommunikation unerlässlich. Eine Möglichkeit, Ihre Präsentationen zu verbessern, besteht darin, Miniaturansichten aus Folien zu erstellen, insbesondere wenn Sie bestimmte Details hervorheben oder einen Überblick vermitteln möchten. Aspose.Slides für .NET ist ein leistungsstarkes Tool, mit dem Sie dies nahtlos erreichen können. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Erstellung von Miniaturansichten aus Folien im Notizenbereich einer Präsentation mit Aspose.Slides für .NET.

## Voraussetzungen

Bevor wir in die Details eintauchen, sollten die folgenden Voraussetzungen erfüllt sein:

### 1. Aspose.Slides für .NET

 Stellen Sie sicher, dass Sie Aspose.Slides für .NET installiert und eingerichtet haben. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/net/).

### 2. .NET-Umgebung

Sie sollten auf Ihrem System eine .NET-Entwicklungsumgebung bereit haben.

### 3. Eine Präsentationsdatei

 Sie haben eine Präsentationsdatei (z. B.`ThumbnailFromSlideInNotes.pptx`), aus denen Sie Miniaturansichten erstellen möchten.

Lassen Sie uns den Prozess nun in Schritte unterteilen:

## Schritt 1: Namespaces importieren

Zuerst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Slides arbeiten zu können. Fügen Sie am Anfang Ihres C#-Skripts den folgenden Code hinzu:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Schritt 2: Laden Sie die Präsentation

 Als nächstes müssen Sie die Präsentationsdatei laden, die die Folien mit Notizen enthält. Verwenden Sie den folgenden Code, um eine`Presentation` Klasse:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Ihr Code kommt hier rein
}
```

## Schritt 3: Zugriff auf die Folie

Sie können auswählen, für welche Folie in der Präsentation Sie eine Miniaturansicht erstellen möchten. In diesem Beispiel greifen wir auf die erste Folie zu:

```csharp
ISlide sld = pres.Slides[0];
```

## Schritt 4: Gewünschte Abmessungen festlegen

Geben Sie die Abmessungen (Breite und Höhe) für das zu erstellende Miniaturbild an. Beispiel:

```csharp
int desiredX = 1200; // Breite
int desiredY = 800;  // Höhe
```

## Schritt 5: Skalierungsfaktoren berechnen

Um sicherzustellen, dass das Miniaturbild die gewünschten Abmessungen hat, berechnen Sie die Skalierungsfaktoren wie folgt:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Schritt 6: Erstellen Sie ein Miniaturbild

Erstellen Sie nun eine Miniaturansicht des Bilds in voller Größe unter Verwendung der berechneten Skalierungsfaktoren:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Schritt 7: Speichern Sie das Miniaturbild

Speichern Sie abschließend das erstellte Miniaturbild als JPEG-Bild:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Das ist es! Sie haben mit Aspose.Slides für .NET erfolgreich eine Miniaturansicht einer Folie im Notizenbereich Ihrer Präsentation erstellt.

## Abschluss

Durch das Einfügen von Miniaturansichten in Ihre Präsentationen können Sie deren visuelle Attraktivität und Effektivität deutlich steigern. Aspose.Slides für .NET vereinfacht diesen Vorgang und ermöglicht Ihnen die einfache Erstellung benutzerdefinierter Miniaturansichten Ihrer Folien.

## FAQs (Häufig gestellte Fragen)

### In welchen Formaten kann ich die generierten Miniaturansichten speichern?
Sie können die Miniaturansichten je nach Bedarf in verschiedenen Formaten speichern, darunter JPEG, PNG und mehr.

### Kann ich Miniaturansichten für mehrere Folien gleichzeitig erstellen?
Ja, Sie können die Folien Ihrer Präsentation durchlaufen und für jede eine Miniaturansicht erstellen.

### Ist Aspose.Slides für .NET mit verschiedenen .NET-Frameworks kompatibel?
Ja, Aspose.Slides für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Framework.

### Kann ich das Erscheinungsbild der generierten Miniaturansichten anpassen?
Auf jeden Fall! Aspose.Slides für .NET bietet Optionen zum Anpassen des Erscheinungsbilds der Miniaturansichten, wie z. B. Abmessungen, Qualität und mehr.

### Wo erhalte ich Support oder weitere Hilfe zu Aspose.Slides für .NET?
 Sie finden Hilfe und können sich mit der Aspose-Community austauschen unter[Aspose Support Forum](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

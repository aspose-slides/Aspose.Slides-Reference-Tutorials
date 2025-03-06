---
title: Erstellen von Folienminiaturen in Aspose.Slides
linktitle: Erstellen von Folienminiaturen in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie Folienminiaturen in Aspose.Slides für .NET mit Schritt-für-Schritt-Anleitung und Codebeispielen. Passen Sie das Erscheinungsbild an und speichern Sie Miniaturansichten. Verbessern Sie die Präsentationsvorschau.
weight: 10
url: /de/net/slide-thumbnail-generation/slide-thumbnail-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Wenn Sie mit Aspose.Slides Folienminiaturen in Ihren .NET-Anwendungen generieren möchten, sind Sie hier richtig. Das Erstellen von Folienminiaturen kann in verschiedenen Szenarien eine wertvolle Funktion sein, beispielsweise beim Erstellen benutzerdefinierter PowerPoint-Viewer oder beim Generieren von Bildvorschauen von Präsentationen. In dieser umfassenden Anleitung führen wir Sie Schritt für Schritt durch den Prozess. Wir behandeln Voraussetzungen, importieren Namespaces und unterteilen jedes Beispiel in mehrere Schritte, sodass Sie die Generierung von Folienminiaturen problemlos implementieren können.

## Voraussetzungen

Bevor Sie mit dem Generieren von Folienminiaturen mit Aspose.Slides für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides-Installation
Stellen Sie zunächst sicher, dass Aspose.Slides für .NET in Ihrer Entwicklungsumgebung installiert ist. Falls noch nicht geschehen, können Sie es von der Aspose-Website herunterladen.

-  Download-Link:[Aspose.Slides für .NET](https://releases.aspose.com/slides/net/)

### 2. Dokument zum Arbeiten
Sie benötigen ein PowerPoint-Dokument, aus dem Sie Folienminiaturen extrahieren können. Stellen Sie sicher, dass Sie Ihre Präsentationsdatei bereit haben.

### 3. .NET-Entwicklungsumgebung
Für dieses Tutorial sind gute Kenntnisse von .NET und die Einrichtung einer Entwicklungsumgebung erforderlich.

Nachdem Sie nun die Voraussetzungen erfüllt haben, beginnen wir mit der Schritt-für-Schritt-Anleitung zur Erstellung von Folienminiaturen in Aspose.Slides für .NET.

## Namespaces importieren

Um auf die Aspose.Slides-Funktionalität zuzugreifen, müssen Sie die erforderlichen Namespaces importieren. Dieser Schritt ist entscheidend, um sicherzustellen, dass Ihr Code korrekt mit der Bibliothek interagiert.

### Schritt 1: Using-Direktiven hinzufügen

Fügen Sie in Ihren C#-Code am Anfang Ihrer Datei die folgenden Using-Direktiven ein:

```csharp
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
```

Mit diesen Anweisungen können Sie die zum Generieren von Folienminiaturansichten erforderlichen Klassen und Methoden verwenden.

Lassen Sie uns nun den Vorgang der Erstellung von Folienminiaturen in mehrere Schritte unterteilen:

## Schritt 2: Dokumentverzeichnis festlegen

 Definieren Sie zunächst das Verzeichnis, in dem sich Ihr PowerPoint-Dokument befindet. Ersetzen Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer Datei.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 3: Instanziieren einer Präsentationsklasse

 In diesem Schritt erstellen Sie eine Instanz des`Presentation` Klasse zur Darstellung Ihrer Präsentationsdatei.

```csharp
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
 // Ihr Code zum Generieren der Folienminiaturansichten kommt hierhin
}
```

 Ersetzen Sie unbedingt`"YourPresentation.pptx"` durch den tatsächlichen Namen Ihrer PowerPoint-Datei.

## Schritt 4: Erstellen Sie das Miniaturbild

 Jetzt kommt der Kern des Prozesses. Innerhalb der`using` Block, fügen Sie den Code hinzu, um eine Miniaturansicht der gewünschten Folie zu erstellen. Im bereitgestellten Beispiel generieren wir eine Miniaturansicht der ersten Form auf der ersten Folie.

```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
 // Ihr Code zum Speichern des Miniaturbilds kommt hier rein
}
```

Sie können diesen Code ändern, um bei Bedarf Miniaturansichten bestimmter Folien und Formen zu erfassen.

## Schritt 5: Speichern Sie das Miniaturbild

Im letzten Schritt wird das generierte Miniaturbild im gewünschten Bildformat auf der Festplatte gespeichert. In diesem Beispiel speichern wir das Miniaturbild im PNG-Format.

```csharp
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```

 Ersetzen`"Shape_thumbnail_Bound_Shape_out.png"` mit dem gewünschten Dateinamen und Speicherort.

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für .NET Folienminiaturen erstellen. Diese leistungsstarke Funktion kann Ihre Anwendungen verbessern, indem sie visuelle Vorschauen Ihrer PowerPoint-Präsentationen bereitstellt. Wenn die richtigen Voraussetzungen erfüllt sind und Sie der Schritt-für-Schritt-Anleitung folgen, können Sie diese Funktion problemlos implementieren.

## FAQs

### F: Kann ich Miniaturansichten für mehrere Folien einer Präsentation erstellen?
A: Ja, Sie können den Code ändern, um Miniaturansichten für jede Folie oder Form in Ihrer Präsentation zu generieren.

### F: Welche Bildformate werden zum Speichern der Miniaturansichten unterstützt?
A: Aspose.Slides für .NET unterstützt verschiedene Bildformate, darunter PNG, JPEG und BMP.

### F: Gibt es beim Erstellen von Miniaturansichten irgendwelche Einschränkungen?
A: Bei größeren Präsentationen oder komplexen Formen kann der Vorgang zusätzlichen Speicher und Verarbeitungszeit beanspruchen.

### F: Kann ich die Größe der generierten Miniaturansichten anpassen?
A: Ja, Sie können die Abmessungen anpassen, indem Sie die Parameter im`GetThumbnail` Methode.

### F: Ist Aspose.Slides für .NET für die kommerzielle Nutzung geeignet?
A: Ja, Aspose.Slides ist eine robuste Lösung für private und kommerzielle Anwendungen. Lizenzdetails finden Sie auf der Aspose-Website.

 Für weitere Hilfe oder Fragen besuchen Sie bitte die[Aspose.Slides Support-Forum](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

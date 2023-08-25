---
title: Exportieren Sie Formen aus der Präsentation in das SVG-Format
linktitle: Exportieren Sie Formen aus der Präsentation in das SVG-Format
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Formen aus einer PowerPoint-Präsentation in das SVG-Format exportieren. Schritt-für-Schritt-Anleitung mit Quellcode im Lieferumfang enthalten. Extrahieren Sie effizient Formen für verschiedene Anwendungen.
type: docs
weight: 16
url: /de/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Diese Anleitung führt Sie durch den Prozess des Exportierens von Formen aus einer Präsentation in das SVG-Format mithilfe der Aspose.Slides für .NET-Bibliothek. Aspose.Slides ist eine leistungsstarke API, die es Ihnen ermöglicht, programmgesteuert mit Microsoft PowerPoint-Dateien zu arbeiten. In diesem Tutorial erfahren Sie, wie Sie Formen aus einer Präsentation extrahieren und sie mit C# im SVG-Format speichern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio installiert
- Grundlegendes Verständnis der C#-Programmierung
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Schritt für Schritt Anleitung

Befolgen Sie diese Schritte, um Formen aus einer Präsentation in das SVG-Format zu exportieren:

### 1. Erstellen Sie ein neues Projekt

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt.

### 2. Fügen Sie einen Verweis auf Aspose.Slides hinzu

Klicken Sie in Ihrem Projekt im Projektmappen-Explorer mit der rechten Maustaste auf „Referenzen“ und dann auf „Referenz hinzufügen“. Durchsuchen Sie die heruntergeladene Aspose.Slides-DLL und wählen Sie sie aus.

### 3. Laden Sie die Präsentation

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Durch Formen iterieren

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Überprüfen Sie, ob es sich bei der Form um eine Gruppenform handelt
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Exportieren Sie die Form nach SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Exportieren Sie die Form nach SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. SVG-Dateien speichern

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Speichern Sie Änderungen an der Präsentation
```

## FAQs

### Wie kann ich Aspose.Slides für .NET installieren?

 Sie können die Aspose.Slides für .NET-Bibliothek unter herunterladen[Hier](https://releases.aspose.com/slides/net/). Befolgen Sie die Installationsanweisungen in der Dokumentation.

### Wie lade ich eine PowerPoint-Präsentation mit Aspose.Slides?

 Sie können eine Präsentation mit laden`Presentation` Klassenkonstruktor. Geben Sie den Pfad zur PowerPoint-Datei als Parameter an.

### Wie exportiere ich eine Form in das SVG-Format?

 Du kannst den ... benutzen`WriteAsSvg` Methode auf einem`IShape` Objekt, um es in das SVG-Format zu exportieren. Sie müssen den Dateinamen für die SVG-Ausgabe angeben.

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Bibliothek Aspose.Slides für .NET Formen aus einer PowerPoint-Präsentation in das SVG-Format exportieren. Dies kann nützlich sein, wenn Sie einzelne Formen zur Verwendung in anderen Anwendungen oder Plattformen extrahieren müssen, die SVG-Grafiken unterstützen. Aspose.Slides bietet eine einfache und effiziente Möglichkeit, dies programmgesteuert zu erreichen.

 Weitere Einzelheiten und erweiterte Funktionen finden Sie im[Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/).
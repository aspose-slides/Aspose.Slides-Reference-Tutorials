---
title: Erstellen von Gruppenformen in Präsentationsfolien mit Aspose.Slides
linktitle: Erstellen von Gruppenformen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET faszinierende Präsentationsfolien mit Gruppenformen erstellen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung und das Quellcode-Beispiel, um Formen einfach hinzuzufügen, zu gruppieren und zu transformieren und so Ihre Präsentationen zu verbessern.
type: docs
weight: 11
url: /de/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine umfassende und funktionsreiche Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu bearbeiten. Unabhängig davon, ob Sie Präsentationsdateien erstellen, ändern oder konvertieren möchten, bietet Aspose.Slides eine breite Palette an Tools und Funktionen, um den Prozess zu vereinfachen.

## Voraussetzungen

Bevor Sie mit Aspose.Slides für .NET arbeiten, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio: Installieren Sie Visual Studio auf Ihrem Computer.
-  Aspose.Slides-Bibliothek: Laden Sie die Aspose.Slides-Bibliothek herunter und referenzieren Sie sie in Ihrem Projekt. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Hinzufügen von Aspose.Slides zu Ihrem Projekt

1. Laden Sie die Aspose.Slides-Bibliothek über den bereitgestellten Link herunter.
2. Erstellen Sie ein neues Projekt in Visual Studio oder öffnen Sie ein vorhandenes.
3. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“.
4. Wählen Sie die Registerkarte „Durchsuchen“ und suchen Sie nach „Aspose.Slides“.
5. Installieren Sie das Aspose.Slides-Paket in Ihrem Projekt.

## Erstellen einer neuen Präsentation

Beginnen wir mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides:

```csharp
using Aspose.Slides;

// Erstellen Sie eine neue Präsentation
Presentation presentation = new Presentation();
```

## Formen zur Folie hinzufügen

Als nächstes fügen wir der Folie einige Formen hinzu. In diesem Beispiel fügen wir zwei Rechtecke hinzu:

```csharp
// Greifen Sie auf die erste Folie zu
ISlide slide = presentation.Slides[0];

// Fügen Sie der Folie Rechtecke hinzu
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Gruppieren von Formen

Nun gruppieren wir die Formen, um sie gemeinsam zu verwalten:

```csharp
// Gruppenformen
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Anwenden von Transformationen auf gruppierte Formen

Sie können verschiedene Transformationen auf die gruppierten Formen anwenden. Drehen wir beispielsweise die gruppierten Formen um 45 Grad:

```csharp
// Drehen Sie die Gruppe um 45 Grad
groupShape.Rotation = 45;
```

## Beispiel für einen Quellcode

Hier ist das vollständige Quellcode-Beispiel zum Erstellen von Gruppenformen mit Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Erstellen Sie eine neue Präsentation
            Presentation presentation = new Presentation();

            // Greifen Sie auf die erste Folie zu
            ISlide slide = presentation.Slides[0];

            // Fügen Sie der Folie Rechtecke hinzu
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Gruppenformen
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Drehen Sie die Gruppe um 45 Grad
            groupShape.Rotation = 45;

            // Speichern Sie die Präsentation
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für .NET Gruppenformen in Präsentationsfolien erstellen. Die Bibliothek bietet eine einfache Möglichkeit, Formen hinzuzufügen, sie zu gruppieren und Transformationen anzuwenden, um Ihre Präsentationen dynamisch zu verbessern.

## FAQs

### Wie installiere ich Aspose.Slides für .NET?

 Sie können die Aspose.Slides-Bibliothek über den bereitgestellten Link herunterladen:[Hier](https://releases.aspose.com/slides/net/). Nach dem Herunterladen können Sie es mithilfe von NuGet-Paketen zu Ihrem Projekt hinzufügen.

### Kann ich unterschiedliche Transformationen auf gruppierte Formen anwenden?

Ja, Sie können verschiedene Transformationen wie Drehung, Skalierung und Positionierung auf die gruppierten Formen anwenden und so das visuelle Erscheinungsbild Ihrer Folien anpassen.

### Eignet sich Aspose.Slides sowohl zum Erstellen als auch zum Ändern von Präsentationen?

Absolut! Aspose.Slides für .NET ist eine vielseitige Bibliothek, die das Erstellen, Ändern und Konvertieren von Präsentationsdateien unterstützt. Es bietet eine breite Palette an Funktionen, um unterschiedlichen Anforderungen gerecht zu werden.

### Kann ich Formen verschiedener Typen gruppieren?

 Ja, Sie können Formen unterschiedlicher Art, z. B. Rechtecke, Kreise und Textfelder, mithilfe von gruppieren`GroupShapes` Methode. Dies ermöglicht Ihnen, sie gemeinsam zu verwalten und zu manipulieren.

### Ist Aspose.Slides nur für .NET-Anwendungen geeignet?

Ja, Aspose.Slides wurde speziell für .NET-Anwendungen entwickelt. Es sind jedoch auch Versionen für andere Programmiersprachen verfügbar, beispielsweise für Java.
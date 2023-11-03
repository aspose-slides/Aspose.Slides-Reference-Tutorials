---
title: Erstellen einer Miniaturansicht mit Skalierungsfaktor für die Form in Aspose.Slides
linktitle: Erstellen einer Miniaturansicht mit Skalierungsfaktor für die Form in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET ansprechende Präsentationen erstellen! Befolgen Sie unsere Schritt-für-Schritt-Anleitung mit vollständigem Quellcode, um Miniaturansichten mit Skalierungsfaktoren für Formen zu erstellen.
type: docs
weight: 12
url: /de/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

# Einführung in die Erstellung von Miniaturansichten mit Skalierungsfaktor für Formen

In der heutigen schnelllebigen Welt spielen visuelle Inhalte eine entscheidende Rolle für eine effektive Kommunikation. Präsentationen, sei es für geschäftliche, Bildungs- oder Unterhaltungszwecke, basieren oft auf fesselnden Bildern, um Ideen zu vermitteln. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zur Verbesserung Ihres Präsentationserstellungsprozesses durch die Bereitstellung von Tools zum Bearbeiten und Anpassen von Formen, Bildern und anderen Elementen. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Slides für .NET eine Miniaturansicht einer Form mit einem bestimmten Skalierungsfaktor erstellen.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio ist auf Ihrem System installiert.
- Grundkenntnisse der C#-Programmierung.
-  Aspose.Slides für .NET-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Einrichten des Projekts

1. Öffnen Sie Visual Studio und erstellen Sie ein neues Projekt. Wählen Sie die entsprechende Projektvorlage (z. B. Konsolenanwendung).
2. Benennen Sie Ihr Projekt und geben Sie den Speicherort an, an dem Sie es speichern möchten.
3. Klicken Sie auf „Erstellen“, um das Projekt zu generieren.

## Aspose.Slides zum Projekt hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten…“
3. Suchen Sie nach „Aspose.Slides“ und installieren Sie das Paket.

## Laden einer Präsentation

Um zu beginnen, benötigen Sie eine PowerPoint-Präsentation, mit der Sie arbeiten können. Nehmen wir an, Sie haben eine Präsentation mit dem Namen „sample.pptx“.

```csharp
using Aspose.Slides;

// Laden Sie die Präsentation
using var presentation = new Presentation("sample.pptx");
```

## Auf Formen zugreifen und diese ändern

Bevor Sie eine Miniaturansicht erstellen, müssen Sie auf die Form zugreifen, die Sie ändern möchten. Formen in Aspose.Slides sind in Foliensammlungen organisiert.

```csharp
// Greifen Sie auf die erste Folie zu
var slide = presentation.Slides[0];

// Greifen Sie auf die Form zu (nehmen wir an, es ist ein Rechteck).
var shape = slide.Shapes[0];
```

## Erstellen einer Miniaturansicht mit Skalierungsfaktor

Jetzt kommt der spannende Teil – das Erstellen eines Miniaturbilds mit einem bestimmten Skalierungsfaktor. Dazu müssen Sie eine Kopie der Originalform erstellen und deren Größe anpassen.

```csharp
// Erstellen Sie eine Kopie der Form
var thumbnailShape = shape.Clone();

// Definieren Sie den Skalierungsfaktor (z. B. 0,5 für 50 %).
double scalingFactor = 0.5;

// Passen Sie die Breite und Höhe der Miniaturansicht an
thumbnailShape.Width *= scalingFactor;
thumbnailShape.Height *= scalingFactor;
```

## Speichern der geänderten Präsentation

Nachdem Sie die Miniaturansicht erstellt haben, können Sie die geänderte Präsentation speichern.

```csharp
// Fügen Sie die geänderte Form zur Folie hinzu
slide.Shapes.AddClone(thumbnailShape);

// Speichern Sie die Präsentation
presentation.Save("modified_sample.pptx", SaveFormat.Pptx);
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie mit Aspose.Slides für .NET eine Miniaturansicht einer Form mit einem bestimmten Skalierungsfaktor erstellen. Wir haben den gesamten Prozess abgedeckt, vom Einrichten des Projekts und dem Laden einer Präsentation bis hin zum Zugriff auf und Ändern von Formen. Die visuelle Bearbeitung von Inhalten steht Ihnen jetzt zur Verfügung und ermöglicht Ihnen die Erstellung ansprechender Präsentationen, die Ihre Botschaft effektiv vermitteln.

## FAQs

### Wie kann ich die Aspose.Slides für .NET-Bibliothek herunterladen?

 Sie können die Aspose.Slides für .NET-Bibliothek unter herunterladen[Hier](https://releases.aspose.com/slides/net/).

### Kann ich den Skalierungsfaktor auf andere Formentypen anwenden, beispielsweise auf Kreise?

Ja, Sie können den Skalierungsfaktor auf verschiedene Arten von Formen anwenden, darunter Kreise, Rechtecke und mehr.

### Ist Aspose.Slides mit verschiedenen PowerPoint-Versionen kompatibel?

Ja, Aspose.Slides generiert Präsentationen, die mit verschiedenen Versionen von Microsoft PowerPoint kompatibel sind.

### Kann ich Miniaturansichten mit unterschiedlichen Skalierungsfaktoren für mehrere Formen erstellen?

Absolut! Sie können den Vorgang für jede Form wiederholen, für die Sie eine Miniaturansicht erstellen möchten, und dabei den Skalierungsfaktor nach Bedarf anpassen.

### Unterstützt Aspose.Slides neben C# auch andere Programmiersprachen?

Ja, Aspose.Slides unterstützt mehrere Programmiersprachen, darunter Java, Python und mehr. Weitere Einzelheiten finden Sie in der Dokumentation.
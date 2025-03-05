---
title: Aspose.Slides - Erstellen von Gruppenformen in .NET
linktitle: Erstellen von Gruppenformen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Gruppenformen in PowerPoint erstellen. Folgen Sie unserer Schritt-für-Schritt-Anleitung für optisch ansprechende Präsentationen.
type: docs
weight: 11
url: /de/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Einführung
Wenn Sie die visuelle Attraktivität Ihrer Präsentationsfolien verbessern und Inhalte effizienter organisieren möchten, ist die Einbindung von Gruppenformen eine leistungsstarke Lösung. Aspose.Slides für .NET bietet eine nahtlose Möglichkeit, Gruppenformen in Ihren PowerPoint-Präsentationen zu erstellen und zu bearbeiten. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung von Gruppenformen mit Aspose.Slides und unterteilen ihn in leicht verständliche Schritte.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek installiert haben. Sie können sie von der[Webseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine Arbeitsumgebung mit einer .NET-kompatiblen IDE wie Visual Studio ein.
- Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt zunächst die erforderlichen Namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Präsentationsklasse instanziieren

 Erstellen Sie eine Instanz des`Presentation` Klasse und geben Sie das Verzeichnis an, in dem Ihre Dokumente gespeichert sind:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Fahren Sie mit den folgenden Schritten innerhalb dieses Using-Blocks fort
}
```

## Schritt 2: Zugriff auf die erste Folie

Rufen Sie die erste Folie aus der Präsentation ab:

```csharp
ISlide sld = pres.Slides[0];
```

## Schritt 3: Zugriff auf die Shape-Sammlung

Greifen Sie auf die Sammlung von Formen auf der Folie zu:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Schritt 4: Hinzufügen einer Gruppenform

Fügen Sie der Folie eine Gruppenform hinzu:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Schritt 5: Hinzufügen von Formen innerhalb der Gruppenform

Füllen Sie die Gruppenform mit einzelnen Formen:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Schritt 6: Gruppenformrahmen hinzufügen

Definieren Sie den Rahmen für die gesamte Gruppenform:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Schritt 7: Speichern Sie die Präsentation

Speichern Sie die geänderte Präsentation in Ihrem angegebenen Verzeichnis:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Wiederholen Sie diese Schritte in Ihrer C#-Anwendung, um mit Aspose.Slides erfolgreich Gruppenformen in Ihren Präsentationsfolien zu erstellen.

## Abschluss
In diesem Tutorial haben wir den Prozess zum Erstellen von Gruppenformen mit Aspose.Slides für .NET untersucht. Indem Sie diese Schritte befolgen, können Sie die visuelle Attraktivität und Organisation Ihrer PowerPoint-Präsentationen verbessern.
## Häufig gestellte Fragen
### Ist Aspose.Slides mit der neuesten Version von .NET kompatibel?
 Ja, Aspose.Slides wird regelmäßig aktualisiert, um die neuesten .NET-Versionen zu unterstützen. Überprüfen Sie die[Dokumentation](https://reference.aspose.com/slides/net/) für Kompatibilitätsdetails.
### Kann ich Aspose.Slides vor dem Kauf ausprobieren?
 Auf jeden Fall! Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Slides-bezogene Fragen?
Besuchen Sie die Aspose.Slides[Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
### Wie erhalte ich eine temporäre Lizenz für Aspose.Slides?
 Sie können eine vorübergehende Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich eine Volllizenz für Aspose.Slides erwerben?
 Sie können eine Lizenz erwerben bei der[Kaufseite](https://purchase.aspose.com/buy).

---
title: Aspose.Slides – Erstellen von Gruppenformen in .NET
linktitle: Erstellen von Gruppenformen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Gruppenformen in PowerPoint erstellen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für optisch ansprechende Präsentationen.
type: docs
weight: 11
url: /de/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Einführung
Wenn Sie die visuelle Attraktivität Ihrer Präsentationsfolien verbessern und Inhalte effizienter organisieren möchten, ist die Integration von Gruppenformen eine leistungsstarke Lösung. Aspose.Slides für .NET bietet eine nahtlose Möglichkeit, Gruppenformen in Ihren PowerPoint-Präsentationen zu erstellen und zu bearbeiten. In diesem Tutorial führen wir den Prozess der Erstellung von Gruppenformen mit Aspose.Slides durch und unterteilen ihn in leicht verständliche Schritte.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek installiert haben. Sie können es hier herunterladen[Webseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine Arbeitsumgebung mit einer .NET-kompatiblen IDE ein, beispielsweise Visual Studio.
- Grundkenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut.
## Namespaces importieren
Beginnen Sie in Ihrem C#-Projekt mit dem Importieren der erforderlichen Namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Instanziieren Sie die Präsentationsklasse

 Erstellen Sie eine Instanz von`Presentation` Klasse und geben Sie das Verzeichnis an, in dem Ihre Dokumente gespeichert sind:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Fahren Sie mit den folgenden Schritten innerhalb dieses using-Blocks fort
}
```

## Schritt 2: Greifen Sie auf die erste Folie zu

Rufen Sie die erste Folie aus der Präsentation ab:

```csharp
ISlide sld = pres.Slides[0];
```

## Schritt 3: Zugriff auf die Formensammlung

Greifen Sie auf die Formensammlung auf der Folie zu:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Schritt 4: Hinzufügen einer Gruppenform

Fügen Sie der Folie eine Gruppenform hinzu:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Schritt 5: Formen innerhalb der Gruppenform hinzufügen

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
In diesem Tutorial haben wir den Prozess der Erstellung von Gruppenformen mit Aspose.Slides für .NET untersucht. Wenn Sie diese Schritte befolgen, können Sie die visuelle Attraktivität und Organisation Ihrer PowerPoint-Präsentationen verbessern.
## Häufig gestellte Fragen
### Ist Aspose.Slides mit der neuesten Version von .NET kompatibel?
 Ja, Aspose.Slides wird regelmäßig aktualisiert, um die neuesten .NET-Versionen zu unterstützen. Überprüf den[Dokumentation](https://reference.aspose.com/slides/net/) für Kompatibilitätsdetails.
### Kann ich Aspose.Slides vor dem Kauf ausprobieren?
 Absolut! Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Slides-bezogene Abfragen?
 Besuchen Sie die Aspose.Slides[Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
### Wie erhalte ich eine temporäre Lizenz für Aspose.Slides?
 Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich eine Volllizenz für Aspose.Slides erwerben?
 Sie können eine Lizenz bei kaufen[Kaufseite](https://purchase.aspose.com/buy).

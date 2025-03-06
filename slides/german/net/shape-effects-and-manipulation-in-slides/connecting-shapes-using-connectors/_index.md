---
title: Aspose.Slides – Formen nahtlos in .NET verbinden
linktitle: Verbinden von Formen mithilfe von Konnektoren in Präsentationen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Slides für .NET und verbinden Sie Formen mühelos in Ihren Präsentationen. Werten Sie Ihre Folien mit dynamischen Konnektoren auf.
weight: 29
url: /de/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
In der dynamischen Welt der Präsentationen verleiht die Möglichkeit, Formen mithilfe von Konnektoren zu verbinden, Ihren Folien eine zusätzliche Ebene der Raffinesse. Aspose.Slides für .NET ermöglicht Entwicklern, dies nahtlos zu erreichen. Dieses Tutorial führt Sie durch den Prozess und unterteilt jeden Schritt, um ein klares Verständnis zu gewährleisten.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse in C# und .NET Framework.
-  Aspose.Slides für .NET installiert. Wenn nicht, laden Sie es herunter[Hier](https://releases.aspose.com/slides/net/).
- Eine Entwicklungsumgebung wurde eingerichtet.
## Namespaces importieren
Beginnen Sie in Ihrem C#-Code mit dem Importieren der erforderlichen Namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Einrichten des Dokumentverzeichnisses
Definieren Sie zunächst das Verzeichnis für Ihr Dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Präsentationsklasse instanziieren
Erstellen Sie eine Instanz der Klasse „Presentation“, um Ihre PPTX-Datei darzustellen:
```csharp
using (Presentation input = new Presentation())
{
    // Auf die Formensammlung für die ausgewählte Folie zugreifen
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Fügen Sie der Folie Formen hinzu
Fügen Sie Ihrer Folie die erforderlichen Formen hinzu, beispielsweise Ellipse und Rechteck:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Verbindungsform hinzufügen
Fügen Sie der Formsammlung der Folie eine Verbindungsform hinzu:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Formen mit Connector verbinden
Geben Sie die Formen an, die durch den Verbinder verbunden werden sollen:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Konnektor umleiten
Rufen Sie die Umleitungsmethode auf, um automatisch den kürzesten Pfad zwischen den Formen festzulegen:
```csharp
connector.Reroute();
```
## 7. Präsentation speichern
Speichern Sie Ihre Präsentation, um die verbundenen Formen anzuzeigen:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Abschluss
Herzlichen Glückwunsch! Sie haben mithilfe von Aspose.Slides für .NET erfolgreich Formen mithilfe von Konnektoren in Präsentationsfolien verbunden. Verbessern Sie Ihre Präsentationen mit dieser erweiterten Funktion und fesseln Sie Ihr Publikum.
## FAQs
### Ist Aspose.Slides für .NET mit dem neuesten .NET-Framework kompatibel?
Ja, Aspose.Slides für .NET wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten Versionen des .NET-Frameworks sicherzustellen.
### Kann ich mehr als zwei Formen mit einem einzigen Verbinder verbinden?
Natürlich können Sie mehrere Formen verbinden, indem Sie die Verbindungslogik in Ihrem Code erweitern.
### Gibt es irgendwelche Einschränkungen hinsichtlich der Formen, die ich verbinden kann?
Aspose.Slides für .NET unterstützt das Verbinden verschiedener Formen, einschließlich Grundformen, Smart Art und benutzerdefinierter Formen.
### Wie kann ich das Erscheinungsbild des Connectors anpassen?
Informieren Sie sich in der Aspose.Slides-Dokumentation über Methoden zum Anpassen des Erscheinungsbilds von Konnektoren, beispielsweise Linienstil und Farbe.
### Gibt es ein Community-Forum für Aspose.Slides-Support?
 Ja, Sie können Hilfe finden und Ihre Erfahrungen teilen im[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

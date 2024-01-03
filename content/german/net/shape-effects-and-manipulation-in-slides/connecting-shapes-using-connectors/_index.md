---
title: Aspose.Slides – Formen nahtlos in .NET verbinden
linktitle: Verbinden von Formen mithilfe von Konnektoren in der Präsentation
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Slides für .NET und verbinden Sie Formen mühelos in Ihren Präsentationen. Werten Sie Ihre Folien mit dynamischen Anschlüssen auf.
type: docs
weight: 29
url: /de/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Einführung
In der dynamischen Welt der Präsentationen verleiht die Möglichkeit, Formen mithilfe von Verbindern zu verbinden, Ihren Folien eine Ebene der Raffinesse. Aspose.Slides für .NET ermöglicht Entwicklern, dies nahtlos zu erreichen. Dieses Tutorial führt Sie durch den Prozess und schlüsselt jeden Schritt auf, um ein klares Verständnis zu gewährleisten.
## Voraussetzungen
Bevor wir uns mit dem Tutorial befassen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- Grundkenntnisse in C# und .NET Framework.
-  Aspose.Slides für .NET installiert. Wenn nicht, laden Sie es herunter[Hier](https://releases.aspose.com/slides/net/).
- Eine Entwicklungsumgebung eingerichtet.
## Namespaces importieren
Beginnen Sie in Ihrem C#-Code mit dem Importieren der erforderlichen Namespaces:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Richten Sie das Dokumentenverzeichnis ein
Beginnen Sie mit der Definition des Verzeichnisses für Ihr Dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instanziieren Sie die Präsentationsklasse
Erstellen Sie eine Instanz der Presentation-Klasse, um Ihre PPTX-Datei darzustellen:
```csharp
using (Presentation input = new Presentation())
{
    // Zugriff auf die Formensammlung für die ausgewählte Folie
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Fügen Sie der Folie Formen hinzu
Fügen Sie Ihrer Folie die erforderlichen Formen hinzu, z. B. Ellipse und Rechteck:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Verbindungsform hinzufügen
Fügen Sie eine Verbindungsform in die Formensammlung der Folie ein:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Formen mit Connector verbinden
Geben Sie die Formen an, die durch den Verbinder verbunden werden sollen:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Anschluss umleiten
Rufen Sie die Reroute-Methode auf, um den automatischen kürzesten Pfad zwischen Formen festzulegen:
```csharp
connector.Reroute();
```
## 7. Präsentation speichern
Speichern Sie Ihre Präsentation, um die verbundenen Formen anzuzeigen:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Abschluss
Glückwunsch! Sie haben erfolgreich Formen mithilfe von Konnektoren in Präsentationsfolien mit Aspose.Slides für .NET verbunden. Werten Sie Ihre Präsentationen mit dieser erweiterten Funktion auf und fesseln Sie Ihr Publikum.
## FAQs
### Ist Aspose.Slides für .NET mit dem neuesten .NET-Framework kompatibel?
Ja, Aspose.Slides für .NET wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET Framework-Versionen sicherzustellen.
### Kann ich mehr als zwei Formen mit einem einzigen Verbinder verbinden?
Auf jeden Fall können Sie mehrere Formen verbinden, indem Sie die Verbindungslogik in Ihrem Code erweitern.
### Gibt es Einschränkungen hinsichtlich der Formen, die ich verbinden kann?
Aspose.Slides für .NET unterstützt das Verbinden verschiedener Formen, einschließlich Grundformen, Smart Art und benutzerdefinierter Formen.
### Wie kann ich das Erscheinungsbild des Connectors anpassen?
Entdecken Sie die Aspose.Slides-Dokumentation für Methoden zum Anpassen des Erscheinungsbilds von Verbindern, z. B. Linienstil und Farbe.
### Gibt es ein Community-Forum für die Unterstützung von Aspose.Slides?
 Ja, Sie können Hilfe finden und Ihre Erfahrungen teilen[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
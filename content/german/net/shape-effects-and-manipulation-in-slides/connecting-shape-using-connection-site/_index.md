---
title: Beherrschung von Formverbindungen mit Aspose.Slides für .NET
linktitle: Verbindungsform mithilfe der Verbindungsstelle in der Präsentation
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie mit Aspose.Slides für .NET fesselnde Präsentationen und verbinden Sie Formen nahtlos. Folgen Sie unserem Leitfaden für ein reibungsloses und ansprechendes Erlebnis.
type: docs
weight: 30
url: /de/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---
## Einführung
In der dynamischen Welt der Präsentationen ist die Erstellung optisch ansprechender Folien mit miteinander verbundenen Formen von entscheidender Bedeutung für eine effektive Kommunikation. Aspose.Slides für .NET bietet eine leistungsstarke Lösung, um dies zu erreichen, indem es Ihnen ermöglicht, Formen mithilfe von Verbindungsstellen zu verbinden. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Verbindens von Formen und stellt sicher, dass Ihre Präsentationen durch nahtlose visuelle Übergänge hervorstechen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Ein grundlegendes Verständnis der C#- und .NET-Programmierung.
-  Aspose.Slides für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio eingerichtet.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihren C#-Code:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
Stellen Sie sicher, dass Sie ein bestimmtes Verzeichnis für Ihr Dokument haben. Wenn es nicht existiert, erstellen Sie eines:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Schritt 2: Erstellen Sie eine Präsentation
Instanziieren Sie die Presentation-Klasse, um Ihre PPTX-Datei darzustellen:
```csharp
using (Presentation presentation = new Presentation())
{
    // Ihr Code für die Präsentation kommt hierher
}
```
## Schritt 3: Formen aufrufen und hinzufügen
Greifen Sie auf die Formensammlung für die ausgewählte Folie zu und fügen Sie die erforderlichen Formen hinzu:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Schritt 4: Formen mithilfe von Verbindern verbinden
Verbinden Sie die Formen mit dem Verbinder:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Schritt 5: Legen Sie die gewünschte Verbindungsseite fest
Geben Sie den gewünschten Verbindungsstandortindex für den Connector an:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## Schritt 6: Speichern Sie Ihre Präsentation
Speichern Sie Ihre Präsentation mit den verbundenen Formen:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
Jetzt haben Sie Formen mithilfe von Verbindungsstellen in Ihrer Präsentation erfolgreich verbunden.
## Abschluss
Aspose.Slides für .NET vereinfacht das Verbinden von Formen und ermöglicht Ihnen die mühelose Erstellung visuell ansprechender Präsentationen. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die visuelle Attraktivität Ihrer Folien verbessern und Ihre Botschaft effektiv vermitteln.
## Häufig gestellte Fragen
### Ist Aspose.Slides mit Visual Studio 2019 kompatibel?
Ja, Aspose.Slides ist mit Visual Studio 2019 kompatibel. Stellen Sie sicher, dass Sie die entsprechende Version installiert haben.
### Kann ich mehr als zwei Formen in einem einzigen Verbinder verbinden?
Mit Aspose.Slides können Sie zwei Formen mit einem einzigen Verbinder verbinden. Um weitere Formen zu verbinden, benötigen Sie zusätzliche Verbinder.
### Wie gehe ich mit Ausnahmen um, während ich Aspose.Slides verwende?
Sie können Try-Catch-Blöcke verwenden, um Ausnahmen zu behandeln. Siehe die[Dokumentation](https://reference.aspose.com/slides/net/) für bestimmte Ausnahmen und Fehlerbehandlung.
### Gibt es eine Testversion von Aspose.Slides?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
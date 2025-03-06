---
title: Shape Connection Mastery mit Aspose.Slides für .NET
linktitle: Verbinden von Formen mithilfe der Verbindungsstelle in der Präsentation
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erstellen Sie mit Aspose.Slides für .NET fesselnde Präsentationen und verbinden Sie Formen nahtlos. Folgen Sie unserer Anleitung für ein reibungsloses, ansprechendes Erlebnis.
weight: 30
url: /de/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
In der dynamischen Welt der Präsentationen ist die Erstellung optisch ansprechender Folien mit verbundenen Formen für eine effektive Kommunikation von entscheidender Bedeutung. Aspose.Slides für .NET bietet hierfür eine leistungsstarke Lösung, indem Sie Formen mithilfe von Verbindungsseiten verbinden können. Dieses Tutorial führt Sie Schritt für Schritt durch den Prozess des Verbindens von Formen und stellt sicher, dass Ihre Präsentationen durch nahtlose visuelle Übergänge hervorstechen.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundlegende Kenntnisse der C#- und .NET-Programmierung.
-  Aspose.Slides für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio muss eingerichtet sein.
## Namespaces importieren
Beginnen Sie mit dem Importieren der erforderlichen Namespaces in Ihren C#-Code:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein
Stellen Sie sicher, dass Sie ein bestimmtes Verzeichnis für Ihr Dokument haben. Wenn es noch keins gibt, erstellen Sie eines:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Schritt 2: Erstellen Sie eine Präsentation
Instanziieren Sie die Klasse „Presentation“, um Ihre PPTX-Datei darzustellen:
```csharp
using (Presentation presentation = new Presentation())
{
    // Hier kommt Ihr Code für die Präsentation rein
}
```
## Schritt 3: Auf Formen zugreifen und diese hinzufügen
Greifen Sie auf die Formensammlung für die ausgewählte Folie zu und fügen Sie die erforderlichen Formen hinzu:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Schritt 4: Formen mit Konnektoren verbinden
Verbinden Sie die Formen mithilfe des Verbinders:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Schritt 5: Gewünschte Verbindungssite festlegen
Geben Sie den gewünschten Verbindungssiteindex für den Connector an:
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
Jetzt haben Sie erfolgreich Formen mithilfe von Verbindungsstellen in Ihrer Präsentation verbunden.
## Abschluss
Aspose.Slides für .NET vereinfacht das Verbinden von Formen und ermöglicht Ihnen das mühelose Erstellen visuell ansprechender Präsentationen. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie die visuelle Attraktivität Ihrer Folien verbessern und Ihre Botschaft effektiv vermitteln.
## Häufig gestellte Fragen
### Ist Aspose.Slides mit Visual Studio 2019 kompatibel?
Ja, Aspose.Slides ist mit Visual Studio 2019 kompatibel. Stellen Sie sicher, dass Sie die entsprechende Version installiert haben.
### Kann ich mehr als zwei Formen mit einem einzigen Verbinder verbinden?
Mit Aspose.Slides können Sie zwei Formen mit einem einzigen Konnektor verbinden. Um weitere Formen zu verbinden, benötigen Sie zusätzliche Konnektoren.
### Wie behandle ich Ausnahmen bei der Verwendung von Aspose.Slides?
Sie können Try-Catch-Blöcke verwenden, um Ausnahmen zu behandeln. Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/net/) für bestimmte Ausnahmen und Fehlerbehandlung.
### Gibt es eine Testversion von Aspose.Slides?
 Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

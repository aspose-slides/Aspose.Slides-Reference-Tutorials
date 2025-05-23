---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen mithilfe von Konnektoren in PowerPoint-Präsentationen verbinden. Schritt-für-Schritt-Anleitung für Anfänger."
"linktitle": "Verbinden Sie Formen mithilfe von Konnektoren in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Verbinden Sie Formen mithilfe von Konnektoren in PowerPoint"
"url": "/de/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Verbinden Sie Formen mithilfe von Konnektoren in PowerPoint

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Slides für Java Formen mithilfe von Konnektoren in PowerPoint-Präsentationen verbinden. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um Formen effizient zu verbinden und optisch ansprechende Folien zu erstellen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse der Programmiersprache Java.
- Java Development Kit (JDK) auf Ihrem System installiert.
- Aspose.Slides für Java heruntergeladen und eingerichtet. Falls Sie es noch nicht installiert haben, können Sie es hier herunterladen: [Hier](https://releases.aspose.com/slides/java/).
- Ein Code-Editor wie Eclipse oder IntelliJ IDEA.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete für die Arbeit mit Aspose.Slides in Ihr Java-Projekt.
```java
import com.aspose.slides.*;

```
## Schritt 1: Präsentationsklasse instanziieren
Instanziieren Sie die `Presentation` Klasse, die die PPTX-Datei darstellt, an der Sie arbeiten.
```java
// Der Pfad zum Dokumentenverzeichnis.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Schritt 2: Zugriff auf die Shapes-Sammlung
Greifen Sie auf die Formensammlung für die ausgewählte Folie zu, der Sie Formen und Verbinder hinzufügen möchten.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Schritt 3: Formen hinzufügen
Fügen Sie der Folie die gewünschten Formen hinzu. In diesem Beispiel fügen wir eine Ellipse und ein Rechteck hinzu.
```java
// AutoForm Ellipse hinzufügen
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// AutoForm Rechteck hinzufügen
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Schritt 4: Connector hinzufügen
Fügen Sie der Folienformsammlung eine Verbindungsform hinzu.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Schritt 5: Formen mit Verbindern verbinden
Verbinden Sie die Formen mit dem Verbinder.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Schritt 6: Connector umleiten
Rufen Sie „Reroute“ auf, um den automatischen kürzesten Pfad zwischen Formen festzulegen.
```java
connector.reroute();
```
## Schritt 7: Präsentation speichern
Speichern Sie die Präsentation, nachdem Sie die Formen mithilfe von Konnektoren verbunden haben.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Vergessen Sie nicht, das Präsentationsobjekt zu entsorgen.
```java
if (input != null) input.dispose();
```
Jetzt haben Sie mithilfe von Aspose.Slides für Java erfolgreich Formen mithilfe von Konnektoren in PowerPoint verbunden.

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie Formen mithilfe von Konnektoren in PowerPoint-Präsentationen mit Aspose.Slides für Java verbinden. Mit diesen einfachen Schritten können Sie Ihre Präsentationen mit optisch ansprechenden Diagrammen und Flussdiagrammen aufwerten.
## Häufig gestellte Fragen
### Kann ich das Erscheinungsbild von Konnektoren in Aspose.Slides für Java anpassen?
Ja, Sie können verschiedene Eigenschaften von Verbindungsstücken wie Farbe, Linienstil und Dicke an Ihre Präsentationsanforderungen anpassen.
### Ist Aspose.Slides für Java mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides für Java unterstützt verschiedene PowerPoint-Formate, darunter PPTX, PPT und ODP.
### Kann ich mehr als zwei Formen mit einem einzigen Verbinder verbinden?
Ja, Sie können mehrere Formen mithilfe komplexer Konnektoren verbinden, die von Aspose.Slides für Java bereitgestellt werden.
### Bietet Aspose.Slides für Java Unterstützung für das Hinzufügen von Text zu Formen?
Auf jeden Fall. Mit Aspose.Slides für Java können Sie Formen und Konnektoren ganz einfach programmgesteuert Text hinzufügen.
### Gibt es ein Community-Forum oder einen Support-Kanal für Aspose.Slides für Java-Benutzer?
Ja, Sie können im Aspose.Slides-Forum hilfreiche Ressourcen finden, Fragen stellen und sich mit anderen Benutzern austauschen. [Hier](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
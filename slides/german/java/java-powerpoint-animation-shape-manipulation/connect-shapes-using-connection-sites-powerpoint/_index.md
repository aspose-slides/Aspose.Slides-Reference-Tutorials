---
title: Verbinden von Formen mithilfe von Verbindungsseiten in PowerPoint
linktitle: Verbinden von Formen mithilfe von Verbindungsseiten in PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint verbinden. Automatisieren Sie Ihre Präsentationen mühelos.
weight: 19
url: /de/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Verbinden von Formen mithilfe von Verbindungsseiten in PowerPoint

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Slides für Java Formen mithilfe von Verbindungsseiten in PowerPoint verbinden. Mit dieser leistungsstarken Bibliothek können Sie PowerPoint-Präsentationen programmgesteuert bearbeiten und Aufgaben wie das Verbinden von Formen nahtlos und effizient erledigen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können es von der[Webseite](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von der[Download-Seite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie eine IDE für die Java-Entwicklung, beispielsweise IntelliJ IDEA, Eclipse oder NetBeans.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;

```
## Schritt 1: Zugriff auf die Shapes-Sammlung
Greifen Sie auf die Formensammlung für die ausgewählte Folie zu:
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Schritt 2: Verbindungsform hinzufügen
Fügen Sie der Folienformsammlung eine Verbindungsform hinzu:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Schritt 3: AutoFormen hinzufügen
Fügen Sie automatische Formen wie Ellipse und Rechteck hinzu:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Schritt 4: Formen mit Verbindungsstücken verbinden
Verbinden Sie die Formen mit dem Verbinder:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Schritt 5: Festlegen des Verbindungssiteindex
Legen Sie den gewünschten Anschlussstellenindex für die Formen fest:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java Formen mithilfe von Verbindungsseiten in PowerPoint verbindet. Mit diesem Wissen können Sie Ihre PowerPoint-Präsentationen jetzt ganz einfach automatisieren und anpassen.
## Häufig gestellte Fragen
### Kann Aspose.Slides für Java für andere PowerPoint-Bearbeitungsaufgaben verwendet werden?
Ja, Aspose.Slides für Java bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Konvertieren von PowerPoint-Präsentationen.
### Ist die Nutzung von Aspose.Slides für Java kostenlos?
 Aspose.Slides für Java ist eine kommerzielle Bibliothek, aber Sie können ihre Funktionen mit einer kostenlosen Testversion erkunden. Besuchen Sie[Hier](https://releases.aspose.com/) um loszulegen.
### Kann ich Support erhalten, wenn bei der Verwendung von Aspose.Slides für Java Probleme auftreten?
 Ja, Sie können Unterstützung in den Aspose-Community-Foren erhalten[Hier](https://forum.aspose.com/c/slides/11).
### Sind temporäre Lizenzen für Aspose.Slides für Java verfügbar?
 Ja, es sind temporäre Lizenzen für Test- und Evaluierungszwecke erhältlich. Sie erhalten eine[Hier](https://purchase.aspose.com/temporary-license/).
### Wo kann ich eine Lizenz für Aspose.Slides für Java erwerben?
Sie können eine Lizenz von der Aspose-Website erwerben[Hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

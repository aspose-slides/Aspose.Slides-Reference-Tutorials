---
title: Formatieren von Verbindungsstilen in PowerPoint
linktitle: Formatieren von Verbindungsstilen in PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen verbessern können, indem Sie mit Aspose.Slides für Java verschiedene Linienverbindungsstile für Formen festlegen. Folgen Sie unserer Schritt-für-Schritt-Anleitung.
weight: 15
url: /de/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Das Erstellen optisch ansprechender PowerPoint-Präsentationen kann eine gewaltige Aufgabe sein, insbesondere wenn jedes Detail perfekt sein soll. Hier kommt Aspose.Slides für Java ins Spiel. Es handelt sich um eine leistungsstarke API, mit der Sie Präsentationen programmgesteuert erstellen, bearbeiten und verwalten können. Eine der Funktionen, die Sie nutzen können, ist das Festlegen verschiedener Linienverbindungsstile für Formen, wodurch die Ästhetik Ihrer Folien erheblich verbessert werden kann. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java Verbindungsstile für Formen in PowerPoint-Präsentationen festlegen können. 
## Voraussetzungen
Bevor wir beginnen, müssen einige Voraussetzungen erfüllt sein:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Rechner installiert ist. Sie können es hier herunterladen:[Website von Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides für Java-Bibliothek: Sie müssen Aspose.Slides für Java herunterladen und in Ihr Projekt einbinden. Sie erhalten es von[Hier](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine IDE wie IntelliJ IDEA, Eclipse oder NetBeans, um Ihren Java-Code zu schreiben und auszuführen.
4. Grundkenntnisse in Java: Grundlegende Kenntnisse der Java-Programmierung helfen Ihnen, dem Tutorial zu folgen.
## Pakete importieren
Zuerst müssen Sie die erforderlichen Pakete für Aspose.Slides importieren. Dies ist wichtig, um auf die Klassen und Methoden zuzugreifen, die für unsere Präsentationsmanipulationen erforderlich sind.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Schritt 1: Einrichten des Projektverzeichnisses
Beginnen wir mit der Erstellung eines Verzeichnisses zum Speichern unserer Präsentationsdateien. Dadurch wird sichergestellt, dass alle unsere Dateien organisiert und leicht zugänglich sind.
```java
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
In diesem Schritt definieren wir einen Verzeichnispfad und prüfen, ob dieser existiert. Wenn nicht, erstellen wir das Verzeichnis. Dies ist eine einfache, aber effektive Möglichkeit, Ihre Dateien zu organisieren.
## Schritt 2: Initialisieren der Präsentation
 Als nächstes instantiieren wir den`Presentation` Klasse, die unsere PowerPoint-Datei darstellt. Dies ist die Grundlage, auf der wir unsere Folien und Formen erstellen werden.
```java
Presentation pres = new Presentation();
```
Diese Codezeile erstellt eine neue Präsentation. Stellen Sie es sich so vor, als würden Sie eine leere PowerPoint-Datei öffnen, in die Sie Ihren gesamten Inhalt einfügen.
## Schritt 3: Formen zur Folie hinzufügen
### Holen Sie sich die erste Folie
Bevor wir Formen hinzufügen, müssen wir einen Verweis auf die erste Folie unserer Präsentation erhalten. Standardmäßig enthält eine neue Präsentation eine leere Folie.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Rechteckige Formen hinzufügen
Fügen wir nun unserer Folie drei rechteckige Formen hinzu. Diese Formen demonstrieren die verschiedenen Linienverbindungsstile.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
In diesem Schritt fügen wir an bestimmten Positionen auf der Folie drei Rechtecke hinzu. Jedes Rechteck wird später anders gestaltet, um verschiedene Verbindungsstile zu präsentieren.
## Schritt 4: Gestalten Sie die Formen
### Füllfarbe festlegen
Wir möchten, dass unsere Rechtecke mit einer Volltonfarbe gefüllt werden. Hier wählen wir Schwarz als Füllfarbe.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Linienbreite und Farbe festlegen
Als nächstes definieren wir die Linienbreite und -farbe für jedes Rechteck. Dies hilft bei der visuellen Unterscheidung der Verbindungsstile.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Schritt 5: Verbindungsstile anwenden
Das Highlight dieses Tutorials ist das Festlegen der Linienverbindungsstile. Wir werden drei verschiedene Stile verwenden: Gehrung, Abschrägung und Rund.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Jeder Linienverbindungsstil verleiht den Formen an den Ecken, an denen die Linien zusammentreffen, ein einzigartiges Aussehen. Dies kann besonders nützlich sein, um optisch unterschiedliche Diagramme oder Illustrationen zu erstellen.
## Schritt 6: Text zu Formen hinzufügen
Um deutlich zu machen, was jede Form darstellt, fügen wir jedem Rechteck einen Text hinzu, der den verwendeten Verbindungsstil beschreibt.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Durch das Hinzufügen von Text können Sie die unterschiedlichen Stile leichter erkennen, wenn Sie die Folie präsentieren oder freigeben.
## Schritt 7: Speichern Sie die Präsentation
Abschließend speichern wir unsere Präsentation im angegebenen Verzeichnis.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Dieser Befehl schreibt die Präsentation in eine PPTX-Datei, die Sie mit Microsoft PowerPoint oder einer anderen kompatiblen Software öffnen können.
## Abschluss
Und da haben Sie es! Sie haben gerade eine PowerPoint-Folie mit drei Rechtecken erstellt, von denen jedes einen anderen Linienverbindungsstil mit Aspose.Slides für Java zeigt. Dieses Tutorial hilft Ihnen nicht nur, die Grundlagen von Aspose.Slides zu verstehen, sondern zeigt Ihnen auch, wie Sie Ihre Präsentationen mit einzigartigen Stilen verbessern können. Viel Spaß beim Präsentieren!
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zum programmgesteuerten Erstellen, Bearbeiten und Verwalten von PowerPoint-Präsentationen.
### Kann ich Aspose.Slides für Java in jeder IDE verwenden?
Ja, Sie können Aspose.Slides für Java in jeder Java-unterstützten IDE wie IntelliJ IDEA, Eclipse oder NetBeans verwenden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion erhalten von[Hier](https://releases.aspose.com/).
### Was sind Linienverbindungsstile in PowerPoint?
Linienverbindungsstile beziehen sich auf die Form der Ecken, an denen zwei Linien zusammentreffen. Gängige Stile sind Gehrung, Abschrägung und Rundung.
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
 Eine ausführliche Dokumentation finden Sie[Hier](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

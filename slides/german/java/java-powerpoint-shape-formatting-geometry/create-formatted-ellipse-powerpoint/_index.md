---
"description": "Erfahren Sie in unserer ausführlichen Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Slides für Java eine formatierte Ellipse in PowerPoint erstellen."
"linktitle": "Erstellen Sie formatierte Ellipsen in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Erstellen Sie formatierte Ellipsen in PowerPoint"
"url": "/de/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie formatierte Ellipsen in PowerPoint

## Einführung
Willkommen zu diesem umfassenden Tutorial zum Erstellen einer formatierten Ellipse in PowerPoint mit Aspose.Slides für Java. Aspose.Slides ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Dateien programmgesteuert bearbeiten können. Ob Sie die Folienerstellung automatisieren oder Präsentationen mit benutzerdefinierten Formen verbessern möchten – diese Anleitung führt Sie Schritt für Schritt durch die Erstellung einer perfekt formatierten Ellipse. Lassen Sie uns gemeinsam herausfinden, wie wir das erreichen können!
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass Sie JDK 1.6 oder höher installiert haben.
2. Aspose.Slides für Java: Laden Sie die neueste Version herunter von [Aspose.Slides für Java](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine IDE wie IntelliJ IDEA oder Eclipse.
4. Grundkenntnisse in Java: Kenntnisse in der Java-Programmierung sind erforderlich.
## Pakete importieren
Um Aspose.Slides verwenden zu können, müssen Sie die erforderlichen Pakete importieren. So geht's:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Schritt 1: Richten Sie Ihr Projektverzeichnis ein
Zunächst benötigen Sie ein Verzeichnis zum Speichern Ihrer PowerPoint-Dateien.
### Verzeichnis erstellen
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Stellen Sie sicher, dass Sie ersetzen `"Your Document Directory"` durch den tatsächlichen Pfad, in dem Sie Ihre Dateien speichern möchten.
## Schritt 2: Initialisieren der Präsentation
Instanziieren Sie nun die Klasse „Presentation“, die die PowerPoint-Datei darstellt.
```java
// Instanziieren Sie die Präsentationsklasse, die das PPTX darstellt
Presentation pres = new Presentation();
```
## Schritt 3: Holen Sie sich die erste Folie
Nehmen Sie als Nächstes die erste Folie aus der Präsentation, in der Sie die Ellipse hinzufügen möchten.
```java
// Holen Sie sich die erste Folie
ISlide sld = pres.getSlides().get_Item(0);
```
## Schritt 4: Fügen Sie eine Ellipsenform hinzu
Fügen Sie der Folie eine automatische Form vom Typ Ellipse hinzu.
```java
// Autoform vom Typ Ellipse hinzufügen
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Hier, `50, 150, 150, 50` sind die Koordinaten und die Größe der Ellipse (x-Position, y-Position, Breite, Höhe).
## Schritt 5: Formatierung auf die Ellipse anwenden
Formatieren Sie nun die Ellipse. Wir legen eine Füllfarbe und eine Linienfarbe fest.
### Füllfarbe festlegen
```java
// Formatierung auf die Ellipsenform anwenden
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Linienfarbe und -breite festlegen
```java
// Wenden Sie eine Formatierung auf die Ellipsenlinie an
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend in Ihrem angegebenen Verzeichnis.
```java
// Schreiben Sie die PPTX-Datei auf die Festplatte
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Schritt 7: Entsorgen Sie das Präsentationsobjekt
Entsorgen Sie das Präsentationsobjekt, um Ressourcen freizugeben.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich eine formatierte Ellipse in einer PowerPoint-Präsentation erstellt. Dieses Tutorial hat Sie durch die Einrichtung Ihres Projekts, das Hinzufügen einer Ellipse, das Anwenden der Formatierung und das Speichern Ihrer Präsentation geführt. Mit diesen Kenntnissen können Sie Ihre PowerPoint-Folien nun programmgesteuert optimieren und Ihre Präsentationen dynamischer und optisch ansprechender gestalten.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert erstellen, ändern und verwalten können.
### Kann ich Aspose.Slides für Java mit jeder IDE verwenden?
Ja, Sie können Aspose.Slides für Java mit jeder Java-IDE wie IntelliJ IDEA, Eclipse oder NetBeans verwenden.
### Benötige ich eine Lizenz für Aspose.Slides?
Ja, Aspose.Slides ist ein kommerzielles Produkt und Sie benötigen eine Lizenz für die volle Funktionalität. Sie können eine temporäre Lizenz erhalten [Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
Eine ausführliche Dokumentation finden Sie auf Aspose.Slides für Java [Dokumentationsseite](https://reference.aspose.com/slides/java/).
### Gibt es Support für Aspose.Slides?
Ja, Aspose bietet Support über ihre [Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
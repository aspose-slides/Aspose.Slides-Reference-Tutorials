---
title: Formen in PowerPoint mit Mustern füllen
linktitle: Formen in PowerPoint mit Mustern füllen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Formen in PowerPoint mit Mustern füllen. Folgen Sie unserer einfachen Schritt-für-Schritt-Anleitung, um Ihre Präsentationen optisch zu verbessern.
weight: 11
url: /de/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Das Erstellen optisch ansprechender Präsentationen ist wichtig, um Ihr Publikum zu fesseln. Eine Möglichkeit, Ihre PowerPoint-Folien zu verbessern, besteht darin, Formen mit Mustern zu füllen. In diesem Tutorial führen wir Sie durch die Schritte zum Füllen von Formen mit Mustern mithilfe von Aspose.Slides für Java. Diese Anleitung ist auf Entwickler zugeschnitten, die die leistungsstarken Funktionen von Aspose.Slides nutzen möchten, um programmgesteuert beeindruckende Präsentationen zu erstellen.
## Voraussetzungen
Bevor Sie in den Code eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem Computer ist Java Development Kit (JDK) installiert.
- Integrierte Entwicklungsumgebung (IDE) wie IntelliJ IDEA oder Eclipse.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
- Grundkenntnisse der Java-Programmierung.
## Pakete importieren
Importieren wir zunächst die für unser Beispiel erforderlichen Pakete.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Stellen Sie vor dem Schreiben des Codes sicher, dass Ihr Projekt richtig eingerichtet ist. Erstellen Sie in Ihrer IDE ein neues Java-Projekt und fügen Sie die Bibliothek Aspose.Slides für Java zu Ihren Projektabhängigkeiten hinzu.
## Schritt 2: Erstellen Sie das Dokumentverzeichnis
Um Ihre Dateien effizient zu verwalten, erstellen wir ein Verzeichnis, in dem wir unsere PowerPoint-Präsentation speichern.
```java
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Dieses Snippet prüft, ob das Verzeichnis existiert, und erstellt es, wenn nicht.
## Schritt 3: Instanziieren der Präsentationsklasse
 Als nächstes müssen wir eine Instanz des`Presentation` Klasse, die unsere PowerPoint-Datei darstellt.
```java
Presentation pres = new Presentation();
```
Dadurch wird ein neues Präsentationsobjekt initialisiert, das wir zum Hinzufügen von Folien und Formen verwenden.
## Schritt 4: Zugriff auf die erste Folie
Zunächst müssen wir auf die erste Folie unserer Präsentation zugreifen. Hier fügen wir unsere Formen hinzu.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Schritt 5: Fügen Sie eine rechteckige Form hinzu
Fügen wir unserer Folie eine rechteckige Form hinzu. Dieses Rechteck wird mit einem Muster gefüllt.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Dieser Codeausschnitt fügt der Folie an der angegebenen Position und in der angegebenen Größe ein Rechteck hinzu.
## Schritt 6: Stellen Sie den Fülltyp auf Muster ein
Jetzt müssen wir den Fülltyp unseres Rechtecks auf eine Musterfüllung einstellen.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Schritt 7: Wählen Sie einen Musterstil
Aspose.Slides bietet verschiedene Musterstile. In diesem Beispiel verwenden wir das Muster „Trellis“.
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Schritt 8: Musterfarben festlegen
Wir können die Farben unseres Musters anpassen. Lassen Sie uns die Hintergrundfarbe auf Hellgrau und die Vordergrundfarbe auf Gelb einstellen.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Schritt 9: Speichern Sie die Präsentation
Nachdem wir unsere Form mit dem gewünschten Muster eingerichtet haben, müssen wir die Präsentation in einer Datei speichern.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Dadurch wird die Präsentation im angegebenen Verzeichnis unter dem Dateinamen „RectShpPatt_out.pptx“ gespeichert.
## Schritt 10: Ressourcen bereinigen
Es empfiehlt sich, das Präsentationsobjekt zu verwerfen, um Ressourcen freizugeben.
```java
if (pres != null) pres.dispose();
```
## Abschluss
Herzlichen Glückwunsch! Sie haben mithilfe von Aspose.Slides für Java erfolgreich eine Form mit einem Muster in einer PowerPoint-Folie gefüllt. Mit dieser leistungsstarken Bibliothek können Sie Präsentationen ganz einfach erstellen und bearbeiten und Ihren Projekten so eine professionelle Note verleihen.
 Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie Ihre Präsentationen mit verschiedenen Mustern verbessern und sie ansprechender und optisch ansprechender gestalten. Weitere erweiterte Funktionen und Anpassungsoptionen finden Sie unter[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API, mit der Entwickler PowerPoint-Präsentationen in Java-Anwendungen erstellen, bearbeiten und konvertieren können.
### Wie kann ich Aspose.Slides für Java erhalten?
 Sie können Aspose.Slides für Java herunterladen von[Hier](https://releases.aspose.com/slides/java/).
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion erhalten von[Hier](https://releases.aspose.com/).
### Kann ich Aspose.Slides für Java verwenden, um vorhandene Präsentationen zu bearbeiten?
Ja, mit Aspose.Slides für Java können Sie vorhandene PowerPoint-Präsentationen öffnen, bearbeiten und speichern.
### Wo erhalte ich Support für Aspose.Slides für Java?
 Unterstützung erhalten Sie vom[Aspose.Slides Support-Forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

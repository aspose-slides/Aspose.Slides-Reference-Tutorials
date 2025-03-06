---
title: Erstellen zusammengesetzter Objekte in geometrischen Formen
linktitle: Erstellen zusammengesetzter Objekte in geometrischen Formen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie in diesem umfassenden Tutorial, wie Sie mit Aspose.Slides für Java zusammengesetzte Objekte in geometrischen Formen erstellen. Perfekt für Java-Entwickler.
weight: 20
url: /de/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Hallo! Wollten Sie schon immer mit Java atemberaubende und komplexe Formen in Ihren PowerPoint-Präsentationen erstellen? Dann sind Sie hier genau richtig. In diesem Tutorial tauchen wir in die leistungsstarke Aspose.Slides-Bibliothek für Java ein, um zusammengesetzte Objekte in geometrischen Formen zu erstellen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Schritt-für-Schritt-Anleitung hilft Ihnen, in kürzester Zeit beeindruckende Ergebnisse zu erzielen. Bereit, loszulegen? Tauchen wir ein!
## Voraussetzungen
Bevor wir uns in den Code stürzen, benötigen Sie ein paar Dinge:
- Java Development Kit (JDK): Stellen Sie sicher, dass JDK 1.8 oder höher auf Ihrem Computer installiert ist.
- Integrierte Entwicklungsumgebung (IDE): Eine IDE wie IntelliJ IDEA oder Eclipse macht Ihnen das Leben leichter.
-  Aspose.Slides für Java: Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/) oder verwenden Sie Maven, um es in Ihr Projekt einzubinden.
- Grundlegende Kenntnisse in Java: Dieses Tutorial setzt grundlegende Kenntnisse in Java voraus.
## Pakete importieren
Lassen Sie uns zunächst die erforderlichen Pakete importieren, um mit Aspose.Slides für Java beginnen zu können.
```java
import com.aspose.slides.*;

```

Das Erstellen zusammengesetzter Objekte klingt vielleicht kompliziert, aber wenn Sie es in überschaubare Schritte aufteilen, werden Sie feststellen, dass es einfacher ist, als Sie denken. Wir erstellen eine PowerPoint-Präsentation, fügen eine Form hinzu und definieren und wenden dann mehrere Geometriepfade an, um eine zusammengesetzte Form zu bilden.
## Schritt 1: Richten Sie Ihr Projekt ein
 Bevor Sie Code schreiben, richten Sie Ihr Java-Projekt ein. Erstellen Sie ein neues Projekt in Ihrer IDE und schließen Sie Aspose.Slides für Java ein. Sie können die Bibliothek mit Maven hinzufügen oder die JAR-Datei von der[Aspose.Slides-Downloadseite](https://releases.aspose.com/slides/java/).
### Hinzufügen von Aspose.Slides zu Ihrem Projekt mit Maven
 Wenn Sie Maven verwenden, fügen Sie die folgende Abhängigkeit zu Ihrem`pom.xml` Datei:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## Schritt 2: Initialisieren der Präsentation
Lassen Sie uns nun eine neue PowerPoint-Präsentation erstellen. Wir beginnen mit der Initialisierung der`Presentation` Klasse.
```java
// Name der Ausgabedatei
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## Schritt 3: Erstellen Sie eine neue Form
Als Nächstes fügen wir der ersten Folie unserer Präsentation eine neue Rechteckform hinzu.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Schritt 4: Definieren Sie den ersten Geometriepfad
 Wir definieren den ersten Teil unserer zusammengesetzten Form durch die Erstellung eines`GeometryPath` und Punkte hinzuzufügen.
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## Schritt 5: Definieren Sie den zweiten Geometriepfad
Definieren Sie auf ähnliche Weise den zweiten Teil unserer zusammengesetzten Form.
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## Schritt 6: Kombinieren Sie die Geometriepfade
Kombinieren Sie die beiden Geometriepfade und legen Sie sie in der Form fest.
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie Ihre Präsentation abschließend als Datei.
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Schritt 8: Ressourcen bereinigen
Stellen Sie sicher, dass Sie alle von der Präsentation verwendeten Ressourcen freigeben.
```java
if (pres != null) pres.dispose();
```
## Abschluss
Und da haben Sie es! Sie haben erfolgreich eine zusammengesetzte Form mit Aspose.Slides für Java erstellt. Indem Sie den Prozess in einfache Schritte aufteilen, können Sie problemlos komplizierte Formen erstellen und Ihre Präsentationen verbessern. Experimentieren Sie weiter mit verschiedenen Geometriepfaden, um einzigartige Designs zu erstellen.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Konvertieren von PowerPoint-Präsentationen in Java.
### Wie installiere ich Aspose.Slides für Java?
 Sie können es mit Maven installieren oder die JAR-Datei von der[Webseite](https://releases.aspose.com/slides/java/).
### Kann ich Aspose.Slides für Java in kommerziellen Projekten verwenden?
 Ja, aber Sie müssen eine Lizenz erwerben. Weitere Informationen finden Sie auf der[Kaufseite](https://purchase.aspose.com/buy).
### Gibt es eine kostenlose Testversion?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### Wo finde ich weitere Dokumentation und Support?
 Besuche die[Dokumentation](https://reference.aspose.com/slides/java/) Und[Hilfeforum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

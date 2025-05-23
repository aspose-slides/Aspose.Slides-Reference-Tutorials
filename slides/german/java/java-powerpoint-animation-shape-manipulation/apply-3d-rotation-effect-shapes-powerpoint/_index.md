---
"description": "Erfahren Sie in diesem umfassenden Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Slides für Java 3D-Rotationseffekte auf Formen in PowerPoint anwenden."
"linktitle": "3D-Rotationseffekt auf Formen in PowerPoint anwenden"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "3D-Rotationseffekt auf Formen in PowerPoint anwenden"
"url": "/de/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 3D-Rotationseffekt auf Formen in PowerPoint anwenden

## Einführung
Sind Sie bereit, Ihre PowerPoint-Präsentationen auf das nächste Level zu heben? Mit 3D-Rotationseffekten können Sie Ihre Folien dynamischer und ansprechender gestalten. Egal, ob Sie bereits erfahrener Entwickler sind oder gerade erst anfangen – dieses Schritt-für-Schritt-Tutorial zeigt Ihnen, wie Sie mit Aspose.Slides für Java 3D-Rotationseffekte auf Formen in PowerPoint anwenden. Los geht‘s!
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es von der [Oracle-Website](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides für Java: Laden Sie die neueste Version von Aspose.Slides für Java herunter von der [Download-Link](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie zum Codieren eine IDE wie IntelliJ IDEA oder Eclipse.
4. Eine gültige Lizenz: Wenn Sie keine Lizenz haben, können Sie eine [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um die Funktionen auszuprobieren.
## Pakete importieren
Importieren wir zunächst die erforderlichen Pakete in Ihr Java-Projekt. Diese Importe helfen Ihnen bei der Handhabung von Präsentationen und Formen mit Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Schritt 1: Richten Sie Ihr Projekt ein
Bevor Sie mit dem Code beginnen, richten Sie Ihre Projektumgebung ein. Stellen Sie sicher, dass Sie Aspose.Slides für Java zu den Abhängigkeiten Ihres Projekts hinzugefügt haben.
Fügen Sie Aspose.Slides zu Ihrem Projekt hinzu:
1. Laden Sie die Aspose.Slides JAR-Dateien von der [Download-Seite](https://releases.aspose.com/slides/java/).
2. Fügen Sie diese JAR-Dateien zum Build-Pfad Ihres Projekts hinzu.
## Schritt 2: Erstellen Sie eine neue PowerPoint-Präsentation
In diesem Schritt erstellen wir eine neue PowerPoint-Präsentation.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation pres = new Presentation();
```
Dieser Codeausschnitt initialisiert ein neues Präsentationsobjekt, dem wir unsere Formen hinzufügen.
## Schritt 3: Fügen Sie eine rechteckige Form hinzu
Als Nächstes fügen wir der ersten Folie eine rechteckige Form hinzu.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Dieser Code fügt auf der ersten Folie an der angegebenen Position und in der angegebenen Größe eine rechteckige Form hinzu.
## Schritt 4: 3D-Rotation auf das Rechteck anwenden
Wenden wir nun einen 3D-Rotationseffekt auf die Rechteckform an.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Hier legen wir die Tiefe, den Kameradrehwinkel, den Kameratyp und die Beleuchtungsart fest, um unserem Rechteck ein 3D-Aussehen zu verleihen.
## Schritt 5: Eine Linienform hinzufügen
Fügen wir der Folie eine weitere Form hinzu, diesmal eine Linie.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Dieser Code platziert eine Linienform auf der Folie.
## Schritt 6: 3D-Rotation auf die Linie anwenden
Abschließend wenden wir einen 3D-Rotationseffekt auf die Linienform an.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Ähnlich wie beim Rechteck legen wir die 3D-Eigenschaften für die Linienform fest.
## Schritt 7: Speichern Sie die Präsentation
Speichern Sie die Präsentation, nachdem Sie Ihre Formen hinzugefügt und konfiguriert haben.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Dieser Code speichert Ihre Präsentation unter dem angegebenen Dateinamen im gewünschten Format.
## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für Java erfolgreich 3D-Rotationseffekte auf Formen in einer PowerPoint-Präsentation angewendet. Mit diesen Schritten erstellen Sie optisch ansprechende und dynamische Präsentationen. Weitere Anpassungsmöglichkeiten und erweiterte Funktionen finden Sie im [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/java/).
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zum programmgesteuerten Erstellen, Ändern und Bearbeiten von PowerPoint-Präsentationen.
### Kann ich Aspose.Slides für Java kostenlos testen?
Ja, Sie können eine [kostenlose Testversion](https://releases.aspose.com/) oder ein [vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um die Funktionen zu testen.
### Welchen Arten von Formen kann ich in Aspose.Slides 3D-Effekte hinzufügen?
Sie können verschiedenen Formen wie Rechtecken, Linien, Ellipsen und benutzerdefinierten Formen 3D-Effekte hinzufügen.
### Wie erhalte ich Support für Aspose.Slides für Java?
Besuchen Sie die [Support-Forum](https://forum.aspose.com/c/slides/11) um Hilfe zu erhalten und etwaige Probleme zu besprechen.
### Kann ich Aspose.Slides für Java in kommerziellen Projekten verwenden?
Ja, aber Sie müssen eine Lizenz erwerben. Sie können eine Lizenz erwerben bei [Kaufseite](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
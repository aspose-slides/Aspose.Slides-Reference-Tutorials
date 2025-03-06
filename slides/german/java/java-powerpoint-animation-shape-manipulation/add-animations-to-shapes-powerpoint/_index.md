---
title: Fügen Sie Formen in PowerPoint Animationen hinzu
linktitle: Fügen Sie Formen in PowerPoint Animationen hinzu
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: In diesem ausführlichen Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java Animationen zu Formen in PowerPoint hinzufügen. Perfekt zum Erstellen ansprechender Präsentationen.
weight: 10
url: /de/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fügen Sie Formen in PowerPoint Animationen hinzu

## Einführung
Um ansprechende Präsentationen zu erstellen, müssen Sie Formen und Text häufig animieren. Animationen können Ihre Folien dynamischer und fesselnder machen und so dafür sorgen, dass Ihr Publikum interessiert bleibt. In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens von Animationen zu Formen in einer PowerPoint-Präsentation mit Aspose.Slides für Java. Am Ende dieses Artikels können Sie mühelos professionelle Animationen erstellen.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:
1.  Aspose.Slides für Java-Bibliothek: Sie müssen die Aspose.Slides für Java-Bibliothek installiert haben. Sie können[hier herunterladen](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Computer installiert ist.
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine beliebige Java-IDE wie IntelliJ IDEA, Eclipse oder NetBeans.
4. Grundkenntnisse in Java: Dieses Tutorial setzt grundlegende Kenntnisse der Java-Programmierung voraus.
## Pakete importieren
Zu Beginn müssen Sie die erforderlichen Pakete für Aspose.Slides und andere erforderliche Java-Klassen importieren.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Schritt 1: Richten Sie Ihr Projektverzeichnis ein
Erstellen Sie zunächst ein Verzeichnis für Ihre Projektdateien.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Schritt 2: Präsentationsobjekt initialisieren
 Als nächstes instantiieren Sie den`Presentation` Klasse zur Darstellung Ihrer PowerPoint-Datei.
```java
// Instanziieren Sie die Präsentationsklasse, die PPTX darstellt
Presentation pres = new Presentation();
```
## Schritt 3: Zugriff auf die erste Folie
Greifen Sie jetzt auf die erste Folie der Präsentation zu, in der Sie die Animationen hinzufügen möchten.
```java
// Greifen Sie auf die erste Folie zu
ISlide sld = pres.getSlides().get_Item(0);
```
## Schritt 4: Fügen Sie der Folie eine Form hinzu
Fügen Sie der Folie eine rechteckige Form hinzu und fügen Sie einen Text ein.
```java
// Fügen Sie der Folie eine rechteckige Form hinzu
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Schritt 5: Einen Animationseffekt anwenden
Wenden Sie den Animationseffekt „PathFootball“ auf die Form an.
```java
// PathFootBall-Animationseffekt hinzufügen
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Schritt 6: Erstellen Sie einen interaktiven Trigger
Erstellen Sie eine Schaltflächenform, die beim Klicken die Animation auslöst.
```java
// Erstellen Sie eine „Schaltflächen“-Form, um die Animation auszulösen
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Schritt 7: Definieren Sie die interaktive Sequenz
Definieren Sie eine Effektsequenz für die Schaltfläche.
```java
// Erstellen Sie eine Effektsequenz für die Schaltfläche
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Schritt 8: Einen benutzerdefinierten Benutzerpfad hinzufügen
Fügen Sie der Form eine benutzerdefinierte Benutzerpfadanimation hinzu.
```java
// Fügen Sie einen benutzerdefinierten Benutzerpfad-Animationseffekt hinzu
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Bewegungseffekt erstellen
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Definieren Sie die Pfadpunkte
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Schritt 9: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend am gewünschten Ort.
```java
// Speichern Sie die Präsentation als PPTX-Datei
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Entsorgen des Präsentationsobjekts
if (pres != null) pres.dispose();
```
## Abschluss
Und da haben Sie es! Sie haben mithilfe von Aspose.Slides für Java erfolgreich Animationen zu Formen in einer PowerPoint-Präsentation hinzugefügt. Mit dieser leistungsstarken Bibliothek können Sie Ihre Präsentationen ganz einfach mit dynamischen Effekten verbessern und so dafür sorgen, dass Ihr Publikum bei der Sache bleibt. Denken Sie daran: Übung macht den Meister. Experimentieren Sie also weiter mit verschiedenen Effekten und Auslösern, um herauszufinden, was für Ihre Anforderungen am besten geeignet ist.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke API zum programmgesteuerten Erstellen, Ändern und Bearbeiten von PowerPoint-Präsentationen.
### Kann ich Aspose.Slides kostenlos nutzen?
 Sie können Aspose.Slides kostenlos testen mit einem[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/)Für die weitere Nutzung ist eine kostenpflichtige Lizenz erforderlich.
### Welche Java-Versionen sind mit Aspose.Slides kompatibel?
Aspose.Slides unterstützt Java SE 6 und höher.
### Wie füge ich mehreren Formen unterschiedliche Animationen hinzu?
Sie können mehreren Formen unterschiedliche Animationen hinzufügen, indem Sie die Schritte für jede Form wiederholen und nach Bedarf unterschiedliche Effekte angeben.
### Wo finde ich weitere Beispiele und Dokumentation?
 Besuche die[Dokumentation](https://reference.aspose.com/slides/java/) Und[Hilfeforum](https://forum.aspose.com/c/slides/11)für weitere Beispiele und Hilfe.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

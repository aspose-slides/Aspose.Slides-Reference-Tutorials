---
title: Äußere Schatteneffekte in Java PowerPoint anwenden
linktitle: Äußere Schatteneffekte in Java PowerPoint anwenden
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie mit unserer ausführlichen Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Slides ganz einfach äußere Schatteneffekte in Java PowerPoint-Präsentationen anwenden.
weight: 11
url: /de/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Beim Erstellen ansprechender Präsentationen müssen häufig verschiedene Effekte hinzugefügt werden, um die visuelle Attraktivität Ihrer Folien zu verbessern. Ein solcher Effekt ist der Außenschatten, der Ihre Elemente hervorstechen lässt und Ihrem Inhalt Tiefe verleiht. In diesem Tutorial werden wir den Prozess des Anwendens von Außenschatteneffekten auf Formen in einer PowerPoint-Präsentation mithilfe von Aspose.Slides für Java durchgehen.
## Voraussetzungen
Bevor wir uns in die Schritt-für-Schritt-Anleitung stürzen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Rechner installiert ist. Sie können es hier herunterladen:[Website von Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides für Java-Bibliothek: Laden Sie die neueste Version herunter von[Aspose.Slides für Java](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine IDE wie IntelliJ IDEA oder Eclipse zum Schreiben und Ausführen Ihres Java-Codes.
4.  Eine gültige Aspose-Lizenz: Sie können eine Lizenz erwerben bei[Aspose](https://purchase.aspose.com/buy) oder erhalten Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) zur Auswertung.
## Pakete importieren
Zuerst müssen Sie die erforderlichen Pakete für Aspose.Slides importieren. Dies schafft die Voraussetzung für die Nutzung der leistungsstarken Funktionen der Bibliothek.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Lassen Sie uns den Vorgang des Anwendens äußerer Schatteneffekte in überschaubare Schritte unterteilen:
## Schritt 1: Einrichten des Projektverzeichnisses
Bevor Sie mit dem Schreiben Ihres Codes beginnen, müssen Sie das Projektverzeichnis einrichten, in dem Ihre PowerPoint-Dateien gespeichert und abgerufen werden.
Stellen Sie sicher, dass Ihr Projektverzeichnis vorhanden ist. Wenn nicht, erstellen Sie es mit dem folgenden Code:
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Schritt 2: Initialisieren der Präsentation
Jetzt müssen wir die Präsentation initialisieren, wo wir unsere Formen und Effekte hinzufügen.

 Erstellen Sie eine neue Instanz des`Presentation` Klasse, mit einer neuen PowerPoint-Datei zu arbeiten.
```java
// Instanziieren einer PPTX-Klasse
Presentation pres = new Presentation();
```
## Schritt 3: Folie und Form hinzufügen
Fügen Sie als Nächstes Ihrer Präsentation eine Folie und dann eine Form hinzu, auf die Sie den Schatteneffekt anwenden.
### Verweis auf die Folie abrufen
Rufen Sie einen Verweis auf die erste Folie der Präsentation ab.
```java
// Referenz der Folie erhalten
ISlide sld = pres.getSlides().get_Item(0);
```
### Hinzufügen einer AutoForm
Fügen Sie der Folie an den angegebenen Koordinaten eine rechteckige AutoForm hinzu.
```java
// Fügen Sie eine AutoForm vom Typ „Rechteck“ hinzu
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Schritt 4: Passen Sie die Form an
Fügen Sie Ihrer Form Text hinzu und passen Sie die Fülleinstellungen an, um den Schatteneffekt besser sichtbar zu machen.
### Fügen Sie der Form einen Textrahmen hinzu
Fügen Sie Text in die Rechteckform ein.
```java
// TextFrame zum Rechteck hinzufügen
aShp.addTextFrame("Aspose TextBox");
```
### Formfüllung deaktivieren
Deaktivieren Sie die Füllung der Form, um den Textschatten hervorzuheben.
```java
// Deaktivieren Sie die Formfüllung, wenn Sie einen Schatten auf den Text bekommen möchten
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Schritt 5: Äußeren Schatteneffekt anwenden
Jetzt ist es Zeit, den äußeren Schatteneffekt auf die Form anzuwenden.
### Äußeren Schatteneffekt aktivieren
Aktivieren Sie den äußeren Schatteneffekt für die Form.
```java
// Äußeren Schatten hinzufügen und alle notwendigen Parameter einstellen
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Schattenparameter konfigurieren
Legen Sie verschiedene Eigenschaften des Schattens fest, beispielsweise Unschärferadius, Richtung, Entfernung, Ausrichtung und Farbe.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Schritt 6: Speichern Sie die Präsentation
Speichern Sie die Präsentation abschließend auf der Festplatte.
```java
//Schreiben Sie die Präsentation auf die Festplatte
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Schritt 7: Ressourcen entsorgen
Stellen Sie sicher, dass Sie durch die Entsorgung des Präsentationsobjekts Ressourcen freigeben.
```java
// Bereinigen von Ressourcen
if (pres != null) pres.dispose();
```
## Abschluss
Und da haben Sie es! Sie haben mit Aspose.Slides für Java erfolgreich einen äußeren Schatteneffekt auf eine Form in einer PowerPoint-Präsentation angewendet. Dieser Effekt kann die visuelle Attraktivität Ihrer Folien erheblich steigern und Ihren Inhalt hervorstechen lassen.
 Wenn Sie auf Probleme stoßen oder weitere Hilfe benötigen, zögern Sie nicht, sich die[Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/java/) oder besuchen Sie die[Hilfeforum](https://forum.aspose.com/c/slides/11). Viel Spaß beim Programmieren!
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen in Java-Anwendungen erstellen, bearbeiten und konvertieren können.
### Wie kann ich eine kostenlose Testversion von Aspose.Slides für Java erhalten?
 Sie können eine kostenlose Testversion herunterladen von der[Aspose-Website](https://releases.aspose.com/).
### Kann ich Aspose.Slides für Java mit jeder IDE verwenden?
Ja, Sie können Aspose.Slides für Java mit jeder Java-IDE wie IntelliJ IDEA, Eclipse oder NetBeans verwenden.
### Wie erhalte ich eine temporäre Lizenz für Aspose.Slides?
 Eine vorläufige Lizenz erhalten Sie bei der[Aspose-Website](https://purchase.aspose.com/temporary-license/).
### Wo finde ich weitere Beispiele und Dokumentation für Aspose.Slides?
 Weitere Beispiele und eine ausführliche Dokumentation finden Sie auf der[Aspose.Slides-Dokumentationsseite](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

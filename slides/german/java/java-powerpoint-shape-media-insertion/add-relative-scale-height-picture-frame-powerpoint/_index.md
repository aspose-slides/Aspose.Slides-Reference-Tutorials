---
title: Fügen Sie in PowerPoint einen Bilderrahmen mit relativer Maßstabhöhe hinzu
linktitle: Fügen Sie in PowerPoint einen Bilderrahmen mit relativer Maßstabhöhe hinzu
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Bilderrahmen mit relativer Maßstabhöhe in PowerPoint-Präsentationen einfügen und so Ihre visuellen Inhalte verbessern.
weight: 15
url: /de/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java einen Bilderrahmen mit relativer Skalenhöhe in PowerPoint-Präsentationen einfügen.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2. Aspose.Slides für die Java-Bibliothek heruntergeladen und zu Ihrem Java-Projekt hinzugefügt.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Stellen Sie zunächst sicher, dass Sie ein Verzeichnis für Ihr Projekt eingerichtet haben und Ihre Java-Umgebung richtig konfiguriert ist.
## Schritt 2: Präsentationsobjekt instanziieren
Erstellen Sie mit Aspose.Slides ein neues Präsentationsobjekt:
```java
Presentation presentation = new Presentation();
```
## Schritt 3: Zu fügendes Bild laden
Laden Sie das Bild, das Sie der Präsentation hinzufügen möchten:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Schritt 4: Bilderrahmen zur Folie hinzufügen
Fügen Sie einer Folie in der Präsentation einen Bilderrahmen hinzu:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Schritt 5: Relative Skalierungsbreite und -höhe festlegen
Legen Sie die relative Skalierungsbreite und -höhe für den Bilderrahmen fest:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Schritt 6: Präsentation speichern
Speichern Sie die Präsentation mit dem hinzugefügten Bilderrahmen:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Slides für Java ganz einfach einen Bilderrahmen mit relativer Skalierungshöhe in PowerPoint-Präsentationen einfügen. Experimentieren Sie mit verschiedenen Skalierungswerten, um das gewünschte Erscheinungsbild für Ihre Bilder zu erzielen.

## Häufig gestellte Fragen
### Kann ich mit dieser Methode einer einzelnen Folie mehrere Bilderrahmen hinzufügen?
Ja, Sie können einer Folie mehrere Bilderrahmen hinzufügen, indem Sie den Vorgang für jedes Bild wiederholen.
### Ist Aspose.Slides für Java mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides für Java ist mit verschiedenen Versionen von PowerPoint kompatibel und gewährleistet Flexibilität beim Erstellen von Präsentationen.
### Kann ich Position und Größe des Bilderrahmens individuell anpassen?
 Natürlich können Sie die Positions- und Größenparameter im`addPictureFrame` Methode, die Ihren Anforderungen entspricht.
### Unterstützt Aspose.Slides für Java andere Bildformate außer JPEG?
Ja, Aspose.Slides für Java unterstützt verschiedene Bildformate, darunter PNG, GIF, BMP und mehr.
### Gibt es ein Community-Forum oder einen Support-Kanal für Aspose.Slides-Benutzer?
Ja, Sie können das Aspose.Slides-Forum für Fragen, Diskussionen oder Hilfe zur Bibliothek besuchen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

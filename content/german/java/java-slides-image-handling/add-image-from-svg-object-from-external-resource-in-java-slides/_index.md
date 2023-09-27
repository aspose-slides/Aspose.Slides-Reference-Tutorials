---
title: Bild aus SVG-Objekt von externer Ressource in Java-Folien hinzufügen
linktitle: Bild aus SVG-Objekt von externer Ressource in Java-Folien hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides vektorbasierte SVG-Bilder aus externen Ressourcen zu Java-Folien hinzufügen. Erstellen Sie beeindruckende Präsentationen mit hochwertigen Bildern.
type: docs
weight: 12
url: /de/java/image-handling/add-image-from-svg-object-from-external-resource-in-java-slides/
---

## Einführung in das Hinzufügen eines Bilds aus einem SVG-Objekt aus einer externen Ressource in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides ein Bild aus einem SVG-Objekt (Scalable Vector Graphics) von einer externen Ressource zu Ihren Java-Folien hinzufügen. Dies kann eine wertvolle Funktion sein, wenn Sie vektorbasierte Bilder in Ihre Präsentationen integrieren möchten, um eine hochwertige visuelle Darstellung sicherzustellen. Lassen Sie uns in die Schritt-für-Schritt-Anleitung eintauchen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Java-Entwicklungsumgebung
- Aspose.Slides für Java-Bibliothek
- Eine SVG-Bilddatei (z. B. „image1.svg“)

## Einrichten des Projekts

Stellen Sie sicher, dass Ihre Java-Entwicklungsumgebung für dieses Projekt eingerichtet und bereit ist. Sie können Ihre bevorzugte integrierte Entwicklungsumgebung (IDE) für Java verwenden.

## Schritt 1: Aspose.Slides zu Ihrem Projekt hinzufügen

 Um Aspose.Slides zu Ihrem Projekt hinzuzufügen, können Sie Maven verwenden oder die Bibliothek manuell herunterladen. Weitere Informationen finden Sie in der Dokumentation unter[Aspose.Slides für Java-API-Referenzen](https://reference.aspose.com/slides/java/) Ausführliche Anweisungen zur Einbindung in Ihr Projekt finden Sie hier.

## Schritt 2: Erstellen Sie eine Präsentation

Beginnen wir mit der Erstellung einer Präsentation mit Aspose.Slides:

```java
String dataDir = "Your Document Directory";
String outPptxPath = dataDir + "presentation_external.pptx";
Presentation p = new Presentation();
```

 Stellen Sie sicher, dass Sie ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrem Projektverzeichnis.

## Schritt 3: Laden des SVG-Bildes

Wir müssen das SVG-Bild von einer externen Ressource laden. So können Sie es machen:

```java
String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
```

 In diesem Code lesen wir den SVG-Inhalt aus der Datei „image1.svg“ und erstellen eine`ISvgImage` Objekt.

## Schritt 4: SVG-Bild zur Folie hinzufügen

Fügen wir nun das SVG-Bild zu einer Folie hinzu:

```java
IPPImage ppImage = p.getImages().addImage(svgImage);
p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
```

Wir fügen das SVG-Bild als Bilderrahmen zur ersten Folie der Präsentation hinzu.

## Schritt 5: Speichern der Präsentation

Speichern Sie abschließend die Präsentation:

```java
p.save(outPptxPath, SaveFormat.Pptx);
```

Dieser Code speichert die Präsentation als „presentation_external.pptx“ im angegebenen Verzeichnis.

## Vollständiger Quellcode zum Hinzufügen eines Bilds aus einem SVG-Objekt aus einer externen Ressource in Java-Folien

```java
        // Der Pfad zum Dokumentenverzeichnis.
        String dataDir = "Your Document Directory";
        String outPptxPath = dataDir + "presentation_external.pptx";
        Presentation p = new Presentation();
        try
        {
            String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
            ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
            IPPImage ppImage = p.getImages().addImage(svgImage);
            p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
            p.save(outPptxPath, SaveFormat.Pptx);
        }
        finally
        {
            if (p != null) p.dispose();
        }
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides ein Bild aus einem SVG-Objekt von einer externen Ressource zu Java-Folien hinzufügt. Mit dieser Funktion können Sie hochwertige vektorbasierte Bilder in Ihre Präsentationen einbinden und so deren visuelle Attraktivität steigern.

## FAQs

### Wie kann ich die Position des hinzugefügten SVG-Bildes auf der Folie anpassen?

 Sie können die Position des SVG-Bildes anpassen, indem Sie die Koordinaten im ändern`addPictureFrame`Methode. Die Parameter`(0, 0)` stellen die X- und Y-Koordinaten der oberen linken Ecke des Bildrahmens dar.

### Kann ich diesen Ansatz verwenden, um mehrere SVG-Bilder zu einer einzelnen Folie hinzuzufügen?

Ja, Sie können einer einzelnen Folie mehrere SVG-Bilder hinzufügen, indem Sie den Vorgang für jedes Bild wiederholen und deren Positionen entsprechend anpassen.

### Welche Formate werden für externe SVG-Ressourcen unterstützt?

Aspose.Slides für Java unterstützt verschiedene SVG-Formate, es wird jedoch empfohlen, sicherzustellen, dass Ihre SVG-Dateien mit der Bibliothek kompatibel sind, um die besten Ergebnisse zu erzielen.

### Ist Aspose.Slides für Java mit den neuesten Java-Versionen kompatibel?

Ja, Aspose.Slides für Java ist mit den neuesten Java-Versionen kompatibel. Stellen Sie sicher, dass Sie eine kompatible Version der Bibliothek für Ihre Java-Umgebung verwenden.

### Kann ich Animationen auf SVG-Bilder anwenden, die zu Folien hinzugefügt werden?

Ja, Sie können mit Aspose.Slides Animationen auf SVG-Bilder in Ihren Folien anwenden, um dynamische Präsentationen zu erstellen.
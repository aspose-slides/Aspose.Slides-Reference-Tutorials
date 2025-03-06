---
title: OLE-Objektrahmen in PowerPoint hinzufügen
linktitle: OLE-Objektrahmen in PowerPoint hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java OLE-Objektrahmen nahtlos in PowerPoint-Präsentationen integrieren.
weight: 13
url: /de/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Das Hinzufügen eines OLE-Objektrahmens (Object Linking and Embedding) in PowerPoint-Präsentationen kann die visuelle Attraktivität und Funktionalität Ihrer Folien erheblich verbessern. Mit Aspose.Slides für Java wird dieser Prozess rationalisiert und effizient. In diesem Tutorial führen wir Sie durch die erforderlichen Schritte, um OLE-Objektrahmen nahtlos in Ihre PowerPoint-Präsentationen zu integrieren.
### Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist.
2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java von der Website herunter und installieren Sie es[Hier](https://releases.aspose.com/slides/java/).
3. Grundlegende Kenntnisse der Java-Programmierung: Machen Sie sich mit den Konzepten und der Syntax der Java-Programmierung vertraut.
## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete importieren, um die Funktionen von Aspose.Slides für Java nutzen zu können. So können Sie das tun:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Schritt 1: Richten Sie Ihre Umgebung ein
Stellen Sie sicher, dass Ihr Projekt richtig konfiguriert ist und die Aspose.Slides-Bibliothek in Ihrem Klassenpfad enthalten ist.
## Schritt 2: Präsentationsobjekt initialisieren
Erstellen Sie ein Präsentationsobjekt, um die PowerPoint-Datei darzustellen, mit der Sie arbeiten:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Instanziieren Sie die Präsentationsklasse, die PPTX darstellt
Presentation pres = new Presentation();
```
## Schritt 3: Auf Folie zugreifen und Objekt laden
Greifen Sie auf die Folie zu, der Sie den OLE-Objektrahmen hinzufügen möchten, und laden Sie die Objektdatei:
```java
ISlide sld = pres.getSlides().get_Item(0);
// Laden Sie eine Datei zum Streamen
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## Schritt 4: Eingebettetes Datenobjekt erstellen
Erstellen Sie ein Datenobjekt zum Einbetten der Datei:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## Schritt 5: OLE-Objektrahmen hinzufügen
Fügen Sie der Folie eine OLE-Objektrahmenform hinzu:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Schritt 6: Präsentation speichern
Speichern Sie die geänderte Präsentation auf der Festplatte:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Slides für Java einen OLE-Objektrahmen in PowerPoint-Präsentationen einfügen. Mit dieser leistungsstarken Funktion können Sie verschiedene Objekttypen einbetten und so die Interaktivität und visuelle Attraktivität Ihrer Folien verbessern.

## Häufig gestellte Fragen
### Kann ich mit Aspose.Slides für Java andere Objekte als Excel-Dateien einbetten?
Ja, Sie können verschiedene Objekttypen einbetten, darunter Word-Dokumente, PDF-Dateien und mehr.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides bietet Kompatibilität mit einer Vielzahl von PowerPoint-Versionen und gewährleistet so eine nahtlose Integration.
### Kann ich das Erscheinungsbild des OLE-Objektrahmens anpassen?
Auf jeden Fall! Aspose.Slides bietet umfangreiche Optionen zum Anpassen des Aussehens und Verhaltens von OLE-Objektrahmen.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
### Wo finde ich Unterstützung für Aspose.Slides für Java?
 Sie können im Aspose.Slides-Forum Unterstützung und Hilfe suchen.[Hier](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

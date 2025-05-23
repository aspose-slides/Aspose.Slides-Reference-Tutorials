---
"description": "Erfahren Sie, wie Sie OLE-Objektdaten in PowerPoint mit Aspose.Slides für Java ändern. Eine Schritt-für-Schritt-Anleitung für effiziente und einfache Aktualisierungen."
"linktitle": "Ändern Sie OLE-Objektdaten in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Ändern Sie OLE-Objektdaten in PowerPoint"
"url": "/de/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ändern Sie OLE-Objektdaten in PowerPoint

## Einführung
Das Ändern von OLE-Objektdaten in PowerPoint-Präsentationen kann eine wichtige Aufgabe sein, wenn Sie eingebettete Inhalte aktualisieren müssen, ohne jede Folie manuell bearbeiten zu müssen. Diese umfassende Anleitung führt Sie durch den Prozess mit Aspose.Slides für Java, einer leistungsstarken Bibliothek für die Bearbeitung von PowerPoint-Präsentationen. Egal, ob Sie ein erfahrener Entwickler oder Anfänger sind, dieses Tutorial ist hilfreich und leicht verständlich.
## Voraussetzungen
Bevor wir uns in den Code vertiefen, stellen wir sicher, dass Sie alles haben, was Sie für den Einstieg benötigen.
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es herunterladen von [Oracle-Site](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides für Java: Laden Sie die neueste Version von der [Aspose.Slides-Downloadseite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Sie können jede Java-IDE wie IntelliJ IDEA, Eclipse oder NetBeans verwenden.
4. Aspose.Cells für Java: Dies ist erforderlich, um die eingebetteten Daten im OLE-Objekt zu ändern. Download von [Aspose.Cells-Downloadseite](https://releases.aspose.com/cells/java/).
5. Präsentationsdatei: Halten Sie eine PowerPoint-Datei mit einem eingebetteten OLE-Objekt bereit. Für dieses Tutorial nennen wir sie `ChangeOLEObjectData.pptx`.
## Pakete importieren
Importieren wir zunächst die erforderlichen Pakete in Ihr Java-Projekt.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Lassen Sie uns den Prozess nun in einfache, überschaubare Schritte unterteilen.
## Schritt 1: Laden Sie die PowerPoint-Präsentation
Zu Beginn müssen Sie die PowerPoint-Präsentation laden, die das OLE-Objekt enthält.
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Schritt 2: Zugriff auf die Folie mit dem OLE-Objekt
Als nächstes holen Sie sich die Folie, in die das OLE-Objekt eingebettet ist.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Schritt 3: Suchen Sie das OLE-Objekt in der Folie
Durchlaufen Sie die Formen in der Folie, um das OLE-Objekt zu finden.
```java
OleObjectFrame ole = null;
// Durchlaufen aller Formen für den Ole-Rahmen
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Schritt 4: Extrahieren der eingebetteten Daten aus dem OLE-Objekt
Wenn das OLE-Objekt gefunden wird, extrahieren Sie seine eingebetteten Daten.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Schritt 5: Ändern Sie die eingebetteten Daten mit Aspose.Cells
Verwenden Sie nun Aspose.Cells, um die eingebetteten Daten zu lesen und zu ändern, bei denen es sich in diesem Fall wahrscheinlich um eine Excel-Arbeitsmappe handelt.
```java
    Workbook wb = new Workbook(msln);
    // Ändern der Arbeitsmappendaten
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Schritt 6: Speichern Sie die geänderten Daten zurück in das OLE-Objekt
Nachdem Sie die erforderlichen Änderungen vorgenommen haben, speichern Sie die geänderte Arbeitsmappe wieder im OLE-Objekt.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Schritt 7: Speichern der aktualisierten Präsentation
Speichern Sie abschließend die aktualisierte PowerPoint-Präsentation.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Abschluss
Das Aktualisieren von OLE-Objektdaten in PowerPoint-Präsentationen mit Aspose.Slides für Java ist ein unkomplizierter Vorgang, sobald Sie ihn in einfache Schritte zerlegen. Diese Anleitung führt Sie durch das Laden einer Präsentation, den Zugriff auf und die Bearbeitung eingebetteter OLE-Daten sowie das Speichern der aktualisierten Präsentation. Mit diesen Schritten können Sie eingebettete Inhalte in Ihren PowerPoint-Folien effizient und programmgesteuert verwalten und aktualisieren.
## Häufig gestellte Fragen
### Was ist ein OLE-Objekt in PowerPoint?
Ein OLE-Objekt (Object Linking and Embedding) ermöglicht das Einbetten von Inhalten aus anderen Anwendungen, beispielsweise Excel-Tabellen, in PowerPoint-Folien.
### Kann ich Aspose.Slides mit anderen Programmiersprachen verwenden?
Ja, Aspose.Slides unterstützt mehrere Sprachen, darunter .NET, Python und C++.
### Benötige ich Aspose.Cells, um OLE-Objekte in PowerPoint zu ändern?
Ja, wenn das OLE-Objekt eine Excel-Tabelle ist, benötigen Sie Aspose.Cells, um es zu ändern.
### Gibt es eine Testversion von Aspose.Slides?
Ja, Sie können eine [kostenlose Testversion](https://releases.aspose.com/) um die Funktionen von Aspose.Slides zu testen.
### Wo finde ich die Dokumentation für Aspose.Slides?
Eine ausführliche Dokumentation finden Sie auf der [Aspose.Slides-Dokumentationsseite](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
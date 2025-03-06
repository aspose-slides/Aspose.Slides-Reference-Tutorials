---
title: Zellen in PowerPoint-Tabellen mit Java aufteilen
linktitle: Zellen in PowerPoint-Tabellen mit Java aufteilen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Tabellenzellen mit Aspose.Slides für Java programmgesteuert teilen, zusammenführen und formatieren. Meistern Sie Präsentationsdesign.
weight: 11
url: /de/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie PowerPoint-Tabellen in Java mit Aspose.Slides bearbeiten. Tabellen sind eine grundlegende Komponente in Präsentationen und werden häufig verwendet, um Daten effektiv zu organisieren und zu präsentieren. Aspose.Slides bietet robuste Funktionen zum programmgesteuerten Erstellen, Ändern und Verbessern von Tabellen und bietet Flexibilität bei Design und Layout.
## Voraussetzungen
Stellen Sie vor dem Starten dieses Tutorials sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse der Java-Programmierung.
- JDK (Java Development Kit) auf Ihrem Computer installiert.
-  Aspose.Slides für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/slides/java/).
- Integrierte Entwicklungsumgebung (IDE) wie Eclipse, IntelliJ IDEA oder eine andere Ihrer Wahl.

## Pakete importieren
Um mit Aspose.Slides für Java zu arbeiten, müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Schritt 1: Einrichten der Präsentation
 Instanziieren Sie zunächst die`Presentation` Klasse, um eine neue PowerPoint-Präsentation zu erstellen.
```java
// Der Pfad zum Verzeichnis, in dem Sie die Ausgabepräsentation speichern möchten
String dataDir = "Your_Document_Directory/";
// Instanziieren Sie die Präsentationsklasse, die die PPTX-Datei darstellt
Presentation presentation = new Presentation();
```
## Schritt 2: Auf die Folie zugreifen und eine Tabelle hinzufügen
Rufen Sie die erste Folie auf und fügen Sie ihr eine Tabellenform hinzu. Definieren Sie Spalten mit Breiten und Zeilen mit Höhen.
```java
try {
    // Zur ersten Folie
    ISlide slide = presentation.getSlides().get_Item(0);
    // Definieren Sie Spalten mit Breiten und Zeilen mit Höhen
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // Tabellenform zur Folie hinzufügen
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Schritt 3: Rahmenformat für jede Zelle festlegen
Gehen Sie jede Zelle in der Tabelle durch und legen Sie die Rahmenformatierung fest (Farbe, Breite usw.).
```java
    // Rahmenformat für jede Zelle festlegen
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // Legen Sie eine ähnliche Formatierung für die anderen Ränder fest (unten, links, rechts).
            // ...
        }
    }
```
## Schritt 4: Zellen zusammenführen
Verbinden Sie die Zellen in der Tabelle nach Bedarf. Verbinden Sie beispielsweise die Zellen (1,1) mit (2,1) und (1,2) mit (2,2).
```java
    // Zellen verbinden (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // Zellen verbinden (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Schritt 5: Zellen teilen
Teilen Sie eine bestimmte Zelle basierend auf der Breite in mehrere Zellen auf.
```java
    // Zelle teilen (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## Schritt 6: Speichern der Präsentation
Speichern Sie die geänderte Präsentation auf der Festplatte.
```java
    // PPTX auf die Festplatte schreiben
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // Entsorgen Sie das Präsentationsobjekt
    if (presentation != null) presentation.dispose();
}
```

## Abschluss
Die programmgesteuerte Bearbeitung von PowerPoint-Tabellen mit Aspose.Slides für Java bietet eine leistungsstarke Möglichkeit, Präsentationen effizient anzupassen. In diesem Tutorial haben Sie gelernt, wie Sie Zellen teilen, Zellen zusammenführen und Zellränder dynamisch festlegen, wodurch Sie visuell ansprechende Präsentationen programmgesteuert erstellen können.

## Häufig gestellte Fragen
### Wo finde ich die Dokumentation für Aspose.Slides für Java?
 Die Dokumentation finden Sie[Hier](https://reference.aspose.com/slides/java/).
### Wie kann ich Aspose.Slides für Java herunterladen?
 Sie können es herunterladen von[dieser Link](https://releases.aspose.com/slides/java/).
### Gibt es eine kostenlose Testversion für Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion erhalten von[Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides für Java?
 Sie können Unterstützung vom Aspose.Slides-Forum erhalten[Hier](https://forum.aspose.com/c/slides/11).
### Kann ich eine temporäre Lizenz für Aspose.Slides für Java erhalten?
 Ja, Sie können eine vorläufige Lizenz erhalten bei[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Diagrammmarkierungsoptionen für Datenpunkte in Java-Folien
linktitle: Diagrammmarkierungsoptionen für Datenpunkte in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Optimieren Sie Ihre Java-Folien mit benutzerdefinierten Diagrammmarkierungsoptionen. Erfahren Sie, wie Sie Datenpunkte mit Aspose.Slides für Java visuell verbessern. Entdecken Sie Schritt-für-Schritt-Anleitungen und FAQs.
type: docs
weight: 14
url: /de/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Einführung in Diagrammmarkierungsoptionen für Datenpunkte in Java-Folien

Wenn es darum geht, wirkungsvolle Präsentationen zu erstellen, kann die Möglichkeit, Diagrammmarkierungen an Datenpunkten anzupassen und zu bearbeiten, den entscheidenden Unterschied ausmachen. Mit Aspose.Slides für Java können Sie Ihre Diagramme in dynamische und visuell ansprechende Elemente verwandeln.

## Voraussetzungen

Bevor wir uns in den Codierungsteil stürzen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java-Entwicklungsumgebung
- Aspose.Slides für die Java-Bibliothek
- Eine integrierte Java-Entwicklungsumgebung (IDE)
- Beispiel eines Präsentationsdokuments (z. B. „Test.pptx“)

## Schritt 1: Einrichten der Umgebung

Stellen Sie zunächst sicher, dass Sie die erforderlichen Tools installiert und bereit haben. Erstellen Sie ein Java-Projekt in Ihrer IDE und importieren Sie die Aspose.Slides für Java-Bibliothek.

## Schritt 2: Laden der Präsentation

Laden Sie zunächst Ihr Beispielpräsentationsdokument. Im bereitgestellten Code gehen wir davon aus, dass das Dokument den Namen „Test.pptx“ trägt.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Schritt 3: Erstellen eines Diagramms

Lassen Sie uns nun ein Diagramm in der Präsentation erstellen. In diesem Beispiel verwenden wir ein Liniendiagramm mit Markierungen.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Schritt 4: Arbeiten mit Diagrammdaten

Um Diagrammdaten zu bearbeiten, müssen wir auf die Diagrammdaten-Arbeitsmappe zugreifen und die Datenreihe vorbereiten. Wir löschen die Standardreihe und fügen unsere benutzerdefinierten Daten hinzu.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Schritt 5: Benutzerdefinierte Markierungen hinzufügen

Jetzt kommt der spannende Teil – das Anpassen der Markierungen an Datenpunkten. In diesem Beispiel verwenden wir Bilder als Markierungen.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Hinzufügen benutzerdefinierter Markierungen zu Datenpunkten
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Wiederholen Sie dies für andere Datenpunkte.
// ...

// Ändern der Markierungsgröße einer Diagrammreihe
series.getMarker().setSize(15);
```

## Schritt 6: Speichern der Präsentation

Nachdem Sie Ihre Diagrammmarkierungen angepasst haben, speichern Sie die Präsentation, um die Änderungen in Aktion zu sehen.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode für Diagrammmarkierungsoptionen für Datenpunkte in Java-Folien

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Erstellen des Standarddiagramms
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Abrufen des Standardarbeitsblattindexes für Diagrammdaten
int defaultWorksheetIndex = 0;
//Abrufen des Arbeitsblatts mit den Diagrammdaten
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Demoserie löschen
chart.getChartData().getSeries().clear();
//Neue Serie hinzufügen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Stellen Sie das Bild ein
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Stellen Sie das Bild ein
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Erste Chartserie erstellen
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Fügen Sie dort einen neuen Punkt (1:3) hinzu.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Ändern der Diagrammreihenmarkierung
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Abschluss

Mit Aspose.Slides für Java können Sie Ihre Präsentationen verbessern, indem Sie Diagrammmarkierungen an Datenpunkten anpassen. Auf diese Weise können Sie visuell beeindruckende und informative Folien erstellen, die Ihr Publikum fesseln.

## Häufig gestellte Fragen

### Wie kann ich die Markierungsgröße für Datenpunkte ändern?

 Um die Markierungsgröße für Datenpunkte zu ändern, verwenden Sie die`series.getMarker().setSize()` Methode und geben Sie die gewünschte Größe als Argument an.

### Kann ich Bilder als benutzerdefinierte Markierungen verwenden?

 Ja, Sie können Bilder als benutzerdefinierte Markierungen für Datenpunkte verwenden. Stellen Sie den Fülltyp auf`FillType.Picture` und geben Sie das Bild an, das Sie verwenden möchten.

### Ist Aspose.Slides für Java zum Erstellen dynamischer Diagramme geeignet?

Auf jeden Fall! Aspose.Slides für Java bietet umfangreiche Funktionen zum Erstellen dynamischer und interaktiver Diagramme in Ihren Präsentationen.

### Kann ich mit Aspose.Slides andere Aspekte des Diagramms anpassen?

Ja, Sie können mit Aspose.Slides für Java verschiedene Aspekte des Diagramms anpassen, einschließlich Titel, Achsen, Datenbeschriftungen und mehr.

### Wo kann ich auf die Dokumentation und Downloads zu Aspose.Slides für Java zugreifen?

 Die Dokumentation finden Sie unter[Hier](https://reference.aspose.com/slides/java/) und laden Sie die Bibliothek herunter unter[Hier](https://releases.aspose.com/slides/java/).
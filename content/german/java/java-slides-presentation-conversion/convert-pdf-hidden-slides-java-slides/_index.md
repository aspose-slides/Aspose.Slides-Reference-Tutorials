---
title: Mit ausgeblendeten Folien in Java Slides in PDF konvertieren
linktitle: Mit ausgeblendeten Folien in Java Slides in PDF konvertieren
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java in PDF mit versteckten Folien konvertieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Quellcode zur nahtlosen PDF-Erstellung.
type: docs
weight: 27
url: /de/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Einführung zum Konvertieren einer PowerPoint-Präsentation in PDF mit ausgeblendeten Folien mithilfe von Aspose.Slides für Java

In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie eine PowerPoint-Präsentation mit Aspose.Slides für Java in PDF konvertieren und dabei versteckte Folien beibehalten. Versteckte Folien sind solche, die während einer normalen Präsentation nicht angezeigt werden, aber in die PDF-Ausgabe aufgenommen werden können. Wir stellen Ihnen den Quellcode und detaillierte Anweisungen zur Erledigung dieser Aufgabe zur Verfügung.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für Java-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihrem Java-Projekt eingerichtet haben. Sie können sie von der[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).

2. Java-Entwicklungsumgebung: Auf Ihrem System sollte eine Java-Entwicklungsumgebung installiert sein.

## Schritt 1: Aspose.Slides für Java importieren

Zuerst müssen Sie die Aspose.Slides-Bibliothek in Ihr Java-Projekt importieren. Stellen Sie sicher, dass Sie die Bibliothek zum Build-Pfad Ihres Projekts hinzugefügt haben.

```java
import com.aspose.slides.*;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

 Laden Sie zunächst die PowerPoint-Präsentation, die Sie in PDF konvertieren möchten. Ersetzen Sie`"Your Document Directory"` Und`"HiddingSlides.pptx"` mit dem entsprechenden Dateipfad.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Schritt 3: PDF-Optionen konfigurieren

 Konfigurieren Sie die PDF-Optionen, um versteckte Folien in die PDF-Ausgabe einzuschließen. Sie können dies tun, indem Sie die`setShowHiddenSlides` Eigentum der`PdfOptions` Klasse zu`true`.

```java
// Instanziieren der PdfOptions-Klasse
PdfOptions pdfOptions = new PdfOptions();
// Geben Sie an, dass das generierte Dokument ausgeblendete Folien enthalten soll
pdfOptions.setShowHiddenSlides(true);
```

## Schritt 4: Speichern Sie die Präsentation als PDF

 Speichern Sie die Präsentation nun mit den angegebenen Optionen als PDF-Datei. Ersetzen Sie`"PDFWithHiddenSlides_out.pdf"` durch den gewünschten Ausgabedateinamen.

```java
// Speichern Sie die Präsentation mit den angegebenen Optionen als PDF
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Schritt 5: Ressourcen bereinigen

Denken Sie daran, die von der Präsentation verwendeten Ressourcen freizugeben, wenn Sie damit fertig sind.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Vollständiger Quellcode für die Konvertierung in PDF mit versteckten Folien in Java Slides

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instanziieren der PdfOptions-Klasse
	PdfOptions pdfOptions = new PdfOptions();
	// Geben Sie an, dass das generierte Dokument ausgeblendete Folien enthalten soll
	pdfOptions.setShowHiddenSlides(true);
	// Speichern Sie die Präsentation mit den angegebenen Optionen als PDF
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In dieser umfassenden Anleitung haben Sie gelernt, wie Sie mit Aspose.Slides für Java eine PowerPoint-Präsentation in PDF konvertieren und dabei versteckte Folien beibehalten. Wir haben Ihnen ein Schritt-für-Schritt-Tutorial sowie den erforderlichen Quellcode zur Verfügung gestellt, damit Sie diese Aufgabe problemlos erledigen können.

## Häufig gestellte Fragen

### Wie kann ich Folien in einer PowerPoint-Präsentation ausblenden?

Um eine Folie in einer PowerPoint-Präsentation auszublenden, gehen Sie folgendermaßen vor:
1. Wählen Sie in der Foliensortieransicht die Folie aus, die Sie ausblenden möchten.
2. Klicken Sie mit der rechten Maustaste auf die ausgewählte Folie.
3. Wählen Sie „Folie ausblenden“ aus dem Kontextmenü.

### Kann ich versteckte Folien in Aspose.Slides für Java programmgesteuert einblenden?

 Ja, Sie können versteckte Folien in Aspose.Slides für Java programmgesteuert wieder einblenden, indem Sie die`Hidden` Eigentum der`Slide` Klasse zu`false`. Hier ist ein Beispiel:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Ersetzen Sie slideIndex durch den Index der ausgeblendeten Folie.
slide.setHidden(false);
```

### Wie lade ich Aspose.Slides für Java herunter?

Sie können Aspose.Slides für Java von der Aspose-Website herunterladen. Besuchen Sie die[Aspose.Slides für Java-Downloadseite](https://releases.aspose.com/slides/java/) um die neueste Version zu erhalten.
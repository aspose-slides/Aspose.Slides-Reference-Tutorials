---
title: Konvertieren Sie die Notizen-Folienansicht in Java Slides in PDF
linktitle: Konvertieren Sie die Notizen-Folienansicht in Java Slides in PDF
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Notizen mithilfe von Aspose.Slides für Java in PDFs konvertieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Quellcode.
weight: 16
url: /de/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung zum Konvertieren der Notes-Folienansicht in PDF in Java Slides

In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PowerPoint-Präsentation mit Notizen-Folienansicht in ein PDF mithilfe der Aspose.Slides für Java-Bibliothek. Diese Bibliothek bietet leistungsstarke Funktionen für die Arbeit mit PowerPoint-Präsentationen in Java.

## Voraussetzungen
1. Java Development Kit (JDK) installiert.
2. Aspose.Slides für die Java-Bibliothek zu Ihrem Projekt hinzugefügt.

## Schritt 1: Erforderliche Klassen importieren
Um zu beginnen, müssen Sie die erforderlichen Klassen aus der Aspose.Slides-Bibliothek importieren. Hier ist der Code dazu:

```java
import com.aspose.slides.*;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation
 Sie sollten Ihre PowerPoint-Präsentationsdatei bereit haben. Ersetzen`"Your Document Directory"` mit dem Pfad zum Verzeichnis, in dem sich Ihre Präsentationsdatei befindet. Hier ist der Code zum Laden der Präsentation:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Schritt 3: PDF-Optionen konfigurieren
Konfigurieren wir nun die PDF-Exportoptionen. Insbesondere setzen wir die Notizenposition auf „BottomFull“, um Notizen unter den Folien in das PDF einzuschließen. Hier ist der Code:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Sie können weitere PDF-Optionen entsprechend Ihren Anforderungen anpassen.

## Schritt 4: Speichern Sie die Präsentation als PDF mit Notizen
 Zum Schluss speichern wir die Präsentation als PDF-Datei, einschließlich der Notizen. Sie können den Namen der Ausgabedatei angeben (z. B.`"Pdf_Notes_out.pdf"`) und wählen Sie das Format (`SaveFormat.Pdf`). Hier ist der Code dafür:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Schritt 5: Ressourcen bereinigen
Vergessen Sie nicht, die Ressourcen freizugeben, wenn Sie mit der Präsentation fertig sind:

```java
if (presentation != null) presentation.dispose();
```

## Vollständiger Quellcode zum Konvertieren der Notizen-Folienansicht in PDF in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Speichern der Präsentation als PDF-Notizen
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man PowerPoint-Präsentationen mit Notizen-Folienansichten mithilfe der Aspose.Slides-Bibliothek für Java in PDFs konvertiert. Wir sind einer Schritt-für-Schritt-Anleitung mit Quellcode gefolgt, um diese Konvertierung durchzuführen. Hier sind die wichtigsten Erkenntnisse:

## Häufig gestellte Fragen

### Wie ändere ich die Position der Notizen im PDF?

 Sie können die Position der Notizen im PDF ändern, indem Sie die`setNotesPosition` Methodenargument. Sie können es beispielsweise auf`NotesPositions.RightFull` um Notizen auf der rechten Seite der Folien zu positionieren.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Kann ich den PDF-Export weiter anpassen?

 Ja, Sie können den PDF-Export anpassen, indem Sie verschiedene Optionen im`PdfOptions` Objekt. Sie können beispielsweise Qualität, Komprimierung und andere Parameter nach Ihren Wünschen einstellen.

### Wie kann ich Aspose.Slides für Java erhalten?

 Sie können Aspose.Slides für Java von der Website unter herunterladen.[Hier](https://releases.aspose.com/slides/java/).

### Gibt es Lizenzanforderungen für die Verwendung von Aspose.Slides?

Ja, für die kommerzielle Nutzung von Aspose.Slides ist eine gültige Lizenz erforderlich. Sie können eine Lizenz von der Aspose-Website erhalten.

### Wo finde ich weitere Dokumentation und Beispiele?

 Ausführliche Dokumentation und Beispiele für Aspose.Slides für Java finden Sie unter[Hier](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

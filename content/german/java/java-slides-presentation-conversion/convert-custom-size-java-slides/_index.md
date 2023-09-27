---
title: Konvertieren Sie mit benutzerdefinierter Größe in Java-Folien
linktitle: Konvertieren Sie mit benutzerdefinierter Größe in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java in TIFF-Bilder mit benutzerdefinierter Größe konvertieren. Schritt-für-Schritt-Anleitung mit Codebeispielen für Entwickler.
type: docs
weight: 31
url: /de/java/presentation-conversion/convert-custom-size-java-slides/
---

## Einführung in die Konvertierung mit benutzerdefinierter Größe in Java-Folien

In diesem Artikel erfahren Sie, wie Sie PowerPoint-Präsentationen mithilfe der Aspose.Slides für Java-API in TIFF-Bilder mit benutzerdefinierter Größe konvertieren. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Dateien zu arbeiten. Wir gehen Schritt für Schritt vor und stellen Ihnen den notwendigen Java-Code zur Verfügung, um diese Aufgabe zu erfüllen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) installiert
- Aspose.Slides für Java-Bibliothek

 Sie können die Aspose.Slides für Java-Bibliothek von der Website herunterladen:[Laden Sie Aspose.Slides für Java herunter](https://releases.aspose.com/slides/java/)

## Schritt 1: Importieren Sie die Aspose.Slides-Bibliothek

Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek in Ihr Java-Projekt importieren. So können Sie es machen:

```java
// Fügen Sie die erforderliche Importanweisung hinzu
import com.aspose.slides.*;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

 Als Nächstes müssen Sie die PowerPoint-Präsentation laden, die Sie in ein TIFF-Bild konvertieren möchten. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei.

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Schritt 3: TIFF-Konvertierungsoptionen festlegen

Lassen Sie uns nun die Optionen für die TIFF-Konvertierung festlegen. Wir geben den Komprimierungstyp, die DPI (Punkte pro Zoll), die Bildgröße und die Position der Notizen an. Sie können diese Optionen entsprechend Ihren Anforderungen anpassen.

```java
// Instanziieren Sie die TiffOptions-Klasse
TiffOptions opts = new TiffOptions();

// Komprimierungstyp einstellen
opts.setCompressionType(TiffCompressionTypes.Default);

// Bild-DPI einstellen
opts.setDpiX(200);
opts.setDpiY(100);

// Bildgröße festlegen
opts.setImageSize(new Dimension(1728, 1078));

// Legen Sie die Position der Notizen fest
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Schritt 4: Als TIFF speichern

Wenn alle Optionen konfiguriert sind, können Sie die Präsentation nun als TIFF-Bild mit den angegebenen Einstellungen speichern.

```java
// Speichern Sie die Präsentation im TIFF-Format mit der angegebenen Bildgröße
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Vollständiger Quellcode zum Konvertieren mit benutzerdefinierter Größe in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Instanziieren Sie die TiffOptions-Klasse
	TiffOptions opts = new TiffOptions();
	// Komprimierungstyp einstellen
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Komprimierungsarten
	// Standard – Gibt das Standardkomprimierungsschema (LZW) an.
	// Keine – Gibt keine Komprimierung an.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Die Tiefe hängt vom Komprimierungstyp ab und kann nicht manuell eingestellt werden.
	// Die Auflösungseinheit ist immer „2“ (Punkte pro Zoll).
	// Bild-DPI einstellen
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Bildgröße festlegen
	opts.setImageSize(new Dimension(1728, 1078));
	// Speichern Sie die Präsentation im TIFF-Format mit der angegebenen Bildgröße
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

Glückwunsch! Sie haben eine PowerPoint-Präsentation mit Aspose.Slides für Java erfolgreich in ein TIFF-Bild mit benutzerdefinierter Größe konvertiert. Dies kann eine wertvolle Funktion sein, wenn Sie für verschiedene Zwecke hochwertige Bilder aus Ihren Präsentationen generieren müssen.

## FAQs

### Wie kann ich den Komprimierungstyp für das TIFF-Bild ändern?

 Sie können den Komprimierungstyp ändern, indem Sie die Datei ändern`setCompressionType` Methode in der`TiffOptions` Klasse. Es stehen verschiedene Komprimierungstypen zur Verfügung, z. B. Standard, Keine, CCITT3, CCITT4, LZW und RLE.

### Kann ich die DPI (Punkte pro Zoll) des TIFF-Bildes anpassen?

Ja, Sie können die DPI mithilfe von anpassen`setDpiX` Und`setDpiY` Methoden in der`TiffOptions` Klasse. Stellen Sie einfach die gewünschten Werte ein, um die Bildauflösung zu steuern.

### Welche Optionen stehen für die Position von Notizen im TIFF-Bild zur Verfügung?

 Die Position der Notizen im TIFF-Bild kann mit konfiguriert werden`setNotesPosition` Methode mit Optionen wie BottomFull, BottomTruncated und SlideOnly. Wählen Sie diejenige aus, die Ihren Anforderungen am besten entspricht.

### Ist es möglich, eine benutzerdefinierte Bildgröße für die TIFF-Konvertierung anzugeben?

 Absolut! Sie können eine benutzerdefinierte Bildgröße festlegen, indem Sie verwenden`setImageSize` Methode in der`TiffOptions` Klasse. Geben Sie die gewünschten Abmessungen (Breite und Höhe) für das Ausgabebild an.

### Wo finde ich weitere Informationen zu Aspose.Slides für Java?

 Eine ausführliche Dokumentation und zusätzliche Informationen zu Aspose.Slides für Java finden Sie in der Dokumentation:[Aspose.Slides für Java API-Referenz](https://reference.aspose.com/slides/java/).
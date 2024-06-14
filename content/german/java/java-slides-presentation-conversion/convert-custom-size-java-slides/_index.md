---
title: Mit benutzerdefinierter Größe in Java-Folien konvertieren
linktitle: Mit benutzerdefinierter Größe in Java-Folien konvertieren
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java in TIFF-Bilder mit benutzerdefinierter Größe konvertieren. Schritt-für-Schritt-Anleitung mit Codebeispielen für Entwickler.
type: docs
weight: 31
url: /de/java/presentation-conversion/convert-custom-size-java-slides/
---

## Einführung in die Konvertierung mit benutzerdefinierter Größe in Java-Folien

In diesem Artikel erfahren Sie, wie Sie PowerPoint-Präsentationen mithilfe der Aspose.Slides für Java-API in TIFF-Bilder mit benutzerdefinierter Größe konvertieren. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Entwickler programmgesteuert mit PowerPoint-Dateien arbeiten können. Wir gehen Schritt für Schritt vor und stellen Ihnen den erforderlichen Java-Code zur Verfügung, um diese Aufgabe zu erfüllen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) installiert
- Aspose.Slides für Java-Bibliothek

 Sie können die Aspose.Slides-Bibliothek für Java von der Website herunterladen:[Laden Sie Aspose.Slides für Java herunter](https://releases.aspose.com/slides/java/)

## Schritt 1: Aspose.Slides-Bibliothek importieren

Um zu beginnen, müssen Sie die Aspose.Slides-Bibliothek in Ihr Java-Projekt importieren. So können Sie das tun:

```java
// Fügen Sie die erforderliche Importanweisung hinzu
import com.aspose.slides.*;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

 Als nächstes müssen Sie die PowerPoint-Präsentation laden, die Sie in ein TIFF-Bild konvertieren möchten. Ersetzen Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrer Präsentationsdatei.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Schritt 3: TIFF-Konvertierungsoptionen festlegen

Legen wir nun die Optionen für die TIFF-Konvertierung fest. Wir geben den Komprimierungstyp, DPI (Punkte pro Zoll), Bildgröße und Notizenposition an. Sie können diese Optionen nach Ihren Anforderungen anpassen.

```java
// Instanziieren der TiffOptions-Klasse
TiffOptions opts = new TiffOptions();

// Komprimierungstyp festlegen
opts.setCompressionType(TiffCompressionTypes.Default);

// Einstellen der Bild-DPI
opts.setDpiX(200);
opts.setDpiY(100);

// Bildgröße festlegen
opts.setImageSize(new Dimension(1728, 1078));

// Notizenposition festlegen
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Schritt 4: Als TIFF speichern

Nachdem Sie alle Optionen konfiguriert haben, können Sie die Präsentation nun mit den angegebenen Einstellungen als TIFF-Bild speichern.

```java
// Speichern Sie die Präsentation im TIFF-Format mit der angegebenen Bildgröße.
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Vollständiger Quellcode zum Konvertieren mit benutzerdefinierter Größe in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Instanziieren der TiffOptions-Klasse
	TiffOptions opts = new TiffOptions();
	// Komprimierungstyp festlegen
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Komprimierungstypen
	// Standard – Gibt das Standardkomprimierungsschema (LZW) an.
	// Keine – Gibt keine Komprimierung an.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Die Tiefe hängt von der Komprimierungsart ab und kann nicht manuell eingestellt werden.
	// Die Auflösungseinheit ist immer gleich „2“ (dots per inch)
	// Einstellen der Bild-DPI
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Bildgröße festlegen
	opts.setImageSize(new Dimension(1728, 1078));
	// Speichern Sie die Präsentation im TIFF-Format mit der angegebenen Bildgröße.
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben eine PowerPoint-Präsentation mit Aspose.Slides für Java erfolgreich in ein TIFF-Bild mit benutzerdefinierter Größe konvertiert. Dies kann eine wertvolle Funktion sein, wenn Sie für verschiedene Zwecke hochwertige Bilder aus Ihren Präsentationen erstellen müssen.

## Häufig gestellte Fragen

### Wie kann ich die Komprimierungsart für das TIFF-Bild ändern?

 Sie können den Komprimierungstyp ändern, indem Sie die`setCompressionType` Methode in der`TiffOptions` Klasse. Es stehen verschiedene Komprimierungstypen zur Verfügung, z. B. Standard, Keine, CCITT3, CCITT4, LZW und RLE.

### Kann ich die DPI (Punkte pro Zoll) des TIFF-Bildes anpassen?

Ja, Sie können die DPI anpassen, indem Sie die`setDpiX` Und`setDpiY` Methoden in der`TiffOptions` Klasse. Stellen Sie einfach die gewünschten Werte ein, um die Bildauflösung zu steuern.

### Welche Optionen stehen für die Notizenposition im TIFF-Bild zur Verfügung?

 Die Position der Notizen im TIFF-Bild kann über die`setNotesPosition` Methode mit Optionen wie BottomFull, BottomTruncated und SlideOnly. Wählen Sie die Methode aus, die Ihren Anforderungen am besten entspricht.

### Ist es möglich, für die TIFF-Konvertierung eine benutzerdefinierte Bildgröße anzugeben?

 Absolut! Sie können eine benutzerdefinierte Bildgröße festlegen, indem Sie`setImageSize` Methode in der`TiffOptions` Klasse. Geben Sie die gewünschten Abmessungen (Breite und Höhe) für das Ausgabebild an.

### Wo finde ich weitere Informationen zu Aspose.Slides für Java?

 Ausführliche Dokumentation und weitere Informationen zu Aspose.Slides für Java finden Sie in der Dokumentation:[Aspose.Slides für Java API-Referenz](https://reference.aspose.com/slides/java/).
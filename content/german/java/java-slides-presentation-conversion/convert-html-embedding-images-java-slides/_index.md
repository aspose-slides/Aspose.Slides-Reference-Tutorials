---
title: Konvertieren Sie HTML-Einbettungsbilder in Java-Folien
linktitle: Konvertieren Sie HTML-Einbettungsbilder in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Konvertieren Sie PowerPoint mit eingebetteten Bildern in HTML. Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.Slides für Java. Erfahren Sie, wie Sie Präsentationskonvertierungen in Java mühelos automatisieren.
type: docs
weight: 11
url: /de/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

## Einführung in die Konvertierung von HTML-Einbettungsbildern in Java-Folien

In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess der Konvertierung einer PowerPoint-Präsentation in ein HTML-Dokument und gleichzeitiger Einbettung von Bildern mit Aspose.Slides für Java. In diesem Tutorial wird davon ausgegangen, dass Sie Ihre Entwicklungsumgebung bereits eingerichtet und die Aspose.Slides für Java-Bibliothek installiert haben.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1.  Aspose.Slides für Java-Bibliothek installiert. Sie können es herunterladen unter[Hier](https://downloads.aspose.com/slides/java).

2. Eine PowerPoint-Präsentationsdatei (PPTX-Format), die Sie in HTML konvertieren möchten.

3. Einrichtung einer Java-Entwicklungsumgebung.

## Schritt 1: Erforderliche Bibliotheken importieren

Zunächst müssen Sie die erforderlichen Bibliotheken und Klassen für Ihr Java-Projekt importieren.

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

 Als Nächstes laden Sie die PowerPoint-Präsentation, die Sie in HTML konvertieren möchten. Unbedingt austauschen`presentationName` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## Schritt 3: Konfigurieren Sie die HTML-Konvertierungsoptionen

Jetzt konfigurieren Sie die HTML-Konvertierungsoptionen. In diesem Beispiel betten wir Bilder in das HTML-Dokument ein und geben das Ausgabeverzeichnis für externe Bilder an.

```java
Html5Options options = new Html5Options();
//Erzwingen Sie, dass Bilder nicht im HTML5-Dokument gespeichert werden
options.setEmbedImages(true); // Auf „true“ setzen, um Bilder einzubetten
// Legen Sie den Pfad für externe Bilder fest (falls erforderlich)
options.setOutputPath("path/to/output/directory/");
```

## Schritt 4: Erstellen Sie das Ausgabeverzeichnis

Erstellen Sie vor dem Speichern des HTML-Dokuments das Ausgabeverzeichnis, falls es noch nicht vorhanden ist.

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## Schritt 5: Speichern Sie die Präsentation als HTML

Speichern Sie nun die Präsentation im HTML5-Format mit den angegebenen Optionen.

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## Schritt 6: Ressourcen bereinigen

Vergessen Sie nicht, das Präsentationsobjekt zu entsorgen, um alle zugewiesenen Ressourcen freizugeben.

```java
if (pres != null) {
    pres.dispose();
}
```

## Vollständiger Quellcode zum Konvertieren von HTML-Einbettungsbildern in Java-Folien

```java
// Pfad zur Quellenpräsentation
String presentationName = RunExamples.getDataDir_Conversion() + "PresentationDemo.pptx";
// Pfad zum HTML-Dokument
String outFilePath = RunExamples.getOutPath() + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	//Erzwingen Sie, dass Bilder nicht im HTML5-Dokument gespeichert werden
	options.setEmbedImages(false);
	// Pfad für externe Bilder festlegen
	options.setOutputPath(outFilePath);
	// Erstellen Sie ein Verzeichnis für das Ausgabe-HTML-Dokument
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// Präsentation im HTML5-Format speichern.
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## Abschluss

In dieser umfassenden Anleitung haben wir gelernt, wie man mit Aspose.Slides für Java eine PowerPoint-Präsentation in ein HTML-Dokument umwandelt und gleichzeitig Bilder einbettet. Wenn Sie die Schritt-für-Schritt-Anleitung befolgen, können Sie diese Funktionalität nahtlos in Ihre Java-Anwendungen integrieren und Ihre Dokumentkonvertierungsprozesse verbessern.

## FAQs

### Wie ändere ich den Namen der Ausgabedatei?

 Sie können den Namen der Ausgabedatei ändern, indem Sie das Argument in ändern`pres.save()` Methode.

### Kann ich die HTML-Vorlage anpassen?

Ja, Sie können die HTML-Vorlage anpassen, indem Sie die von Aspose.Slides generierten HTML- und CSS-Dateien ändern. Sie finden sie im Ausgabeverzeichnis.

### Wie gehe ich mit Fehlern bei der Konvertierung um?

Sie können den Konvertierungscode in einen Try-Catch-Block einschließen, um Ausnahmen zu behandeln, die während des Konvertierungsprozesses auftreten können.

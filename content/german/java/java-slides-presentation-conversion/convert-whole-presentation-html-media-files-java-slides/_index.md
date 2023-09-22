---
title: Konvertieren Sie die gesamte Präsentation mit Mediendateien in Java Slides in HTML
linktitle: Konvertieren Sie die gesamte Präsentation mit Mediendateien in Java Slides in HTML
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Präsentationen mit Mediendateien mithilfe von Java Slides in HTML konvertieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung mit Aspose.Slides für Java API.
type: docs
weight: 30
url: /de/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

## Einführung in die Konvertierung ganzer Präsentationen in HTML mit Mediendateien in Java Slides

Im heutigen digitalen Zeitalter ist die Konvertierung von Präsentationen in verschiedene Formate, einschließlich HTML, eine häufige Anforderung. Java-Entwickler stehen oft vor dieser Herausforderung. Glücklicherweise kann diese Aufgabe mit der Aspose.Slides für Java-API effizient erledigt werden. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Java Slides eine ganze Präsentation in HTML konvertieren und gleichzeitig Mediendateien beibehalten.

## Voraussetzungen

Bevor wir uns mit dem Codierungsaspekt befassen, stellen wir sicher, dass alles richtig eingerichtet ist:

- Java Development Kit (JDK): Stellen Sie sicher, dass das JDK auf Ihrem System installiert ist.
-  Aspose.Slides für Java: Sie müssen die Aspose.Slides für Java-API installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Notwendige Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete importieren. Diese Pakete stellen die für unsere Aufgabe erforderlichen Klassen und Methoden bereit.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## Schritt 2: Geben Sie das Dokumentverzeichnis an

 Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis, in dem sich die Präsentationsdatei befindet. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad.

```java
String dataDir = "Your Document Directory";
```

## Schritt 3: Initialisieren Sie die Präsentation

 Laden Sie die Präsentation, die Sie in HTML konvertieren möchten. Unbedingt austauschen`"presentationWith.pptx"` mit dem Dateinamen Ihrer Präsentation.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## Schritt 4: Erstellen Sie den HTML-Controller

 Wir erstellen eine`VideoPlayerHtmlController` um den Konvertierungsprozess abzuwickeln. Ersetzen Sie die URL durch Ihre gewünschte Webadresse.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## Schritt 5: Konfigurieren Sie die HTML- und SVG-Optionen

Richten Sie HTML- und SVG-Optionen für die Konvertierung ein. Hier können Sie die Formatierung nach Bedarf anpassen.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## Schritt 6: Speichern Sie die Präsentation als HTML

Jetzt ist es an der Zeit, die Präsentation einschließlich der Mediendateien als HTML-Datei zu speichern.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Vollständiger Quellcode zum Konvertieren der gesamten Präsentation in HTML mit Mediendateien in Java Slides

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir den Prozess der Konvertierung einer gesamten Präsentation in HTML mit Mediendateien mithilfe von Java Slides und der Aspose.Slides für Java-API durchlaufen. Wenn Sie diese Schritte befolgen, können Sie Ihre Präsentationen effizient in ein webfreundliches Format umwandeln und dabei alle wesentlichen Medienelemente beibehalten.

## FAQs

### Wie kann ich Aspose.Slides für Java installieren?

 Um Aspose.Slides für Java zu installieren, besuchen Sie die Download-Seite unter[Hier](https://releases.aspose.com/slides/java/) und befolgen Sie die mitgelieferten Installationsanweisungen.

### Kann ich die HTML-Ausgabe weiter anpassen?

 Ja, Sie können die HTML-Ausgabe entsprechend Ihren Anforderungen anpassen. Der`HtmlOptions` Die Klasse bietet verschiedene Einstellungen zur Steuerung des Konvertierungsprozesses, einschließlich Formatierungs- und Layoutoptionen.

### Unterstützt Aspose.Slides für Java andere Ausgabeformate?

Ja, Aspose.Slides für Java unterstützt verschiedene Ausgabeformate, darunter PDF, PPTX und mehr. Sie können diese Optionen in der Dokumentation erkunden.

### Ist Aspose.Slides für Java für kommerzielle Projekte geeignet?

Ja, Aspose.Slides für Java ist eine robuste und kommerziell realisierbare Lösung für die Bearbeitung präsentationsbezogener Aufgaben in Java-Anwendungen. Es wird häufig in Projekten auf Unternehmensebene verwendet.

### Wie kann ich auf die konvertierte HTML-Präsentation zugreifen?

 Sobald Sie die Konvertierung abgeschlossen haben, können Sie auf die HTML-Präsentation zugreifen, indem Sie die in angegebene Datei suchen`htmlDocumentFileName` Variable.
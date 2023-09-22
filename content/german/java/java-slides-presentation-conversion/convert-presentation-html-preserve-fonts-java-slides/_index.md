---
title: Konvertieren einer Präsentation in HTML unter Beibehaltung der Originalschriftarten in Java-Folien
linktitle: Konvertieren einer Präsentation in HTML unter Beibehaltung der Originalschriftarten in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Konvertieren Sie PowerPoint-Präsentationen in HTML und behalten Sie dabei die Originalschriftarten mit Aspose.Slides für Java bei.
type: docs
weight: 14
url: /de/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Einführung in die Konvertierung von Präsentationen in HTML unter Beibehaltung der Originalschriftarten in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java eine PowerPoint-Präsentation (PPTX) in HTML konvertieren und dabei die Originalschriftarten beibehalten. Dadurch wird sichergestellt, dass der resultierende HTML-Code dem Erscheinungsbild der Originalpräsentation sehr ähnlich ist.

## Schritt 1: Einrichten des Projekts
Bevor wir uns mit dem Code befassen, stellen wir sicher, dass Sie über die erforderlichen Einstellungen verfügen:

1. Laden Sie Aspose.Slides für Java herunter: Falls Sie dies noch nicht getan haben, laden Sie die Aspose.Slides für Java-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein.

2. Erstellen Sie ein Java-Projekt: Richten Sie ein Java-Projekt in Ihrer bevorzugten IDE ein und stellen Sie sicher, dass Sie über einen „lib“-Ordner verfügen, in dem Sie die Aspose.Slides-JAR-Datei ablegen können.

3. Erforderliche Klassen importieren: Importieren Sie die erforderlichen Klassen am Anfang Ihrer Java-Datei:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Schritt 2: Konvertieren der Präsentation in HTML mit Originalschriftarten

Lassen Sie uns nun eine PowerPoint-Präsentation in HTML konvertieren und dabei die Originalschriftarten beibehalten:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Laden Sie die Präsentation
Presentation pres = new Presentation("input.pptx");

try {
    //Schließen Sie Standard-Präsentationsschriftarten wie Calibri und Arial aus
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Erstellen Sie HTML-Optionen und legen Sie den benutzerdefinierten HTML-Formatierer fest
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Speichern Sie die Präsentation als HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Entsorgen Sie das Präsentationsobjekt
    if (pres != null) pres.dispose();
}
```

In diesem Codeausschnitt:

-  Wir laden die Eingabe PowerPoint-Präsentation mit`Presentation`.

- Wir definieren eine Liste von Schriftarten (`fontNameExcludeList`), die wir von der Einbettung in den HTML-Code ausschließen möchten. Dies ist nützlich, um gängige Schriftarten wie Calibri und Arial auszuschließen und die Dateigröße zu reduzieren.

-  Wir erstellen eine Instanz von`EmbedAllFontsHtmlController` und übergeben Sie ihm die Schriftarten-Ausschlussliste.

-  Wir erstellen`HtmlOptions` und legen Sie einen benutzerdefinierten HTML-Formatierer fest`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Abschließend speichern wir die Präsentation als HTML mit den angegebenen Optionen.

## Vollständiger Quellcode zum Konvertieren von Präsentationen in HTML unter Beibehaltung der Originalschriftarten in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// Standard-Präsentationsschriftarten ausschließen
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für Java eine PowerPoint-Präsentation in HTML konvertieren und dabei die Originalschriftarten beibehalten. Dies ist nützlich, wenn Sie die visuelle Wiedergabetreue Ihrer Präsentationen beim Teilen im Web beibehalten möchten.

## FAQs

### Wie lade ich Aspose.Slides für Java herunter?

Sie können Aspose.Slides für Java von der Aspose-Website herunterladen. Besuchen[Hier](https://downloads.aspose.com/slides/java/) um die neueste Version zu erhalten.

### Kann ich die Liste der ausgeschlossenen Schriftarten anpassen?

 Ja, Sie können das anpassen`fontNameExcludeList` Array, um bestimmte Schriftarten entsprechend Ihren Anforderungen einzuschließen oder auszuschließen.

### Funktioniert diese Methode für ältere PowerPoint-Formate wie PPT?

Dieses Codebeispiel ist für PPTX-Dateien konzipiert. Wenn Sie ältere PPT-Dateien konvertieren müssen, müssen Sie möglicherweise Anpassungen am Code vornehmen.

### Wie kann ich die HTML-Ausgabe weiter anpassen?

 Sie können die erkunden`HtmlOptions` Klasse, um verschiedene Aspekte der HTML-Ausgabe anzupassen, wie z. B. Foliengröße, Bildqualität und mehr.
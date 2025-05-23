---
"description": "Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java in das XPS-Format konvertieren. Schritt-für-Schritt-Anleitung mit Quellcode."
"linktitle": "Konvertieren ohne XPS-Optionen in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Konvertieren ohne XPS-Optionen in Java-Folien"
"url": "/de/java/presentation-conversion/convert-without-xps-options-java-slides/"
"weight": 33
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren ohne XPS-Optionen in Java-Folien


## Einführung Konvertieren Sie PowerPoint in XPS ohne XPS-Optionen in Aspose.Slides für Java

In diesem Tutorial führen wir Sie durch die Konvertierung einer PowerPoint-Präsentation in ein XPS-Dokument (XML Paper Specification) mit Aspose.Slides für Java, ohne XPS-Optionen anzugeben. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen und Java-Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Aspose.Slides für Java: Stellen Sie sicher, dass die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und konfiguriert ist. Sie können sie von der [Aspose.Slides für Java-Website](https://downloads.aspose.com/slides/java).

2. Java-Entwicklungsumgebung: Sie sollten auf Ihrem Computer eine Java-Entwicklungsumgebung eingerichtet haben.

## Schritt 1: Importieren Sie Aspose.Slides für Java

Importieren Sie in Ihrem Java-Projekt die erforderlichen Aspose.Slides für Java-Klassen am Anfang Ihrer Java-Datei:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Schritt 2: Laden Sie die PowerPoint-Präsentation

Nun laden wir die PowerPoint-Präsentation, die Sie in XPS konvertieren möchten. Ersetzen Sie `"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrer PowerPoint-Präsentationsdatei:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

Stellen Sie sicher, dass Sie ersetzen `"Convert_XPS.pptx"` durch den tatsächlichen Namen Ihrer PowerPoint-Datei.

## Schritt 3: Als XPS speichern ohne XPS-Optionen

Mit Aspose.Slides für Java können Sie die geladene Präsentation einfach als XPS-Dokument speichern, ohne XPS-Optionen angeben zu müssen. So geht's:

```java
try {
    // Speichern der Präsentation als XPS-Dokument
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

Dieser Codeblock speichert die Präsentation als XPS-Dokument mit dem Namen `"XPS_Output_Without_XPSOption_out.xps"`. Sie können den Namen der Ausgabedatei nach Bedarf ändern.

## Vollständiger Quellcode zum Konvertieren ohne XPS-Optionen in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// Speichern der Präsentation als XPS-Dokument
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie eine PowerPoint-Präsentation mit Aspose.Slides für Java ohne Angabe von XPS-Optionen in ein XPS-Dokument konvertieren. Sie können den Konvertierungsprozess weiter anpassen, indem Sie die Optionen von Aspose.Slides für Java erkunden. Weitere erweiterte Funktionen und eine ausführliche Dokumentation finden Sie unter [Aspose.Slides für Java-Dokumentation](https://docs.aspose.com/slides/java/).

## Häufig gestellte Fragen

### Wie gebe ich beim Konvertieren XPS-Optionen an?

Um XPS-Optionen beim Konvertieren einer PowerPoint-Präsentation festzulegen, können Sie die `XpsOptions` Klasse und legen Sie verschiedene Eigenschaften wie Bildkomprimierung und Schriftarteinbettung fest. Wenn Sie spezielle Anforderungen für die XPS-Konvertierung haben, lesen Sie die [Aspose.Slides für Java-Dokumentation](https://docs.aspose.com/slides/java/) für weitere Details.

### Gibt es zusätzliche Möglichkeiten zum Speichern in anderen Formaten?

Ja, Aspose.Slides für Java bietet neben XPS verschiedene Ausgabeformate wie PDF, TIFF und HTML. Sie können das gewünschte Ausgabeformat festlegen, indem Sie die `SaveFormat` Parameter beim Aufruf des `save` Methode. Eine vollständige Liste der unterstützten Formate finden Sie in der Dokumentation.

### Wie kann ich Ausnahmen während des Konvertierungsprozesses behandeln?

Sie können eine Ausnahmebehandlung implementieren, um alle während des Konvertierungsprozesses auftretenden Fehler ordnungsgemäß zu behandeln. Wie im Code gezeigt, `try` Und `finally` Blöcke werden verwendet, um eine ordnungsgemäße Ressourcenverfügung auch bei Auftreten einer Ausnahme sicherzustellen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
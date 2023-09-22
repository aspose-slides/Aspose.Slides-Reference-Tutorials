---
title: Konvertieren Sie eine HTML-Präsentation mit eingebetteten Bildern
linktitle: Konvertieren Sie eine HTML-Präsentation mit eingebetteten Bildern
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Konvertieren Sie HTML-Präsentationen mit eingebetteten Bildern mühelos mit Aspose.Slides für .NET. Erstellen, anpassen und speichern Sie PowerPoint-Dateien nahtlos.
type: docs
weight: 11
url: /de/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1. Einleitung

Aspose.Slides für .NET bietet eine praktische Möglichkeit, PowerPoint-Präsentationen in das HTML5-Format zu konvertieren und dabei eingebettete Bilder beizubehalten. Dies kann für die Anzeige Ihrer Präsentationen auf Websites oder in Webanwendungen äußerst nützlich sein.

## 2. Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine beliebige C#-Entwicklungsumgebung.
- Aspose.Slides für .NET-Bibliothek.
- Eine Beispiel-PowerPoint-Präsentation mit eingebetteten Bildern.
- Grundkenntnisse der C#-Programmierung.

## 3. Einrichten Ihres Projekts

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Stellen Sie sicher, dass in Ihrem Projekt ordnungsgemäß auf die Aspose.Slides for .NET-Bibliothek verwiesen wird.

## 4. Laden der Quellpräsentation

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // Hier finden Sie Ihren Code zur Verarbeitung der Präsentation
}
```

## 5. Konfigurieren der HTML-Konvertierungsoptionen

 Um HTML-Konvertierungsoptionen zu konfigurieren, können Sie die verwenden`Html5Options` Klasse. Hier ist ein Beispiel für das Festlegen einiger Optionen:

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // Speichern Sie keine Bilder im HTML5-Dokument
    OutputPath = "Your Output Directory" // Legen Sie den Pfad für externe Bilder fest
};
```

## 6. Erstellen des Ausgabeverzeichnisses

Bevor Sie die Präsentation im HTML5-Format speichern, empfiehlt es sich, das Ausgabeverzeichnis zu erstellen, falls es noch nicht vorhanden ist:

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. Speichern der Präsentation im HTML5-Format

Speichern wir nun die Präsentation im HTML5-Format:

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. Fazit

Glückwunsch! Sie haben eine PowerPoint-Präsentation mit eingebetteten Bildern mit Aspose.Slides für .NET erfolgreich in das HTML5-Format konvertiert. Dies kann ein wertvolles Tool zum Teilen Ihrer Präsentationen online sein.

## 9. FAQs

**Q1: Can I customize the appearance of the HTML5 presentation?**
Ja, Sie können das Erscheinungsbild anpassen, indem Sie die von Aspose.Slides generierten HTML- und CSS-Dateien ändern.

**Q2: Does Aspose.Slides for .NET support other output formats?**
Ja, es unterstützt verschiedene Ausgabeformate, darunter PDF, Bilder und mehr.

**Q3: Are there any limitations to converting presentations with embedded images?**
Obwohl Aspose.Slides für .NET leistungsstark ist, können bei hochkomplexen Präsentationen einige Einschränkungen auftreten.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
Ja, es ist mit PowerPoint-Dateien verschiedener Versionen kompatibel, einschließlich der neuesten.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 Umfassende Dokumentation und Ressourcen finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
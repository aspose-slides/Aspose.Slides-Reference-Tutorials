---
title: Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML
linktitle: Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Konvertieren Sie PowerPoint-Präsentationen mit eingebetteten Schriftarten in HTML mit Aspose.Slides für .NET. Behalten Sie die Originalität nahtlos bei.
type: docs
weight: 13
url: /de/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

Im heutigen digitalen Zeitalter ist der Online-Austausch von Präsentationen und Dokumenten zu einer gängigen Praxis geworden. Eine häufige Herausforderung besteht jedoch darin, sicherzustellen, dass Ihre Schriftarten beim Konvertieren von Präsentationen in HTML korrekt angezeigt werden. Dieses Schritt-für-Schritt-Tutorial führt Sie durch den Prozess der Verwendung von Aspose.Slides für .NET zum Konvertieren von Präsentationen in HTML mit eingebetteten Schriftarten und stellt sicher, dass Ihre Dokumente genau so aussehen, wie Sie es beabsichtigt haben.

## Einführung in Aspose.Slides für .NET

Bevor wir uns mit dem Tutorial befassen, stellen wir Aspose.Slides für .NET kurz vor. Es handelt sich um eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mit PowerPoint-Präsentationen in .NET-Anwendungen zu arbeiten. Mit Aspose.Slides können Sie PowerPoint-Dateien programmgesteuert erstellen, ändern und konvertieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: In Ihrem Projekt sollte die Aspose.Slides-Bibliothek installiert sein. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

## Schritt 1: Richten Sie Ihr Projekt ein

1. Erstellen Sie ein neues Projekt oder öffnen Sie ein vorhandenes in Ihrer bevorzugten .NET-Entwicklungsumgebung.

2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides-Bibliothek hinzu.

3. Importieren Sie die erforderlichen Namespaces in Ihren Code:

   ```csharp
   using Aspose.Slides;
   ```

## Schritt 2: Laden Sie Ihre Präsentation

 Zunächst müssen Sie die Präsentation laden, die Sie in HTML konvertieren möchten. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre Präsentationsdatei befindet.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Ihr Code kommt hierher
}
```

## Schritt 3: Standard-Präsentationsschriftarten ausschließen

In diesem Schritt können Sie alle Standard-Präsentationsschriftarten angeben, die Sie von der Einbettung ausschließen möchten. Dies kann dabei helfen, die Größe der resultierenden HTML-Datei zu optimieren.

```csharp
string[] fontNameExcludeList = { };
```

## Schritt 4: Wählen Sie einen HTML-Controller

Nun haben Sie zwei Möglichkeiten, Schriftarten in den HTML-Code einzubetten:

### Option 1: Alle Schriftarten einbetten

 Um alle in der Präsentation verwendeten Schriftarten einzubetten, verwenden Sie die`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Option 2: Alle Schriftarten verknüpfen

 Um eine Verknüpfung zu allen in der Präsentation verwendeten Schriftarten herzustellen, verwenden Sie die`LinkAllFontsHtmlController`. Sie sollten das Verzeichnis angeben, in dem sich die Schriftarten auf Ihrem System befinden.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Schritt 5: HTML-Optionen definieren

 Erstelle ein`HtmlOptions` Objekt und stellen Sie den HTML-Formatierer auf den ein, den Sie im vorherigen Schritt ausgewählt haben.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Verwenden Sie embedFontsController zum Einbetten aller Schriftarten
};
```

## Schritt 6: Als HTML speichern

 Speichern Sie abschließend die Präsentation als HTML-Datei. Sie können beides wählen`SaveFormat.Html` oder`SaveFormat.Html5` je nach Ihren Anforderungen.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Abschluss

Glückwunsch! Sie haben Ihre Präsentation mit Aspose.Slides für .NET erfolgreich in HTML mit eingebetteten Schriftarten konvertiert. Dadurch wird sichergestellt, dass Ihre Schriftarten korrekt angezeigt werden, wenn Sie Ihre Präsentationen online teilen.

Jetzt können Sie Ihre schön formatierten Präsentationen ganz einfach mit der Gewissheit teilen, dass Ihr Publikum sie genau so sieht, wie Sie es beabsichtigt haben.

 Weitere Informationen und detaillierte API-Referenzen finden Sie im[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

## FAQs

### 1. Kann ich PowerPoint-Präsentationen mit Aspose.Slides für .NET im Batch-Modus in HTML konvertieren?

Ja, Sie können mit Aspose.Slides für .NET mehrere Präsentationen stapelweise in HTML konvertieren, indem Sie Ihre Präsentationsdateien durchlaufen und den Konvertierungsprozess auf jede einzelne anwenden.

### 2. Gibt es eine Möglichkeit, das Erscheinungsbild der HTML-Ausgabe anzupassen?

Sicherlich! Aspose.Slides für .NET bietet verschiedene Optionen zum Anpassen des Erscheinungsbilds und der Formatierung der HTML-Ausgabe, z. B. das Anpassen von Farben, Schriftarten und Layout.

### 3. Gibt es Einschränkungen beim Einbetten von Schriftarten in HTML mit Aspose.Slides für .NET?

Obwohl Aspose.Slides für .NET hervorragende Funktionen zum Einbetten von Schriftarten bietet, bedenken Sie, dass sich die Größe Ihrer HTML-Dateien beim Einbetten von Schriftarten erhöhen kann. Achten Sie darauf, Ihre Schriftartenauswahl für die Webnutzung zu optimieren.

### 4. Kann ich PowerPoint-Präsentationen mit Aspose.Slides für .NET in andere Formate konvertieren?

Ja, Aspose.Slides für .NET unterstützt eine Vielzahl von Ausgabeformaten, darunter PDF, Bilder und mehr. Sie können Ihre Präsentationen ganz einfach in das Format Ihrer Wahl konvertieren.

### 5. Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Slides für .NET?

 Sie können auf eine Fülle von Ressourcen, einschließlich Dokumentation, zugreifen[Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/).

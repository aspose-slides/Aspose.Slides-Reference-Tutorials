---
"description": "Konvertieren Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET in HTML mit eingebetteten Schriftarten. Bewahren Sie nahtlos die Originalität."
"linktitle": "Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML"
"url": "/de/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML


Im digitalen Zeitalter ist das Teilen von Präsentationen und Dokumenten online gängige Praxis. Eine Herausforderung besteht jedoch häufig darin, sicherzustellen, dass Ihre Schriftarten bei der Konvertierung von Präsentationen in HTML korrekt angezeigt werden. Dieses Schritt-für-Schritt-Tutorial führt Sie durch die Verwendung von Aspose.Slides für .NET zur Konvertierung von Präsentationen in HTML mit eingebetteten Schriftarten und stellt sicher, dass Ihre Dokumente genau Ihren Vorstellungen entsprechen.

## Einführung in Aspose.Slides für .NET

Bevor wir in das Tutorial eintauchen, stellen wir kurz Aspose.Slides für .NET vor. Es handelt sich um eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mit PowerPoint-Präsentationen in .NET-Anwendungen zu arbeiten. Mit Aspose.Slides können Sie PowerPoint-Dateien programmgesteuert erstellen, ändern und konvertieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Slides für .NET: Die Aspose.Slides-Bibliothek sollte in Ihrem Projekt installiert sein. Sie können sie hier herunterladen. [Hier](https://releases.aspose.com/slides/net/).

## Schritt 1: Richten Sie Ihr Projekt ein

1. Erstellen Sie ein neues Projekt oder öffnen Sie ein vorhandenes in Ihrer bevorzugten .NET-Entwicklungsumgebung.

2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides-Bibliothek hinzu.

3. Importieren Sie die erforderlichen Namespaces in Ihren Code:

   ```csharp
   using Aspose.Slides;
   ```

## Schritt 2: Laden Sie Ihre Präsentation

Laden Sie zunächst die Präsentation, die Sie in HTML konvertieren möchten. Ersetzen Sie `"Your Document Directory"` durch das tatsächliche Verzeichnis, in dem sich Ihre Präsentationsdatei befindet.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Ihr Code kommt hier hin
}
```

## Schritt 3: Standard-Präsentationsschriftarten ausschließen

In diesem Schritt können Sie alle Standard-Präsentationsschriftarten angeben, die Sie von der Einbettung ausschließen möchten. Dies kann dazu beitragen, die Größe der resultierenden HTML-Datei zu optimieren.

```csharp
string[] fontNameExcludeList = { };
```

## Schritt 4: Wählen Sie einen HTML-Controller

Nun haben Sie zwei Möglichkeiten, Schriftarten in das HTML einzubetten:

### Option 1: Alle Schriftarten einbetten

Um alle in der Präsentation verwendeten Schriftarten einzubetten, verwenden Sie die `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Option 2: Alle Schriftarten verknüpfen

Um auf alle in der Präsentation verwendeten Schriftarten zu verlinken, verwenden Sie die `LinkAllFontsHtmlController`Sie sollten das Verzeichnis angeben, in dem sich die Schriftarten auf Ihrem System befinden.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Schritt 5: HTML-Optionen definieren

Erstellen Sie ein `HtmlOptions` Objekt und legen Sie den HTML-Formatierer auf den im vorherigen Schritt ausgewählten fest.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Verwenden Sie embedFontsController zum Einbetten aller Schriftarten
};
```

## Schritt 6: Als HTML speichern

Speichern Sie die Präsentation abschließend als HTML-Datei. Sie können wählen zwischen `SaveFodermat.Html` or `SaveFormat.Html5` je nach Ihren Anforderungen.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben Ihre Präsentation mit Aspose.Slides für .NET erfolgreich in HTML mit eingebetteten Schriftarten konvertiert. Dadurch wird sichergestellt, dass Ihre Schriftarten beim Online-Teilen Ihrer Präsentationen korrekt angezeigt werden.

Jetzt können Sie Ihre schön formatierten Präsentationen problemlos und mit der Gewissheit weitergeben, dass Ihr Publikum sie genau so sieht, wie Sie es beabsichtigt haben.

Weitere Informationen und detaillierte API-Referenzen finden Sie in der [Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

## FAQs

### 1. Kann ich PowerPoint-Präsentationen mit Aspose.Slides für .NET im Batchmodus in HTML konvertieren?

Ja, Sie können mit Aspose.Slides für .NET mehrere Präsentationen stapelweise in HTML konvertieren, indem Sie Ihre Präsentationsdateien durchlaufen und den Konvertierungsprozess auf jede einzelne anwenden.

### 2. Gibt es eine Möglichkeit, das Erscheinungsbild der HTML-Ausgabe anzupassen?

Sicher! Aspose.Slides für .NET bietet verschiedene Optionen zum Anpassen des Erscheinungsbilds und der Formatierung der HTML-Ausgabe, z. B. durch Anpassen von Farben, Schriftarten und Layout.

### 3. Gibt es Einschränkungen beim Einbetten von Schriftarten in HTML mit Aspose.Slides für .NET?

Obwohl Aspose.Slides für .NET hervorragende Funktionen zum Einbetten von Schriftarten bietet, beachten Sie, dass sich die Größe Ihrer HTML-Dateien beim Einbetten von Schriftarten erhöhen kann. Stellen Sie sicher, dass Sie Ihre Schriftartenauswahl für die Webnutzung optimieren.

### 4. Kann ich mit Aspose.Slides für .NET PowerPoint-Präsentationen in andere Formate konvertieren?

Ja, Aspose.Slides für .NET unterstützt eine Vielzahl von Ausgabeformaten, darunter PDF, Bilder und mehr. Sie können Ihre Präsentationen problemlos in das Format Ihrer Wahl konvertieren.

### 5. Wo finde ich zusätzliche Ressourcen und Support für Aspose.Slides für .NET?

Sie können auf eine Fülle von Ressourcen, einschließlich Dokumentation, zugreifen auf der [Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
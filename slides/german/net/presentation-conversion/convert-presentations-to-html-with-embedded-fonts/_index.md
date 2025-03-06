---
title: Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML
linktitle: Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Konvertieren Sie PowerPoint-Präsentationen mit Aspose.Slides für .NET in HTML mit eingebetteten Schriftarten. Bewahren Sie nahtlos die Originalität.
weight: 13
url: /de/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertieren Sie Präsentationen mit eingebetteten Schriftarten in HTML


Im heutigen digitalen Zeitalter ist das Teilen von Präsentationen und Dokumenten online eine gängige Praxis geworden. Eine Herausforderung besteht jedoch häufig darin, sicherzustellen, dass Ihre Schriftarten beim Konvertieren von Präsentationen in HTML korrekt angezeigt werden. Dieses Schritt-für-Schritt-Tutorial führt Sie durch den Prozess der Verwendung von Aspose.Slides für .NET zum Konvertieren von Präsentationen in HTML mit eingebetteten Schriftarten und stellt sicher, dass Ihre Dokumente genau so aussehen, wie Sie es beabsichtigt haben.

## Einführung in Aspose.Slides für .NET

Bevor wir in das Tutorial eintauchen, stellen wir kurz Aspose.Slides für .NET vor. Es handelt sich um eine leistungsstarke Bibliothek, mit der Entwickler mit PowerPoint-Präsentationen in .NET-Anwendungen arbeiten können. Mit Aspose.Slides können Sie PowerPoint-Dateien programmgesteuert erstellen, ändern und konvertieren.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass die folgenden Voraussetzungen erfüllt sind:

-  Aspose.Slides für .NET: Sie sollten die Aspose.Slides-Bibliothek in Ihrem Projekt installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/net/).

## Schritt 1: Richten Sie Ihr Projekt ein

1. Erstellen Sie ein neues Projekt oder öffnen Sie ein vorhandenes in Ihrer bevorzugten .NET-Entwicklungsumgebung.

2. Fügen Sie in Ihrem Projekt einen Verweis auf die Aspose.Slides-Bibliothek hinzu.

3. Importieren Sie die erforderlichen Namespaces in Ihren Code:

   ```csharp
   using Aspose.Slides;
   ```

## Schritt 2: Laden Sie Ihre Präsentation

 Zunächst müssen Sie die Präsentation laden, die Sie in HTML konvertieren möchten. Ersetzen Sie`"Your Document Directory"` durch das tatsächliche Verzeichnis, in dem sich Ihre Präsentationsdatei befindet.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Ihr Code kommt hier rein
}
```

## Schritt 3: Standardmäßige Präsentationsschriftarten ausschließen

In diesem Schritt können Sie alle Standardpräsentationsschriftarten angeben, die Sie vom Einbetten ausschließen möchten. Dadurch können Sie die Größe der resultierenden HTML-Datei optimieren.

```csharp
string[] fontNameExcludeList = { };
```

## Schritt 4: Wählen Sie einen HTML-Controller

Nun haben Sie zwei Möglichkeiten, Schriftarten in das HTML einzubetten:

### Option 1: Alle Schriftarten einbetten

 Um alle in der Präsentation verwendeten Schriftarten einzubetten, verwenden Sie die`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Option 2: Alle Schriftarten verknüpfen

 Um auf alle in der Präsentation verwendeten Schriftarten zu verlinken, verwenden Sie die`LinkAllFontsHtmlController`. Sie sollten das Verzeichnis angeben, in dem sich die Schriftarten auf Ihrem System befinden.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Schritt 5: HTML-Optionen definieren

 Erstelle ein`HtmlOptions` Objekt und legen Sie den HTML-Formatierer auf den fest, den Sie im vorherigen Schritt ausgewählt haben.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Verwenden Sie embedFontsController zum Einbetten aller Schriftarten
};
```

## Schritt 6: Als HTML speichern

 Speichern Sie die Präsentation abschließend als HTML-Datei. Sie können wählen zwischen`SaveFormat.Html` oder`SaveFormat.Html5` abhängig von Ihren Anforderungen.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben Ihre Präsentation mit Aspose.Slides für .NET erfolgreich in HTML mit eingebetteten Schriftarten konvertiert. Dadurch wird sichergestellt, dass Ihre Schriftarten beim Online-Teilen Ihrer Präsentationen korrekt angezeigt werden.

Jetzt können Sie Ihre schön formatierten Präsentationen problemlos weitergeben, da Sie wissen, dass Ihr Publikum sie genau so sieht, wie Sie es beabsichtigt haben.

 Weitere Informationen und detaillierte API-Referenzen finden Sie in der[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).

## FAQs

### 1. Kann ich PowerPoint-Präsentationen mit Aspose.Slides für .NET im Batchmodus in HTML konvertieren?

Ja, Sie können mit Aspose.Slides für .NET mehrere Präsentationen stapelweise in HTML konvertieren, indem Sie Ihre Präsentationsdateien durchlaufen und den Konvertierungsprozess auf jede einzelne Datei anwenden.

### 2. Gibt es eine Möglichkeit, das Erscheinungsbild der HTML-Ausgabe anzupassen?

Sicherlich! Aspose.Slides für .NET bietet verschiedene Optionen zum Anpassen des Erscheinungsbilds und der Formatierung der HTML-Ausgabe, beispielsweise zum Anpassen von Farben, Schriftarten und Layout.

### 3. Gibt es Einschränkungen beim Einbetten von Schriftarten in HTML mit Aspose.Slides für .NET?

Obwohl Aspose.Slides für .NET hervorragende Funktionen zum Einbetten von Schriftarten bietet, sollten Sie bedenken, dass sich die Größe Ihrer HTML-Dateien beim Einbetten von Schriftarten erhöhen kann. Achten Sie darauf, Ihre Schriftartenauswahl für die Verwendung im Web zu optimieren.

### 4. Kann ich mit Aspose.Slides für .NET PowerPoint-Präsentationen in andere Formate konvertieren?

Ja, Aspose.Slides für .NET unterstützt eine Vielzahl von Ausgabeformaten, darunter PDF, Bilder und mehr. Sie können Ihre Präsentationen problemlos in das Format Ihrer Wahl konvertieren.

### 5. Wo finde ich zusätzliche Ressourcen und Support für Aspose.Slides für .NET?

 Sie können auf eine Fülle von Ressourcen, einschließlich Dokumentationen, zugreifen auf der[Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

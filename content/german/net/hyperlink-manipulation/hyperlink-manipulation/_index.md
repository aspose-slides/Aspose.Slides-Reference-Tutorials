---
title: Hyperlink-Manipulation in Aspose.Slides
linktitle: Hyperlink-Manipulation in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Hyperlinks mithilfe von Aspose.Slides für .NET verbessern. Erstellen, ändern und verwalten Sie interaktive Inhalte nahtlos.
type: docs
weight: 10
url: /de/net/hyperlink-manipulation/hyperlink-manipulation/
---

## Einführung in die Hyperlink-Manipulation

Hyperlinks bereichern Präsentationen, indem sie Folien, Dokumente, Webseiten und mehr verbinden. Sie bieten ein interaktives Erlebnis und steigern das Engagement des Publikums. Aspose.Slides für .NET bietet umfassende Funktionen zur programmgesteuerten Verwaltung von Hyperlinks und gibt Ihnen die volle Kontrolle über die Navigation Ihrer Präsentation.

## Setzen von Hyperlinks in Folien

 Zum Erstellen von Hyperlinks können Sie Aspose.Slides für .NET verwenden`HyperlinkManager` Klasse. Mit dieser Klasse können Sie verschiedene Arten von Hyperlinks zu bestimmten Formen oder Texten in Ihren Folien hinzufügen.

```csharp
// Codebeispiel zum Hinzufügen eines Hyperlinks zu einer Form
HyperlinkManager.AddHyperlinkToShape(shape, "https://www.example.com“, „Besuchen Sie unsere Website“);
```

## Hyperlinks ändern

Mit Aspose.Slides für .NET können Sie vorhandene Hyperlinks problemlos ändern. Dies ist nützlich, wenn Sie die Ziel-URL aktualisieren oder den Text des Hyperlinks ändern müssen.

```csharp
// Codebeispiel zum Ändern der URL eines Hyperlinks
HyperlinkManager.ModifyHyperlinkUrl(shape, "https://newurl.com");
```

## Hyperlinks entfernen

Wenn Sie einen Hyperlink aus einer Form entfernen möchten, bietet Aspose.Slides für .NET eine einfache Methode dafür.

```csharp
// Codebeispiel zum Entfernen eines Hyperlinks aus einer Form
HyperlinkManager.RemoveHyperlink(shape);
```

## Arbeiten mit Ankerpunkten

Beim Umgang mit Hyperlinks innerhalb von Folien sind Ankerpunkte von entscheidender Bedeutung. Sie bestimmen die Position, auf die der Hyperlink innerhalb der Zielfolie verweist.

```csharp
// Codebeispiel zum Festlegen eines Ankerpunkts für einen Hyperlink
HyperlinkManager.SetHyperlinkAnchor(shape, targetSlide, anchorX, anchorY);
```

## Umgang mit verschiedenen Hyperlink-Typen

Aspose.Slides für .NET unterstützt verschiedene Hyperlink-Typen, darunter URL-Links, interne Dokument-Links, Links zu E-Mail-Adressen und mehr.

```csharp
// Codebeispiel zum Hinzufügen eines E-Mail-Hyperlinks
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");
```

## Hinzufügen von Tooltips zu Hyperlinks

Tooltips bieten zusätzliche Informationen, wenn Benutzer mit der Maus über Hyperlinks fahren. Mit Aspose.Slides für .NET können Sie Tooltips für Ihre Hyperlinks festlegen.

```csharp
// Codebeispiel zum Hinzufügen eines Tooltips zu einem Hyperlink
HyperlinkManager.AddHyperlinkWithTooltip(shape, "https://www.example.com“, „Besuchen Sie unsere Website“, „Klicken Sie zum Erkunden“);
```

## Verwalten externer Hyperlinks

Sie können mit Aspose.Slides für .NET auch externe Hyperlinks verwalten und so sicherstellen, dass Ihre Präsentationen mit relevanten Online-Ressourcen verbunden bleiben.

```csharp
// Codebeispiel zum Öffnen eines Hyperlinks in einem Webbrowser
HyperlinkManager.OpenHyperlinkInBrowser(shape);
```

## Hyperlinks in Masterfolien

Masterfolien enthalten oft wiederkehrende Elemente. Mit Aspose.Slides für .NET können Sie Hyperlinks auf Masterfolien anwenden und so die Konsistenz Ihrer Präsentation gewährleisten.

```csharp
// Codebeispiel zum Setzen eines Hyperlinks in einer Masterfolie
HyperlinkManager.SetHyperlinkInMasterSlide(masterSlide, "https://www.example.com“, „Besuchen Sie unsere Website“);
```

## Extrahieren von Hyperlink-Informationen

Mit Aspose.Slides für .NET können Sie Informationen aus vorhandenen Hyperlinks extrahieren, die für Analyse- oder Berichtszwecke hilfreich sein können.

```csharp
// Codebeispiel zum Extrahieren von Hyperlink-Informationen
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

## Hinzufügen von Hyperlinks zu Bildern und Formen

Hyperlinks können nicht nur zu Text, sondern auch zu Bildern und Formen in Ihren Folien hinzugefügt werden.

```csharp
// Codebeispiel zum Hinzufügen eines Hyperlinks zu einem Bild
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com“, „Klicken Sie auf das Bild, um mehr zu erfahren“);
```

## Verlinkung mit E-Mail-Adressen und Telefonnummern

Mit Aspose.Slides für .NET können Sie Hyperlinks erstellen, die beim Klicken das Verfassen von E-Mails auslösen oder Telefonanrufe einleiten.

```csharp
// Codebeispiel zum Erstellen eines E-Mail-Hyperlinks
HyperlinkManager.AddEmailHyperlink(shape, "support@example.com", "Contact Support");

// Codebeispiel zum Erstellen eines Telefonnummern-Hyperlinks
HyperlinkManager.AddPhoneHyperlink(shape, "+1234567890", "Call our support");
```

## Hyperlink-Formatierung

Sie können Hyperlinks formatieren, um sie optisch von normalen Texten oder Formen abzuheben.

```csharp
// Codebeispiel zum Formatieren des Erscheinungsbilds eines Hyperlinks
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

## Hinzufügen von Hyperlinks über die API

Aspose.Slides für .NET bietet eine robuste API für die Hyperlink-Manipulation. Sie können diese Funktionen nahtlos in Ihre Anwendungen integrieren.

```csharp
// Codebeispiel zum Hinzufügen eines Hyperlinks über die API
HyperlinkManager.AddHyperlink(shape, HyperlinkType.Url, "https://www.example.com");
```

## Abschluss

Die Hyperlink-Manipulation mit Aspose.Slides für .NET bietet ein umfassendes Toolkit zur Verbesserung der Interaktivität und des Engagements Ihrer PowerPoint-Präsentationen. Mit der Möglichkeit, Hyperlinks zu erstellen, zu ändern und zu verwalten, können Sie dynamische und informative Diashows erstellen, die Ihr Publikum fesseln.

## FAQs

### Wie entferne ich einen Hyperlink aus einer Form?

Um einen Hyperlink aus einer Form zu entfernen, können Sie den folgenden Code verwenden:

```csharp
HyperlinkManager.RemoveHyperlink(shape);
```

### Kann ich Hyperlinks auf Bilder in meinen Folien anwenden?

Ja, Sie können mit Aspose.Slides für .NET Hyperlinks zu Bildern und Formen in Ihren Folien hinzufügen. Zum Beispiel:

```csharp
HyperlinkManager.AddHyperlinkToImage(imageShape, "https://www.example.com“, „Klicken Sie auf das Bild, um mehr zu erfahren“);
```

### Ist es möglich, das Erscheinungsbild eines Hyperlinks zu formatieren?

Sicherlich! Sie können das Erscheinungsbild eines Hyperlinks mit Aspose.Slides für .NET formatieren. Hier ist ein Beispiel:

```csharp
HyperlinkManager.FormatHyperlink(shape, HyperlinkFormat.Highlighted);
```

### Wie kann ich Informationen aus einem vorhandenen Hyperlink extrahieren?

Mit dem folgenden Ansatz können Sie Informationen aus einem vorhandenen Hyperlink extrahieren:

```csharp
HyperlinkManager.ExtractHyperlinkInfo(shape, out string linkUrl, out string linkText);
```

### Wo kann ich auf eine ausführlichere Dokumentation zu Aspose.Slides für .NET zugreifen?

Ausführlichere Informationen und Codebeispiele finden Sie im[Dokumentation](https://reference.aspose.com/slides/net/) für Aspose.Slides für .NET.
---
title: Originalschriftarten beibehalten - Präsentation in HTML konvertieren
linktitle: Originalschriftarten beibehalten - Präsentation in HTML konvertieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie beim Konvertieren von Präsentationen in HTML mit Aspose.Slides für .NET die Originalschriftarten beibehalten. Sorgen Sie mühelos für Schriftkonsistenz und visuelle Wirkung.
weight: 14
url: /de/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


In dieser umfassenden Anleitung führen wir Sie durch den Prozess der Beibehaltung der Originalschriftarten bei der Konvertierung einer Präsentation in HTML mit Aspose.Slides für .NET. Wir stellen Ihnen den erforderlichen C#-Quellcode zur Verfügung und erklären jeden Schritt im Detail. Am Ende dieses Tutorials können Sie sicherstellen, dass die Schriftarten in Ihrem konvertierten HTML-Dokument der Originalpräsentation treu bleiben.

## 1. Einleitung

Beim Konvertieren von PowerPoint-Präsentationen in HTML ist es wichtig, die Originalschriftarten beizubehalten, um die visuelle Konsistenz Ihres Inhalts sicherzustellen. Aspose.Slides für .NET bietet hierfür eine leistungsstarke Lösung. In diesem Tutorial führen wir Sie durch die Schritte, die erforderlich sind, um die Originalschriftarten während des Konvertierungsprozesses beizubehalten.

## 2. Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio ist auf Ihrem Computer installiert.
- Aspose.Slides für .NET-Bibliothek zu Ihrem Projekt hinzugefügt.

## 3. Einrichten Ihres Projekts

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie die Bibliothek Aspose.Slides für .NET als Referenz hinzu.

## 4. Laden der Präsentation

Verwenden Sie den folgenden Code, um Ihre PowerPoint-Präsentation zu laden:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Ihr Code hier
}
```

 Ersetzen`"Your Document Directory"` durch den Pfad zu Ihrer Präsentationsdatei.

## 5. Standardschriftarten ausschließen

Um Standardschriftarten wie Calibri und Arial auszuschließen, verwenden Sie den folgenden Code:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Sie können diese Liste nach Bedarf anpassen.

## 6. Einbetten aller Schriftarten

Als nächstes betten wir alle Schriftarten in das HTML-Dokument ein. Dadurch wird sichergestellt, dass die Originalschriftarten erhalten bleiben. Verwenden Sie den folgenden Code:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Als HTML speichern

Speichern Sie die Präsentation nun als HTML-Dokument mit eingebetteten Schriftarten:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Ersetzen`"output.html"` durch den gewünschten Ausgabedateinamen.

## 8. Fazit

In diesem Tutorial haben wir gezeigt, wie Sie beim Konvertieren einer PowerPoint-Präsentation in HTML mit Aspose.Slides für .NET die Originalschriftarten beibehalten. Indem Sie diese Schritte befolgen, können Sie sicherstellen, dass Ihr konvertiertes HTML-Dokument die visuelle Integrität der Originalpräsentation beibehält.

## 9. Häufig gestellte Fragen

### F1: Kann ich die Liste der ausgeschlossenen Schriftarten anpassen?

 Ja, das können Sie. Ändern Sie die`fontNameExcludeList`Array, um bestimmte Schriftarten entsprechend Ihren Anforderungen ein- oder auszuschließen.

### F2: Was ist, wenn ich nicht alle Schriftarten einbetten möchte?

Wenn Sie nur bestimmte Schriftarten einbetten möchten, können Sie den Code entsprechend ändern. Weitere Einzelheiten finden Sie in der Dokumentation zu Aspose.Slides für .NET.

### F3: Gibt es Lizenzanforderungen für die Verwendung von Aspose.Slides für .NET?

Ja, Sie benötigen möglicherweise eine gültige Lizenz, um Aspose.Slides für .NET in Ihren Projekten zu verwenden. Lizenzinformationen finden Sie auf der Aspose-Website.

### F4: Kann ich mit Aspose.Slides für .NET andere Dateiformate in HTML konvertieren?

Aspose.Slides für .NET konzentriert sich hauptsächlich auf PowerPoint-Präsentationen. Um andere Dateiformate in HTML zu konvertieren, müssen Sie möglicherweise andere Aspose-Produkte erkunden, die auf diese Formate zugeschnitten sind.

### F5: Wo kann ich auf zusätzliche Ressourcen und Support zugreifen?

 Weitere Dokumentation, Tutorials und Support finden Sie auf der Aspose-Website. Besuchen Sie[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/) für detaillierte Informationen.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

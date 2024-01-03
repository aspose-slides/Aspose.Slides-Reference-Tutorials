---
title: Fügen Sie Layoutfolien zur Präsentation hinzu
linktitle: Fügen Sie Layoutfolien zur Präsentation hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen mit Aspose.Slides für .NET verbessern. Fügen Sie Layout-Folien für eine professionelle Note hinzu.
type: docs
weight: 11
url: /de/net/chart-creation-and-customization/add-layout-slides/
---

Im heutigen digitalen Zeitalter ist die Erstellung einer wirkungsvollen Präsentation eine wesentliche Fähigkeit. Eine gut strukturierte und optisch ansprechende Präsentation kann Ihre Botschaft effektiv vermitteln. Aspose.Slides für .NET ist ein leistungsstarkes Tool, mit dem Sie im Handumdrehen beeindruckende Präsentationen erstellen können. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Slides für .NET Ihrer Präsentation Layout-Folien hinzufügen. Wir unterteilen den Prozess in leicht verständliche Schritte, um sicherzustellen, dass Sie die Konzepte gründlich verstehen. Lass uns anfangen!

## Voraussetzungen

Bevor wir uns mit dem Tutorial befassen, müssen einige Voraussetzungen erfüllt sein:

1.  Aspose.Slides für .NET-Bibliothek: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).

2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung wie Visual Studio eingerichtet haben, um den Code zu schreiben und auszuführen.

3. Beispielpräsentation: Sie benötigen eine Beispiel-PowerPoint-Präsentation, mit der Sie arbeiten können. Sie können Ihre vorhandene Präsentation verwenden oder eine neue erstellen.

Nachdem Sie nun alle Voraussetzungen erfüllt haben, können Sie mit dem Hinzufügen von Layoutfolien zu Ihrer Präsentation fortfahren.

## Namespaces importieren

Zunächst müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren, um mit Aspose.Slides arbeiten zu können. Fügen Sie Ihrem Code die folgenden Namespaces hinzu:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Schritt 1: Instanziieren Sie die Präsentation

 In diesem Schritt erstellen wir eine Instanz von`Presentation` Klasse, die die Präsentationsdatei darstellt, mit der Sie arbeiten möchten. So können Sie es machen:

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // Ihr Code wird hier angezeigt
}
```

 Hier,`FileName` ist der Pfad zu Ihrer PowerPoint-Präsentationsdatei. Stellen Sie sicher, dass Sie den Pfad zu Ihrer Datei entsprechend anpassen.

## Schritt 2: Wählen Sie eine Layoutfolie

Im nächsten Schritt wählen Sie eine Layoutfolie aus, die Sie Ihrer Präsentation hinzufügen möchten. Mit Aspose.Slides können Sie aus verschiedenen vordefinierten Layout-Folientypen auswählen, z. B. „Titel und Objekt“ oder „Titel“. Wenn Ihre Präsentation kein bestimmtes Layout enthält, können Sie auch ein benutzerdefiniertes Layout erstellen. So können Sie eine Layoutfolie auswählen:

```csharp
IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
ILayoutSlide layoutSlide =
    layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
    layoutSlides.GetByType(SlideLayoutType.Title);
```

Wie im obigen Code gezeigt, versuchen wir, eine Layoutfolie vom Typ „Titel und Objekt“ zu finden. Wenn es nicht gefunden wird, greifen wir auf ein „Titel“-Layout zurück. Sie können diese Logik an Ihre Bedürfnisse anpassen.

## Schritt 3: Legen Sie eine leere Folie ein

 Nachdem Sie nun eine Layoutfolie ausgewählt haben, können Sie Ihrer Präsentation eine leere Folie mit diesem Layout hinzufügen. Dies wird mit der erreicht`InsertEmptySlide` Methode. Hier ist der Code für diesen Schritt:

```csharp
p.Slides.InsertEmptySlide(0, layoutSlide);
```

In diesem Beispiel fügen wir die leere Folie an Position 0 ein, Sie können jedoch bei Bedarf eine andere Position angeben.

## Schritt 4: Speichern Sie die Präsentation

 Schließlich ist es an der Zeit, Ihre aktualisierte Präsentation zu speichern. Du kannst den ... benutzen`Save`Methode, um die Präsentation im gewünschten Format zu speichern. Hier ist der Code:

```csharp
p.Save(FileName, SaveFormat.Pptx);
```

 Stellen Sie sicher, dass Sie die anpassen`FileName` Variable, um die Präsentation mit dem gewünschten Dateinamen und Format zu speichern.

Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine Layoutfolie zu Ihrer Präsentation hinzugefügt. Dies verbessert die Struktur und visuelle Attraktivität Ihrer Folien und macht Ihre Präsentation ansprechender.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Aspose.Slides für .NET verwenden, um Ihrer Präsentation Layoutfolien hinzuzufügen. Mit dem richtigen Layout werden Ihre Inhalte organisierter und optisch ansprechender präsentiert. Aspose.Slides vereinfacht diesen Prozess und ermöglicht Ihnen die einfache Erstellung professioneller Präsentationen.

Experimentieren Sie ruhig mit verschiedenen Layout-Folientypen und passen Sie Ihre Präsentationen an Ihre Bedürfnisse an. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur Verfügung, mit dem Sie Ihre Präsentationsfähigkeiten auf die nächste Stufe heben können.

## Häufig gestellte Fragen (FAQs)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine .NET-Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Es bietet eine breite Palette von Funktionen zum Erstellen, Bearbeiten und Bearbeiten von PowerPoint-Dateien.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/). Es bietet detaillierte Informationen und Beispiele, die Ihnen den Einstieg erleichtern.

### Gibt es eine kostenlose Testversion von Aspose.Slides für .NET?
 Ja, Sie können auf eine kostenlose Testversion von Aspose.Slides für .NET zugreifen[Hier](https://releases.aspose.com/). Mit dieser Testversion können Sie die Möglichkeiten der Bibliothek erkunden, bevor Sie einen Kauf tätigen.

### Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
 Sie können eine temporäre Lizenz erhalten, indem Sie hier besuchen[dieser Link](https://purchase.aspose.com/temporary-license/). Eine temporäre Lizenz ist für Evaluierungs- und Testzwecke nützlich.

### Wo kann ich Unterstützung oder Hilfe zu Aspose.Slides für .NET erhalten?
 Wenn Sie Fragen haben oder Hilfe benötigen, können Sie das Aspose.Slides für .NET-Forum unter besuchen[Aspose-Community-Forum](https://forum.aspose.com/). Die Community ist aktiv und hilfsbereit bei der Beantwortung von Benutzeranfragen.
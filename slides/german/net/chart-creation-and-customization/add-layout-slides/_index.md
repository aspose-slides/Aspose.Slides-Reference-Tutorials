---
title: Layoutfolien zur Präsentation hinzufügen
linktitle: Layoutfolien zur Präsentation hinzufügen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre PowerPoint-Präsentationen mit Aspose.Slides für .NET verbessern. Fügen Sie Layoutfolien für einen professionellen Touch hinzu.
weight: 11
url: /de/net/chart-creation-and-customization/add-layout-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Im heutigen digitalen Zeitalter ist es eine wesentliche Fähigkeit, eine wirkungsvolle Präsentation zu erstellen. Eine gut strukturierte und optisch ansprechende Präsentation kann Ihre Botschaft effektiv vermitteln. Aspose.Slides für .NET ist ein leistungsstarkes Tool, mit dem Sie im Handumdrehen beeindruckende Präsentationen erstellen können. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Slides für .NET Ihrer Präsentation Layoutfolien hinzufügen können. Wir unterteilen den Prozess in leicht verständliche Schritte, um sicherzustellen, dass Sie die Konzepte gründlich verstehen. Lassen Sie uns anfangen!

## Voraussetzungen

Bevor wir mit dem Tutorial beginnen, müssen einige Voraussetzungen erfüllt sein:

1.  Aspose.Slides für .NET-Bibliothek: Sie müssen die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/net/).

2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung wie Visual Studio eingerichtet haben, um den Code zu schreiben und auszuführen.

3. Beispielpräsentation: Sie benötigen eine PowerPoint-Beispielpräsentation zum Arbeiten. Sie können Ihre vorhandene Präsentation verwenden oder eine neue erstellen.

Nachdem Sie nun die Voraussetzungen erfüllt haben, können wir mit dem Hinzufügen von Layout-Folien zu Ihrer Präsentation fortfahren.

## Namespaces importieren

Zuerst müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren, um mit Aspose.Slides zu arbeiten. Fügen Sie Ihrem Code die folgenden Namespaces hinzu:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Schritt 1: Instanziieren der Präsentation

 In diesem Schritt erstellen wir eine Instanz des`Presentation` Klasse, die die Präsentationsdatei darstellt, mit der Sie arbeiten möchten. So können Sie es machen:

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // Ihr Code wird hier eingefügt
}
```

 Hier,`FileName` ist der Pfad zu Ihrer PowerPoint-Präsentationsdatei. Stellen Sie sicher, dass Sie den Pfad zu Ihrer Datei entsprechend anpassen.

## Schritt 2: Wählen Sie eine Layoutfolie

Im nächsten Schritt wählen Sie eine Layoutfolie aus, die Sie Ihrer Präsentation hinzufügen möchten. Aspose.Slides bietet Ihnen die Auswahl aus verschiedenen vordefinierten Layoutfolientypen, wie beispielsweise „Titel und Objekt“ oder „Titel“. Wenn Ihre Präsentation kein bestimmtes Layout enthält, können Sie auch ein benutzerdefiniertes Layout erstellen. So wählen Sie eine Layoutfolie aus:

```csharp
IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
ILayoutSlide layoutSlide =
    layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
    layoutSlides.GetByType(SlideLayoutType.Title);
```

Wie im obigen Code gezeigt, versuchen wir, eine Layoutfolie vom Typ „Titel und Objekt“ zu finden. Wenn keine gefunden wird, greifen wir auf ein „Titel“-Layout zurück. Sie können diese Logik an Ihre Bedürfnisse anpassen.

## Schritt 3: Einfügen einer leeren Folie

 Nachdem Sie nun eine Layoutfolie ausgewählt haben, können Sie Ihrer Präsentation eine leere Folie mit diesem Layout hinzufügen. Dies erreichen Sie mit dem`InsertEmptySlide` Methode. Hier ist der Code für diesen Schritt:

```csharp
p.Slides.InsertEmptySlide(0, layoutSlide);
```

In diesem Beispiel fügen wir die leere Folie an Position 0 ein, Sie können aber bei Bedarf eine andere Position angeben.

## Schritt 4: Speichern Sie die Präsentation

 Zum Schluss ist es an der Zeit, Ihre aktualisierte Präsentation zu speichern. Sie können dazu den`Save`Methode, um die Präsentation im gewünschten Format zu speichern. Hier ist der Code:

```csharp
p.Save(FileName, SaveFormat.Pptx);
```

 Stellen Sie sicher, dass Sie die`FileName` Variable, um die Präsentation mit dem gewünschten Dateinamen und Format zu speichern.

Herzlichen Glückwunsch! Sie haben Ihrer Präsentation mit Aspose.Slides für .NET erfolgreich eine Layoutfolie hinzugefügt. Dies verbessert die Struktur und die visuelle Attraktivität Ihrer Folien und macht Ihre Präsentation ansprechender.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für .NET Ihrer Präsentation Layoutfolien hinzufügen können. Mit dem richtigen Layout werden Ihre Inhalte übersichtlicher und optisch ansprechender präsentiert. Aspose.Slides vereinfacht diesen Prozess und ermöglicht Ihnen die mühelose Erstellung professioneller Präsentationen.

Experimentieren Sie mit verschiedenen Folienlayouttypen und passen Sie Ihre Präsentationen Ihren Bedürfnissen entsprechend an. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur Verfügung, mit dem Sie Ihre Präsentationsfähigkeiten auf die nächste Stufe heben können.

## Häufig gestellte Fragen (FAQs)

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine .NET-Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Sie bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Manipulieren von PowerPoint-Dateien.

### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Die Dokumentation finden Sie unter[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/). Es bietet detaillierte Informationen und Beispiele, die Ihnen den Einstieg erleichtern.

### Gibt es eine kostenlose Testversion von Aspose.Slides für .NET?
 Ja, Sie können auf eine kostenlose Testversion von Aspose.Slides für .NET zugreifen.[Hier](https://releases.aspose.com/). Mit dieser Testversion können Sie die Funktionen der Bibliothek erkunden, bevor Sie einen Kauf tätigen.

### Wie kann ich eine temporäre Lizenz für Aspose.Slides für .NET erhalten?
 Sie können eine temporäre Lizenz erhalten, indem Sie[dieser Link](https://purchase.aspose.com/temporary-license/). Eine temporäre Lizenz ist für Evaluierungs- und Testzwecke sinnvoll.

### Wo kann ich Support oder Hilfe zu Aspose.Slides für .NET erhalten?
 Wenn Sie Fragen haben oder Hilfe benötigen, können Sie das Aspose.Slides für .NET-Forum unter besuchen.[Aspose-Gemeinschaftsforum](https://forum.aspose.com/). Die Community ist aktiv und hilfsbereit bei der Beantwortung von Benutzeranfragen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

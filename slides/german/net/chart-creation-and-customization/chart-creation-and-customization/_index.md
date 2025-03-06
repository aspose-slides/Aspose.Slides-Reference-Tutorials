---
title: Diagrammerstellung und -anpassung in Aspose.Slides
linktitle: Diagrammerstellung und -anpassung in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Diagramme in PowerPoint erstellen und anpassen. Schritt-für-Schritt-Anleitung zum Erstellen dynamischer Präsentationen.
weight: 10
url: /de/net/chart-creation-and-customization/chart-creation-and-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Einführung

In der Welt der Datenpräsentation spielen visuelle Hilfsmittel eine entscheidende Rolle bei der effektiven Informationsvermittlung. PowerPoint-Präsentationen werden häufig zu diesem Zweck verwendet, und Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie Folien programmgesteuert erstellen und anpassen können. In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie Diagramme erstellen und mit Aspose.Slides für .NET anpassen.

## Voraussetzungen

Bevor wir mit dem Erstellen und Anpassen von Diagrammen beginnen, müssen die folgenden Voraussetzungen erfüllt sein:

1.  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für .NET installiert haben. Sie können sie von der[Download-Seite](https://releases.aspose.com/slides/net/).

2. Präsentationsdatei: Bereiten Sie eine PowerPoint-Präsentationsdatei vor, in der Sie die Diagramme hinzufügen und anpassen möchten.

Lassen Sie uns den Vorgang nun für ein umfassendes Tutorial in mehrere Schritte aufteilen.

## Schritt 1: Layoutfolien zur Präsentation hinzufügen

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // Versuchen Sie, nach Layout-Folientyp zu suchen
    IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
    ILayoutSlide layoutSlide =
        layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
        layoutSlides.GetByType(SlideLayoutType.Title);

    if (layoutSlide == null)
    {
        //Die Situation, wenn eine Präsentation bestimmte Layouttypen nicht enthält.
        // ...

        // Hinzufügen einer leeren Folie mit hinzugefügter Layoutfolie
        p.Slides.InsertEmptySlide(0, layoutSlide);

        // Präsentation speichern
        p.Save(FileName, SaveFormat.Pptx);
    }
}
```

In diesem Schritt erstellen wir eine neue Präsentation, suchen nach einer geeigneten Layoutfolie und fügen mit Aspose.Slides eine leere Folie hinzu.

## Schritt 2: Beispiel für Basisplatzhalter abrufen

```csharp
string presentationName = Path.Combine("Your Document Directory", "placeholder.pptx");

using (Presentation presentation = new Presentation(presentationName))
{
    ISlide slide = presentation.Slides[0];
    IShape shape = slide.Shapes[0];

    // ...

    IShape masterShape = layoutShape.GetBasePlaceholder();

    // ...
}
```

In diesem Schritt wird eine vorhandene Präsentation geöffnet und Basisplatzhalter extrahiert, sodass Sie mit den Platzhaltern in Ihren Folien arbeiten können.

## Schritt 3: Kopf- und Fußzeile in Folien verwalten

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;

    // ...

    presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
}
```

In diesem letzten Schritt verwalten wir Kopf- und Fußzeilen in Folien, indem wir ihre Sichtbarkeit umschalten, Text festlegen und Platzhalter für Datum und Uhrzeit anpassen.

Nachdem wir nun jedes Beispiel in mehrere Schritte unterteilt haben, können Sie Aspose.Slides für .NET verwenden, um PowerPoint-Präsentationen programmgesteuert zu erstellen, anzupassen und zu verwalten. Diese leistungsstarke Bibliothek bietet eine breite Palette an Funktionen, mit denen Sie mühelos ansprechende und informative Präsentationen erstellen können.

## Abschluss

Das Erstellen und Anpassen von Diagrammen in Aspose.Slides für .NET eröffnet eine Welt voller Möglichkeiten für dynamische und datengesteuerte Präsentationen. Mit diesen Schritt-für-Schritt-Anleitungen können Sie das volle Potenzial dieser Bibliothek nutzen, um Ihre PowerPoint-Präsentationen zu verbessern und Informationen effektiv zu vermitteln.

## FAQs

### Welche .NET-Versionen werden von Aspose.Slides für .NET unterstützt?
Aspose.Slides für .NET unterstützt eine Vielzahl von .NET-Versionen, einschließlich .NET Framework und .NET Core. Weitere Einzelheiten finden Sie in der Dokumentation.

### Kann ich mit Aspose.Slides für .NET komplexe Diagramme erstellen?
Ja, Sie können verschiedene Diagrammtypen erstellen, darunter Balkendiagramme, Kreisdiagramme und Liniendiagramme, mit umfassenden Anpassungsoptionen.

### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine kostenlose Testversion von der Aspose-Website herunterladen[Hier](https://releases.aspose.com/).

### Wo finde ich zusätzlichen Support und Ressourcen für Aspose.Slides für .NET?
 Besuchen Sie das Aspose-Supportforum[Hier](https://forum.aspose.com/) für alle Fragen oder Hilfe, die Sie benötigen.

### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
Ja, Sie können eine temporäre Lizenz von der Aspose-Website erhalten[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

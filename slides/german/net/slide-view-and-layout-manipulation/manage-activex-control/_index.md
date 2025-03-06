---
title: Verwalten von ActiveX-Steuerelementen in PowerPoint
linktitle: Verwalten von ActiveX-Steuerelementen in PowerPoint
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit ActiveX-Steuerelementen mithilfe von Aspose.Slides für .NET verbessern können. Unsere Schritt-für-Schritt-Anleitung behandelt Einfügung, Bearbeitung, Anpassung, Ereignisbehandlung und mehr.
type: docs
weight: 13
url: /de/net/slide-view-and-layout-manipulation/manage-activex-control/
---
ActiveX-Steuerelemente sind leistungsstarke Elemente, die die Funktionalität und Interaktivität Ihrer PowerPoint-Präsentationen verbessern können. Mit diesen Steuerelementen können Sie Objekte wie Multimedia-Player, Dateneingabeformulare und mehr direkt in Ihre Folien einbetten und bearbeiten. In diesem Artikel erfahren Sie, wie Sie ActiveX-Steuerelemente in PowerPoint mit Aspose.Slides für .NET verwalten, einer vielseitigen Bibliothek, die eine nahtlose Integration und Bearbeitung von PowerPoint-Dateien in Ihren .NET-Anwendungen ermöglicht.

## Hinzufügen von ActiveX-Steuerelementen zu PowerPoint-Folien

Um mit der Einbindung von ActiveX-Steuerelementen in Ihre PowerPoint-Präsentationen zu beginnen, führen Sie die folgenden Schritte aus:

1.  Erstellen Sie eine neue PowerPoint-Präsentation: Erstellen Sie zunächst eine neue PowerPoint-Präsentation mit Aspose.Slides für .NET. Weitere Informationen finden Sie im[Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/) Anleitungen zum Arbeiten mit Präsentationen.

2. Folie hinzufügen: Verwenden Sie die Bibliothek, um Ihrer Präsentation eine neue Folie hinzuzufügen. Dies ist die Folie, auf der Sie das ActiveX-Steuerelement einfügen möchten.

3. Einfügen des ActiveX-Steuerelements: Jetzt ist es an der Zeit, das ActiveX-Steuerelement in die Folie einzufügen. Sie können dies erreichen, indem Sie dem folgenden Beispielcode folgen:

```csharp
// Laden Sie die Präsentation
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Holen Sie sich die Folie, wo Sie das ActiveX-Steuerelement einfügen möchten
ISlide slide = presentation.Slides[0];

// Definieren Sie die Eigenschaften des ActiveX-Steuerelements
int left = 100; // Geben Sie die linke Position an
int top = 100; // Geben Sie die oberste Position an
int width = 200; // Geben Sie die Breite an
int height = 100; // Geben Sie die Höhe an
string progId = "YourActiveXControl.ProgID"; // Geben Sie die ProgID des ActiveX-Steuerelements an

// Fügen Sie der Folie das ActiveX-Steuerelement hinzu
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Ersetzen Sie unbedingt`"YourActiveXControl.ProgID"` durch die tatsächliche ProgID des ActiveX-Steuerelements, das Sie einfügen möchten.

4. Speichern der Präsentation: Nachdem Sie das ActiveX-Steuerelement eingefügt haben, speichern Sie die Präsentation mit dem folgenden Code:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Programmgesteuertes Bearbeiten von ActiveX-Steuerelementen

Nachdem Sie das ActiveX-Steuerelement zu Ihrer Folie hinzugefügt haben, möchten Sie es möglicherweise programmgesteuert bearbeiten. So können Sie das tun:

1. Zugriff auf das ActiveX-Steuerelement: Um auf die Eigenschaften und Methoden des ActiveX-Steuerelements zuzugreifen, müssen Sie einen Verweis darauf erhalten. Verwenden Sie den folgenden Code, um das Steuerelement von der Folie abzurufen:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Methoden aufrufen: Sie können Methoden des ActiveX-Steuerelements mithilfe der erhaltenen Referenz aufrufen. Wenn das ActiveX-Steuerelement beispielsweise eine Methode namens „Play“ hat, können Sie sie folgendermaßen aufrufen:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Eigenschaften festlegen: Sie können Eigenschaften des ActiveX-Steuerelements auch programmgesteuert festlegen. Wenn das Steuerelement beispielsweise eine Eigenschaft namens „Lautstärke“ hat, können Sie diese folgendermaßen festlegen:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Anpassen der Eigenschaften von ActiveX-Steuerelementen

Durch Anpassen der Eigenschaften Ihres ActiveX-Steuerelements können Sie die Benutzerfreundlichkeit Ihrer Präsentation erheblich verbessern. So können Sie diese Eigenschaften anpassen:

1.  Zugriff auf Eigenschaften: Wie bereits erwähnt, können Sie auf die Eigenschaften des ActiveX-Steuerelements zugreifen, indem Sie`IOleObjectFrame` Referenz.

2.  Eigenschaften festlegen: Verwenden Sie die`SetProperty`Methode, um verschiedene Eigenschaften des ActiveX-Steuerelements festzulegen. Sie können beispielsweise die Hintergrundfarbe folgendermaßen ändern:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Behandeln von Ereignissen im Zusammenhang mit ActiveX-Steuerelementen

ActiveX-Steuerelemente verfügen häufig über zugehörige Ereignisse, die Aktionen basierend auf Benutzerinteraktionen auslösen können. So können Sie diese Ereignisse handhaben:

1. Ereignisse abonnieren: Abonnieren Sie zunächst das gewünschte Ereignis des ActiveX-Steuerelements. Wenn das Steuerelement beispielsweise ein „Klick“-Ereignis hat, können Sie es folgendermaßen abonnieren:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Ihr Ereignisbehandlungscode hier
};
```

## Löschen von ActiveX-Steuerelementen aus Folien

Wenn Sie ein ActiveX-Steuerelement aus einer Folie entfernen möchten, führen Sie die folgenden Schritte aus:

1.  Zugriff auf das Steuerelement: Erhalten Sie einen Verweis auf das ActiveX-Steuerelement mit dem`IOleObjectFrame` Referenz wie zuvor gezeigt.

2. Entfernen des Steuerelements: Verwenden Sie den folgenden Code, um das Steuerelement von der Folie zu entfernen:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Speichern und Exportieren der geänderten Präsentation

Nachdem Sie alle notwendigen Änderungen an Ihrer Präsentation vorgenommen haben, können Sie diese mit dem folgenden Code speichern und exportieren:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Vorteile der Verwendung von Aspose.Slides für .NET

Aspose.Slides für .NET vereinfacht die Arbeit mit ActiveX-Steuerelementen in PowerPoint-Präsentationen, indem es eine benutzerfreundliche API bereitstellt, mit der Sie diese Steuerelemente nahtlos integrieren und bearbeiten können. Einige Vorteile der Verwendung von Aspose.Slides für .NET sind:

- Einfaches Einfügen von ActiveX-Steuerelementen in Folien.
- Umfassende Methoden zur programmgesteuerten Interaktion mit Steuerelementen.
- Vereinfachte Anpassung der Steuerelementeigenschaften.
- Effizientes Eventhandling für interaktive Präsentationen.
- Optimiertes Entfernen von Steuerelementen aus Folien.

## Abschluss

Durch die Einbindung von ActiveX-Steuerelementen in Ihre PowerPoint-Präsentationen können Sie die Interaktivität und das Engagement Ihres Publikums steigern. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur nahtlosen Verwaltung von ActiveX-Steuerelementen zur Verfügung, mit dem Sie dynamische und fesselnde Präsentationen erstellen können, die einen bleibenden Eindruck hinterlassen.

## FAQs

### Wie kann ich einer bestimmten Folie ein ActiveX-Steuerelement hinzufügen?

 Um ein ActiveX-Steuerelement zu einer bestimmten Folie hinzuzufügen, können Sie das`AddOleObjectFrame` Methode bereitgestellt von Aspose.Slides für .NET. Mit dieser Methode können Sie die Position, Größe und ProgID des ActiveX-Steuerelements angeben, das Sie einfügen möchten.

### Kann ich ActiveX-Steuerelemente programmgesteuert bearbeiten?

 Ja, Sie können ActiveX-Steuerelemente programmgesteuert mit Aspose.Slides für .NET bearbeiten. Indem Sie einen Verweis auf die`IOleObjectFrame` Bei der Darstellung des Steuerelements können Sie Methoden aufrufen und Eigenschaften festlegen, um dynamisch mit dem Steuerelement zu interagieren.

### Wie gehe ich mit Ereignissen um?

 durch ActiveX-Steuerelemente ausgelöst?

Sie können Ereignisse, die von ActiveX-Steuerelementen ausgelöst werden, behandeln, indem Sie die entsprechenden Ereignisse abonnieren. Dazu verwenden Sie den`EventClick` (oder ähnlicher) Ereignishandler. Damit können Sie bestimmte Aktionen als Reaktion auf Benutzerinteraktionen mit dem Steuerelement ausführen.

### Ist es möglich, das Erscheinungsbild von ActiveX-Steuerelementen anzupassen?

 Natürlich können Sie das Erscheinungsbild von ActiveX-Steuerelementen anpassen, indem Sie`SetProperty` Methode bereitgestellt von Aspose.Slides für .NET. Mit dieser Methode können Sie verschiedene Eigenschaften ändern, wie z. B. Hintergrundfarbe, Schriftstil und mehr.

### Kann ich ein ActiveX-Steuerelement aus einer Folie entfernen?

 Ja, Sie können ein ActiveX-Steuerelement von einer Folie entfernen, indem Sie`Remove` Methode der`Shapes` Sammlung. Übergeben Sie den Verweis an die`IOleObjectFrame` Darstellung des Steuerelements als Argument für den`Remove` Methode, und das Steuerelement wird von der Folie entfernt.
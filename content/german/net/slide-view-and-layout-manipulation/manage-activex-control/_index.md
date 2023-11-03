---
title: Verwalten Sie das ActiveX-Steuerelement in PowerPoint
linktitle: Verwalten Sie das ActiveX-Steuerelement in PowerPoint
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit ActiveX-Steuerelementen mithilfe von Aspose.Slides für .NET verbessern. Unsere Schritt-für-Schritt-Anleitung behandelt das Einfügen, Bearbeiten, Anpassen, Ereignishandling und mehr.
type: docs
weight: 13
url: /de/net/slide-view-and-layout-manipulation/manage-activex-control/
---
ActiveX-Steuerelemente sind leistungsstarke Elemente, die die Funktionalität und Interaktivität Ihrer PowerPoint-Präsentationen verbessern können. Mit diesen Steuerelementen können Sie Objekte wie Multimedia-Player, Dateneingabeformulare usw. direkt in Ihre Folien einbetten und bearbeiten. In diesem Artikel erfahren Sie, wie Sie ActiveX-Steuerelemente in PowerPoint mithilfe von Aspose.Slides für .NET verwalten, einer vielseitigen Bibliothek, die eine nahtlose Integration und Bearbeitung von PowerPoint-Dateien in Ihre .NET-Anwendungen ermöglicht.

## Hinzufügen von ActiveX-Steuerelementen zu PowerPoint-Folien

Führen Sie die folgenden Schritte aus, um mit der Integration von ActiveX-Steuerelementen in Ihre PowerPoint-Präsentationen zu beginnen:

1.  Erstellen Sie eine neue PowerPoint-Präsentation: Erstellen Sie zunächst eine neue PowerPoint-Präsentation mit Aspose.Slides für .NET. Sie können sich auf die beziehen[Aspose.Slides für .NET API-Referenz](https://reference.aspose.com/slides/net/) für Anleitungen zum Arbeiten mit Präsentationen.

2. Eine Folie hinzufügen: Verwenden Sie die Bibliothek, um Ihrer Präsentation eine neue Folie hinzuzufügen. Dies ist die Folie, auf der Sie das ActiveX-Steuerelement einfügen möchten.

3. Einfügen des ActiveX-Steuerelements: Jetzt ist es an der Zeit, das ActiveX-Steuerelement auf der Folie einzufügen. Sie können dies erreichen, indem Sie dem folgenden Beispielcode folgen:

```csharp
// Laden Sie die Präsentation
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Rufen Sie die Folie auf, an der Sie das ActiveX-Steuerelement einfügen möchten
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

 Unbedingt austauschen`"YourActiveXControl.ProgID"` mit der tatsächlichen ProgID des ActiveX-Steuerelements, das Sie einfügen möchten.

4. Speichern Sie die Präsentation: Speichern Sie die Präsentation nach dem Einfügen des ActiveX-Steuerelements mit dem folgenden Code:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Programmgesteuertes Bearbeiten von ActiveX-Steuerelementen

Nachdem Sie das ActiveX-Steuerelement zu Ihrer Folie hinzugefügt haben, möchten Sie es möglicherweise programmgesteuert bearbeiten. So können Sie es machen:

1. Auf das ActiveX-Steuerelement zugreifen: Um auf die Eigenschaften und Methoden des ActiveX-Steuerelements zuzugreifen, müssen Sie einen Verweis darauf erhalten. Verwenden Sie den folgenden Code, um das Steuerelement von der Folie abzurufen:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Methoden aufrufen: Sie können Methoden des ActiveX-Steuerelements mithilfe der erhaltenen Referenz aufrufen. Wenn das ActiveX-Steuerelement beispielsweise über eine Methode namens „Play“ verfügt, können Sie diese folgendermaßen aufrufen:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Eigenschaften festlegen: Sie können Eigenschaften des ActiveX-Steuerelements auch programmgesteuert festlegen. Wenn das Steuerelement beispielsweise über eine Eigenschaft namens „Volume“ verfügt, können Sie diese wie folgt festlegen:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Anpassen der ActiveX-Steuerelementeigenschaften

Das Anpassen der Eigenschaften Ihres ActiveX-Steuerelements kann das Benutzererlebnis Ihrer Präsentation erheblich verbessern. So können Sie diese Eigenschaften anpassen:

1.  Zugriffseigenschaften: Wie bereits erwähnt, können Sie mit auf die Eigenschaften des ActiveX-Steuerelements zugreifen`IOleObjectFrame` Referenz.

2.  Eigenschaften festlegen: Verwenden Sie die`SetProperty`Methode zum Festlegen verschiedener Eigenschaften des ActiveX-Steuerelements. Sie können die Hintergrundfarbe beispielsweise wie folgt ändern:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Umgang mit Ereignissen im Zusammenhang mit ActiveX-Steuerelementen

ActiveX-Steuerelemente verfügen häufig über zugehörige Ereignisse, die auf der Grundlage von Benutzerinteraktionen Aktionen auslösen können. So können Sie mit diesen Ereignissen umgehen:

1. Ereignisse abonnieren: Abonnieren Sie zunächst das gewünschte Ereignis des ActiveX-Steuerelements. Wenn das Steuerelement beispielsweise über ein „Clicked“-Ereignis verfügt, können Sie es wie folgt abonnieren:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Ihr Event-Handling-Code hier
};
```

## ActiveX-Steuerelemente aus Folien löschen

Wenn Sie ein ActiveX-Steuerelement von einer Folie entfernen möchten, gehen Sie folgendermaßen vor:

1.  Greifen Sie auf das Steuerelement zu: Rufen Sie mithilfe von einen Verweis auf das ActiveX-Steuerelement ab`IOleObjectFrame` Referenz wie zuvor gezeigt.

2. Entfernen Sie das Steuerelement: Verwenden Sie den folgenden Code, um das Steuerelement von der Folie zu entfernen:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Speichern und Exportieren der geänderten Präsentation

Nachdem Sie alle notwendigen Änderungen an Ihrer Präsentation vorgenommen haben, können Sie sie mit dem folgenden Code speichern und exportieren:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Vorteile der Verwendung von Aspose.Slides für .NET

Aspose.Slides für .NET vereinfacht die Arbeit mit ActiveX-Steuerelementen in PowerPoint-Präsentationen, indem es eine benutzerfreundliche API bereitstellt, mit der Sie diese Steuerelemente nahtlos integrieren und bearbeiten können. Zu den Vorteilen der Verwendung von Aspose.Slides für .NET gehören:

- Einfaches Einfügen von ActiveX-Steuerelementen in Folien.
- Umfassende Methoden für die programmgesteuerte Interaktion mit Steuerelementen.
- Vereinfachte Anpassung der Steuereigenschaften.
- Effizientes Event-Handling für interaktive Präsentationen.
- Optimierte Entfernung von Steuerelementen von Folien.

## Abschluss

Durch die Integration von ActiveX-Steuerelementen in Ihre PowerPoint-Präsentationen können Sie die Interaktivität und das Engagement Ihres Publikums steigern. Mit Aspose.Slides für .NET steht Ihnen ein leistungsstarkes Tool zur nahtlosen Verwaltung von ActiveX-Steuerelementen zur Verfügung, mit dem Sie dynamische und fesselnde Präsentationen erstellen können, die einen bleibenden Eindruck hinterlassen.

## FAQs

### Wie kann ich einer bestimmten Folie ein ActiveX-Steuerelement hinzufügen?

Um einer bestimmten Folie ein ActiveX-Steuerelement hinzuzufügen, können Sie das verwenden`AddOleObjectFrame` Methode, die von Aspose.Slides für .NET bereitgestellt wird. Mit dieser Methode können Sie die Position, Größe und ProgID des ActiveX-Steuerelements angeben, das Sie einfügen möchten.

### Kann ich ActiveX-Steuerelemente programmgesteuert bearbeiten?

 Ja, Sie können ActiveX-Steuerelemente programmgesteuert mit Aspose.Slides für .NET bearbeiten. Durch Einholen eines Verweises auf die`IOleObjectFrame` Wenn Sie das Steuerelement darstellen, können Sie Methoden aufrufen und Eigenschaften festlegen, um dynamisch mit dem Steuerelement zu interagieren.

### Wie gehe ich mit Ereignissen um?

 ausgelöst durch ActiveX-Steuerelemente?

 Sie können von ActiveX-Steuerelementen ausgelöste Ereignisse verarbeiten, indem Sie die entsprechenden Ereignisse mit abonnieren`EventClick` (oder ähnlicher) Event-Handler. Dadurch können Sie als Reaktion auf Benutzerinteraktionen mit dem Steuerelement bestimmte Aktionen ausführen.

### Ist es möglich, das Erscheinungsbild von ActiveX-Steuerelementen anzupassen?

 Auf jeden Fall können Sie das Erscheinungsbild von ActiveX-Steuerelementen mithilfe von anpassen`SetProperty`Methode, die von Aspose.Slides für .NET bereitgestellt wird. Mit dieser Methode können Sie verschiedene Eigenschaften ändern, z. B. Hintergrundfarbe, Schriftstil und mehr.

### Kann ich ein ActiveX-Steuerelement von einer Folie entfernen?

 Ja, Sie können ein ActiveX-Steuerelement mithilfe von von einer Folie entfernen`Remove` Methode der`Shapes` Sammlung. Übergeben Sie den Verweis auf die`IOleObjectFrame` Darstellung der Kontrolle als Argument für die`Remove` Methode, und das Steuerelement wird von der Folie entfernt.
---
title: Hinzufügen einer stilvollen Notizformatierung mit Aspose.Slides für .NET
linktitle: Fügen Sie eine Notizenfolie mit stilvoller Notizenformatierung hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET stilvolle Notizformate zu Ihren PowerPoint-Präsentationen hinzufügen. Werten Sie Ihre Folien mit Symbolen und Aufzählungspunkten auf.
type: docs
weight: 14
url: /de/net/slide-access-and-manipulation/add-notes-slide-with-notes-style/
---

In der Welt der Präsentationen kommt es nicht nur auf die Inhalte an, die Sie liefern, sondern auch darauf, wie Sie diese präsentieren. Eine stilvolle Formatierung von Notizen kann die Wirkung Ihrer Präsentation erheblich beeinflussen. Mit Aspose.Slides für .NET können Sie Ihre PowerPoint-Präsentationen ganz einfach verbessern, indem Sie stilvolle Notizen mit Aufzählungspunkten und Symbolen hinzufügen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Hinzufügens stilvoller Notizformate zu Ihren PowerPoint-Folien.

## Voraussetzungen

Bevor wir uns mit der Schritt-für-Schritt-Anleitung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Aspose.Slides für .NET
    Sie müssen Aspose.Slides für .NET installiert haben. Wenn Sie es noch nicht getan haben, können Sie es von der Website herunterladen[Hier](https://releases.aspose.com/slides/net/).

### 2. Eine PowerPoint-Präsentation
   Sie sollten über eine PowerPoint-Präsentationsdatei (PPTX) verfügen, der Sie eine stilvolle Notizformatierung hinzufügen möchten. Stellen Sie sicher, dass Sie den Pfad zu dieser Präsentationsdatei kennen.

Nachdem wir nun unsere Voraussetzungen parat haben, fahren wir mit der Schritt-für-Schritt-Anleitung fort.

## Schritt 1: Namespaces importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren. Diese Namespaces sind für die Arbeit mit Aspose.Slides für .NET unerlässlich. So können Sie es machen:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Schritt 2: Fügen Sie eine stilvolle Notizformatierung hinzu

Kommen wir nun zum Kern unseres Tutorials – dem Hinzufügen einer stilvollen Notizformatierung zu Ihren PowerPoint-Folien. Zum besseren Verständnis unterteilen wir dies in mehrere Schritte:

### Schritt 2.1: Instanziieren Sie die Präsentationsklasse

 Zuerst müssen wir eine Instanz davon erstellen`Presentation` Klasse, die Ihre PowerPoint-Präsentationsdatei darstellt. Sie sollten den Pfad zu Ihrer Präsentationsdatei im angeben`dataDir` Variable.

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // Ihr Code kommt hierher
}
```

### Schritt 2.2: Greifen Sie auf die Master Notes-Folie zu

 Innerhalb der`using` Block, greifen wir auf die Masternotizen-Folie zu. Die Masternotizenfolie enthält den Standardstil für Notizen in Ihrer Präsentation.

```csharp
IMasterNotesSlide notesMaster = presentation.MasterNotesSlideManager.MasterNotesSlide;

if (notesMaster != null)
{
    // Ihr Code kommt hierher
}
```

### Schritt 2.3: Holen Sie sich den Notizenstil

Jetzt rufen wir den Textstil der Masternotizen-Folie ab. Diesen Stil werden wir ändern, um unseren Notizen Stil zu verleihen.

```csharp
ITextStyle notesStyle = notesMaster.NotesStyle;
```

### Schritt 2.4: Aufzählungspunkte festlegen

In diesem Schritt legen wir Symbolaufzählungszeichen für die Absätze der ersten Ebene in den Notizen fest. Dadurch werden stilvolle Aufzählungspunkte in Ihren Notizen erstellt.

```csharp
IParagraphFormat paragraphFormat = notesStyle.GetLevel(0);
paragraphFormat.Bullet.Type = BulletType.Symbol;
```

### Schritt 2.5: Speichern Sie die Präsentation

Schließlich speichern wir die geänderte Präsentation auf der Festplatte und erstellen eine neue PowerPoint-Datei mit der stilvollen Notizformatierung.

```csharp
presentation.Save(dataDir + "StylishNotesPresentation.pptx", SaveFormat.Pptx);
```

Und das ist es! Sie haben Ihrer PowerPoint-Präsentation mit Aspose.Slides für .NET erfolgreich eine stilvolle Notizformatierung hinzugefügt.

## Abschluss

Wenn Sie Ihre PowerPoint-Präsentationen mit einer stilvollen Notizformatierung aufwerten, können Sie deren optische Attraktivität und Effektivität deutlich verbessern. Mit Aspose.Slides für .NET wird der Prozess einfach und zugänglich, sodass Sie mühelos professionell aussehende Präsentationen erstellen können.

Integrieren Sie diese Technik in Ihre Präsentationen und Sie sind auf dem besten Weg, wirkungsvolle Inhalte mit Stil zu liefern.

## Häufig gestellte Fragen

### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek für die programmgesteuerte Arbeit mit Microsoft PowerPoint-Dateien. Es ermöglicht Ihnen, PowerPoint-Präsentationen mithilfe von .NET-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren.

### Wo finde ich die Dokumentation zu Aspose.Slides für .NET?
 Sie können auf die Dokumentation zugreifen[Hier](https://reference.aspose.com/slides/net/). Es bietet umfassende Informationen zur Nutzung der Bibliothek.

### Ist die Nutzung von Aspose.Slides für .NET kostenlos?
 Aspose.Slides für .NET ist eine kommerzielle Bibliothek und erfordert für die vollständige Nutzung eine Lizenz. Sie können es jedoch mit einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).

### Kann ich Aspose.Slides für .NET mit einer temporären Lizenz testen?
 Ja, Sie können eine temporäre Lizenz zu Test- und Evaluierungszwecken bei erhalten[Hier](https://purchase.aspose.com/temporary-license/).

### Gibt es ein Community-Forum oder Support für Aspose.Slides für .NET?
 Ja, Sie können im Aspose.Slides für .NET-Community-Forum Hilfe suchen und an Diskussionen teilnehmen[Hier](https://forum.aspose.com/).
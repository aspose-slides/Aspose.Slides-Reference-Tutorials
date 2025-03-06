---
title: Folie ans Ende einer bestehenden Präsentation duplizieren
linktitle: Folie ans Ende einer bestehenden Präsentation duplizieren
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET eine Folie duplizieren und am Ende einer vorhandenen PowerPoint-Präsentation hinzufügen. Diese Schritt-für-Schritt-Anleitung enthält Quellcodebeispiele und behandelt Einrichtung, Folienduplizierung, Änderung und mehr.
weight: 22
url: /de/net/slide-access-and-manipulation/clone-slide-within-same-presentation-to-end/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, auf verschiedene Weise mit PowerPoint-Präsentationen zu arbeiten, einschließlich der programmgesteuerten Erstellung, Änderung und Bearbeitung von Folien. Es unterstützt eine breite Palette von Funktionen und ist daher eine beliebte Wahl für die Automatisierung von Aufgaben im Zusammenhang mit Präsentationen.

## Schritt 1: Einrichten des Projekts

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können sie von der[Download-Link](https://releases.aspose.com/slides/net/). Erstellen Sie ein neues Visual Studio-Projekt und fügen Sie einen Verweis auf die heruntergeladene Aspose.Slides-Bibliothek hinzu.

## Schritt 2: Eine vorhandene Präsentation laden

In diesem Schritt laden wir eine vorhandene PowerPoint-Präsentation mit Aspose.Slides für .NET. Sie können den folgenden Codeausschnitt als Referenz verwenden:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Laden Sie die vorhandene Präsentation
        Presentation presentation = new Presentation("existing-presentation.pptx");
    }
}
```

 Ersetzen`"existing-presentation.pptx"`durch den Pfad zu Ihrer eigentlichen PowerPoint-Präsentationsdatei.

## Schritt 3: Eine Folie duplizieren

Um eine Folie zu duplizieren, müssen wir zunächst die Folie auswählen, die wir duplizieren möchten. Dann klonen wir sie, um eine identische Kopie zu erstellen. So geht's:

```csharp
// Wählen Sie die zu duplizierende Folie aus (Index beginnt bei 0)
ISlide sourceSlide = presentation.Slides[0];

// Ausgewählte Folie klonen
ISlide duplicatedSlide = presentation.Slides.InsertClone(1, sourceSlide);
```

In diesem Beispiel duplizieren wir die erste Folie und fügen die duplizierte Folie am Index 1 (Position 2) ein.

## Schritt 4: Duplizierte Folie am Ende hinzufügen

Da wir nun eine duplizierte Folie haben, fügen wir sie am Ende der Präsentation hinzu. Sie können den folgenden Code verwenden:

```csharp
// Fügen Sie die duplizierte Folie am Ende der Präsentation hinzu
presentation.Slides.AddClone(duplicatedSlide);
```

Dieser Codeausschnitt fügt die duplizierte Folie am Ende der Präsentation hinzu.

## Schritt 5: Speichern der geänderten Präsentation

Nachdem wir die duplizierte Folie hinzugefügt haben, müssen wir die geänderte Präsentation speichern. So geht's:

```csharp
//Speichern der geänderten Präsentation
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

 Ersetzen`"modified-presentation.pptx"` durch den gewünschten Namen für die geänderte Präsentation.

## Abschluss

In dieser Anleitung haben wir untersucht, wie man mit Aspose.Slides für .NET eine Folie dupliziert und sie am Ende einer vorhandenen PowerPoint-Präsentation hinzufügt. Diese leistungsstarke Bibliothek vereinfacht die programmgesteuerte Arbeit mit Präsentationen und bietet eine breite Palette von Funktionen für verschiedene Aufgaben.

## Häufig gestellte Fragen

### Wie kann ich Aspose.Slides für .NET erhalten?

 Sie können die Aspose.Slides für .NET-Bibliothek von der[Download-Link](https://releases.aspose.com/slides/net/). Befolgen Sie unbedingt die Installationsanweisungen auf der Website.

### Kann ich mehrere Folien gleichzeitig duplizieren?

Ja, Sie können mehrere Folien gleichzeitig duplizieren, indem Sie die Folien durchlaufen und sie nach Bedarf klonen. Passen Sie den Code entsprechend Ihren Anforderungen an.

### Ist die Nutzung von Aspose.Slides für .NET kostenlos?

Nein, Aspose.Slides für .NET ist eine kommerzielle Bibliothek, für deren Nutzung eine gültige Lizenz erforderlich ist. Sie können die Preisdetails auf der Aspose-Website prüfen.

### Unterstützt Aspose.Slides andere Dateiformate?

Ja, Aspose.Slides unterstützt verschiedene PowerPoint-Formate, darunter PPT, PPTX, PPS und mehr. Eine vollständige Liste der unterstützten Formate finden Sie in der Dokumentation.

### Kann ich Folieninhalte mit Aspose.Slides ändern?

Auf jeden Fall! Mit Aspose.Slides können Sie Folien nicht nur duplizieren, sondern auch deren Inhalt wie Text, Bilder, Formen und Animationen programmgesteuert bearbeiten.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

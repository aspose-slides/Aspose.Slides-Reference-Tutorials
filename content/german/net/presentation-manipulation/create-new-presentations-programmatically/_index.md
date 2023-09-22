---
title: Erstellen Sie programmgesteuert neue Präsentationen
linktitle: Erstellen Sie programmgesteuert neue Präsentationen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Präsentationen programmgesteuert mit Aspose.Slides für .NET erstellen. Schritt-für-Schritt-Anleitung mit Quellcode für effiziente Automatisierung.
type: docs
weight: 10
url: /de/net/presentation-manipulation/create-new-presentations-programmatically/
---

Wenn Sie Präsentationen programmgesteuert in .NET erstellen möchten, ist Aspose.Slides für .NET ein leistungsstarkes Tool, mit dem Sie diese Aufgabe effizient erledigen können. Dieses Schritt-für-Schritt-Tutorial führt Sie durch den Prozess der Erstellung neuer Präsentationen mithilfe des bereitgestellten Quellcodes.

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine robuste Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Ob Sie Berichte erstellen, Präsentationen automatisieren oder Folien bearbeiten müssen, Aspose.Slides bietet eine breite Palette von Funktionen, die Ihnen die Aufgabe erleichtern.

## Schritt 1: Einrichten Ihrer Umgebung

Bevor wir uns mit dem Code befassen, müssen Sie Ihre Entwicklungsumgebung einrichten. Stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Visual Studio oder eine beliebige .NET-Entwicklungsumgebung.
-  Aspose.Slides für .NET-Bibliothek (Sie können sie herunterladen[Hier](https://releases.aspose.com/slides/net/)).

## Schritt 2: Erstellen einer Präsentation

Beginnen wir mit der Erstellung einer neuen Präsentation mit dem folgenden Code:

```csharp
// Erstellen Sie eine Präsentation
Presentation pres = new Presentation();
```

Dieser Code initialisiert ein neues Präsentationsobjekt, das als Grundlage für Ihre PowerPoint-Datei dient.

## Schritt 3: Hinzufügen einer Titelfolie

In den meisten Präsentationen ist die erste Folie eine Titelfolie. So können Sie einen hinzufügen:

```csharp
// Fügen Sie die Titelfolie hinzu
Slide slide = pres.AddTitleSlide();
```

Dieser Code fügt Ihrer Präsentation eine Titelfolie hinzu.

## Schritt 4: Titel und Untertitel festlegen

Legen wir nun den Titel und den Untertitel für Ihre Titelfolie fest:

```csharp
// Legen Sie den Titeltext fest
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// Legen Sie den Untertiteltext fest
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

Ersetzen Sie „Überschrift des Folientitels“ und „Unterüberschrift des Folientitels“ durch die gewünschten Titel.

## Schritt 5: Speichern Sie Ihre Präsentation

Zum Schluss speichern wir Ihre Präsentation in einer Datei:

```csharp
// Ausgabe auf die Festplatte schreiben
pres.Write("outAsposeSlides.ppt");
```

Dieser Code speichert Ihre Präsentation als „outAsposeSlides.ppt“ in Ihrem Projektverzeichnis.

## Abschluss

Glückwunsch! Sie haben gerade programmgesteuert eine PowerPoint-Präsentation mit Aspose.Slides für .NET erstellt. Diese leistungsstarke Bibliothek bietet Ihnen die Flexibilität, Ihre Präsentationen problemlos zu automatisieren und anzupassen.

Jetzt können Sie damit beginnen, diesen Code in Ihre .NET-Projekte zu integrieren, um dynamische Präsentationen zu erstellen, die auf Ihre spezifischen Anforderungen zugeschnitten sind.

## FAQs

1. ### Ist die Nutzung von Aspose.Slides für .NET kostenlos?
    Nein, Aspose.Slides für .NET ist eine kommerzielle Bibliothek. Hier finden Sie Preis- und Lizenzinformationen[Hier](https://purchase.aspose.com/buy).

2. ### Benötige ich spezielle Berechtigungen, um Aspose.Slides für .NET in meinen Projekten zu verwenden?
    Sie benötigen eine gültige Lizenz, um Aspose.Slides für .NET verwenden zu können. Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zur Auswertung.

3. ### Wo finde ich Unterstützung für Aspose.Slides für .NET?
    Für technische Unterstützung und Diskussionen können Sie das Aspose.Slides-Forum besuchen[Hier](https://forum.aspose.com/).

4. ### Kann ich Aspose.Slides für .NET vor dem Kauf testen?
    Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET herunterladen[Hier](https://releases.aspose.com/)Die Testversion unterliegt Einschränkungen. Überprüfen Sie daher unbedingt, ob sie Ihren Anforderungen entspricht.
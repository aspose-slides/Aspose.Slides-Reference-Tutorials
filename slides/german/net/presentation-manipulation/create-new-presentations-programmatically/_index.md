---
title: Neue Präsentationen programmgesteuert erstellen
linktitle: Neue Präsentationen programmgesteuert erstellen
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET programmgesteuert Präsentationen erstellen. Schritt-für-Schritt-Anleitung mit Quellcode für effiziente Automatisierung.
weight: 10
url: /de/net/presentation-manipulation/create-new-presentations-programmatically/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Neue Präsentationen programmgesteuert erstellen


Wenn Sie Präsentationen programmgesteuert in .NET erstellen möchten, ist Aspose.Slides für .NET ein leistungsstarkes Tool, mit dem Sie diese Aufgabe effizient erledigen können. Dieses Schritt-für-Schritt-Tutorial führt Sie durch den Prozess der Erstellung neuer Präsentationen mit dem bereitgestellten Quellcode.

## Einführung in Aspose.Slides für .NET

Aspose.Slides für .NET ist eine robuste Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten. Ob Sie Berichte erstellen, Präsentationen automatisieren oder Folien bearbeiten müssen, Aspose.Slides bietet eine breite Palette an Funktionen, die Ihnen die Arbeit erleichtern.

## Schritt 1: Einrichten Ihrer Umgebung

Bevor wir uns in den Code vertiefen, müssen Sie Ihre Entwicklungsumgebung einrichten. Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder jede andere .NET-Entwicklungsumgebung.
-  Aspose.Slides für .NET-Bibliothek (Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/)).

## Schritt 2: Erstellen einer Präsentation

Beginnen wir mit der Erstellung einer neuen Präsentation mit dem folgenden Code:

```csharp
// Erstellen einer Präsentation
Presentation pres = new Presentation();
```

Dieser Code initialisiert ein neues Präsentationsobjekt, das als Grundlage für Ihre PowerPoint-Datei dient.

## Schritt 3: Hinzufügen einer Titelfolie

In den meisten Präsentationen ist die erste Folie eine Titelfolie. So können Sie eine hinzufügen:

```csharp
// Fügen Sie die Titelfolie hinzu
Slide slide = pres.AddTitleSlide();
```

Dieser Code fügt Ihrer Präsentation eine Titelfolie hinzu.

## Schritt 4: Titel und Untertitel festlegen

Legen wir nun den Titel und Untertitel für Ihre Titelfolie fest:

```csharp
// Legen Sie den Titeltext fest
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// Untertiteltext festlegen
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

Ersetzen Sie „Überschrift des Folientitels“ und „Unterüberschrift des Folientitels“ durch die gewünschten Titel.

## Schritt 5: Speichern Ihrer Präsentation

Zum Schluss speichern wir Ihre Präsentation in einer Datei:

```csharp
// Ausgabe auf die Festplatte schreiben
pres.Write("outAsposeSlides.ppt");
```

Dieser Code speichert Ihre Präsentation als „outAsposeSlides.ppt“ in Ihrem Projektverzeichnis.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade programmgesteuert eine PowerPoint-Präsentation mit Aspose.Slides für .NET erstellt. Diese leistungsstarke Bibliothek bietet Ihnen die Flexibilität, Ihre Präsentationen mühelos zu automatisieren und anzupassen.

Jetzt können Sie damit beginnen, diesen Code in Ihre .NET-Projekte zu integrieren, um dynamische Präsentationen zu erstellen, die auf Ihre spezifischen Anforderungen zugeschnitten sind.

## FAQs

1. ### Ist die Nutzung von Aspose.Slides für .NET kostenlos?
    Nein, Aspose.Slides für .NET ist eine kommerzielle Bibliothek. Preis- und Lizenzinformationen finden Sie[Hier](https://purchase.aspose.com/buy).

2. ### Benötige ich besondere Berechtigungen, um Aspose.Slides für .NET in meinen Projekten zu verwenden?
    Sie benötigen eine gültige Lizenz, um Aspose.Slides für .NET zu verwenden. Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zur Auswertung.

3. ### Wo finde ich Unterstützung für Aspose.Slides für .NET?
    Für technische Unterstützung und Diskussionen können Sie das Aspose.Slides-Forum besuchen[Hier](https://forum.aspose.com/).

4. ### Kann ich Aspose.Slides für .NET vor dem Kauf ausprobieren?
    Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET herunterladen[Hier](https://releases.aspose.com/). Die Testversion weist Einschränkungen auf. Prüfen Sie daher unbedingt, ob sie Ihren Anforderungen entspricht.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

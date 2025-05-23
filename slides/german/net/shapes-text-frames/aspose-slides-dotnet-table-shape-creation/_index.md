---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET dynamische Tabellen und Formen in PowerPoint-Präsentationen erstellen. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine verbesserte Optik."
"title": "Erstellen von Tabellen und Formen in PowerPoint mit Aspose.Slides für .NET – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Tabellen und Formen in PowerPoint mit Aspose.Slides für .NET: Eine Schritt-für-Schritt-Anleitung

## Einführung

Optimieren Sie Ihre PowerPoint-Präsentationen durch die Erstellung dynamischer Tabellen oder das Zeichnen von Formen um Text mit C# und Aspose.Slides für .NET. Diese Anleitung führt Sie durch die Implementierung von Tabellenerstellungs- und Formzeichnungsfunktionen und macht Ihre Folien informativer und optisch ansprechender.

In diesem Tutorial behandeln wir:
- Erstellen von Tabellen in PowerPoint-Präsentationen
- Absätze mit Textteilen in Tabellenzellen einfügen
- Einbetten von Textrahmen in Formen
- Zeichnen von Rechtecken um bestimmte Textelemente

Am Ende dieses Leitfadens sind Sie bestens gerüstet, Ihre Präsentationsfolien mit Aspose.Slides für .NET zu optimieren. Lassen Sie uns zunächst die Voraussetzungen betrachten.

### Voraussetzungen

Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Entwicklungsumgebung**: Visual Studio auf Ihrem Computer installiert.
- **Aspose.Slides für die .NET-Bibliothek**: Wir verwenden Version 22.x oder höher.
- **Grundlegende C#-Kenntnisse**: Vertrautheit mit der Syntax und den Konzepten von C# ist erforderlich.

## Einrichten von Aspose.Slides für .NET

Bevor wir mit dem Programmieren beginnen, richten wir die Aspose.Slides-Bibliothek in Ihrem Projekt ein. Es gibt mehrere Möglichkeiten, sie zu installieren:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paket-Manager-Konsole**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**: Suchen Sie nach „Aspose.Slides“ und klicken Sie auf die Schaltfläche Installieren.

### Lizenzerwerb

Sie können mit einer kostenlosen Testlizenz beginnen, um alle Funktionen zu erkunden. Für eine längere Nutzung können Sie eine temporäre oder kostenpflichtige Lizenz erwerben. [Aspose-Website](https://purchase.aspose.com/buy).

Initialisieren Sie Aspose.Slides nach der Installation in Ihrem Projekt, indem Sie Folgendes hinzufügen:

```csharp
using Aspose.Slides;
```

## Implementierungshandbuch

### Erstellen einer Tabelle auf einer Folie

**Überblick:**
Das Erstellen von Tabellen ist grundlegend für die übersichtliche Darstellung von Daten. Mit Aspose.Slides können Sie Tabellenabmessungen und -positionen einfach definieren.

#### Schritt 1: Präsentation initialisieren
Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse:

```csharp
Presentation pres = new Presentation();
```

#### Schritt 2: Eine Tabelle hinzufügen
Verwenden Sie die `AddTable` Methode, um Ihrer Folie eine Tabelle hinzuzufügen. Geben Sie die Position und Größe für Zeilen und Spalten an:

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**Erklärte Parameter:**
- `50, 50`: X- und Y-Koordinaten für die obere linke Ecke.
- Arrays geben Spaltenbreiten und Zeilenhöhen an.

#### Schritt 3: Präsentation speichern
Speichern Sie abschließend Ihre Präsentation:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
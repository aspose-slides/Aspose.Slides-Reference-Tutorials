---
title: Erstellen von Rechteckformen mit Aspose.Slides für .NET
linktitle: Erstellen einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Welt dynamischer PowerPoint-Präsentationen mit Aspose.Slides für .NET. Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie ansprechende Rechteckformen in Folien erstellen.
type: docs
weight: 12
url: /de/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## Einführung
Wenn Sie Ihre .NET-Anwendungen mit dynamischen und optisch ansprechenden PowerPoint-Präsentationen erweitern möchten, ist Aspose.Slides für .NET Ihre Lösung der Wahl. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Entwicklungscomputer installiert ist.
-  Aspose.Slides für .NET: Laden Sie die Aspose.Slides für .NET-Bibliothek herunter und installieren Sie sie[Hier](https://releases.aspose.com/slides/net/).
- Grundlegende C#-Kenntnisse: Vertrautheit mit der Programmiersprache C# ist unerlässlich.
## Namespaces importieren
Beginnen Sie in Ihrem C#-Projekt mit dem Importieren der erforderlichen Namespaces, um auf die Funktionen von Aspose.Slides zuzugreifen:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Richten Sie das Projekt ein
Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Visual Studio. Stellen Sie sicher, dass Aspose.Slides für .NET in Ihrem Projekt korrekt referenziert wird.
## Schritt 2: Präsentationsobjekt initialisieren
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Hier finden Sie Ihren Code für die nächsten Schritte.
}
```
## Schritt 3: Holen Sie sich die erste Folie
```csharp
ISlide sld = pres.Slides[0];
```
## Schritt 4: Rechteck-AutoForm hinzufügen
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Dieser Code fügt an den Koordinaten (50, 150) eine Rechteckform mit einer Breite von 150 und einer Höhe von 50 hinzu.
## Schritt 5: Speichern Sie die Präsentation
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Dieser Schritt speichert die Präsentation mit der hinzugefügten Rechteckform im angegebenen Verzeichnis.
## Abschluss
Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine einfache Rechteckform in einer Präsentationsfolie erstellt. Das ist erst der Anfang – Aspose.Slides bietet eine breite Palette an Funktionen, mit denen Sie Ihre Präsentationen weiter anpassen und verbessern können.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?
Ja, Aspose.Slides für .NET ist plattformunabhängig und kann sowohl in Windows- als auch in Linux-Umgebungen verwendet werden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wie erhalte ich Unterstützung für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung der Gemeinschaft.
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/slides/net/).
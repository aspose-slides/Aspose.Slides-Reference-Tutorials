---
title: Erstellen rechteckiger Formen mit Aspose.Slides für .NET
linktitle: Erstellen einer einfachen rechteckigen Form in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Welt dynamischer PowerPoint-Präsentationen mit Aspose.Slides für .NET. Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie ansprechende Rechteckformen in Folien erstellen.
type: docs
weight: 12
url: /de/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## Einführung
Wenn Sie Ihre .NET-Anwendungen mit dynamischen und optisch ansprechenden PowerPoint-Präsentationen verbessern möchten, ist Aspose.Slides für .NET Ihre Lösung. In diesem Tutorial führen wir Sie durch den Prozess der Erstellung einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Entwicklungscomputer installiert ist.
-  Aspose.Slides für .NET: Laden Sie die Aspose.Slides für .NET-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/slides/net/).
- Grundlegende C#-Kenntnisse: Vertrautheit mit der Programmiersprache C# ist unbedingt erforderlich.
## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt zunächst die erforderlichen Namespaces, um auf die Aspose.Slides-Funktionen zuzugreifen:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Einrichten des Projekts
Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Visual Studio. Stellen Sie sicher, dass in Ihrem Projekt korrekt auf Aspose.Slides für .NET verwiesen wird.
## Schritt 2: Präsentationsobjekt initialisieren
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ihr Code für die nächsten Schritte wird hier eingefügt.
}
```
## Schritt 3: Holen Sie sich die erste Folie
```csharp
ISlide sld = pres.Slides[0];
```
## Schritt 4: Rechteckige AutoForm hinzufügen
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Dieser Code fügt bei den Koordinaten (50, 150) eine rechteckige Form mit einer Breite von 150 und einer Höhe von 50 hinzu.
## Schritt 5: Speichern Sie die Präsentation
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Dieser Schritt speichert die Präsentation mit der hinzugefügten Rechteckform im angegebenen Verzeichnis.
## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine einfache rechteckige Form in einer Präsentationsfolie erstellt. Dies ist erst der Anfang – Aspose.Slides bietet eine breite Palette an Funktionen zum weiteren Anpassen und Verbessern Ihrer Präsentationen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?
Ja, Aspose.Slides für .NET ist plattformunabhängig und kann sowohl in Windows- als auch in Linux-Umgebungen verwendet werden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
 Ja, Sie können eine kostenlose Testversion erhalten[Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für .NET?
 Besuche den[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung der Community.
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
 Ja, Sie können eine temporäre Lizenz erwerben[Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
 Weitere Informationen finden Sie in der Dokumentation[Hier](https://reference.aspose.com/slides/net/).
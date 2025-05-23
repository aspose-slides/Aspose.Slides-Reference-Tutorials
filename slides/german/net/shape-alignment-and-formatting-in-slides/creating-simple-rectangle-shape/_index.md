---
"description": "Entdecken Sie die Welt dynamischer PowerPoint-Präsentationen mit Aspose.Slides für .NET. Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie ansprechende Rechteckformen in Folien erstellen."
"linktitle": "Erstellen einer einfachen rechteckigen Form in Präsentationsfolien mit Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Erstellen von Rechteckformen mit Aspose.Slides für .NET"
"url": "/de/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen von Rechteckformen mit Aspose.Slides für .NET

## Einführung
Wenn Sie Ihre .NET-Anwendungen mit dynamischen und optisch ansprechenden PowerPoint-Präsentationen erweitern möchten, ist Aspose.Slides für .NET die ideale Lösung. In diesem Tutorial führen wir Sie durch die Erstellung einer einfachen Rechteckform in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Entwicklungscomputer installiert ist.
- Aspose.Slides für .NET: Laden Sie die Aspose.Slides für .NET-Bibliothek herunter und installieren Sie sie von [Hier](https://releases.aspose.com/slides/net/).
- Grundlegende C#-Kenntnisse: Kenntnisse der Programmiersprache C# sind unerlässlich.
## Namespaces importieren
Beginnen Sie in Ihrem C#-Projekt mit dem Importieren der erforderlichen Namespaces, um auf die Funktionen von Aspose.Slides zuzugreifen:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Schritt 1: Einrichten des Projekts
Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Stellen Sie sicher, dass Aspose.Slides für .NET in Ihrem Projekt korrekt referenziert wird.
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
## Schritt 4: Rechteck-AutoForm hinzufügen
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
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine einfache Rechteckform in einer Präsentationsfolie erstellt. Dies ist erst der Anfang – Aspose.Slides bietet zahlreiche Funktionen zur weiteren Anpassung und Verbesserung Ihrer Präsentationen.
## Häufig gestellte Fragen
### Kann ich Aspose.Slides für .NET sowohl in Windows- als auch in Linux-Umgebungen verwenden?
Ja, Aspose.Slides für .NET ist plattformunabhängig und kann sowohl in Windows- als auch in Linux-Umgebungen verwendet werden.
### Gibt es eine kostenlose Testversion für Aspose.Slides für .NET?
Ja, Sie können eine kostenlose Testversion erhalten [Hier](https://releases.aspose.com/).
### Wie erhalte ich Support für Aspose.Slides für .NET?
Besuchen Sie die [Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung der Gemeinschaft.
### Kann ich eine temporäre Lizenz für Aspose.Slides für .NET erwerben?
Ja, Sie können eine temporäre Lizenz erwerben [Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich die Dokumentation für Aspose.Slides für .NET?
Weitere Informationen finden Sie in der Dokumentation [Hier](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
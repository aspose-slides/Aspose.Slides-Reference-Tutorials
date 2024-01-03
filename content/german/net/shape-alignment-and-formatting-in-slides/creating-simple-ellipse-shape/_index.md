---
title: Erstellen Sie ganz einfach eine Ellipsenform mit Aspose.Slides .NET
linktitle: Erstellen einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET beeindruckende Ellipsenformen in Präsentationsfolien erstellen. Einfache Schritte für dynamisches Design!
type: docs
weight: 11
url: /de/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## Einführung
In der dynamischen Welt des Präsentationsdesigns kann die Integration von Formen wie Ellipsen einen Hauch von Kreativität und Professionalität verleihen. Aspose.Slides für .NET bietet eine leistungsstarke Lösung für die programmgesteuerte Bearbeitung von Präsentationsdateien. Dieses Tutorial führt Sie durch den Prozess der Erstellung einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für .NET installiert haben. Sie können es hier herunterladen[Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie eine .NET-Entwicklungsumgebung auf Ihrem Computer ein.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Diese Namespaces stellen die wesentlichen Klassen und Methoden bereit, die für die Arbeit mit Präsentationsfolien und -formen erforderlich sind.
## Schritt 1: Richten Sie die Präsentation ein
Erstellen Sie zunächst eine neue Präsentation und greifen Sie auf die erste Folie zu. Fügen Sie den folgenden Code hinzu, um dies zu erreichen:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instanziieren Sie die Präsentationsklasse
using (Presentation pres = new Presentation())
{
    // Holen Sie sich die erste Folie
    ISlide sld = pres.Slides[0];
```
Dieser Code initialisiert eine neue Präsentation und wählt die erste Folie zur weiteren Bearbeitung aus.
## Schritt 2: Ellipsenform hinzufügen
Nun fügen wir der Folie mithilfe von eine Ellipsenform hinzu`AddAutoShape` Methode:
```csharp
// Fügen Sie eine automatische Form vom Typ Ellipse hinzu
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Diese Codezeile erstellt eine Ellipsenform an den Koordinaten (50, 150) mit einer Breite von 150 Einheiten und einer Höhe von 50 Einheiten.
## Schritt 3: Speichern Sie die Präsentation
Speichern Sie abschließend die geänderte Präsentation mit dem folgenden Code unter einem angegebenen Dateinamen auf der Festplatte:
```csharp
// Schreiben Sie die PPTX-Datei auf die Festplatte
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Durch diesen Schritt wird sichergestellt, dass Ihre Änderungen beibehalten werden und Sie die resultierende Präsentation mit der neu hinzugefügten Ellipsenform anzeigen können.
## Abschluss
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## FAQs
### Kann ich die Ellipsenform weiter anpassen?
Ja, Sie können verschiedene Eigenschaften der Ellipsenform ändern, z. B. Farbe, Größe und Position, um Ihren spezifischen Designanforderungen gerecht zu werden.
### Ist Aspose.Slides mit den neuesten .NET-Frameworks kompatibel?
Ja, Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Frameworks sicherzustellen.
### Wo finde ich weitere Tutorials und Beispiele für Aspose.Slides?
 Besuche den[Dokumentation](https://reference.aspose.com/slides/net/) Ausführliche Anleitungen und Beispiele finden Sie hier.
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
 Folge dem[temporärer Lizenzlink](https://purchase.aspose.com/temporary-license/) eine temporäre Lizenz zu Testzwecken anzufordern.
### Benötigen Sie Hilfe oder haben Sie spezielle Fragen?
 Besuche den[Aspose.Slides-Supportforum](https://forum.aspose.com/c/slides/11) um Hilfe von der Community und Experten zu erhalten.
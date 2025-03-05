---
title: Ändern von OLE-Objektdaten in Präsentationen mit Aspose.Slides
linktitle: Ändern von OLE-Objektdaten in Präsentationen mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Slides für .NET beim mühelosen Ändern von OLE-Objektdaten. Verbessern Sie Ihre Präsentationen mit dynamischen Inhalten.
type: docs
weight: 25
url: /de/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## Einführung
Das Erstellen dynamischer und interaktiver PowerPoint-Präsentationen ist in der heutigen digitalen Welt eine gängige Anforderung. Ein leistungsstarkes Tool hierfür ist Aspose.Slides für .NET, eine robuste Bibliothek, mit der Entwickler PowerPoint-Präsentationen programmgesteuert bearbeiten und verbessern können. In diesem Tutorial werden wir uns mit dem Prozess des Änderns von OLE-Objektdaten (Object Linking and Embedding) in Präsentationsfolien mithilfe von Aspose.Slides befassen.
## Voraussetzungen
Bevor Sie mit der Arbeit mit Aspose.Slides für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit installiertem .NET ein.
2.  Aspose.Slides-Bibliothek: Laden Sie die Aspose.Slides-Bibliothek für .NET herunter und installieren Sie sie. Sie finden die Bibliothek[Hier](https://releases.aspose.com/slides/net/).
3. Grundlegendes Verständnis: Machen Sie sich mit den grundlegenden Konzepten der C#-Programmierung und PowerPoint-Präsentationen vertraut.
## Namespaces importieren
Importieren Sie in Ihr C#-Projekt die erforderlichen Namespaces, um die Aspose.Slides-Funktionen zu nutzen:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Erstellung eines neuen C#-Projekts und dem Importieren der Aspose.Slides-Bibliothek. Stellen Sie sicher, dass Ihr Projekt richtig konfiguriert ist und die erforderlichen Abhängigkeiten vorhanden sind.
## Schritt 2: Auf Präsentation und Folie zugreifen
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Schritt 3: OLE-Objekt lokalisieren
Durchsuchen Sie alle Formen in der Folie, um den OLE-Objektrahmen zu finden:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Schritt 4: Lesen und Ändern von Arbeitsmappendaten
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Lesen von Objektdaten im Arbeitsbuch
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Ändern der Arbeitsmappendaten
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Ändern von Ole-Frame-Objektdaten
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Schritt 5: Speichern Sie die Präsentation
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Abschluss
Wenn Sie diese Schritte befolgen, können Sie OLE-Objektdaten in Präsentationsfolien mithilfe von Aspose.Slides für .NET nahtlos ändern. Dies eröffnet Ihnen eine Welt voller Möglichkeiten für die Erstellung dynamischer und individueller Präsentationen, die auf Ihre spezifischen Anforderungen zugeschnitten sind.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die programmgesteuerte Arbeit mit PowerPoint-Präsentationen sowie deren einfache Bearbeitung und Verbesserung ermöglicht.
### Wo finde ich die Aspose.Slides-Dokumentation?
 Die Dokumentation für Aspose.Slides für .NET finden Sie[Hier](https://reference.aspose.com/slides/net/).
### Wie lade ich Aspose.Slides für .NET herunter?
 Sie können die Bibliothek von der Release-Seite herunterladen[Hier](https://releases.aspose.com/slides/net/).
### Gibt es eine kostenlose Testversion für Aspose.Slides?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo erhalte ich Support für Aspose.Slides für .NET?
 Für Unterstützung und Diskussionen besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
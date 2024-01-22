---
title: Ändern von OLE-Objektdaten in der Präsentation mit Aspose.Slides
linktitle: Ändern von OLE-Objektdaten in der Präsentation mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Slides für .NET bei der mühelosen Änderung von OLE-Objektdaten. Werten Sie Ihre Präsentationen mit dynamischen Inhalten auf.
type: docs
weight: 25
url: /de/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## Einführung
Die Erstellung dynamischer und interaktiver PowerPoint-Präsentationen ist in der heutigen digitalen Welt eine häufige Anforderung. Ein leistungsstarkes Tool, um dies zu erreichen, ist Aspose.Slides für .NET, eine robuste Bibliothek, die es Entwicklern ermöglicht, PowerPoint-Präsentationen programmgesteuert zu bearbeiten und zu verbessern. In diesem Tutorial befassen wir uns mit dem Prozess der Änderung von OLE-Objektdaten (Object Linking and Embedding) in Präsentationsfolien mithilfe von Aspose.Slides.
## Voraussetzungen
Bevor Sie mit Aspose.Slides für .NET arbeiten, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit installiertem .NET ein.
2.  Aspose.Slides-Bibliothek: Laden Sie die Aspose.Slides für .NET-Bibliothek herunter und installieren Sie sie. Sie finden die Bibliothek[Hier](https://releases.aspose.com/slides/net/).
3. Grundverständnis: Machen Sie sich mit den Grundkonzepten der C#-Programmierung und PowerPoint-Präsentationen vertraut.
## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um die Funktionen von Aspose.Slides zu nutzen:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Schritt 1: Richten Sie Ihr Projekt ein
Beginnen Sie mit der Erstellung eines neuen C#-Projekts und dem Import der Aspose.Slides-Bibliothek. Stellen Sie sicher, dass Ihr Projekt richtig konfiguriert ist und die erforderlichen Abhängigkeiten vorhanden sind.
## Schritt 2: Greifen Sie auf Präsentation und Folie zu
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Schritt 3: Suchen Sie das OLE-Objekt
Durchlaufen Sie alle Formen auf der Folie, um den OLE-Objektrahmen zu finden:
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
## Schritt 4: Arbeitsmappendaten lesen und ändern
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Objektdaten in der Arbeitsmappe lesen
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
            // Ole-Frame-Objektdaten ändern
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
Wenn Sie diese Schritte befolgen, können Sie OLE-Objektdaten in Präsentationsfolien mit Aspose.Slides für .NET nahtlos ändern. Dies eröffnet eine Welt voller Möglichkeiten für die Erstellung dynamischer und individueller Präsentationen, die auf Ihre spezifischen Bedürfnisse zugeschnitten sind.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für .NET?
Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten und so eine einfache Bearbeitung und Verbesserung zu ermöglichen.
### Wo finde ich die Aspose.Slides-Dokumentation?
 Die Dokumentation für Aspose.Slides für .NET finden Sie hier[Hier](https://reference.aspose.com/slides/net/).
### Wie lade ich Aspose.Slides für .NET herunter?
 Sie können die Bibliothek von der Release-Seite herunterladen[Hier](https://releases.aspose.com/slides/net/).
### Gibt es eine kostenlose Testversion für Aspose.Slides?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.aspose.com/).
### Wo erhalte ich Unterstützung für Aspose.Slides für .NET?
 Für Unterstützung und Diskussionen besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
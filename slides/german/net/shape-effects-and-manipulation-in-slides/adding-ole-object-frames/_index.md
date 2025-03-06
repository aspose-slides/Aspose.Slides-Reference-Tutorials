---
title: Hinzufügen von OLE-Objektrahmen zur Präsentation mit Aspose.Slides
linktitle: Hinzufügen von OLE-Objektrahmen zur Präsentation mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit dynamischen Inhalten verbessern können! Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Aspose.Slides für .NET. Steigern Sie jetzt das Engagement!
weight: 15
url: /de/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial beschäftigen wir uns mit dem Hinzufügen von OLE-Objektrahmen (Object Linking and Embedding) zu Präsentationsfolien mithilfe von Aspose.Slides für .NET. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Dateien zu arbeiten. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um OLE-Objekte nahtlos in Ihre Präsentationsfolien einzubetten und Ihre PowerPoint-Dateien mit dynamischen und interaktiven Inhalten zu erweitern.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Slides für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für .NET installiert haben. Sie können sie von der[Aspose.Slides für .NET-Dokumentation](https://reference.aspose.com/slides/net/).
2. Dokumentverzeichnis: Erstellen Sie auf Ihrem System ein Verzeichnis, in dem Sie die erforderlichen Dateien speichern können. Den Pfad zu diesem Verzeichnis können Sie im bereitgestellten Codeausschnitt festlegen.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihr Projekt:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## Schritt 1: Präsentation vorbereiten
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instanziieren Sie die Präsentationsklasse, die PPTX darstellt
using (Presentation pres = new Presentation())
{
    // Greifen Sie auf die erste Folie zu
    ISlide sld = pres.Slides[0];
    
    // Fahren Sie mit den nächsten Schritten fort ...
}
```
## Schritt 2: Laden Sie ein OLE-Objekt (Excel-Datei) in den Stream
```csharp
// Laden Sie eine Excel-Datei zum Streamen
MemoryStream mstream = new MemoryStream();
using (FileStream fs = new FileStream(dataDir + "book1.xlsx", FileMode.Open, FileAccess.Read))
{
    byte[] buf = new byte[4096];
    while (true)
    {
        int bytesRead = fs.Read(buf, 0, buf.Length);
        if (bytesRead <= 0)
            break;
        mstream.Write(buf, 0, bytesRead);
    }
}
```
## Schritt 3: Datenobjekt zum Einbetten erstellen
```csharp
// Datenobjekt zum Einbetten erstellen
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.ToArray(), "xlsx");
```
## Schritt 4: Fügen Sie eine OLE-Objektrahmenform hinzu
```csharp
//Hinzufügen einer OLE-Objektrahmenform
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## Schritt 5: Speichern Sie die Präsentation
```csharp
// Schreiben Sie die PPTX-Datei auf die Festplatte
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
Jetzt haben Sie mit Aspose.Slides für .NET erfolgreich einen OLE-Objektrahmen zu Ihrer Präsentationsfolie hinzugefügt.
## Abschluss
In diesem Tutorial haben wir die nahtlose Integration von OLE-Objektrahmen in PowerPoint-Folien mithilfe von Aspose.Slides für .NET untersucht. Diese Funktion verbessert Ihre Präsentationen, indem sie die dynamische Einbettung verschiedener Objekte, wie z. B. Excel-Tabellen, ermöglicht und so ein interaktiveres Benutzererlebnis bietet.
## FAQs
### F: Kann ich mit Aspose.Slides für .NET andere Objekte als Excel-Tabellen einbetten?
A: Ja, Aspose.Slides unterstützt das Einbetten verschiedener OLE-Objekte, einschließlich Word-Dokumente und PDF-Dateien.
### F: Wie gehe ich mit Fehlern während des Einbettungsprozesses von OLE-Objekten um?
A: Stellen Sie sicher, dass in Ihrem Code eine ordnungsgemäße Ausnahmebehandlung erfolgt, um alle Probleme zu beheben, die während des Einbettungsvorgangs auftreten können.
### F: Ist Aspose.Slides mit den neuesten PowerPoint-Dateiformaten kompatibel?
A: Ja, Aspose.Slides unterstützt die neuesten PowerPoint-Dateiformate, einschließlich PPTX.
### F: Kann ich das Erscheinungsbild des eingebetteten OLE-Objektrahmens anpassen?
A: Auf jeden Fall. Sie können die Größe, Position und andere Eigenschaften des OLE-Objektrahmens nach Ihren Wünschen anpassen.
### F: Wo kann ich Unterstützung suchen, wenn ich während der Implementierung auf Herausforderungen stoße?
 A: Besuchen Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für die Unterstützung und Anleitung der Community.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

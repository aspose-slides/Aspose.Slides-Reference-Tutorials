---
title: Leitfaden zum Einbetten von OLE-Objekten mit Aspose.Slides für .NET
linktitle: Ersetzen des Bildtitels des OLE-Objektrahmens in Präsentationsfolien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationsfolien mit dynamischen OLE-Objekten mithilfe von Aspose.Slides für .NET verbessern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 15
url: /de/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Einführung
Die Erstellung dynamischer und ansprechender Präsentationsfolien erfordert häufig die Einbindung verschiedener Multimedia-Elemente. In diesem Tutorial erfahren Sie, wie Sie den Bildtitel eines OLE-Objektrahmens (Object Linking and Embedding) in Präsentationsfolien mithilfe der leistungsstarken Bibliothek Aspose.Slides für .NET ersetzen. Aspose.Slides vereinfacht den Umgang mit OLE-Objekten und stellt Entwicklern die Tools zur Verfügung, mit denen sie ihre Präsentationen problemlos verbessern können.
## Voraussetzungen
Bevor wir uns mit der Schritt-für-Schritt-Anleitung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides for .NET-Bibliothek installiert haben. Sie können es hier herunterladen[Aspose.Slides .NET-Dokumentation](https://reference.aspose.com/slides/net/).
- Beispieldaten: Bereiten Sie eine Beispiel-Excel-Datei (z. B. „ExcelObject.xlsx“) vor, die Sie als OLE-Objekt in die Präsentation einbetten möchten. Darüber hinaus benötigen Sie eine Bilddatei (z. B. „Image.png“), die als Symbol für das OLE-Objekt dient.
- Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit den erforderlichen Tools ein, z. B. Visual Studio oder eine andere bevorzugte IDE für die .NET-Entwicklung.
## Namespaces importieren
Stellen Sie in Ihrem .NET-Projekt sicher, dass Sie die erforderlichen Namespaces für die Arbeit mit Aspose.Slides importieren:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
```csharp
string dataDir = "Your Document Directory";
```
Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis ersetzen.
## Schritt 2: Definieren Sie die Pfade für OLE-Quelldateien und Symboldateien
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Aktualisieren Sie diese Pfade mit den tatsächlichen Pfaden zu Ihrer Beispiel-Excel-Datei und Bilddatei.
## Schritt 3: Erstellen Sie eine Präsentationsinstanz
```csharp
using (Presentation pres = new Presentation())
{
    // Der Code für die nachfolgenden Schritte wird hier angezeigt
}
```
 Initialisieren Sie eine neue Instanz von`Presentation` Klasse.
## Schritt 4: OLE-Objektrahmen hinzufügen
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Fügen Sie der Folie einen OLE-Objektrahmen hinzu und geben Sie dessen Position und Abmessungen an.
## Schritt 5: Bildobjekt hinzufügen
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Lesen Sie die Bilddatei und fügen Sie sie als Bildobjekt zur Präsentation hinzu.
## Schritt 6: Stellen Sie die Beschriftung auf das OLE-Symbol ein
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Legen Sie die gewünschte Beschriftung für das OLE-Symbol fest.
## Abschluss
Das Einbinden von OLE-Objekten in Ihre Präsentationsfolien mit Aspose.Slides für .NET ist ein unkomplizierter Vorgang. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt, vom Einrichten des Dokumentverzeichnisses bis zum Hinzufügen und Anpassen von OLE-Objekten. Experimentieren Sie mit verschiedenen Dateitypen und Beschriftungen, um die visuelle Attraktivität Ihrer Präsentationen zu verbessern.
## FAQs
### Kann ich mit Aspose.Slides andere Dateitypen als OLE-Objekte einbetten?
Ja, Aspose.Slides unterstützt das Einbetten verschiedener Dateitypen, z. B. Excel-Tabellen, Word-Dokumente und mehr.
### Ist das OLE-Objektsymbol anpassbar?
Absolut. Sie können das Standardsymbol durch ein beliebiges Bild Ihrer Wahl ersetzen, um es besser zum Thema Ihrer Präsentation zu passen.
### Bietet Aspose.Slides Unterstützung für Animationen mit OLE-Objekten?
Ab der neuesten Version konzentriert sich Aspose.Slides auf die Einbettung und Anzeige von OLE-Objekten und verarbeitet Animationen innerhalb der OLE-Objekte nicht direkt.
### Kann ich OLE-Objekte programmgesteuert bearbeiten, nachdem ich sie einer Folie hinzugefügt habe?
Sicherlich. Sie haben die vollständige programmgesteuerte Kontrolle über OLE-Objekte und können deren Eigenschaften und Erscheinungsbild nach Bedarf ändern.
### Gibt es Einschränkungen hinsichtlich der Größe der eingebetteten OLE-Objekte?
Obwohl es Größenbeschränkungen gibt, sind sie im Allgemeinen großzügig. Es wird empfohlen, Tests mit Ihrem spezifischen Anwendungsfall durchzuführen, um eine optimale Leistung sicherzustellen.
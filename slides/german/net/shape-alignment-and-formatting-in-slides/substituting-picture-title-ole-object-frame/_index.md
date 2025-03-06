---
title: Anleitung zum Einbetten von OLE-Objekten mit Aspose.Slides für .NET
linktitle: Ersetzen des Bildtitels durch einen OLE-Objektrahmen in Präsentationsfolien
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie Ihre Präsentationsfolien mit Aspose.Slides für .NET mit dynamischen OLE-Objekten verbessern können. Folgen Sie unserer Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 15
url: /de/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Einführung
Beim Erstellen dynamischer und ansprechender Präsentationsfolien müssen häufig verschiedene Multimedia-Elemente integriert werden. In diesem Tutorial erfahren Sie, wie Sie mithilfe der leistungsstarken Aspose.Slides-Bibliothek für .NET den Bildtitel eines OLE-Objektrahmens (Object Linking and Embedding) in Präsentationsfolien ersetzen können. Aspose.Slides vereinfacht den Umgang mit OLE-Objekten und bietet Entwicklern die Tools, mit denen sie ihre Präsentationen mühelos verbessern können.
## Voraussetzungen
Bevor wir in die Schritt-für-Schritt-Anleitung eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können sie von der[Aspose.Slides .NET Dokumentation](https://reference.aspose.com/slides/net/).
- Beispieldaten: Bereiten Sie eine Excel-Beispieldatei (z. B. „ExcelObject.xlsx“) vor, die Sie als OLE-Objekt in die Präsentation einbetten möchten. Halten Sie außerdem eine Bilddatei (z. B. „Image.png“) bereit, die als Symbol für das OLE-Objekt dient.
- Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit den erforderlichen Tools ein, beispielsweise Visual Studio oder eine andere bevorzugte IDE für die .NET-Entwicklung.
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
## Schritt 1: Einrichten des Dokumentverzeichnisses
```csharp
string dataDir = "Your Document Directory";
```
Stellen Sie sicher, dass Sie „Ihr Dokumentverzeichnis“ durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis ersetzen.
## Schritt 2: Definieren Sie die OLE-Quelldatei- und Symboldateipfade
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Aktualisieren Sie diese Pfade mit den tatsächlichen Pfaden zu Ihrer Beispiel-Excel-Datei und Bilddatei.
## Schritt 3: Erstellen einer Präsentationsinstanz
```csharp
using (Presentation pres = new Presentation())
{
    // Der Code für die nachfolgenden Schritte wird hier eingefügt.
}
```
 Initialisieren Sie eine neue Instanz des`Presentation` Klasse.
## Schritt 4: OLE-Objektrahmen hinzufügen
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Fügen Sie der Folie einen OLE-Objektrahmen hinzu und geben Sie seine Position und Abmessungen an.
## Schritt 5: Bildobjekt hinzufügen
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Lesen Sie die Bilddatei ein und fügen Sie sie der Präsentation als Bildobjekt hinzu.
## Schritt 6: Beschriftung auf OLE-Symbol setzen
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Legen Sie die gewünschte Beschriftung für das OLE-Symbol fest.
## Abschluss
Das Einbinden von OLE-Objekten in Ihre Präsentationsfolien mit Aspose.Slides für .NET ist ein unkomplizierter Vorgang. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt, vom Einrichten des Dokumentverzeichnisses bis zum Hinzufügen und Anpassen von OLE-Objekten. Experimentieren Sie mit verschiedenen Dateitypen und Beschriftungen, um die visuelle Attraktivität Ihrer Präsentationen zu verbessern.
## FAQs
### Kann ich mit Aspose.Slides andere Dateitypen als OLE-Objekte einbetten?
Ja, Aspose.Slides unterstützt das Einbetten verschiedener Dateitypen, wie Excel-Tabellen, Word-Dokumente und mehr.
### Ist das OLE-Objektsymbol anpassbar?
Auf jeden Fall. Sie können das Standardsymbol durch ein beliebiges Bild Ihrer Wahl ersetzen, das besser zum Thema Ihrer Präsentation passt.
### Bietet Aspose.Slides Unterstützung für Animationen mit OLE-Objekten?
Ab der neuesten Version konzentriert sich Aspose.Slides auf das Einbetten und Anzeigen von OLE-Objekten und verarbeitet Animationen innerhalb der OLE-Objekte nicht direkt.
### Kann ich OLE-Objekte programmgesteuert bearbeiten, nachdem ich sie einer Folie hinzugefügt habe?
Natürlich. Sie haben die volle programmtechnische Kontrolle über OLE-Objekte und können deren Eigenschaften und Erscheinungsbild nach Bedarf ändern.
### Gibt es irgendwelche Beschränkungen hinsichtlich der Größe der eingebetteten OLE-Objekte?
Es gibt zwar Größenbeschränkungen, diese sind jedoch im Allgemeinen großzügig. Es wird empfohlen, mit Ihrem spezifischen Anwendungsfall zu testen, um optimale Leistung sicherzustellen.
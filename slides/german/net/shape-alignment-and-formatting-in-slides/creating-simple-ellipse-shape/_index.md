---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET beeindruckende Ellipsenformen in Präsentationsfolien erstellen. Einfache Schritte für dynamisches Design!"
"linktitle": "Erstellen einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Erstellen Sie ganz einfach Ellipsenformen mit Aspose.Slides .NET"
"url": "/de/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie ganz einfach Ellipsenformen mit Aspose.Slides .NET

## Einführung
In der dynamischen Welt des Präsentationsdesigns können Formen wie Ellipsen einen Hauch von Kreativität und Professionalität verleihen. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zur programmgesteuerten Bearbeitung von Präsentationsdateien. Dieses Tutorial führt Sie durch die Erstellung einer einfachen Ellipsenform in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass Sie die Aspose.Slides-Bibliothek für .NET installiert haben. Sie können sie von der [Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie auf Ihrem Computer eine .NET-Entwicklungsumgebung ein.
## Namespaces importieren
Beginnen Sie in Ihrem .NET-Projekt mit dem Importieren der erforderlichen Namespaces:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Diese Namespaces stellen die wesentlichen Klassen und Methoden bereit, die für die Arbeit mit Präsentationsfolien und -formen erforderlich sind.
## Schritt 1: Einrichten der Präsentation
Erstellen Sie zunächst eine neue Präsentation und rufen Sie die erste Folie auf. Fügen Sie dazu den folgenden Code hinzu:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instanziieren der Präsentationsklasse
using (Presentation pres = new Presentation())
{
    // Holen Sie sich die erste Folie
    ISlide sld = pres.Slides[0];
```
Dieser Code initialisiert eine neue Präsentation und wählt die erste Folie zur weiteren Bearbeitung aus.
## Schritt 2: Ellipsenform hinzufügen
Fügen wir nun der Folie eine Ellipsenform hinzu, indem wir `AddAutoShape` Verfahren:
```csharp
// Autoform vom Typ Ellipse hinzufügen
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Diese Codezeile erstellt eine Ellipsenform bei den Koordinaten (50, 150) mit einer Breite von 150 Einheiten und einer Höhe von 50 Einheiten.
## Schritt 3: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation abschließend mit dem folgenden Code unter einem angegebenen Dateinamen auf der Festplatte:
```csharp
// Schreiben Sie die PPTX-Datei auf die Festplatte
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Dieser Schritt stellt sicher, dass Ihre Änderungen erhalten bleiben und Sie die resultierende Präsentation mit der neu hinzugefügten Ellipsenform anzeigen können.
## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich eine einfache Ellipsenform in einer Präsentationsfolie erstellt. Dieses Tutorial vermittelt Ihnen grundlegende Kenntnisse zum Arbeiten mit Formen, zum Einrichten von Präsentationen und zum Speichern der geänderten Dateien.
---
## FAQs
### Kann ich die Ellipsenform weiter anpassen?
Ja, Sie können verschiedene Eigenschaften der Ellipsenform, wie Farbe, Größe und Position, ändern, um sie Ihren spezifischen Designanforderungen anzupassen.
### Ist Aspose.Slides mit den neuesten .NET-Frameworks kompatibel?
Ja, Aspose.Slides wird regelmäßig aktualisiert, um die Kompatibilität mit den neuesten .NET-Frameworks sicherzustellen.
### Wo finde ich weitere Tutorials und Beispiele für Aspose.Slides?
Besuchen Sie die [Dokumentation](https://reference.aspose.com/slides/net/) für umfassende Anleitungen und Beispiele.
### Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?
Folgen Sie den [temporärer Lizenzlink](https://purchase.aspose.com/temporary-license/) um eine temporäre Lizenz zu Testzwecken anzufordern.
### Benötigen Sie Hilfe oder haben Sie konkrete Fragen?
Besuchen Sie die [Aspose.Slides-Supportforum](https://forum.aspose.com/c/slides/11) um Hilfe von der Community und Experten zu erhalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
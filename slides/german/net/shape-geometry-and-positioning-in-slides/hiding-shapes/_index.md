---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Formen in PowerPoint-Folien ausblenden. Mit dieser Schritt-für-Schritt-Anleitung können Sie Präsentationen programmgesteuert anpassen."
"linktitle": "Formen in Präsentationsfolien mit Aspose.Slides ausblenden"
"second_title": "Aspose.Slides .NET PowerPoint-Verarbeitungs-API"
"title": "Formen in PowerPoint mit dem Aspose.Slides .NET-Tutorial ausblenden"
"url": "/de/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formen in PowerPoint mit dem Aspose.Slides .NET-Tutorial ausblenden

## Einführung
In der dynamischen Welt der Präsentationen ist Anpassung entscheidend. Aspose.Slides für .NET bietet eine leistungsstarke Lösung zur programmgesteuerten Bearbeitung von PowerPoint-Präsentationen. Eine häufige Anforderung ist die Möglichkeit, bestimmte Formen innerhalb einer Folie auszublenden. Dieses Tutorial führt Sie durch das Ausblenden von Formen in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides für .NET: Stellen Sie sicher, dass die Aspose.Slides-Bibliothek installiert ist. Sie können sie herunterladen [Hier](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung für .NET ein.
- Grundkenntnisse in C#: Machen Sie sich mit C# vertraut, da die bereitgestellten Codebeispiele in dieser Sprache verfasst sind.
## Namespaces importieren
Um mit Aspose.Slides zu arbeiten, importieren Sie die erforderlichen Namespaces in Ihr C#-Projekt. Dadurch stellen Sie sicher, dass Sie Zugriff auf die benötigten Klassen und Methoden haben.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Lassen Sie uns nun den Beispielcode für ein klares und prägnantes Verständnis in mehrere Schritte aufteilen.
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues C#-Projekt und achten Sie darauf, die Bibliothek Aspose.Slides einzubinden.
## Schritt 2: Erstellen Sie eine Präsentation
Instanziieren Sie die `Presentation` Klasse, die die PowerPoint-Datei darstellt. Fügen Sie eine Folie hinzu und erhalten Sie einen Verweis darauf.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Schritt 3: Formen zur Folie hinzufügen
Fügen Sie der Folie Autoformen mit bestimmten Abmessungen hinzu, beispielsweise Rechtecke und Monde.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Schritt 4: Formen basierend auf alternativem Text ausblenden
Geben Sie einen alternativen Text an und verbergen Sie Formen, die diesem Text entsprechen.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Schritt 5: Speichern Sie die Präsentation
Speichern Sie die geänderte Präsentation im PPTX-Format auf der Festplatte.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Abschluss
Herzlichen Glückwunsch! Sie haben mit Aspose.Slides für .NET erfolgreich Formen in Ihrer Präsentation ausgeblendet. Dies eröffnet Ihnen unzählige Möglichkeiten für die programmgesteuerte Erstellung dynamischer und individueller Folien.
---
## FAQs
### Ist Aspose.Slides mit .NET Core kompatibel?
Ja, Aspose.Slides unterstützt .NET Core und bietet Flexibilität in Ihrer Entwicklungsumgebung.
### Kann ich Formen basierend auf anderen Bedingungen als alternativem Text ausblenden?
Absolut! Sie können die Ausblendlogik anhand verschiedener Attribute wie Formtyp, Farbe oder Position anpassen.
### Wo finde ich zusätzliche Aspose.Slides-Dokumentation?
Dokumentation erkunden [Hier](https://reference.aspose.com/slides/net/) für ausführliche Informationen und Beispiele.
### Sind temporäre Lizenzen für Aspose.Slides verfügbar?
Ja, Sie können eine vorübergehende Lizenz erhalten [Hier](https://purchase.aspose.com/temporary-license/) zu Testzwecken.
### Wie kann ich Community-Support für Aspose.Slides erhalten?
Treten Sie der Aspose.Slides-Community bei auf der [Forum](https://forum.aspose.com/c/slides/11) für Diskussionen und Hilfe.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
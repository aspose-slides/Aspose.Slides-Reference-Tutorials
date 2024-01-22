---
title: Ausblenden von Formen in PowerPoint mit dem Aspose.Slides .NET-Tutorial
linktitle: Ausblenden von Formen in Präsentationsfolien mit Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET Formen in PowerPoint-Folien ausblenden. Passen Sie Präsentationen programmgesteuert mit dieser Schritt-für-Schritt-Anleitung an.
type: docs
weight: 21
url: /de/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Einführung
In der dynamischen Welt der Präsentationen kommt es auf die individuelle Anpassung an. Aspose.Slides für .NET bietet eine leistungsstarke Lösung für die programmgesteuerte Bearbeitung von PowerPoint-Präsentationen. Eine häufige Anforderung ist die Möglichkeit, bestimmte Formen innerhalb einer Folie auszublenden. Dieses Tutorial führt Sie durch den Prozess des Ausblendens von Formen in Präsentationsfolien mit Aspose.Slides für .NET.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
-  Aspose.Slides für .NET: Stellen Sie sicher, dass die Aspose.Slides-Bibliothek installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).
- Entwicklungsumgebung: Richten Sie Ihre bevorzugte Entwicklungsumgebung für .NET ein.
- Grundkenntnisse von C#: Machen Sie sich mit C# vertraut, da die bereitgestellten Codebeispiele in dieser Sprache vorliegen.
## Namespaces importieren
Um mit Aspose.Slides zu arbeiten, importieren Sie die erforderlichen Namespaces in Ihr C#-Projekt. Dadurch wird sichergestellt, dass Sie Zugriff auf die erforderlichen Klassen und Methoden haben.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Lassen Sie uns nun den Beispielcode für ein klares und präzises Verständnis in mehrere Schritte aufteilen.
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie ein neues C#-Projekt und stellen Sie sicher, dass die Aspose.Slides-Bibliothek enthalten ist.
## Schritt 2: Erstellen Sie eine Präsentation
 Instanziieren Sie die`Presentation` Klasse, die die PowerPoint-Datei darstellt. Fügen Sie eine Folie hinzu und erhalten Sie einen Verweis darauf.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Schritt 3: Formen zur Folie hinzufügen
Fügen Sie der Folie automatische Formen wie Rechtecke und Monde mit bestimmten Abmessungen hinzu.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Schritt 4: Formen basierend auf alternativem Text ausblenden
Geben Sie einen alternativen Text an und blenden Sie Formen aus, die diesem Text entsprechen.
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
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## FAQs
### Ist Aspose.Slides mit .NET Core kompatibel?
Ja, Aspose.Slides unterstützt .NET Core und bietet so Flexibilität in Ihrer Entwicklungsumgebung.
### Kann ich Formen basierend auf anderen Bedingungen als Alternativtext ausblenden?
Absolut! Sie können die Ausblendungslogik basierend auf verschiedenen Attributen wie Formtyp, Farbe oder Position anpassen.
### Wo finde ich zusätzliche Aspose.Slides-Dokumentation?
 Entdecken Sie die Dokumentation[Hier](https://reference.aspose.com/slides/net/) für ausführliche Informationen und Beispiele.
### Sind temporäre Lizenzen für Aspose.Slides verfügbar?
 Ja, Sie können eine temporäre Lizenz erhalten[Hier](https://purchase.aspose.com/temporary-license/) zu Testzwecken.
### Wie kann ich Community-Unterstützung für Aspose.Slides erhalten?
 Treten Sie der Aspose.Slides-Community bei[Forum](https://forum.aspose.com/c/slides/11) für Diskussionen und Hilfe.
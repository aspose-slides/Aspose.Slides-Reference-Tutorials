---
title: Aspose.Slides - Anslut former sömlöst i .NET
linktitle: Ansluta former med kopplingar i presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Utforska kraften i Aspose.Slides för .NET, koppla samman former utan ansträngning i dina presentationer. Lyft dina bilder med dynamiska kontakter.
type: docs
weight: 29
url: /sv/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Introduktion
I den dynamiska presentationsvärlden ger möjligheten att koppla samman former med hjälp av kopplingar ett lager av sofistikering till dina bilder. Aspose.Slides för .NET ger utvecklare möjlighet att uppnå detta sömlöst. Denna handledning guidar dig genom processen och delar upp varje steg för att säkerställa en tydlig förståelse.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:
- Grundläggande kunskaper i C# och .NET framework.
-  Aspose.Slides för .NET installerat. Om inte, ladda ner den[här](https://releases.aspose.com/slides/net/).
- En utvecklingsmiljö inrättad.
## Importera namnområden
Börja med att importera de nödvändiga namnrymden i din C#-kod:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Ställ in dokumentkatalogen
Börja med att definiera katalogen för ditt dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instant presentationsklass
Skapa en instans av klassen Presentation för att representera din PPTX-fil:
```csharp
using (Presentation input = new Presentation())
{
    // Åtkomst till formsamling för den valda bilden
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Lägg till former på bilden
Lägg till de nödvändiga formerna till din bild, till exempel Ellips och rektangel:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Lägg till kopplingsform
Inkludera en kopplingsform i bildens formsamling:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Anslut Shapes med Connector
Ange formerna som ska kopplas ihop med kontakten:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Omdirigera anslutning
Anropa omdirigeringsmetoden för att ställa in den automatiska kortaste vägen mellan former:
```csharp
connector.Reroute();
```
## 7. Spara presentation
Spara din presentation för att se de anslutna formerna:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Slutsats
Grattis! Du har framgångsrikt kopplat samman former med kopplingar i presentationsbilder med Aspose.Slides för .NET. Förbättra dina presentationer med denna avancerade funktion och fängsla din publik.
## Vanliga frågor
### Är Aspose.Slides för .NET kompatibelt med det senaste .NET-ramverket?
Ja, Aspose.Slides för .NET uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET framework-versionerna.
### Kan jag ansluta fler än två former med en enda kontakt?
Absolut, du kan ansluta flera former genom att utöka kopplingslogiken i din kod.
### Finns det några begränsningar för de former jag kan ansluta?
Aspose.Slides för .NET stöder sammankoppling av olika former, inklusive grundläggande former, smart konst och anpassade former.
### Hur kan jag anpassa utseendet på kontakten?
Utforska Aspose.Slides-dokumentationen för metoder för att anpassa kontaktens utseende, som linjestil och färg.
### Finns det ett communityforum för Aspose.Slides-stöd?
 Ja, du kan få hjälp och dela dina erfarenheter i[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
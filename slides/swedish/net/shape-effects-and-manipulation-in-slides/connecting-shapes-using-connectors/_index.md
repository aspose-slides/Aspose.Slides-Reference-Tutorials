---
"description": "Utforska kraften hos Aspose.Slides för .NET och koppla samman former utan ansträngning i dina presentationer. Förhöj dina bilder med dynamiska kopplingar."
"linktitle": "Koppla samman former med hjälp av kopplingar i presentationer"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Aspose.Slides - Koppla ihop former sömlöst i .NET"
"url": "/sv/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Koppla ihop former sömlöst i .NET

## Introduktion
I presentationernas dynamiska värld ger möjligheten att koppla samman former med hjälp av kopplingar dina bilder ett extra lager av sofistikering. Aspose.Slides för .NET ger utvecklare möjlighet att uppnå detta sömlöst. Den här handledningen guidar dig genom processen och bryter ner varje steg för att säkerställa en tydlig förståelse.
## Förkunskapskrav
Innan vi går in i handledningen, se till att du har följande:
- Grundläggande kunskaper i C# och .NET framework.
- Aspose.Slides för .NET installerat. Om inte, ladda ner det. [här](https://releases.aspose.com/slides/net/).
- En utvecklingsmiljö konfigurerad.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i din C#-kod:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Konfigurera dokumentkatalogen
Börja med att definiera katalogen för ditt dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Instansiera presentationsklassen
Skapa en instans av Presentation-klassen för att representera din PPTX-fil:
```csharp
using (Presentation input = new Presentation())
{
    // Åtkomst till formsamlingen för den valda bilden
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Lägg till former på bilden
Lägg till nödvändiga former på din bild, till exempel Ellips och Rektangel:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Lägg till kontaktform
Inkludera en kopplingsform i bildens formsamling:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Koppla ihop former med koppling
Ange de former som ska anslutas av kopplingen:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Omdirigera kontakten
Anropa metoden omdirigering för att ställa in den automatiska kortaste vägen mellan former:
```csharp
connector.Reroute();
```
## 7. Spara presentation
Spara din presentation för att visa de kopplade formerna:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Slutsats
Grattis! Du har framgångsrikt kopplat ihop former med hjälp av kopplingar i presentationsbilder med Aspose.Slides för .NET. Förbättra dina presentationer med den här avancerade funktionen och fängsla din publik.
## Vanliga frågor
### Är Aspose.Slides för .NET kompatibelt med det senaste .NET-ramverket?
Ja, Aspose.Slides för .NET uppdateras regelbundet för att säkerställa kompatibilitet med de senaste versionerna av .NET Framework.
### Kan jag koppla ihop fler än två former med en enda koppling?
Absolut, du kan koppla samman flera former genom att utöka kopplingslogiken i din kod.
### Finns det några begränsningar för vilka former jag kan koppla ihop?
Aspose.Slides för .NET stöder koppling av olika former, inklusive grundläggande former, smart konst och anpassade former.
### Hur kan jag anpassa utseendet på kontakten?
Utforska Aspose.Slides-dokumentationen för metoder för att anpassa kopplingens utseende, till exempel linjestil och färg.
### Finns det ett communityforum för support av Aspose.Slides?
Ja, du kan få hjälp och dela dina erfarenheter i [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
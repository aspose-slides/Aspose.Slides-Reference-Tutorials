---
title: Shape Connection Mastery med Aspose.Slides för .NET
linktitle: Connecting Shape med Connection Site i Presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Skapa fängslande presentationer med Aspose.Slides för .NET, som sömlöst förbinder former. Följ vår guide för en smidig, engagerande upplevelse.
weight: 30
url: /sv/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
den dynamiska presentationsvärlden är det avgörande att skapa visuellt tilltalande bilder med sammankopplade former för effektiv kommunikation. Aspose.Slides för .NET tillhandahåller en kraftfull lösning för att uppnå detta genom att låta dig ansluta former med anslutningsplatser. Den här handledningen guidar dig genom processen att koppla samman former steg för steg, för att säkerställa att dina presentationer sticker ut med sömlösa visuella övergångar.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En grundläggande förståelse för programmering i C# och .NET.
-  Aspose.Slides för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/slides/net/).
- En integrerad utvecklingsmiljö (IDE) som Visual Studio konfigurerad.
## Importera namnområden
Börja med att importera de nödvändiga namnrymden i din C#-kod:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera din dokumentkatalog
Se till att du har en angiven katalog för ditt dokument. Om den inte finns, skapa en:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Steg 2: Skapa en presentation
Instantiera klassen Presentation för att representera din PPTX-fil:
```csharp
using (Presentation presentation = new Presentation())
{
    // Din kod för presentationen kommer här
}
```
## Steg 3: Få åtkomst till och lägg till former
Öppna formsamlingen för den valda bilden och lägg till de nödvändiga formerna:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Steg 4: Sammanfoga former med kopplingar
Anslut formerna med kontakten:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## Steg 5: Ställ in önskad anslutningsplats
Ange önskat anslutningsplatsindex för anslutaren:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## Steg 6: Spara din presentation
Spara din presentation med de anslutna formerna:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
Nu har du framgångsrikt kopplat former med hjälp av anslutningsplatser i din presentation.
## Slutsats
Aspose.Slides för .NET förenklar processen att koppla samman former, så att du kan skapa visuellt engagerande presentationer utan ansträngning. Genom att följa den här steg-för-steg-guiden kan du förbättra dina bilders visuella tilltalande och effektivt förmedla ditt budskap.
## Vanliga frågor
### Är Aspose.Slides kompatibel med Visual Studio 2019?
Ja, Aspose.Slides är kompatibel med Visual Studio 2019. Se till att du har rätt version installerad.
### Kan jag ansluta fler än två former i en enda kontakt?
Aspose.Slides låter dig ansluta två former med en enda kontakt. För att ansluta fler former behöver du ytterligare kontakter.
### Hur hanterar jag undantag när jag använder Aspose.Slides?
Du kan använda try-catch-block för att hantera undantag. Referera till[dokumentation](https://reference.aspose.com/slides/net/) för specifika undantag och felhantering.
### Finns det en testversion av Aspose.Slides?
 Ja, du kan ladda ner en gratis testversion[här](https://releases.aspose.com/).
### Var kan jag få support för Aspose.Slides?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd och diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

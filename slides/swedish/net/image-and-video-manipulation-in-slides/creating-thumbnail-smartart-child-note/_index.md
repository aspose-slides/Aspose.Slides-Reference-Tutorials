---
title: Skapa miniatyrbild för SmartArt Child Note i Aspose.Slides
linktitle: Skapa miniatyrbild för SmartArt Child Note i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar fängslande SmartArt Child Note-miniatyrer med Aspose.Slides för .NET. Lyft dina presentationer med dynamiska bilder!
weight: 15
url: /sv/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa miniatyrbild för SmartArt Child Note i Aspose.Slides

## Introduktion
Inom sfären av dynamiska presentationer framstår Aspose.Slides för .NET som ett kraftfullt verktyg som ger utvecklare möjlighet att manipulera och förbättra PowerPoint-presentationer programmatiskt. En spännande funktion är möjligheten att generera miniatyrer för SmartArt Child Notes, vilket lägger till ett lager av visuell tilltal till dina presentationer. Den här steg-för-steg-guiden leder dig genom processen att skapa miniatyrer för SmartArt Child Notes med Aspose.Slides för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket integrerat i ditt .NET-projekt. Om inte, ladda ner den från[släpper sida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Sätt upp en fungerande .NET-utvecklingsmiljö och ha en grundläggande förståelse för C#-programmering.
- Exempelpresentation: Skapa eller skaffa en PowerPoint-presentation som innehåller SmartArt med underordnade anteckningar för testning.
## Importera namnområden
Börja med att importera de nödvändiga namnrymden till ditt C#-projekt. Dessa namnrymder ger tillgång till de klasser och metoder som behövs för att arbeta med Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Steg 1: Instantera presentationsklass
 Börja med att instansiera`Presentation` klass, som representerar PPTX-filen du kommer att arbeta med.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Steg 2: Lägg till SmartArt
 Lägg nu till SmartArt till en bild i presentationen. I det här exemplet använder vi`BasicCycle` layout.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Steg 3: Skaffa nodreferens
För att arbeta med en specifik nod i SmartArt, skaffa dess referens med hjälp av dess index.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Steg 4: Skaffa miniatyrbild
Hämta miniatyrbilden av barnanteckningen i SmartArt-noden.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Steg 5: Spara miniatyrbild
Spara den genererade miniatyrbilden i en angiven katalog.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Upprepa dessa steg för varje SmartArt-nod i din presentation och anpassa layouten och stilarna efter behov.
## Slutsats
Sammanfattningsvis ger Aspose.Slides för .NET utvecklare möjlighet att skapa engagerande presentationer med lätthet. Möjligheten att generera miniatyrer för SmartArt Child Notes förbättrar det visuella tilltalandet av dina presentationer, vilket ger en dynamisk och interaktiv användarupplevelse.
## Vanliga frågor
### F: Kan jag anpassa storleken och formatet på den genererade miniatyrbilden?
S: Ja, du kan justera dimensionerna och formatet för miniatyrbilden genom att ändra motsvarande parametrar i koden.
### F: Stöder Aspose.Slides andra SmartArt-layouter?
A: Absolut! Aspose.Slides erbjuder en mängd olika SmartArt-layouter, så att du kan välja den som bäst passar dina presentationsbehov.
### F: Finns en tillfällig licens tillgänglig för teständamål?
 S: Ja, du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.
### F: Var kan jag söka hjälp eller få kontakt med Aspose.Slides-communityt?
 A: Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) att engagera sig i samhället, ställa frågor och hitta lösningar.
### F: Kan jag köpa Aspose.Slides för .NET?
 A: Visst! Utforska köpalternativen[här](https://purchase.aspose.com/buy) för att låsa upp Aspose.Slides fulla potential i dina projekt.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Lär dig hur du skapar fängslande miniatyrer för SmartArt-anteckningar med Aspose.Slides för .NET. Förhöj dina presentationer med dynamiska bilder!"
"linktitle": "Skapa miniatyrbild för SmartArt-underanteckning i Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Skapa miniatyrbild för SmartArt-underanteckning i Aspose.Slides"
"url": "/sv/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skapa miniatyrbild för SmartArt-underanteckning i Aspose.Slides

## Introduktion
Inom dynamiska presentationer utmärker sig Aspose.Slides för .NET som ett kraftfullt verktyg som ger utvecklare möjligheten att manipulera och förbättra PowerPoint-presentationer programmatiskt. En spännande funktion är möjligheten att generera miniatyrbilder för SmartArt-underordnade anteckningar, vilket ger dina presentationer ett extra visuellt intryck. Den här steg-för-steg-guiden guidar dig genom processen att skapa miniatyrbilder för SmartArt-underordnade anteckningar med Aspose.Slides för .NET.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket integrerat i ditt .NET-projekt. Om inte, ladda ner det från [utgivningssida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en fungerande .NET-utvecklingsmiljö och ha grundläggande förståelse för C#-programmering.
- Exempelpresentation: Skapa eller hämta en PowerPoint-presentation som innehåller SmartArt med underordnade anteckningar för testning.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna till ditt C#-projekt. Dessa namnrymder ger åtkomst till de klasser och metoder som behövs för att arbeta med Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Steg 1: Instansiera presentationsklassen
Börja med att instansiera `Presentation` klass, som representerar PPTX-filen du kommer att arbeta med.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Steg 2: Lägg till SmartArt
Lägg nu till SmartArt på en bild i presentationen. I det här exemplet använder vi `BasicCycle` layout.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Steg 3: Hämta nodreferens
För att arbeta med en specifik nod i SmartArt-objektet, hämta dess referens med hjälp av dess index.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Steg 4: Hämta miniatyrbild
Hämta miniatyrbilden av den underordnade anteckningen i SmartArt-noden.
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
Sammanfattningsvis ger Aspose.Slides för .NET utvecklare möjlighet att enkelt skapa engagerande presentationer. Möjligheten att generera miniatyrer för SmartArt Child Notes förbättrar presentationernas visuella attraktionskraft och ger en dynamisk och interaktiv användarupplevelse.
## Vanliga frågor
### F: Kan jag anpassa storleken och formatet på den genererade miniatyrbilden?
A: Ja, du kan justera miniatyrbildens dimensioner och format genom att ändra motsvarande parametrar i koden.
### F: Stöder Aspose.Slides andra SmartArt-layouter?
A: Absolut! Aspose.Slides erbjuder en mängd olika SmartArt-layouter, så att du kan välja den som bäst passar dina presentationsbehov.
### F: Finns en tillfällig licens tillgänglig för teständamål?
A: Ja, du kan få en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/) för testning och utvärdering.
### F: Var kan jag söka hjälp eller få kontakt med Aspose.Slides-communityn?
A: Besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) att engagera sig i samhället, ställa frågor och hitta lösningar.
### F: Kan jag köpa Aspose.Slides för .NET?
A: Absolut! Utforska köpalternativen [här](https://purchase.aspose.com/buy) för att frigöra Aspose.Slides fulla potential i dina projekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Lär dig lägga till bildramar med relativ skalhöjd i Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för sömlösa presentationer."
"linktitle": "Lägga till tavelramar med relativ skalhöjd i Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Handledning för att lägga till tavelramar med Aspose.Slides .NET"
"url": "/sv/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Handledning för att lägga till tavelramar med Aspose.Slides .NET

## Introduktion
Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PowerPoint-presentationer i sina .NET-applikationer utan ansträngning. I den här handledningen går vi in på processen att lägga till bildramar med relativ skalhöjd med hjälp av Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för att förbättra dina färdigheter i att bygga presentationer.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i programmeringsspråket C#.
- Visual Studio eller annan föredragen C#-utvecklingsmiljö installerad.
- Aspose.Slides för .NET-biblioteket har lagts till i ditt projekt.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna till din C#-kod. Detta steg säkerställer att du har tillgång till de klasser och funktioner som tillhandahålls av Aspose.Slides-biblioteket.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera ditt projekt
Börja med att skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö. Se till att lägga till Aspose.Slides för .NET-biblioteket i ditt projekt genom att referera till det.
## Steg 2: Ladda presentation och bild
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Ladda bild som ska läggas till i presentationsbildsamlingen
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
I det här steget skapar vi ett nytt presentationsobjekt och laddar bilden som vi vill lägga till i presentationen.
## Steg 3: Lägg till bildram till diabild
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Lägg nu till en bildram på den första bilden i presentationen. Justera parametrar som formtyp, position och dimensioner efter dina behov.
## Steg 4: Ställ in relativ skalbredd och höjd
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Ställ in den relativa skalningshöjden och bredden för bildramen för att uppnå önskad skalningseffekt.
## Steg 5: Spara presentationen
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Spara slutligen presentationen med den tillagda bildramen i det angivna utdataformatet.
## Slutsats
Grattis! Du har nu lärt dig hur man lägger till bildramar med relativ skalhöjd med hjälp av Aspose.Slides för .NET. Experimentera med olika bilder, positioner och skalor för att skapa visuellt tilltalande presentationer skräddarsydda efter dina behov.
## Vanliga frågor
### Kan jag använda Aspose.Slides för .NET med andra programmeringsspråk?
Aspose.Slides stöder främst .NET-språk, men du kan utforska andra Aspose-produkter för kompatibilitet med olika plattformar.
### Var kan jag hitta detaljerad dokumentation för Aspose.Slides för .NET?
Se [dokumentation](https://reference.aspose.com/slides/net/) för omfattande information och exempel.
### Finns det en gratis testversion av Aspose.Slides för .NET?
Ja, du kan få en [gratis provperiod](https://releases.aspose.com/) att utvärdera bibliotekets kapacitet.
### Hur kan jag få support för Aspose.Slides för .NET?
Besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) att söka hjälp från samhället och Aspose-experter.
### Var kan jag köpa Aspose.Slides för .NET?
Du kan köpa Aspose.Slides för .NET från [köpsida](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
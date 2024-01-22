---
title: Handledning för att lägga till bildramar med Aspose.Slides .NET
linktitle: Lägga till bildramar med relativ skalhöjd i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig att lägga till bildramar med relativ skalhöjd i Aspose.Slides för .NET. Följ den här steg-för-steg-guiden för sömlösa presentationer.
type: docs
weight: 17
url: /sv/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## Introduktion
Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PowerPoint-presentationer i sina .NET-applikationer utan ansträngning. I den här handledningen kommer vi att dyka in i processen att lägga till bildramar med relativ skalhöjd med Aspose.Slides för .NET. Följ med den här steg-för-steg-guiden för att förbättra dina färdigheter i presentationsbyggande.
## Förutsättningar
Innan vi börjar, se till att du har följande:
- Grundläggande kunskaper i programmeringsspråket C#.
- Visual Studio eller någon annan föredragen C#-utvecklingsmiljö installerad.
- Aspose.Slides för .NET-bibliotek har lagts till i ditt projekt.
## Importera namnområden
Börja med att importera de nödvändiga namnrymden till din C#-kod. Detta steg säkerställer att du har tillgång till klasserna och funktionerna som tillhandahålls av Aspose.Slides-biblioteket.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera ditt projekt
Börja med att skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö. Se till att lägga till Aspose.Slides för .NET-biblioteket till ditt projekt genom att referera till det.
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
I det här steget skapar vi ett nytt presentationsobjekt och laddar in bilden som vi vill lägga till i presentationen.
## Steg 3: Lägg till bildram till bild
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Lägg nu till en bildram till den första bilden i presentationen. Justera parametrarna som formtyp, position och dimensioner enligt dina krav.
## Steg 4: Ställ in relativ skalbredd och höjd
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Ställ in den relativa skalhöjden och -bredden för bildramen för att uppnå önskad skalningseffekt.
## Steg 5: Spara presentationen
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Spara slutligen presentationen med den tillagda bildramen i det angivna utdataformatet.
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till bildramar med relativ skalhöjd med Aspose.Slides för .NET. Experimentera med olika bilder, positioner och skalor för att skapa visuellt tilltalande presentationer skräddarsydda efter dina behov.
## Vanliga frågor
### Kan jag använda Aspose.Slides för .NET med andra programmeringsspråk?
Aspose.Slides stöder främst .NET-språk, men du kan utforska andra Aspose-produkter för kompatibilitet med olika plattformar.
### Var kan jag hitta detaljerad dokumentation för Aspose.Slides för .NET?
 Referera till[dokumentation](https://reference.aspose.com/slides/net/) för omfattande information och exempel.
### Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 Ja, du kan få en[gratis provperiod](https://releases.aspose.com/) för att utvärdera bibliotekets kapacitet.
### Hur kan jag få support för Aspose.Slides för .NET?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) att söka hjälp från samhället och Aspose-experter.
### Var kan jag köpa Aspose.Slides för .NET?
 Du kan köpa Aspose.Slides för .NET från[köpsidan](https://purchase.aspose.com/buy).
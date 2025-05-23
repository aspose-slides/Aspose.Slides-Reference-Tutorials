---
"description": "Utforska kraften hos Aspose.Slides för .NET för att enkelt ändra OLE-objektdata. Förbättra dina presentationer med dynamiskt innehåll."
"linktitle": "Ändra OLE-objektdata i presentationer med Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Ändra OLE-objektdata i presentationer med Aspose.Slides"
"url": "/sv/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ändra OLE-objektdata i presentationer med Aspose.Slides

## Introduktion
Att skapa dynamiska och interaktiva PowerPoint-presentationer är ett vanligt krav i dagens digitala värld. Ett kraftfullt verktyg för att uppnå detta är Aspose.Slides för .NET, ett robust bibliotek som låter utvecklare manipulera och förbättra PowerPoint-presentationer programmatiskt. I den här handledningen ska vi fördjupa oss i processen att ändra OLE-objektdata (Object Linking and Embedding) i presentationsbilder med hjälp av Aspose.Slides.
## Förkunskapskrav
Innan du börjar arbeta med Aspose.Slides för .NET, se till att du har följande förutsättningar på plats:
1. Utvecklingsmiljö: Konfigurera en utvecklingsmiljö med .NET installerat.
2. Aspose.Slides-biblioteket: Ladda ner och installera Aspose.Slides för .NET-biblioteket. Du hittar biblioteket [här](https://releases.aspose.com/slides/net/).
3. Grundläggande förståelse: Bekanta dig med grundläggande koncept inom C#-programmering och PowerPoint-presentationer.
## Importera namnrymder
Importera de namnrymder som behövs för att använda Aspose.Slides-funktioner i ditt C#-projekt:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Steg 1: Konfigurera ditt projekt
Börja med att skapa ett nytt C#-projekt och importera Aspose.Slides-biblioteket. Se till att ditt projekt är korrekt konfigurerat och att du har de nödvändiga beroendena på plats.
## Steg 2: Åtkomst till presentation och bild
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Steg 3: Leta reda på OLE-objektet
Gå igenom alla former i bilden för att hitta OLE-objektramen:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Steg 4: Läs och ändra arbetsboksdata
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Läser objektdata i arbetsboken
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Ändra arbetsboksdata
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Ändra Ole-ramobjektdata
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Steg 5: Spara presentationen
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Slutsats
Genom att följa dessa steg kan du sömlöst ändra OLE-objektdata i presentationsbilder med hjälp av Aspose.Slides för .NET. Detta öppnar upp en värld av möjligheter för att skapa dynamiska och anpassade presentationer skräddarsydda efter dina specifika behov.
## Vanliga frågor
### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med PowerPoint-presentationer programmatiskt, vilket möjliggör enkel manipulation och förbättring.
### Var kan jag hitta dokumentationen för Aspose.Slides?
Dokumentationen för Aspose.Slides för .NET finns här [här](https://reference.aspose.com/slides/net/).
### Hur laddar jag ner Aspose.Slides för .NET?
Du kan ladda ner biblioteket från utgivningssidan [här](https://releases.aspose.com/slides/net/).
### Finns det en gratis provversion av Aspose.Slides?
Ja, du kan få tillgång till gratis provperioden [här](https://releases.aspose.com/).
### Var kan jag få support för Aspose.Slides för .NET?
För stöd och diskussioner, besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
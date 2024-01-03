---
title: Ändra OLE-objektdata i presentation med Aspose.Slides
linktitle: Ändra OLE-objektdata i presentation med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Utforska kraften i Aspose.Slides för .NET för att enkelt ändra OLE-objektdata. Förbättra dina presentationer med dynamiskt innehåll.
type: docs
weight: 25
url: /sv/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## Introduktion
Att skapa dynamiska och interaktiva PowerPoint-presentationer är ett vanligt krav i dagens digitala värld. Ett kraftfullt verktyg för att uppnå detta är Aspose.Slides för .NET, ett robust bibliotek som tillåter utvecklare att manipulera och förbättra PowerPoint-presentationer programmatiskt. I den här handledningen kommer vi att fördjupa oss i processen att ändra OLE (Object Linking and Embedding)-objektdata i presentationsbilder med Aspose.Slides.
## Förutsättningar
Innan du börjar arbeta med Aspose.Slides för .NET, se till att du har följande förutsättningar på plats:
1. Utvecklingsmiljö: Skapa en utvecklingsmiljö med .NET installerat.
2.  Aspose.Slides Library: Ladda ner och installera Aspose.Slides för .NET-biblioteket. Du hittar biblioteket[här](https://releases.aspose.com/slides/net/).
3. Grundläggande förståelse: Bekanta dig med grundläggande begrepp inom C#-programmering och PowerPoint-presentationer.
## Importera namnområden
I ditt C#-projekt, importera de nödvändiga namnrymden för att använda Aspose.Slides-funktioner:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Steg 1: Konfigurera ditt projekt
Börja med att skapa ett nytt C#-projekt och importera Aspose.Slides-biblioteket. Se till att ditt projekt är korrekt konfigurerat och att du har de nödvändiga beroenden på plats.
## Steg 2: Öppna presentation och bild
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Steg 3: Hitta OLE-objekt
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
        // Läser objektdata i arbetsbok
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
            // Ändra Ole ramobjektdata
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
Genom att följa dessa steg kan du sömlöst ändra OLE-objektdata i presentationsbilder med Aspose.Slides för .NET. Detta öppnar upp en värld av möjligheter för att skapa dynamiska och skräddarsydda presentationer skräddarsydda efter dina specifika behov.
## Vanliga frågor
### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att arbeta med PowerPoint-presentationer programmatiskt, vilket möjliggör enkel manipulation och förbättring.
### Var kan jag hitta Aspose.Slides-dokumentationen?
 Dokumentationen för Aspose.Slides för .NET finns[här](https://reference.aspose.com/slides/net/).
### Hur laddar jag ner Aspose.Slides för .NET?
 Du kan ladda ner biblioteket från releasesidan[här](https://releases.aspose.com/slides/net/).
### Finns det en gratis testversion tillgänglig för Aspose.Slides?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.aspose.com/).
### Var kan jag få support för Aspose.Slides för .NET?
 För support och diskussioner, besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
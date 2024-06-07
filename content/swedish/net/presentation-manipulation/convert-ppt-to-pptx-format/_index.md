---
title: Konvertera PPT till PPTX-format
linktitle: Konvertera PPT till PPTX-format
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du enkelt konverterar PPT till PPTX med Aspose.Slides för .NET. Steg-för-steg-guide med kodexempel för sömlös formatomvandling.
type: docs
weight: 25
url: /sv/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

Om du någonsin har behövt konvertera PowerPoint-filer från det äldre PPT-formatet till det nyare PPTX-formatet med .NET, är du på rätt plats. I den här steg-för-steg-handledningen går vi igenom processen med Aspose.Slides för .NET API. Med detta kraftfulla bibliotek kan du enkelt hantera sådana konverteringar. Låt oss börja!

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande inställning:

- Visual Studio: Se till att du har Visual Studio installerat och redo för .NET-utveckling.
-  Aspose.Slides for .NET: Ladda ner och installera Aspose.Slides for .NET-biblioteket från[här](https://releases.aspose.com/slides/net/).

## Konfigurera projektet

1. Skapa ett nytt projekt: Öppna Visual Studio och skapa ett nytt C#-projekt.

2. Lägg till referens till Aspose.Slides: Högerklicka på ditt projekt i Solution Explorer, välj "Hantera NuGet-paket" och sök efter "Aspose.Slides." Installera paketet.

3. Importera nödvändiga namnområden:

```csharp
using Aspose.Slides;
```

## Konvertera PPT till PPTX

Nu när vi har satt upp vårt projekt, låt oss skriva koden för att konvertera en PPT-fil till PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

//Instantiera ett presentationsobjekt som representerar en PPT-fil
Presentation pres = new Presentation(srcFileName);

//Sparar presentationen i PPTX-format
pres.Save(outPath, SaveFormat.Pptx);
```

I detta kodavsnitt:

- `dataDir` ska ersättas med katalogsökvägen där din PPT-fil finns.
- `outPath` ska ersättas med katalogen där du vill spara den konverterade PPTX-filen.
- `srcFileName` är namnet på din PPT-fil.
- `destFileName` är det önskade namnet för utdata-PPTX-filen.

## Slutsats

Grattis! Du har framgångsrikt konverterat en PowerPoint-presentation från PPT- till PPTX-format med Aspose.Slides för .NET API. Detta kraftfulla bibliotek förenklar komplexa uppgifter som denna, vilket gör din .NET-utvecklingsupplevelse smidigare.

 Om du inte redan har gjort det,[ladda ner Aspose.Slides för .NET](https://releases.aspose.com/slides/net/) och utforska dess kapacitet ytterligare.

 För fler handledningar och tips, besök vår[dokumentation](https://reference.aspose.com/slides/net/).

## Vanliga frågor

### 1. Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett .NET-bibliotek som låter utvecklare skapa, manipulera och konvertera PowerPoint-presentationer programmatiskt.

### 2. Kan jag konvertera andra format till PPTX med Aspose.Slides för .NET?
Ja, Aspose.Slides för .NET stöder olika format, inklusive PPT, PPTX, ODP och mer.

### 3. Är Aspose.Slides för .NET gratis att använda?
 Nej, det är ett kommersiellt bibliotek, men du kan utforska ett[gratis provperiod](https://releases.aspose.com/) för att utvärdera dess egenskaper.

### 4. Finns det några andra dokumentformat som stöds av Aspose.Slides för .NET?
Ja, Aspose.Slides för .NET stöder också arbete med Word-dokument, Excel-kalkylblad och andra filformat.

### 5. Var kan jag få support eller ställa frågor om Aspose.Slides för .NET?
 Du kan hitta svar på dina frågor och söka stöd i[Aspose.Slides forum](https://forum.aspose.com/).


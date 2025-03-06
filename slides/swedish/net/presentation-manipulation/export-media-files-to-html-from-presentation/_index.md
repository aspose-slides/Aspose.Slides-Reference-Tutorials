---
title: Exportera mediafiler till HTML från presentation
linktitle: Exportera mediafiler till HTML från presentation
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Optimera din presentationsdelning med Aspose.Slides för .NET! Lär dig hur du exporterar mediefiler till HTML från din presentation i den här steg-för-steg-guiden.
weight: 15
url: /sv/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


I den här handledningen går vi igenom processen att exportera mediafiler till HTML från en presentation med Aspose.Slides för .NET. Aspose.Slides är ett kraftfullt API som låter dig arbeta med PowerPoint-presentationer programmatiskt. I slutet av den här guiden kommer du att kunna konvertera dina presentationer till HTML-format med lätthet. Så, låt oss komma igång!

## 1. Introduktion

PowerPoint-presentationer innehåller ofta multimediaelement som videor, och du kan behöva exportera dessa presentationer till HTML-format för webbkompatibilitet. Aspose.Slides för .NET är ett bekvämt sätt att utföra denna uppgift programmatiskt.

## 2. Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

-  Aspose.Slides för .NET: Du bör ha Aspose.Slides för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## 3. Ladda en presentation

För att börja måste du ladda PowerPoint-presentationen du vill konvertera till HTML. Du måste också ange utdatakatalogen där HTML-filen ska sparas. Här är koden för att ladda en presentation:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Laddar en presentation
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Din kod här
}
```

## 4. Ställa in HTML-alternativ

Låt oss nu ställa in HTML-alternativen för konverteringen. Vi konfigurerar en HTML-kontroller, HTML-formaterare och bildformat. Denna kod säkerställer att din HTML-fil innehåller de komponenter som krävs för att visa multimediaelement.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Ställa in HTML-alternativ
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Spara HTML-filen

 Med HTML-alternativen konfigurerade kan du nu spara HTML-filen. De`Save` metoden för presentationsobjektet genererar HTML-filen med inbäddade multimediaelement.

```csharp
// Sparar filen
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Sammanfattning

Grattis! Du har framgångsrikt exporterat mediafiler till HTML från en PowerPoint-presentation med Aspose.Slides för .NET. Detta gör att du enkelt kan dela dina presentationer online och se till att multimediaelement visas korrekt.

## 7. Vanliga frågor

### F1: Är Aspose.Slides för .NET ett gratis bibliotek?
 S1: Aspose.Slides för .NET är ett kommersiellt bibliotek, men du kan få en gratis provperiod från[här](https://releases.aspose.com/) att prova det.

### F2: Kan jag anpassa HTML-utdata ytterligare?
S2: Ja, du kan anpassa HTML-utdata genom att ändra HTML-alternativen i koden.

### F3: Stöder Aspose.Slides för .NET andra exportformat?
S3: Ja, Aspose.Slides för .NET stöder olika exportformat, inklusive PDF, bildformat och mer.

### F4: Var kan jag få support för Aspose.Slides för .NET?
 S4: Du kan hitta support och ställa frågor på Aspose-forumen[här](https://forum.aspose.com/).

### F5: Hur köper jag en licens för Aspose.Slides för .NET?
 S5: Du kan köpa en licens från[den här länken](https://purchase.aspose.com/buy).

Nu när du har slutfört den här handledningen har du färdigheter att exportera mediefiler till HTML från PowerPoint-presentationer med Aspose.Slides för .NET. Njut av att dela dina multimediarika presentationer online!
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

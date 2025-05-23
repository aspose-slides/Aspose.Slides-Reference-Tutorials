---
"description": "Optimera din presentationsdelning med Aspose.Slides för .NET! Lär dig hur du exporterar mediefiler till HTML från din presentation i den här steg-för-steg-guiden."
"linktitle": "Exportera mediefiler till HTML från presentation"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Exportera mediefiler till HTML från presentation"
"url": "/sv/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Exportera mediefiler till HTML från presentation


den här handledningen guidar vi dig genom processen att exportera mediefiler till HTML från en presentation med hjälp av Aspose.Slides för .NET. Aspose.Slides är ett kraftfullt API som låter dig arbeta med PowerPoint-presentationer programmatiskt. I slutet av den här guiden kommer du enkelt att kunna konvertera dina presentationer till HTML-format. Så, låt oss komma igång!

## 1. Introduktion

PowerPoint-presentationer innehåller ofta multimediaelement som videor, och du kan behöva exportera dessa presentationer till HTML-format för webbkompatibilitet. Aspose.Slides för .NET erbjuder ett bekvämt sätt att utföra denna uppgift programmatiskt.

## 2. Förkunskapskrav

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Aspose.Slides för .NET: Du bör ha biblioteket Aspose.Slides för .NET installerat. Du kan ladda ner det från [här](https://releases.aspose.com/slides/net/).

## 3. Ladda en presentation

För att börja måste du ladda PowerPoint-presentationen som du vill konvertera till HTML. Du måste också ange utdatakatalogen där HTML-filen ska sparas. Här är koden för att ladda en presentation:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Läser in en presentation
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Din kod här
}
```

## 4. Konfigurera HTML-alternativ

Nu ska vi konfigurera HTML-alternativen för konverteringen. Vi konfigurerar en HTML-kontroller, HTML-formaterare och bildformat. Den här koden säkerställer att din HTML-fil innehåller de komponenter som krävs för att visa multimediaelement.

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

Med HTML-alternativen konfigurerade kan du nu spara HTML-filen. `Save` Metoden för presentationsobjektet genererar HTML-filen med inbäddade multimediaelement.

```csharp
// Sparar filen
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Slutsats

Grattis! Du har lyckats exportera mediefiler till HTML från en PowerPoint-presentation med Aspose.Slides för .NET. Detta gör att du enkelt kan dela dina presentationer online och säkerställa att multimediaelement visas korrekt.

## 7. Vanliga frågor

### F1: Är Aspose.Slides för .NET ett gratis bibliotek?
A1: Aspose.Slides för .NET är ett kommersiellt bibliotek, men du kan få en gratis provperiod från [här](https://releases.aspose.com/) att prova det.

### F2: Kan jag anpassa HTML-utdata ytterligare?
A2: Ja, du kan anpassa HTML-utdata genom att ändra HTML-alternativen i koden.

### F3: Stöder Aspose.Slides för .NET andra exportformat?
A3: Ja, Aspose.Slides för .NET stöder olika exportformat, inklusive PDF, bildformat och mer.

### F4: Var kan jag få support för Aspose.Slides för .NET?
A4: Du kan hitta support och ställa frågor på Aspose-forumen [här](https://forum.aspose.com/).

### F5: Hur köper jag en licens för Aspose.Slides för .NET?
A5: Du kan köpa en licens från [den här länken](https://purchase.aspose.com/buy).

Nu när du har slutfört den här handledningen har du kunskaperna för att exportera mediefiler till HTML från PowerPoint-presentationer med hjälp av Aspose.Slides för .NET. Ha en trevlig stund med att dela dina multimedierika presentationer online!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
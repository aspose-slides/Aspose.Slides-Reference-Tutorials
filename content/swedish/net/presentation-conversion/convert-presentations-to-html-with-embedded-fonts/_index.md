---
title: Konvertera presentationer till HTML med inbäddade teckensnitt
linktitle: Konvertera presentationer till HTML med inbäddade teckensnitt
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Konvertera PowerPoint-presentationer till HTML med inbäddade typsnitt med Aspose.Slides för .NET. Behåll originaliteten sömlöst.
type: docs
weight: 13
url: /sv/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

I dagens digitala tidsålder har det blivit vanligt att dela presentationer och dokument online. En utmaning som ofta dyker upp är dock att se till att dina teckensnitt visas korrekt när du konverterar presentationer till HTML. Denna steg-för-steg handledning guidar dig genom processen att använda Aspose.Slides för .NET för att konvertera presentationer till HTML med inbäddade typsnitt, vilket säkerställer att dina dokument ser ut precis som du tänkt dig.

## Introduktion till Aspose.Slides för .NET

Innan vi dyker in i handledningen, låt oss kort presentera Aspose.Slides för .NET. Det är ett kraftfullt bibliotek som låter utvecklare arbeta med PowerPoint-presentationer i .NET-applikationer. Med Aspose.Slides kan du skapa, ändra och konvertera PowerPoint-filer programmatiskt.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

-  Aspose.Slides för .NET: Du bör ha Aspose.Slides-biblioteket installerat i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Steg 1: Konfigurera ditt projekt

1. Skapa ett nytt projekt eller öppna ett befintligt i din föredragna .NET-utvecklingsmiljö.

2. Lägg till en referens till Aspose.Slides-biblioteket i ditt projekt.

3. Importera de nödvändiga namnrymden i din kod:

   ```csharp
   using Aspose.Slides;
   ```

## Steg 2: Ladda din presentation

 Till att börja med måste du ladda presentationen du vill konvertera till HTML. Byta ut`"Your Document Directory"` med den faktiska katalogen där din presentationsfil finns.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Din kod kommer hit
}
```

## Steg 3: Uteslut standardteckensnitt för presentationer

det här steget kan du ange alla standardpresentationsfonter som du vill utesluta från inbäddning. Detta kan hjälpa till att optimera storleken på den resulterande HTML-filen.

```csharp
string[] fontNameExcludeList = { };
```

## Steg 4: Välj en HTML-kontroller

Nu har du två alternativ för att bädda in teckensnitt i HTML:en:

### Alternativ 1: Bädda in alla teckensnitt

 För att bädda in alla teckensnitt som används i presentationen, använd`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Alternativ 2: Länka alla teckensnitt

 För att länka till alla teckensnitt som används i presentationen, använd`LinkAllFontsHtmlController`. Du bör ange katalogen där typsnitten finns på ditt system.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Steg 5: Definiera HTML-alternativ

 Skapa en`HtmlOptions` objekt och ställ in HTML-formateraren till den du valde i föregående steg.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Använd embedFontsController för att bädda in alla teckensnitt
};
```

## Steg 6: Spara som HTML

 Slutligen, spara presentationen som en HTML-fil. Du kan välja antingen`SaveFormat.Html` eller`SaveFormat.Html5` beroende på dina krav.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Slutsats

Grattis! Du har framgångsrikt konverterat din presentation till HTML med inbäddade typsnitt med Aspose.Slides för .NET. Detta säkerställer att dina teckensnitt visas korrekt när du delar dina presentationer online.

Nu kan du enkelt dela dina vackert formaterade presentationer med tillförsikt, i vetskap om att din publik kommer att se dem precis som du tänkt dig.

 För mer information och detaljerade API-referenser, kolla in[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).

## Vanliga frågor

### 1. Kan jag konvertera PowerPoint-presentationer till HTML med Aspose.Slides för .NET i batchläge?

Ja, du kan batchkonvertera flera presentationer till HTML med Aspose.Slides för .NET genom att gå igenom dina presentationsfiler och tillämpa konverteringsprocessen på var och en.

### 2. Finns det något sätt att anpassa utseendet på HTML-utdata?

Säkert! Aspose.Slides för .NET tillhandahåller olika alternativ för att anpassa utseendet och formateringen av HTML-utdata, som att justera färger, teckensnitt och layout.

### 3. Finns det några begränsningar för att bädda in typsnitt i HTML med Aspose.Slides för .NET?

Även om Aspose.Slides för .NET erbjuder utmärkta funktioner för inbäddning av teckensnitt, kom ihåg att storleken på dina HTML-filer kan öka när du bäddar in teckensnitt. Se till att optimera dina teckensnittsval för webbanvändning.

### 4. Kan jag konvertera PowerPoint-presentationer till andra format med Aspose.Slides för .NET?

Ja, Aspose.Slides för .NET stöder ett brett utbud av utdataformat, inklusive PDF, bilder och mer. Du kan enkelt konvertera dina presentationer till det format du väljer.

### 5. Var kan jag hitta ytterligare resurser och support för Aspose.Slides för .NET?

 Du kan få tillgång till en mängd resurser, inklusive dokumentation, på[Aspose.Slides för .NET API Referens](https://reference.aspose.com/slides/net/).

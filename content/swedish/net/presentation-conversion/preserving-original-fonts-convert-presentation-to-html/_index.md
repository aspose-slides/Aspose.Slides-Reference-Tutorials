---
title: Bevara ursprungliga teckensnitt - Konvertera presentation till HTML
linktitle: Bevara ursprungliga teckensnitt - Konvertera presentation till HTML
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du bevarar originaltypsnitt samtidigt som du konverterar presentationer till HTML med Aspose.Slides för .NET. Säkerställ teckensnittskonsistens och visuell effekt utan ansträngning.
type: docs
weight: 14
url: /sv/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

I den här omfattande guiden går vi igenom processen att bevara originaltypsnitt när du konverterar en presentation till HTML med Aspose.Slides för .NET. Vi kommer att förse dig med den nödvändiga C#-källkoden och förklara varje steg i detalj. I slutet av denna handledning kommer du att kunna se till att typsnitten i ditt konverterade HTML-dokument förblir trogna den ursprungliga presentationen.

## 1. Introduktion

När du konverterar PowerPoint-presentationer till HTML är det viktigt att behålla de ursprungliga typsnitten för att säkerställa den visuella konsekvensen i ditt innehåll. Aspose.Slides för .NET ger en kraftfull lösning för att uppnå detta. I den här handledningen guidar vi dig genom stegen som behövs för att bevara de ursprungliga teckensnitten under konverteringsprocessen.

## 2. Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio installerat på din dator.
- Aspose.Slides för .NET-bibliotek har lagts till i ditt projekt.

## 3. Konfigurera ditt projekt

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till Aspose.Slides för .NET-biblioteket som referens.

## 4. Laddar presentationen

Använd följande kod för att ladda din PowerPoint-presentation:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Din kod här
}
```

 Byta ut`"Your Document Directory"` med sökvägen till din presentationsfil.

## 5. Exklusive standardteckensnitt

För att utesluta standardteckensnitt som Calibri och Arial, använd följande kod:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Du kan anpassa den här listan efter behov.

## 6. Bädda in alla teckensnitt

Därefter bäddar vi in alla teckensnitt i HTML-dokumentet. Detta säkerställer att de ursprungliga typsnitten bevaras. Använd följande kod:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Spara som HTML

Spara nu presentationen som ett HTML-dokument med inbäddade typsnitt:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Byta ut`"output.html"` med önskat utdatafilnamn.

## 8. Slutsats

den här handledningen har vi visat hur man bevarar originaltypsnitt när man konverterar en PowerPoint-presentation till HTML med Aspose.Slides för .NET. Genom att följa dessa steg kan du säkerställa att ditt konverterade HTML-dokument behåller den visuella integriteten hos den ursprungliga presentationen.

## 9. Vanliga frågor

### F1: Kan jag anpassa listan över uteslutna typsnitt?

 Jo det kan du. Ändra`fontNameExcludeList` array för att inkludera eller utesluta specifika teckensnitt enligt dina krav.

### F2: Vad händer om jag inte vill bädda in alla teckensnitt?

Om du bara vill bädda in specifika typsnitt kan du ändra koden därefter. Se Aspose.Slides för .NET-dokumentationen för mer information.

### F3: Finns det några licenskrav för att använda Aspose.Slides för .NET?

Ja, du kan behöva en giltig licens för att använda Aspose.Slides för .NET i dina projekt. Se Asposes webbplats för licensinformation.

### F4: Kan jag konvertera andra filformat till HTML med Aspose.Slides för .NET?

Aspose.Slides för .NET fokuserar främst på PowerPoint-presentationer. För att konvertera andra filformat till HTML kan du behöva utforska andra Aspose-produkter som är skräddarsydda för dessa format.

### F5: Var kan jag få tillgång till ytterligare resurser och support?

 Du kan hitta mer dokumentation, handledning och support på Asposes webbplats. Besök[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.

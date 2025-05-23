---
"description": "Lär dig hur du bevarar originaltypsnitt när du konverterar presentationer till HTML med Aspose.Slides för .NET. Säkerställ typsnittskonsekvens och visuell effekt utan problem."
"linktitle": "Bevara originalteckensnitt - Konvertera presentation till HTML"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Bevara originalteckensnitt - Konvertera presentation till HTML"
"url": "/sv/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bevara originalteckensnitt - Konvertera presentation till HTML


I den här omfattande guiden går vi igenom processen för att bevara originaltypsnitt när du konverterar en presentation till HTML med Aspose.Slides för .NET. Vi förser dig med nödvändig C#-källkod och förklarar varje steg i detalj. I slutet av den här handledningen kommer du att kunna säkerställa att typsnitten i ditt konverterade HTML-dokument förblir trogna den ursprungliga presentationen.

## 1. Introduktion

När du konverterar PowerPoint-presentationer till HTML är det avgörande att behålla de ursprungliga teckensnitten för att säkerställa den visuella konsistensen i ditt innehåll. Aspose.Slides för .NET erbjuder en kraftfull lösning för att uppnå detta. I den här handledningen guidar vi dig genom stegen som behövs för att bevara de ursprungliga teckensnitten under konverteringsprocessen.

## 2. Förkunskapskrav

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio installerat på din dator.
- Aspose.Slides för .NET-biblioteket har lagts till i ditt projekt.

## 3. Konfigurera ditt projekt

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till Aspose.Slides för .NET-biblioteket som referens.

## 4. Ladda presentationen

Använd följande kod för att ladda din PowerPoint-presentation:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Din kod här
}
```

Ersätta `"Your Document Directory"` med sökvägen till din presentationsfil.

## 5. Exkludera standardteckensnitt

För att exkludera standardteckensnitt som Calibri och Arial, använd följande kod:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Du kan anpassa den här listan efter behov.

## 6. Bädda in alla teckensnitt

Härnäst bäddar vi in alla teckensnitt i HTML-dokumentet. Detta säkerställer att de ursprungliga teckensnitten bevaras. Använd följande kod:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Spara som HTML

Spara nu presentationen som ett HTML-dokument med inbäddade teckensnitt:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Ersätta `"output.html"` med ditt önskade utdatafilnamn.

## 8. Slutsats

I den här handledningen har vi visat hur man bevarar originalteckensnitt när man konverterar en PowerPoint-presentation till HTML med Aspose.Slides för .NET. Genom att följa dessa steg kan du säkerställa att ditt konverterade HTML-dokument behåller den visuella integriteten hos den ursprungliga presentationen.

## 9. Vanliga frågor

### F1: Kan jag anpassa listan över undantagna teckensnitt?

Ja, det kan du. Ändra `fontNameExcludeList` array för att inkludera eller exkludera specifika teckensnitt enligt dina krav.

### F2: Vad händer om jag inte vill bädda in alla teckensnitt?

Om du bara vill bädda in specifika teckensnitt kan du ändra koden därefter. Se dokumentationen för Aspose.Slides för .NET för mer information.

### F3: Finns det några licenskrav för att använda Aspose.Slides för .NET?

Ja, du kan behöva en giltig licens för att använda Aspose.Slides för .NET i dina projekt. Se Asposes webbplats för licensinformation.

### F4: Kan jag konvertera andra filformat till HTML med Aspose.Slides för .NET?

Aspose.Slides för .NET fokuserar främst på PowerPoint-presentationer. För att konvertera andra filformat till HTML kan du behöva utforska andra Aspose-produkter som är anpassade för dessa format.

### F5: Var kan jag få tillgång till ytterligare resurser och support?

Du hittar mer dokumentation, handledningar och support på Asposes webbplats. Besök [Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
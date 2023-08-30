---
title: Lägg till hyperlänk till bild
linktitle: Lägg till hyperlänk till bild
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du lägger till hyperlänkar till bilder i PowerPoint med Aspose.Slides för .NET. Förbättra presentationer med interaktivt innehåll.
type: docs
weight: 12
url: /sv/net/hyperlink-manipulation/add-hyperlink/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett omfattande bibliotek som gör det möjligt för utvecklare att skapa, ändra och manipulera PowerPoint-presentationer utan att förlita sig på Microsoft Office. Det ger ett brett utbud av funktioner, inklusive att lägga till och hantera hyperlänkar i bilder.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

- Visual Studio installerat på ditt system.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://downloads.aspose.com/slides/net).

## Lägga till en hyperlänk till en text i en bild

1. Skapa ett nytt C#-projekt i Visual Studio.
2. Lägg till en referens till Aspose.Slides DLL i ditt projekt.
3. Använd följande kod för att lägga till en hyperlänk till en text i en bild:

```csharp
using Aspose.Slides;

// Ladda presentationen
Presentation presentation = new Presentation("presentation.pptx");

// Få tillgång till en bild
ISlide slide = presentation.Slides[0];

// Öppna en textruta
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Lägg till en del av texten med en hyperlänk
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Lägga till en hyperlänk till en form i en bild

1. Följ stegen ovan för att skapa ett nytt C#-projekt och lägg till referensen Aspose.Slides.
2. Använd följande kod för att lägga till en hyperlänk till en form i en bild:

```csharp
using Aspose.Slides;

// Ladda presentationen
Presentation presentation = new Presentation("presentation.pptx");

// Få tillgång till en bild
ISlide slide = presentation.Slides[0];

// Få tillgång till en form
IShape shape = slide.Shapes[1];

// Lägg till en hyperlänk till formen
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Lägga till en hyperlänk till en bild

1. Följ de första stegen för att ställa in ditt C#-projekt och referera till Aspose.Slides-biblioteket.
2. Använd följande kod för att lägga till en hyperlänk till en bild:

```csharp
using Aspose.Slides;

// Ladda presentationen
Presentation presentation = new Presentation("presentation.pptx");

// Få tillgång till en bild
ISlide slide = presentation.Slides[2];

// Lägg till en hyperlänk till bilden
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Lägga till externa hyperlänkar

Förutom interna hyperlänkar kan du också lägga till externa hyperlänkar till dina bilder. Använd samma tillvägagångssätt som ovan, men ange den externa URL:en som hyperlänksmål.

## Ändra och ta bort hyperlänkar

För att ändra en befintlig hyperlänk eller ta bort den kan du komma åt hyperlänkegenskaperna för respektive bildelement och göra nödvändiga ändringar.

## Slutsats

Att lägga till hyperlänkar till bilder med Aspose.Slides för .NET är en enkel process som avsevärt kan förbättra interaktiviteten i dina presentationer. Oavsett om du vill länka till externa resurser eller skapa navigering i dina bilder, tillhandahåller Aspose.Slides de verktyg du behöver för att utföra dessa uppgifter effektivt.

## FAQ's

### Hur tar jag bort en hyperlänk från en del av texten?

 För att ta bort en hyperlänk från en del av texten kan du helt enkelt ställa in`HyperlinkClick` egendom till`null` för den delen.

### Kan jag lägga till hyperlänkar till andra former än textrutor?

Ja, du kan lägga till hyperlänkar till olika former, inklusive bilder och anpassade former, med hjälp av`HyperlinkClick` fast egendom.

### Är Aspose.Slides kompatibel med olika PowerPoint-format?

Ja, Aspose.Slides stöder olika PowerPoint-format, inklusive PPTX, PPT och mer.

### Hur kan jag testa hyperlänkarna i min presentation?

Du kan köra presentationen i en PowerPoint-visningsprogram eller -redigerare för att testa hyperlänkarnas funktionalitet.

### Var kan jag ladda ner Aspose.Slides för .NET-biblioteket?

 Du kan ladda ner Aspose.Slides for .NET-biblioteket från Asposes webbplats:[Ladda ner Aspose.Slides för .NET](https://releases.aspose.com/slides/net).
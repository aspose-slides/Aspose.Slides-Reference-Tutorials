---
title: Konvertera bilder till PDF med Notes
linktitle: Konvertera bilder till PDF med Notes
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Konvertera enkelt presentationsbilder med talaranteckningar till PDF med Aspose.Slides för .NET. Bevara innehåll och sammanhang sömlöst.
type: docs
weight: 18
url: /sv/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

# Skriv steg för steg handledning om att konvertera diabilder till PDF med anteckningar med Aspose.Slides för .NET

Letar du efter ett pålitligt sätt att konvertera dina PowerPoint-bilder till PDF-format samtidigt som du bevarar alla viktiga anteckningar? Kolla inte vidare! I denna omfattande handledning kommer vi att guida dig genom processen att använda Aspose.Slides för .NET för att utföra denna uppgift steg för steg.

## 1. Introduktion

Att konvertera PowerPoint-bilder till PDF med anteckningar kan vara ett värdefullt verktyg för att dela presentationer samtidigt som man säkerställer att viktiga sammanhang och kommentarer behålls. Aspose.Slides för .NET ger en kraftfull lösning för denna uppgift.

## 2. Ställa in din miljö

Innan vi dyker in i kodningsprocessen, se till att du har den nödvändiga miljön inställd. Du kommer att behöva:

- Visual Studio eller din föredragna .NET-utvecklingsmiljö.
- Aspose.Slides för .NET-biblioteket installerat.
- En PowerPoint-presentation med anteckningar som du vill konvertera.

## 3. Laddar presentationen

I din C#-kod måste du ladda PowerPoint-presentationen som du vill konvertera. Så här kan du göra det:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Klona objektglaset

För att säkerställa att din PDF innehåller alla nödvändiga bilder med anteckningar kan du klona dem från den ursprungliga presentationen. Här är hur:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Justera objektglasets storlek

Du kanske vill justera bildstorleken så att den passar din PDF. Aspose.Slides för .NET låter dig göra detta enkelt:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Konfigurera PDF-alternativ

För att styra hur dina anteckningar kommer att visas i PDF:en kan du konfigurera PDF-alternativen:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Spara som PDF med Notes

Slutligen kan du spara din presentation som en PDF med anteckningar:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Slutsats

Grattis! Du har framgångsrikt konverterat dina PowerPoint-bilder till ett PDF-format samtidigt som du har bevarat alla viktiga anteckningar. Aspose.Slides för .NET gör denna process enkel och effektiv.

## 9. Vanliga frågor

### F1: Kan jag anpassa layouten för anteckningarna i PDF-filen?

 Ja, du kan anpassa layouten för anteckningarna med hjälp av`INotesCommentsLayoutingOptions` i PDF-alternativen.

### F2: Stöder Aspose.Slides för .NET andra utdataformat förutom PDF?

Ja, Aspose.Slides för .NET stöder olika utdataformat, inklusive PPTX, DOCX och mer.

### F3: Finns det en testversion tillgänglig för Aspose.Slides för .NET?

 Ja, du kan få en gratis provversion av Aspose.Slides för .NET på[https://releases.aspose.com/](https://releases.aspose.com/).

### F4: Var kan jag få support för Aspose.Slides för .NET?

 Du kan hitta stöd och diskussioner i samhället på[https://forum.aspose.com/](https://forum.aspose.com/).

### F5: Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?

 Ja, du kan köpa en tillfällig licens på[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Sammanfattningsvis, med Aspose.Slides för .NET kan du enkelt konvertera PowerPoint-bilder till PDF-format med anteckningar intakta. Det är ett värdefullt verktyg för proffs som behöver dela presentationer med kollegor och kunder samtidigt som det säkerställer att viktiga sammanhang inte går förlorade.
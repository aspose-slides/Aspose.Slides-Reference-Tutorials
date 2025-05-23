---
"description": "Konvertera enkelt presentationsbilder med talaranteckningar till PDF med Aspose.Slides för .NET. Bevara innehåll och sammanhang sömlöst."
"linktitle": "Konvertera bilder till PDF med anteckningar"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Konvertera bilder till PDF med anteckningar"
"url": "/sv/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera bilder till PDF med anteckningar


# Skriv en steg-för-steg-handledning för att konvertera bilder till PDF med anteckningar med Aspose.Slides för .NET

Letar du efter ett pålitligt sätt att konvertera dina PowerPoint-bilder till PDF-format samtidigt som du bevarar alla viktiga anteckningar? Leta inte längre! I den här omfattande handledningen guidar vi dig genom processen att använda Aspose.Slides för .NET för att utföra denna uppgift steg för steg.

## 1. Introduktion

Att konvertera PowerPoint-bilder till PDF med anteckningar kan vara ett värdefullt verktyg för att dela presentationer samtidigt som det säkerställer att viktig kontext och kommentarer behålls. Aspose.Slides för .NET erbjuder en kraftfull lösning för denna uppgift.

## 2. Konfigurera din miljö

Innan vi går in i kodningsprocessen, se till att du har den nödvändiga miljön konfigurerad. Du behöver:

- Visual Studio eller din föredragna .NET-utvecklingsmiljö.
- Aspose.Slides för .NET-biblioteket installerat.
- En PowerPoint-presentation med anteckningar som du vill konvertera.

## 3. Ladda presentationen

din C#-kod behöver du ladda PowerPoint-presentationen som du vill konvertera. Så här gör du:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Kloning av bilden

För att säkerställa att din PDF innehåller alla nödvändiga bilder med anteckningar kan du klona dem från den ursprungliga presentationen. Så här gör du:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Justera bildstorlek

Du kanske vill justera bildstorleken så att den passar din PDF. Med Aspose.Slides för .NET kan du göra detta enkelt:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Konfigurera PDF-alternativ

För att styra hur dina anteckningar visas i PDF-filen kan du konfigurera PDF-alternativen:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Spara som PDF med Anteckningar

Slutligen kan du spara din presentation som en PDF med anteckningar:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Slutsats

Grattis! Du har konverterat dina PowerPoint-bilder till PDF-format samtidigt som du behåller alla viktiga anteckningar. Aspose.Slides för .NET gör den här processen enkel och effektiv.

## 9. Vanliga frågor

### F1: Kan jag anpassa layouten för anteckningarna i PDF-filen?

Ja, du kan anpassa anteckningarnas layout med hjälp av `INotesCommentsLayoutingOptions` i PDF-alternativen.

### F2: Stöder Aspose.Slides för .NET andra utdataformat förutom PDF?

Ja, Aspose.Slides för .NET stöder olika utdataformat, inklusive PPTX, DOCX och mer.

### F3: Finns det en testversion tillgänglig för Aspose.Slides för .NET?

Ja, du kan få en gratis provperiod av Aspose.Slides för .NET på [https://releases.aspose.com/](https://releases.aspose.com/).

### F4: Var kan jag få support för Aspose.Slides för .NET?

Du kan hitta stöd och diskussioner i gemenskapen på [https://forum.aspose.com/](https://forum.aspose.com/).

### F5: Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?

Ja, du kan köpa en tillfällig licens på [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Sammanfattningsvis kan du med Aspose.Slides för .NET enkelt konvertera PowerPoint-bilder till PDF-format med anteckningarna intakta. Det är ett värdefullt verktyg för yrkesverksamma som behöver dela presentationer med kollegor och kunder samtidigt som de säkerställer att viktig kontext inte går förlorad.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
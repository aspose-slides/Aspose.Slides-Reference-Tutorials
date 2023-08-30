---
title: Hantera sidhuvud och sidfot i Notes Slide
linktitle: Hantera sidhuvud och sidfot i Notes Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du anpassar sidhuvud och sidfot i anteckningsbilder med Aspose.Slides för .NET. Den här steg-för-steg-guiden ger exempel på källkod och täcker åtkomst, modifiering och stilelement.
type: docs
weight: 11
url: /sv/net/notes-slide-manipulation/header-and-footer-in-notes-slide/
---

## Introduktion till Aspose.Slides för .NET

Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med Microsoft PowerPoint-filer programmatiskt. Det gör det möjligt att manipulera och skapa presentationer, bilder, former och olika element i dem. I den här guiden kommer vi att fokusera på hur du hanterar sidhuvud och sidfotselement i anteckningsbilden med Aspose.Slides för .NET.

## Lägga till en anteckningsbild till en presentation

 För att komma igång, se till att du har Aspose.Slides för .NET installerat. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/net/). Efter installationen skapar du ett nytt projekt i din föredragna .NET-utvecklingsmiljö.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        // Ladda presentationen
        using (Presentation presentation = new Presentation())
        {
            // Lägg till en ny bild
            ISlide slide = presentation.Slides.AddEmptySlide();
            
            // Lägg till anteckningsbild till den aktuella bilden
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            
            // Din kod för att manipulera sidhuvuds- och sidfotselement kommer hit
            
            // Spara den ändrade presentationen
            presentation.Save("output.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Åtkomst till sidhuvud och sidfotselement

När du har lagt till en anteckningsbild till din presentation kan du komma åt sidhuvudet och sidfoten för anpassning. Sidhuvud- och sidfotselementen kan innehålla text, datum och bildnummer. Använd följande kod för att komma åt dessa element:

```csharp
INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

// Åtkomst till rubriktext
string headerText = headerFooterManager.HeaderText;

// Åtkomst till sidfotstext
string footerText = headerFooterManager.FooterText;

// Åtkomst till datum och tid
bool isDateTimeVisible = headerFooterManager.IsDateTimeVisible;

//Åtkomst till bildnummer
bool isSlideNumberVisible = headerFooterManager.IsSlideNumberVisible;
```

## Ändra sidhuvud och sidfotstext

Du kan enkelt ändra sidhuvudet och sidfoten för att ge sammanhang eller annan nödvändig information. Använd följande kod för att uppdatera sidhuvudet och sidfoten:

```csharp
headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");
```

## Styling av sidhuvud och sidfotselement

Aspose.Slides för .NET låter dig också utforma sidhuvudet och sidfoten enligt din presentations design. Du kan ändra teckensnitt, storlek, färg och justering. Här är ett exempel på hur man stylar elementen:

```csharp
ITextStyle textStyle = presentation.Slides[0].TextStyle;
textStyle.FontHeight = 14;
textStyle.FontColor.Color = Color.Blue;
textStyle.Alignment = TextAlignment.Center;

headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);
```

## Uppdatering av datum och bildnummer

För att uppdatera datum och bildnummer automatiskt, använd följande kod:

```csharp
headerFooterManager.SetDateTimeVisible(true);
headerFooterManager.SetSlideNumberVisible(true);
```

## Sparar den ändrade presentationen

Efter att ha anpassat sidhuvudet och sidfoten i anteckningsbilden kan du spara den ändrade presentationen i en fil:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Komplett källkod

Här är den fullständiga källkoden för att hantera sidhuvud och sidfotselement i anteckningsbilden med Aspose.Slides för .NET:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        using (Presentation presentation = new Presentation())
        {
            ISlide slide = presentation.Slides.AddEmptySlide();
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

            // Anpassa sidhuvud och sidfotselement
            headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
            headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");

            ITextStyle textStyle = presentation.Slides[0].TextStyle;
            textStyle.FontHeight = 14;
            textStyle.FontColor.Color = Color.Blue;
            textStyle.Alignment = TextAlignment.Center;

            headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
            headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);

            headerFooterManager.SetDateTimeVisible(true);
            headerFooterManager.SetSlideNumberVisible(true);

            // Spara den ändrade presentationen
            presentation.Save("modified.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Slutsats

den här guiden har vi utforskat hur man använder Aspose.Slides för .NET för att hantera sidhuvud och sidfotselement i anteckningsbilden i en presentation. Du lärde dig hur du lägger till en anteckningsbild, får åtkomst till sidhuvud och sidfotselement, ändrar text, stilelement och uppdaterar datum och bildnummer. Detta kraftfulla bibliotek möjliggör sömlös anpassning, vilket förbättrar den övergripande presentationsupplevelsen.

## FAQ's

### Hur kommer jag åt sidhuvudet och sidfoten i anteckningsbilden?

 För att komma åt sidhuvud och sidfotselement kan du använda`INotesHeaderFooterManager` gränssnitt från Aspose.Slides för .NET.

### Kan jag stila sidhuvudet och sidfoten?

 Ja, du kan formatera sidhuvudet och sidfoten med hjälp av`SetTextStyle` metod. Du kan anpassa teckenstorlek, färg, justering och andra egenskaper.

### Hur uppdaterar jag automatiskt datum och bildnummer?

 Du kan använda`SetDateTimeVisible` och`SetSlideNumberVisible` metoder för att automatiskt visa datum och bildnummer i sidhuvudet och sidfoten.

### Är Aspose.Slides för .NET kompatibelt med PowerPoint-filer?

Ja, Aspose.Slides för .NET är helt kompatibel med PowerPoint-filer, vilket gör att du kan manipulera och skapa presentationer programmatiskt.

### Var kan jag hitta den fullständiga källkoden för anpassning av sidhuvud och sidfot?

Du kan hitta det kompletta exemplet på källkoden i den här guiden. Se avsnittet "Fullständig källkod" för kodavsnittet.
---
title: Lägga till Stretch Offset för bildfyll i bilder med Aspose.Slides
linktitle: Lägga till Stretch Offset för bildfyllning i diabilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar dina presentationsbilder med Aspose.Slides för .NET. Den här steg-för-steg-guiden handlar om att lägga till stretchoffset för bildfyllning, skapa dynamiska bilder och optimera designen.
type: docs
weight: 18
url: /sv/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

moderna presentationer spelar bilder en avgörande roll för att förmedla budskap effektivt. Aspose.Slides, ett kraftfullt API för att arbeta med presentationsfiler i .NET, erbjuder en funktion som heter "Stretch Offset" som låter dig exakt styra hur bilder fylls i former. Den här artikeln guidar dig genom processen att lägga till stretch offset för bildfyllning i presentationsbilder med Aspose.Slides för .NET.

## Introduktion till Stretch Offset

Stretch Offset är en värdefull teknik när du behöver anpassa hur bilder visas i former. Det gör att du kan styra bildens position och inriktning i en form, vilket möjliggör kreativa och visuellt tilltalande bilddesigner. Genom att använda Aspose.Slides API kan du programmässigt implementera stretch offset och ge dina presentationer liv.

## Konfigurera din utvecklingsmiljö

 Innan vi dyker in i implementeringen, se till att du har Aspose.Slides för .NET installerat i din utvecklingsmiljö. Du kan ladda ner den från Asposes webbplats[nedladdningslänk](https://releases.aspose.com/slides/net/)När du har laddat ned, följ installationsinstruktionerna för att ställa in API:et för ditt projekt.

## Lägga till en bild till en bild

För att demonstrera stretch offset-funktionen, låt oss börja med att lägga till en bild till en bild med Aspose.Slides. Följande kodavsnitt visar hur du uppnår detta:

```csharp
// Instantiera ett presentationsobjekt
Presentation presentation = new Presentation();

// Gå till den första bilden
ISlide slide = presentation.Slides[0];

// Definiera bildfilens sökväg
string imagePath = "path_to_your_image.jpg";

// Lägg till en bild på bilden
byte[] imageBytes = File.ReadAllBytes(imagePath);
IPictureFillFormat pictureFill = slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, 400, 300).FillFormat.PictureFillFormat;
pictureFill.Picture.Image = presentation.Images.AddImage(imageBytes);

// Spara presentationen
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Tillämpa sträckförskjutning på bilder

 Nu när vi har lagt till en bild på en bild, låt oss utforska hur man tillämpar stretch offset på den. Stretch offset styrs av två egenskaper:`StretchX` och`StretchY`. Dessa egenskaper bestämmer förskjutningen av bilden inom formen horisontellt respektive vertikalt.

Så här kan du implementera stretch offset med Aspose.Slides:

```csharp
// Öppna bildfyllningsformatet
IPictureFillFormat pictureFill = slide.Shapes[0].FillFormat.PictureFillFormat;

// Applicera stretch offset
pictureFill.StretchX = 0.5; // Horisontell offset på 50 %
pictureFill.StretchY = -0.2; // Vertikal offset på -20 %
```

det här exemplet har vi satt en horisontell offset på 50 % och en vertikal offset på -20 %. Det negativa värdet för vertikal offset flyttar bilden uppåt inom formen.

## Justering av Stretch Offset-värden

 Att hitta de perfekta sträckförskjutningsvärdena kan kräva lite försök och misstag för att uppnå den önskade visuella effekten. Justera värdena för`StretchX` och`StretchY` för att passa din design och inriktningspreferenser. Experimentera med positiva och negativa värden för att se hur bildens placering förändras.

## Använda Stretch Offset med olika former

 Stretch offset kan tillämpas på olika formtyper, inklusive rektanglar, ellipser och mer. Metoden för att komma åt`PictureFillFormat` förblir konsekvent i olika former. Känn dig fri att utforska och experimentera med olika former för att skapa unika bildkompositioner.

## Avancerade tekniker och tips

- Kombinera stretch offset med andra formateringsfunktioner för intrikata mönster.
- Använd stretch offset för att framhäva specifika delar av en bild i en form.
-  Använd`PictureFillFormat.TileAsTexture`egenskap för att sida vid sida bilder inom former istället för att sträcka ut dem.

## Slutsats

Att integrera stretchoffset för bildfyllning i presentationsbilder med Aspose.Slides öppnar upp en värld av kreativa möjligheter. Med exakt kontroll över bildpositionering kan du förbättra den visuella effekten av dina presentationer. Genom att följa stegen som beskrivs i den här artikeln har du lärt dig hur du kan utnyttja den här funktionen effektivt.

## Vanliga frågor

### Hur kan jag ladda ner Aspose.Slides för .NET?

 Du kan ladda ner Aspose.Slides för .NET från Asposes webbplats[nedladdningslänk](https://releases.aspose.com/slides/net/).

### Kan jag använda stretch offset med vilken bildtyp som helst?

Ja, stretch offset kan tillämpas på bilder i olika format, inklusive JPG, PNG och mer.

###  Vad händer om jag ställer in båda`StretchX` and `StretchY` to the same value?

Om du ställer in båda egenskaperna till samma värde bibehålls bildens bildförhållande samtidigt som dess position flyttas inom formen.

### Är stretch offset kompatibel med animationer?

Ja, stretch offset fungerar sömlöst med diaanimationer, så att du kan skapa dynamiska presentationer.

### Hur får jag tillgång till avancerade alternativ för stretch offset?

Utforska Aspose.Slides-dokumentationen för djupgående information om avancerade stretch offset-tekniker och egenskaper.
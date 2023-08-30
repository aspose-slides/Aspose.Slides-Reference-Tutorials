---
title: Skapa skissade former i presentationsbilder med Aspose.Slides
linktitle: Skapa skissade former i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar fängslande presentationsbilder med skissade former med Aspose.Slides för .NET. Följ den här steg-för-steg-guiden med komplett källkod för att lägga till personliga och kreativa element till dina bilder.
type: docs
weight: 13
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Introduktion till att skapa skissade former i presentationsbilder

Presentationsbilder är ett kraftfullt verktyg för att förmedla information visuellt. Ibland kanske du vill sätta en personlig touch till dina bilder genom att inkludera skissade former, vilket kan göra dina presentationer mer engagerande och kreativa. I den här steg-för-steg-guiden kommer vi att utforska hur du uppnår detta med Aspose.Slides för .NET-biblioteket. I slutet av den här handledningen kommer du att kunna skapa presentationsbilder med skissade former som sticker ut. Låt oss dyka in!

## Konfigurera projektet

 Innan vi börjar, se till att du har .NET-utvecklingsmiljön inställd på din dator. Du kan ladda ner den senaste versionen av Aspose.Slides från webbplatsen[här](https://releases.aspose.com/slides/net/). När du har laddat ned, installerar du biblioteket i ditt projekt.

## Skapa en ny presentation

Låt oss börja med att skapa en ny presentation med Aspose.Slides. Så här kan du göra det:

```csharp
using Aspose.Slides;

// Skapa en ny presentation
Presentation presentation = new Presentation();
```

## Lägga till skissade former

För att lägga till skissade former till dina bilder kan du använda friformsformer tillgängliga i Aspose.Slides. Dessa former kan anpassas för att likna handritade skisser. Här är ett exempel på hur man lägger till en skissad rektangel till en bild:

```csharp
// Gå till den första bilden
ISlide slide = presentation.Slides[0];

// Definiera punkterna för den skissade rektangeln
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Lägg till en friformsform på bilden
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Anpassa utseendet på den skissade formen
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Anpassa skissade former

Du kan ytterligare anpassa de skissade formerna genom att justera deras färger, linjestilar och andra egenskaper. Experimentera med olika inställningar för att uppnå önskad handritad effekt.

## Spara och exportera presentationen

När du har lagt till skissade former till din presentation kan du spara den och exportera den till olika format, som PPTX eller PDF. Så här kan du göra det:

```csharp
// Spara presentationen till en fil
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Slutsats

den här handledningen utforskade vi hur man skapar presentationsbilder med skissade former med Aspose.Slides för .NET. Genom att lägga till skissade former på dina bilder kan du lägga till en kreativ och personlig touch till dina presentationer, vilket gör dem mer engagerande för din publik. Experimentera gärna med olika former och anpassningsalternativ för att skapa visuellt tilltalande bilder som lämnar en bestående effekt.

## FAQ's

### Hur kan jag ladda ner Aspose.Slides för .NET?

 Du kan ladda ner den senaste versionen av Aspose.Slides för .NET från deras releasesida[här](https://releases.aspose.com/slides/net/).

### Kan jag anpassa utseendet på skissade former?

Ja, du kan anpassa utseendet på skissade former genom att justera deras färger, linjestilar och andra egenskaper med Aspose.Slides.

### Är Aspose.Slides lämplig för både nybörjare och erfarna utvecklare?

Ja, Aspose.Slides tillhandahåller ett användarvänligt API som passar både nybörjare och erfarna utvecklare. Den erbjuder omfattande dokumentation som hjälper dig att komma igång.

### Kan jag exportera min presentation med skissade former till PDF?

Absolut! Du kan exportera din presentation med skissade former till olika format, inklusive PDF, med hjälp av exportalternativen från Aspose.Slides.

### Hur kan jag lägga till andra typer av skissade former, som cirklar eller linjer?

 Du kan lägga till andra typer av skissade former, som cirklar eller linjer, genom att ändra punkterna och formtypen i`AddFreeform` metod. Experimentera med olika punktkonfigurationer för att skapa de former du vill ha.
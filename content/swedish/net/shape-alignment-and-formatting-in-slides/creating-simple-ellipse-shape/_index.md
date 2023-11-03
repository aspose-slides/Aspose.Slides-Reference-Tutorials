---
title: Skapa enkel ellipsform i presentationsbilder med Aspose.Slides
linktitle: Skapa enkel ellipsform i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar en enkel ellipsform i presentationsbilder med Aspose.Slides för .NET. Den här steg-för-steg-guiden ger källkod och instruktioner för att lägga till, anpassa och spara ellipsformer.
type: docs
weight: 11
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Introduktion till att skapa enkel ellipsform i presentationsbilder

Om du vill förbättra dina presentationsbilder genom att lägga till visuellt tilltalande former, erbjuder Aspose.Slides för .NET en kraftfull lösning för att åstadkomma detta. I den här steg-för-steg-guiden går vi igenom processen att skapa en enkel ellipsform i dina presentationsbilder med Aspose.Slides för .NET.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio eller någon annan .NET-utvecklingsmiljö installerad.
-  Aspose.Slides för .NET-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

## Konfigurera ditt projekt

1. Skapa ett nytt Visual Studio-projekt eller öppna ett befintligt.
2. Lägg till en referens till Aspose.Slides för .NET-biblioteket i ditt projekt.

## Skapa en presentation

För att komma igång, låt oss skapa en ny presentation där vi lägger till vår ellipsform.

```csharp
using Aspose.Slides;

// Skapa en ny presentation
Presentation presentation = new Presentation();
```

## Lägga till en Ellipsform

Nu när vi har vår presentation klar, låt oss lägga till en ellipsform på en bild.

```csharp
// Öppna den första bilden av presentationen
ISlide slide = presentation.Slides[0];

// Definiera ellipsdimensioner och position
float x = 100;   // X-koordinat
float y = 100;   // Y-koordinat
float width = 200;  // Bredd
float height = 100; // Höjd

// Lägg till ellipsformen på bilden
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Anpassa Ellipsen

Du kan anpassa utseendet på ellipsformen med olika egenskaper.

```csharp
// Ställ in fyllningsfärgen för ellipsen
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

//Ställ in konturfärg och bredd
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Lägg till en textram till ellipsen
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Sparar presentationen

Efter att ha lagt till och anpassat ellipsformen är det dags att spara presentationen.

```csharp
// Spara presentationen
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Slutsats

Grattis! Du har framgångsrikt skapat en enkel ellipsform i dina presentationsbilder med Aspose.Slides för .NET. Den här guiden behandlade processen med att ställa in ditt projekt, skapa en presentation, lägga till en ellipsform, anpassa dess utseende och spara den slutliga presentationen.

## FAQ's

### Hur kan jag ändra placeringen av ellipsformen?

 Du kan ändra`x` och`y` koordinater när du lägger till ellipsformen för att justera dess position på bilden.

### Kan jag ändra färgen på ellipsens kontur?

 Ja, du kan ställa in konturfärgen med hjälp av`LineFormat.FillFormat.SolidFillColor.Color` fast egendom.

### Är det möjligt att lägga till text inuti ellipsen?

 Absolut! Du kan lägga till text till ellipsformen med hjälp av`TextFrame.Text` fast egendom.

### Vilka andra former kan jag skapa med Aspose.Slides för .NET?

Aspose.Slides för .NET stöder olika former, inklusive rektanglar, linjer, pilar och mer.

### Var kan jag hitta mer information om Aspose.Slides för .NET?

För detaljerad dokumentation och exempel, se[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).
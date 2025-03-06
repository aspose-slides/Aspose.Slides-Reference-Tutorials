---
title: Aspose.Slides - Skapa gruppformer i .NET
linktitle: Skapa gruppformer i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar gruppformer i PowerPoint med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för visuellt tilltalande presentationer.
weight: 11
url: /sv/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
Om du vill förbättra det visuella tilltalande av dina presentationsbilder och organisera innehåll mer effektivt, är inkorporering av gruppformer en kraftfull lösning. Aspose.Slides för .NET ger ett sömlöst sätt att skapa och manipulera gruppformer i dina PowerPoint-presentationer. I den här självstudien går vi igenom processen att skapa gruppformer med Aspose.Slides, och dela upp det i lätta att följa steg.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:
-  Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket installerat. Du kan ladda ner den från[hemsida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en arbetsmiljö med en .NET-kompatibel IDE, som Visual Studio.
- Grundläggande kunskaper i C#: Bekanta dig med grunderna i programmeringsspråket C#.
## Importera namnområden
I ditt C#-projekt börjar du med att importera de nödvändiga namnrymden:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Instantera presentationsklass

 Skapa en instans av`Presentation` klass och ange katalogen där dina dokument lagras:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Fortsätt med följande steg inom detta block
}
```

## Steg 2: Öppna den första bilden

Hämta den första bilden från presentationen:

```csharp
ISlide sld = pres.Slides[0];
```

## Steg 3: Få åtkomst till Shape Collection

Få tillgång till samlingen av former på bilden:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Steg 4: Lägga till en gruppform

Lägg till en gruppform på bilden:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Steg 5: Lägga till former i gruppformen

Fyll gruppformen med individuella former:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Steg 6: Lägga till Group Shape Frame

Definiera ramen för hela gruppformen:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Steg 7: Spara presentationen

Spara den ändrade presentationen i din angivna katalog:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Upprepa dessa steg i din C#-applikation för att framgångsrikt skapa gruppformer i dina presentationsbilder med Aspose.Slides.

## Slutsats
I den här handledningen utforskade vi processen att skapa gruppformer med Aspose.Slides för .NET. Genom att följa dessa steg kan du förbättra den visuella överklagandet och organisationen av dina PowerPoint-presentationer.
## Vanliga frågor
### Är Aspose.Slides kompatibel med den senaste versionen av .NET?
 Ja, Aspose.Slides uppdateras regelbundet för att stödja de senaste .NET-versionerna. Kolla[dokumentation](https://reference.aspose.com/slides/net/) för kompatibilitetsinformation.
### Kan jag prova Aspose.Slides innan jag köper?
 Absolut! Du kan ladda ner en gratis testversion[här](https://releases.aspose.com/).
### Var kan jag hitta stöd för Aspose.Slides-relaterade frågor?
Besök Aspose.Slides[forum](https://forum.aspose.com/c/slides/11) för samhällsstöd och diskussioner.
### Hur får jag en tillfällig licens för Aspose.Slides?
 Du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa en fullständig licens för Aspose.Slides?
 Du kan köpa en licens från[köpsidan](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

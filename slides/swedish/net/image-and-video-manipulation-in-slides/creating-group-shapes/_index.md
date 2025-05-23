---
"description": "Lär dig hur du skapar gruppformer i PowerPoint med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för visuellt tilltalande presentationer."
"linktitle": "Skapa gruppformer i presentationsbilder med Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Aspose.Slides - Skapa gruppformer i .NET"
"url": "/sv/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Skapa gruppformer i .NET

## Introduktion
Om du vill förbättra dina presentationsbilders visuella attraktionskraft och organisera innehåll mer effektivt är det en kraftfull lösning att integrera gruppformer. Aspose.Slides för .NET ger ett smidigt sätt att skapa och manipulera gruppformer i dina PowerPoint-presentationer. I den här handledningen går vi igenom processen för att skapa gruppformer med Aspose.Slides och delar upp den i lättförståeliga steg.
## Förkunskapskrav
Innan vi går in i handledningen, se till att du har följande:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket installerat. Du kan ladda ner det från [webbplats](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en arbetsmiljö med en .NET-kompatibel IDE, till exempel Visual Studio.
- Grundläggande kunskaper i C#: Bekanta dig med grunderna i programmeringsspråket C#.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i ditt C#-projekt:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Instansiera presentationsklassen

Skapa en instans av `Presentation` klass och ange katalogen där dina dokument lagras:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Fortsätt med följande steg inom detta block med hjälp av
}
```

## Steg 2: Öppna den första bilden

Hämta den första bilden från presentationen:

```csharp
ISlide sld = pres.Slides[0];
```

## Steg 3: Åtkomst till formsamlingen

Få åtkomst till samlingen av former på bilden:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Steg 4: Lägga till en gruppform

Lägg till en gruppform på bilden:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Steg 5: Lägga till former inuti gruppformen

Fyll gruppformen med enskilda former:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Steg 6: Lägga till gruppformram

Definiera ramen för hela gruppformen:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Steg 7: Spara presentationen

Spara den ändrade presentationen i din angivna katalog:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Upprepa dessa steg i ditt C#-program för att skapa gruppformer i dina presentationsbilder med Aspose.Slides.

## Slutsats
I den här handledningen utforskade vi processen att skapa gruppformer med Aspose.Slides för .NET. Genom att följa dessa steg kan du förbättra det visuella utseendet och organisationen i dina PowerPoint-presentationer.
## Vanliga frågor
### Är Aspose.Slides kompatibel med den senaste versionen av .NET?
Ja, Aspose.Slides uppdateras regelbundet för att stödja de senaste .NET-versionerna. Kontrollera [dokumentation](https://reference.aspose.com/slides/net/) för kompatibilitetsinformation.
### Kan jag prova Aspose.Slides innan jag köper?
Absolut! Du kan ladda ner en gratis testversion [här](https://releases.aspose.com/).
### Var kan jag hitta support för Aspose.Slides-relaterade frågor?
Besök Aspose.Slides [forum](https://forum.aspose.com/c/slides/11) för stöd och diskussioner i samhället.
### Hur får jag en tillfällig licens för Aspose.Slides?
Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).
### Var kan jag köpa en fullständig licens för Aspose.Slides?
Du kan köpa en licens från [köpsida](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
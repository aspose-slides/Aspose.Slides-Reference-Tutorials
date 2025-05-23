---
"description": "Förbättra dina presentationer med Aspose.Slides för .NET! Lär dig att tillämpa 3D-rotationseffekter på former i den här handledningen. Skapa dynamiska och visuellt fantastiska presentationer."
"linktitle": "Tillämpa 3D-rotationseffekt på former i presentationsbilder"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Bemästra 3D-rotation i presentationer med Aspose.Slides för .NET"
"url": "/sv/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra 3D-rotation i presentationer med Aspose.Slides för .NET

## Introduktion
Att skapa engagerande och dynamiska presentationsbilder är en viktig aspekt av effektiv kommunikation. Aspose.Slides för .NET erbjuder en kraftfull uppsättning verktyg för att förbättra dina presentationer, inklusive möjligheten att tillämpa 3D-rotationseffekter på former. I den här handledningen går vi igenom processen att tillämpa en 3D-rotationseffekt på former i presentationsbilder med hjälp av Aspose.Slides för .NET.
## Förkunskapskrav
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket för .NET installerat. Du kan ladda ner det från [webbplats](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö, till exempel Visual Studio, för att skriva och köra din kod.
## Importera namnrymder
Importera de namnrymder som behövs i ditt .NET-projekt för att utnyttja funktionaliteten i Aspose.Slides. Inkludera följande namnrymder i början av din kod:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt projekt i din föredragna .NET-utvecklingsmiljö. Se till att du har lagt till referensen Aspose.Slides i ditt projekt.
## Steg 2: Initiera presentationen
Skapa en Presentationsklass för att börja arbeta med bilder:
```csharp
Presentation pres = new Presentation();
```
## Steg 3: Lägg till autoform
Lägg till en autoform på bilden och ange dess typ, position och dimensioner:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Steg 4: Ställ in 3D-rotationseffekt
Konfigurera 3D-rotationseffekten för autoformen:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Steg 5: Spara presentationen
Spara den modifierade presentationen med den tillämpade 3D-rotationseffekten:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Steg 6: Upprepa för andra former
Om du har fler former, upprepa steg 3 till 5 för varje form.
## Slutsats
Att lägga till 3D-rotationseffekter till former i dina presentationsbilder kan avsevärt förbättra deras visuella attraktionskraft. Med Aspose.Slides för .NET blir den här processen enkel, vilket gör att du kan skapa fängslande presentationer.
## Vanliga frågor
### Kan jag använda 3D-rotation på textrutor i Aspose.Slides för .NET?
Ja, du kan använda 3D-rotationseffekter på olika former, inklusive textrutor, med Aspose.Slides.
### Finns det en testversion av Aspose.Slides för .NET tillgänglig?
Ja, du kan komma åt testversionen [här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Slides för .NET?
Besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) för stöd och diskussioner i samhället.
### Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?
Ja, du kan få ett tillfälligt körkort [här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta detaljerad dokumentation för Aspose.Slides för .NET?
Dokumentationen finns tillgänglig [här](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
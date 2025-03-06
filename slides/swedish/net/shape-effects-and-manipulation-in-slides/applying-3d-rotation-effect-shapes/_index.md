---
title: Bemästra 3D-rotation i presentationer med Aspose.Slides för .NET
linktitle: Tillämpa 3D-rotationseffekt på former i presentationsbilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Förbättra dina presentationer med Aspose.Slides för .NET! Lär dig att tillämpa 3D-rotationseffekter på former i den här handledningen. Skapa dynamisk och visuellt fantastisk presentation.
type: docs
weight: 23
url: /sv/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## Introduktion
Att skapa engagerande och dynamiska presentationsbilder är en nyckelaspekt för effektiv kommunikation. Aspose.Slides för .NET tillhandahåller en kraftfull uppsättning verktyg för att förbättra dina presentationer, inklusive möjligheten att tillämpa 3D-rotationseffekter på former. I den här handledningen kommer vi att gå igenom processen att tillämpa en 3D-rotationseffekt på former i presentationsbilder med Aspose.Slides för .NET.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket för .NET installerat. Du kan ladda ner den från[hemsida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö, som Visual Studio, för att skriva och köra din kod.
## Importera namnområden
I ditt .NET-projekt importerar du de nödvändiga namnområdena för att dra nytta av funktionerna i Aspose.Slides. Inkludera följande namnrymder i början av koden:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt projekt i din föredragna .NET-utvecklingsmiljö. Se till att du har lagt till Aspose.Slides-referensen till ditt projekt.
## Steg 2: Initiera presentationen
Instantiera en presentationsklass för att börja arbeta med bilder:
```csharp
Presentation pres = new Presentation();
```
## Steg 3: Lägg till AutoShape
Lägg till en AutoShape till bilden och ange dess typ, position och dimensioner:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Steg 4: Ställ in 3D-rotationseffekt
Konfigurera 3D-rotationseffekten för AutoShape:
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
Om du har ytterligare former, upprepa steg 3 till 5 för varje form.
## Slutsats
Att lägga till 3D-rotationseffekter till former i dina presentationsbilder kan avsevärt förbättra deras visuella tilltalande. Med Aspose.Slides för .NET blir denna process enkel, så att du kan skapa fängslande presentationer.
## Vanliga frågor
### Kan jag använda 3D-rotation på textrutor i Aspose.Slides för .NET?
Ja, du kan använda 3D-rotationseffekter på olika former, inklusive textrutor, med Aspose.Slides.
### Finns det en testversion av Aspose.Slides för .NET tillgänglig?
 Ja, du kan komma åt testversionen[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Slides för .NET?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd och diskussioner.
### Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?
 Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta detaljerad dokumentation för Aspose.Slides för .NET?
 Dokumentationen finns tillgänglig[här](https://reference.aspose.com/slides/net/).
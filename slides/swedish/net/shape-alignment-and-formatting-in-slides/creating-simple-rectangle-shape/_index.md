---
title: Skapa rektangelformer med Aspose.Slides för .NET
linktitle: Skapa enkel rektangelform i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Utforska en värld av dynamiska PowerPoint-presentationer med Aspose.Slides för .NET. Lär dig hur du skapar engagerande rektangelformer i bilder med denna steg-för-steg-guide.
weight: 12
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
Om du vill förbättra dina .NET-applikationer med dynamiska och visuellt tilltalande PowerPoint-presentationer, är Aspose.Slides för .NET din bästa lösning. I den här handledningen guidar vi dig genom processen att skapa en enkel rektangelform i presentationsbilder med Aspose.Slides för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
- Visual Studio: Se till att du har Visual Studio installerat på din utvecklingsmaskin.
-  Aspose.Slides for .NET: Ladda ner och installera Aspose.Slides for .NET-biblioteket från[här](https://releases.aspose.com/slides/net/).
- Grundläggande C#-kunskaper: Bekantskap med C#-programmeringsspråket är viktigt.
## Importera namnområden
I ditt C#-projekt börjar du med att importera de nödvändiga namnrymden för att komma åt Aspose.Slides-funktioner:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera projektet
Börja med att skapa ett nytt C#-projekt i Visual Studio. Se till att Aspose.Slides för .NET är korrekt refererad i ditt projekt.
## Steg 2: Initiera presentationsobjekt
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Din kod för nästa steg kommer här.
}
```
## Steg 3: Skaffa den första bilden
```csharp
ISlide sld = pres.Slides[0];
```
## Steg 4: Lägg till Rectangle AutoShape
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Den här koden lägger till en rektangelform vid koordinater (50, 150) med en bredd på 150 och en höjd på 50.
## Steg 5: Spara presentationen
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Detta steg sparar presentationen med den tillagda rektangelformen till den angivna katalogen.
## Slutsats
Grattis! Du har framgångsrikt skapat en enkel rektangelform i en presentationsbild med Aspose.Slides för .NET. Det här är bara början – Aspose.Slides erbjuder ett brett utbud av funktioner för att ytterligare anpassa och förbättra dina presentationer.
## Vanliga frågor
### Kan jag använda Aspose.Slides för .NET i både Windows- och Linux-miljöer?
Ja, Aspose.Slides för .NET är plattformsoberoende och kan användas i både Windows- och Linux-miljöer.
### Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 Ja, du kan få en gratis provperiod[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Slides för .NET?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd.
### Kan jag köpa en tillfällig licens för Aspose.Slides för .NET?
 Ja, du kan köpa en tillfällig licens[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
 Se dokumentationen[här](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

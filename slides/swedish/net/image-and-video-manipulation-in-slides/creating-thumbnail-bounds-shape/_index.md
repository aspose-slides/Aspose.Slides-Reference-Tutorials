---
title: Skapa miniatyrbild med gränser för form i Aspose.Slides
linktitle: Skapa miniatyrbild med gränser för form i Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lås upp kraften i Aspose.Slides för .NET! Lär dig att skapa formminiatyrer utan ansträngning med gränser med hjälp av vår steg-för-steg-guide.
weight: 10
url: /sv/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
Om du är en .NET-utvecklare som söker en robust lösning för att skapa miniatyrbilder med gränser för former i PowerPoint-presentationer, är Aspose.Slides för .NET ditt bästa verktyg. Detta kraftfulla bibliotek ger sömlös integration, vilket gör att du effektivt kan manipulera och extrahera värdefull information från PowerPoint-filer. I den här handledningen går vi igenom processen att skapa en miniatyrbild med gränser för en form med Aspose.Slides.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  Aspose.Slides for .NET Library: Ladda ner och installera Aspose.Slides for .NET-biblioteket från[här](https://releases.aspose.com/slides/net/).
2. Din dokumentkatalog: Ersätt "Din dokumentkatalog" i kodavsnittet med den faktiska sökvägen till din dokumentkatalog.
## Importera namnområden
Börja med att importera de nödvändiga namnområdena för att utnyttja funktionerna i Aspose.Slides. Lägg till följande kod i början av ditt projekt:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
Låt oss nu dela upp den medföljande koden i flera steg för en heltäckande förståelse:
## Steg 1: Instantera presentationsklass
```csharp
string dataDir = "Your Documents Directory";
// Instantiera en presentationsklass som representerar presentationsfilen
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Presentationsobjektet är nu redo för vidare manipulation.
}
```
 I det här steget initierar vi Aspose.Slides`Presentation` klass, som representerar PowerPoint-presentationsfilen. De`using` uttalande säkerställer korrekt avyttring av resurser när blocket har lämnats.
## Steg 2: Skapa en bild med bunden form
```csharp
// Skapa en utseendebunden formbild
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // Bitmappsobjektet innehåller nu miniatyrbilden med angivna gränser.
}
```
 Detta steg innebär att skapa en miniatyrbild av en form med specificerade gränser. Här,`ShapeThumbnailBounds.Appearance` används för att definiera utseendets gränser. Justera parametrarna (1, 1) enligt dina krav.
## Steg 3: Spara bilden på disk
```csharp
//Spara bilden på disk i PNG-format
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
I detta sista steg sparas den genererade miniatyrbilden på disken i PNG-format. Du kan anpassa filnamnet och formatet baserat på dina preferenser.
Nu har du skapat en miniatyrbild med gränser för en form med Aspose.Slides för .NET! Denna process är effektiv och kan sömlöst integreras i dina .NET-projekt för hantering av PowerPoint-presentationer.
## Slutsats
Aspose.Slides för .NET förenklar processen att arbeta med PowerPoint-presentationer och ger utvecklare kraftfulla verktyg för uppgifter som att skapa miniatyrer med gränser för former. Genom att följa den här steg-för-steg-guiden har du fått insikter i hur du effektivt använder det här biblioteket för dina .NET-projekt.
## Vanliga frågor
### Är Aspose.Slides kompatibel med det senaste .NET-ramverket?
Ja, Aspose.Slides uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET framework-versionerna.
### Kan jag använda Aspose.Slides för kommersiella projekt?
 Absolut! Aspose.Slides erbjuder licensalternativ för både individuell och kommersiell användning. Besök[här](https://purchase.aspose.com/buy) för att utforska licensdetaljer.
### Finns det en gratis testversion tillgänglig för Aspose.Slides?
 Ja, du kan få tillgång till en gratis provperiod[här](https://releases.aspose.com/)att utforska funktionerna innan du gör ett köp.
### Hur kan jag få support för Aspose.Slides?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) att få kontakt med samhället och söka hjälp från erfarna utvecklare.
### Kan jag få en tillfällig licens för Aspose.Slides?
 Ja, du kan få en tillfällig licens[här](https://purchase.aspose.com/temporary-license/) för kortsiktiga projektbehov.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

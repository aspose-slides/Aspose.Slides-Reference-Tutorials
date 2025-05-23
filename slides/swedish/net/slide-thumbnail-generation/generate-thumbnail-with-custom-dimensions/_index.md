---
"description": "Lär dig hur du genererar anpassade miniatyrbilder från PowerPoint-presentationer med Aspose.Slides för .NET. Förbättra användarupplevelsen och funktionaliteten."
"linktitle": "Generera miniatyrbild med anpassade dimensioner"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Generera miniatyrbilder i bilder med anpassade dimensioner"
"url": "/sv/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generera miniatyrbilder i bilder med anpassade dimensioner


Att skapa anpassade miniatyrbilder av dina PowerPoint-presentationer kan vara en värdefull tillgång, oavsett om du bygger en interaktiv applikation, förbättrar användarupplevelsen eller optimerar innehåll för olika plattformar. I den här handledningen guidar vi dig genom processen att generera anpassade miniatyrbilder från PowerPoint-presentationer med hjälp av biblioteket Aspose.Slides för .NET. Detta kraftfulla bibliotek låter dig manipulera, konvertera och förbättra PowerPoint-filer programmatiskt i .NET-applikationer.

## Förkunskapskrav

Innan vi går in på att skapa anpassade miniatyrbilder, se till att du har följande förutsättningar på plats:

### 1. Aspose.Slides för .NET

Du behöver ha biblioteket Aspose.Slides för .NET installerat i ditt projekt. Om du inte redan har gjort det kan du hitta nödvändig dokumentation och nedladdningslänkar. [här](https://reference.aspose.com/slides/net/).

### 2. En PowerPoint-presentation

Se till att du har PowerPoint-presentationen som du vill generera en anpassad miniatyrbild från. Presentationen ska vara tillgänglig i din projektkatalog.

### 3. Utvecklingsmiljö

För att följa den här handledningen bör du ha praktiska kunskaper i .NET-programmering med C# och en utvecklingsmiljö som Visual Studio.

Nu när vi har gått igenom förutsättningarna, låt oss dela upp processen för att generera anpassade miniatyrbilder i steg-för-steg-instruktioner.

## Importera namnrymder

Först måste du inkludera de namnrymder som krävs i din C#-kod. Dessa namnrymder låter dig arbeta med Aspose.Slides och manipulera PowerPoint-presentationer.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Steg 1: Ladda presentationen

Börja med att ladda PowerPoint-presentationen som du vill generera en anpassad miniatyrbild från. Detta görs med hjälp av Aspose.Slides-biblioteket.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instansiera en Presentation-klass som representerar presentationsfilen
using (Presentation pres = new Presentation(srcFileName))
{
    // Din kod för miniatyrgenerering kommer att placeras här
}
```

## Steg 2: Öppna bilden

I den laddade presentationen behöver du komma åt den specifika bilden från vilken du vill generera den anpassade miniatyrbilden. Du kan välja bilden utifrån dess index.

```csharp
// Gå till den första bilden (du kan ändra indexet efter behov)
ISlide sld = pres.Slides[0];
```

## Steg 3: Definiera anpassade miniatyrdimensioner

Ange önskade dimensioner för din anpassade miniatyrbild. Du kan definiera bredd och höjd i pixlar enligt programmets krav.

```csharp
int desiredX = 1200; // Bredd
int desiredY = 800;  // Höjd
```

## Steg 4: Beräkna skalningsfaktorer

För att bibehålla bildförhållandet för bilden, beräkna skalningsfaktorerna för X- och Y-dimensionerna baserat på bildens storlek och dina önskade dimensioner.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Steg 5: Generera miniatyrbilden

Skapa en fullskalig bild av bilden med de angivna anpassade måtten och spara den på disk i JPEG-format.

```csharp
// Skapa en fullskalig bild
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Spara bilden på disken i JPEG-format
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nu när du har följt dessa steg borde du ha genererat en anpassad miniatyrbild från din PowerPoint-presentation.

## Slutsats

Att generera anpassade miniatyrbilder från PowerPoint-presentationer med hjälp av Aspose.Slides för .NET är en värdefull färdighet som kan förbättra användarupplevelsen och funktionaliteten i dina applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt skapa anpassade miniatyrbilder som uppfyller dina specifika krav.

---

## Vanliga frågor (FAQs)

### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med PowerPoint-presentationer programmatiskt i .NET-applikationer.

### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
Du kan hitta dokumentationen [här](https://reference.aspose.com/slides/net/).

### Är Aspose.Slides för .NET gratis att använda?
Aspose.Slides för .NET är ett kommersiellt bibliotek. Du hittar information om priser och licenser. [här](https://purchase.aspose.com/buy).

### Behöver jag avancerade programmeringskunskaper för att använda Aspose.Slides för .NET?
Även om viss kunskap om .NET-programmering är fördelaktigt, erbjuder Aspose.Slides för .NET ett användarvänligt API som förenklar arbetet med PowerPoint-presentationer.

### Finns teknisk support tillgänglig för Aspose.Slides för .NET?
Ja, du har tillgång till teknisk support och communityforum [här](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
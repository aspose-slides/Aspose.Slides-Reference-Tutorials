---
title: Skapa miniatyrbilder i presentationer med anpassade mått
linktitle: Skapa miniatyrer med anpassade mått
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar anpassade miniatyrbilder från PowerPoint-presentationer med Aspose.Slides för .NET. Förbättra användarupplevelsen och funktionaliteten.
weight: 13
url: /sv/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa miniatyrbilder i presentationer med anpassade mått


Att skapa anpassade miniatyrbilder av dina PowerPoint-presentationer kan vara en värdefull tillgång, oavsett om du bygger en interaktiv applikation, förbättrar användarupplevelsen eller optimerar innehåll för olika plattformar. I den här handledningen kommer vi att guida dig genom processen att skapa anpassade miniatyrbilder från PowerPoint-presentationer med hjälp av Aspose.Slides för .NET-biblioteket. Detta kraftfulla bibliotek låter dig manipulera, konvertera och förbättra PowerPoint-filer programmatiskt i .NET-applikationer.

## Förutsättningar

Innan vi dyker in i att skapa anpassade miniatyrbilder, se till att du har följande förutsättningar på plats:

### 1. Aspose.Slides för .NET

 Du måste ha Aspose.Slides för .NET-biblioteket installerat i ditt projekt. Om du inte redan har gjort det kan du hitta den nödvändiga dokumentationen och ladda ner länkar[här](https://reference.aspose.com/slides/net/).

### 2. En PowerPoint-presentation

Se till att du har PowerPoint-presentationen från vilken du vill skapa en anpassad miniatyrbild. Denna presentation bör vara tillgänglig i din projektkatalog.

### 3. Utvecklingsmiljö

För att följa den här handledningen bör du ha praktiska kunskaper om .NET-programmering med C# och en uppsatt utvecklingsmiljö, som Visual Studio.

Nu när vi har täckt förutsättningarna, låt oss dela upp processen för att skapa anpassade miniatyrer i steg-för-steg-instruktioner.

## Importera namnområden

Först måste du inkludera de nödvändiga namnrymden i din C#-kod. Dessa namnutrymmen låter dig arbeta med Aspose.Slides och manipulera PowerPoint-presentationer.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Steg 1: Ladda presentationen

Börja med att ladda PowerPoint-presentationen från vilken du vill skapa en anpassad miniatyrbild. Detta uppnås med Aspose.Slides-biblioteket.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instantiera en presentationsklass som representerar presentationsfilen
using (Presentation pres = new Presentation(srcFileName))
{
    // Din kod för att generera miniatyrer kommer hit
}
```

## Steg 2: Öppna bilden

Inom den laddade presentationen måste du komma åt den specifika bild från vilken du vill generera den anpassade miniatyrbilden. Du kan välja bilden efter dess index.

```csharp
// Öppna den första bilden (du kan ändra indexet efter behov)
ISlide sld = pres.Slides[0];
```

## Steg 3: Definiera anpassade miniatyrdimensioner

Ange önskade mått för din anpassade miniatyrbild. Du kan definiera bredd och höjd i pixlar enligt din applikations krav.

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

## Steg 5: Skapa miniatyrbilden

Skapa en fullskalig bild av bilden med de angivna anpassade måtten och spara den på disk i JPEG-format.

```csharp
// Skapa en fullskalig bild
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Spara bilden på disken i JPEG-format
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nu när du har följt dessa steg bör du ha skapat en anpassad miniatyrbild från din PowerPoint-presentation.

## Slutsats

Att generera anpassade miniatyrbilder från PowerPoint-presentationer med Aspose.Slides för .NET är en värdefull färdighet som kan förbättra användarupplevelsen och funktionaliteten i dina applikationer. Genom att följa stegen som beskrivs i denna handledning kan du enkelt skapa anpassade miniatyrer som uppfyller dina specifika krav.

---

## Vanliga frågor (vanliga frågor)

### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med PowerPoint-presentationer programmatiskt i .NET-applikationer.

### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
 Du hittar dokumentationen[här](https://reference.aspose.com/slides/net/).

### Är Aspose.Slides för .NET gratis att använda?
 Aspose.Slides för .NET är ett kommersiellt bibliotek. Du kan hitta pris- och licensinformation[här](https://purchase.aspose.com/buy).

### Behöver jag avancerade programmeringskunskaper för att använda Aspose.Slides för .NET?
Även om viss kunskap om .NET-programmering är fördelaktig, tillhandahåller Aspose.Slides för .NET ett användarvänligt API som förenklar arbetet med PowerPoint-presentationer.

### Finns teknisk support tillgänglig för Aspose.Slides för .NET?
 Ja, du kan komma åt teknisk support och communityforum[här](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

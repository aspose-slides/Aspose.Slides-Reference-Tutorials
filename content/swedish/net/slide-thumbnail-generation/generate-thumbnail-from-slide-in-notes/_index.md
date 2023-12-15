---
title: Generera miniatyrbild från Slide in Notes
linktitle: Generera miniatyrbild från Slide in Notes
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du genererar miniatyrer från bilder i anteckningsdelen av din presentation med Aspose.Slides för .NET. Förbättra ditt visuella innehåll!
type: docs
weight: 12
url: /sv/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

en värld av moderna presentationer är visuellt innehåll kung. Att skapa tilltalande bilder är avgörande för effektiv kommunikation. Ett sätt att förbättra dina presentationer är genom att generera miniatyrer från bilder, särskilt när du vill framhäva specifika detaljer eller dela en översikt. Aspose.Slides för .NET är ett kraftfullt verktyg som kan hjälpa dig att uppnå detta sömlöst. I den här steg-för-steg-guiden går vi igenom processen att generera miniatyrer från bilder i anteckningssektionen i en presentation med Aspose.Slides för .NET.

## Förutsättningar

Innan vi dyker in i detaljerna bör du ha följande förutsättningar på plats:

### 1. Aspose.Slides för .NET

 Se till att du har Aspose.Slides för .NET installerat och konfigurerat. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net/).

### 2. .NET-miljö

Du bör ha en .NET-utvecklingsmiljö redo på ditt system.

### 3. En presentationsfil

 Ha en presentationsfil (t.ex.`ThumbnailFromSlideInNotes.pptx`) från vilken du vill generera miniatyrer.

Låt oss nu dela upp processen i steg:

## Steg 1: Importera namnområden

Först måste du importera de nödvändiga namnrymden för att arbeta med Aspose.Slides. Lägg till följande kod i början av ditt C#-skript:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Steg 2: Ladda presentationen

 Därefter måste du ladda presentationsfilen som innehåller bilderna med anteckningar. Använd följande kod för att instansiera en`Presentation` klass:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Din kod kommer hit
}
```

## Steg 3: Gå till bilden

Du kan välja vilken bild i presentationen du vill generera en miniatyrbild för. I det här exemplet kommer vi åt den första bilden:

```csharp
ISlide sld = pres.Slides[0];
```

## Steg 4: Definiera önskade mått

Ange måtten (bredd och höjd) för den miniatyrbild du vill generera. Till exempel:

```csharp
int desiredX = 1200; // Bredd
int desiredY = 800;  // Höjd
```

## Steg 5: Beräkna skalningsfaktorer

För att säkerställa att miniatyrbilden passar de önskade måtten, beräkna skalningsfaktorerna enligt följande:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Steg 6: Skapa en miniatyrbild

Skapa nu en bildminiatyr i full skala med de beräknade skalningsfaktorerna:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Steg 7: Spara miniatyrbilden

Slutligen, spara den genererade miniatyren som en JPEG-bild:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Det är allt! Du har framgångsrikt skapat en miniatyrbild från en bild i anteckningsdelen av din presentation med Aspose.Slides för .NET.

## Slutsats

Att integrera miniatyrer i dina presentationer kan avsevärt förbättra deras visuella tilltalande och effektivitet. Aspose.Slides för .NET gör denna process enkel, så att du enkelt kan skapa anpassade miniatyrer från dina bilder.

## Vanliga frågor (vanliga frågor)

### Vilka format kan jag spara de genererade miniatyrerna i?
Du kan spara miniatyrerna i olika format, inklusive JPEG, PNG och mer, beroende på dina krav.

### Kan jag skapa miniatyrer för flera bilder samtidigt?
Ja, du kan gå igenom bilderna i din presentation och generera miniatyrer för var och en.

### Är Aspose.Slides för .NET kompatibelt med olika .NET-ramverk?
Ja, Aspose.Slides för .NET är kompatibel med olika .NET-ramverk, inklusive .NET Core och .NET Framework.

### Kan jag anpassa utseendet på de genererade miniatyrerna?
Absolut! Aspose.Slides för .NET ger alternativ för att anpassa utseendet på miniatyrbilderna, som mått, kvalitet och mer.

### Var kan jag få support eller ytterligare hjälp med Aspose.Slides för .NET?
 Du kan hitta hjälp och engagera dig i Aspose-gemenskapen på[Aspose Support Forum](https://forum.aspose.com/).
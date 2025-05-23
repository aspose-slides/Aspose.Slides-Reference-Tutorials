---
"description": "Lär dig hur du genererar miniatyrbilder från bilder i anteckningsavsnittet i din presentation med Aspose.Slides för .NET. Förbättra ditt visuella innehåll!"
"linktitle": "Generera miniatyrbild från bild i anteckningar"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Generera miniatyrbild från bild i anteckningar"
"url": "/sv/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generera miniatyrbild från bild i anteckningar


den moderna presentationsvärlden är visuellt innehåll kung. Att skapa tilltalande bilder är avgörande för effektiv kommunikation. Ett sätt att förbättra dina presentationer är att generera miniatyrbilder från bilder, särskilt när du vill betona specifika detaljer eller dela en översikt. Aspose.Slides för .NET är ett kraftfullt verktyg som kan hjälpa dig att uppnå detta smidigt. I den här steg-för-steg-guiden guidar vi dig genom processen att generera miniatyrbilder från bilder i anteckningsavsnittet i en presentation med Aspose.Slides för .NET.

## Förkunskapskrav

Innan vi går in på detaljerna bör du ha följande förutsättningar på plats:

### 1. Aspose.Slides för .NET

Se till att du har Aspose.Slides för .NET installerat och konfigurerat. Du kan ladda ner det från [här](https://releases.aspose.com/slides/net/).

### 2. .NET-miljö

Du bör ha en .NET-utvecklingsmiljö redo på ditt system.

### 3. En presentationsfil

Ha en presentationsfil (t.ex. `ThumbnailFromSlideInNotes.pptx`) som du vill generera miniatyrbilder från.

Nu ska vi dela upp processen i steg:

## Steg 1: Importera namnrymder

Först måste du importera de namnrymder som behövs för att fungera med Aspose.Slides. Lägg till följande kod i början av ditt C#-skript:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Steg 2: Ladda presentationen

Nästa steg är att ladda presentationsfilen som innehåller bilderna med anteckningar. Använd följande kod för att instansiera en `Presentation` klass:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Din kod hamnar här
}
```

## Steg 3: Öppna bilden

Du kan välja vilken bild i presentationen du vill generera en miniatyrbild för. I det här exemplet kommer vi åt den första bilden:

```csharp
ISlide sld = pres.Slides[0];
```

## Steg 4: Definiera önskade dimensioner

Ange måtten (bredd och höjd) för miniatyrbilden du vill generera. Till exempel:

```csharp
int desiredX = 1200; // Bredd
int desiredY = 800;  // Höjd
```

## Steg 5: Beräkna skalningsfaktorer

För att säkerställa att miniatyrbilden får önskade dimensioner, beräkna skalningsfaktorerna enligt följande:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Steg 6: Skapa en miniatyrbild

Skapa nu en fullskalig miniatyrbild med hjälp av de beräknade skalningsfaktorerna:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Steg 7: Spara miniatyrbilden

Slutligen, spara den genererade miniatyrbilden som en JPEG-bild:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Det var allt! Du har lyckats generera en miniatyrbild från en bild i anteckningsavsnittet i din presentation med hjälp av Aspose.Slides för .NET.

## Slutsats

Att integrera miniatyrbilder i dina presentationer kan avsevärt förbättra deras visuella attraktionskraft och effektivitet. Aspose.Slides för .NET gör den här processen enkel och låter dig enkelt skapa anpassade miniatyrbilder från dina bilder.

## Vanliga frågor (FAQs)

### I vilka format kan jag spara de genererade miniatyrbilderna?
Du kan spara miniatyrbilderna i olika format, inklusive JPEG, PNG och mer, beroende på dina behov.

### Kan jag generera miniatyrbilder för flera bilder samtidigt?
Ja, du kan loopa igenom bilderna i din presentation och generera miniatyrbilder för var och en.

### Är Aspose.Slides för .NET kompatibelt med olika .NET-ramverk?
Ja, Aspose.Slides för .NET är kompatibelt med olika .NET-ramverk, inklusive .NET Core och .NET Framework.

### Kan jag anpassa utseendet på de genererade miniatyrbilderna?
Absolut! Aspose.Slides för .NET erbjuder alternativ för att anpassa utseendet på miniatyrbilderna, såsom dimensioner, kvalitet med mera.

### Var kan jag få support eller ytterligare hjälp med Aspose.Slides för .NET?
Du kan hitta hjälp och engagera dig i Aspose-communityn på [Aspose Supportforum](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
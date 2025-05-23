---
"description": "Lär dig hur du extraherar videor från PowerPoint-bilder med Aspose.Slides för .NET. Den här steg-för-steg-guiden förenklar processen för dig."
"linktitle": "Extrahera video från bild"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Hur man extraherar video från en bild med Aspose.Slides för .NET"
"url": "/sv/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar video från en bild med Aspose.Slides för .NET


Aspose.Slides för .NET är ett kraftfullt bibliotek som låter dig arbeta med PowerPoint-presentationer i en .NET-miljö. En av de användbara funktionerna det erbjuder är möjligheten att extrahera videor från bilder. I den här steg-för-steg-guiden visar vi dig hur du extraherar en video från en PowerPoint-bild med hjälp av Aspose.Slides för .NET.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

- Aspose.Slides för .NET: Du måste ha Aspose.Slides för .NET installerat. Du kan hämta det från [webbplats](https://purchase.aspose.com/buy).

- En PowerPoint-presentation: Förbered en PowerPoint-presentation (t.ex. Video.pptx) som innehåller videon du vill extrahera.

## Importera namnrymder

Du behöver importera de namnrymder som krävs för att fungera med Aspose.Slides för .NET. Så här gör du:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Nu ska vi dela upp processen att extrahera en video från en bild i flera steg.

## Steg 1: Ställ in dokumentkatalogen

```csharp
string dataDir = "Your Document Directory";
```

Ersätta `"Your Document Directory"` med sökvägen till katalogen där din PowerPoint-presentation finns.

## Steg 2: Ladda presentationen

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Den här koden initierar ett presentationsobjekt som representerar din PowerPoint-presentationsfil.

## Steg 3: Iterera genom bilder och former

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Här loopar vi igenom varje bild i presentationen och itererar sedan igenom formerna i den första bilden (ändra efter behov).

## Steg 4: Kontrollera om formen är en videobildruta

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Det här steget kontrollerar om formen på bilden är en videobildruta.

## Steg 5: Extrahera videodata

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Den här koden extraherar information om videon, inklusive dess innehållstyp och binära data.

## Steg 6: Spara videon

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Slutligen sparar detta steg videon till en ny fil i den angivna katalogen.

När du har slutfört dessa steg har du framgångsrikt extraherat en video från en PowerPoint-bild med hjälp av Aspose.Slides för .NET.

## Slutsats

Aspose.Slides för .NET förenklar processen att arbeta med PowerPoint-presentationer, vilket gör att du enkelt kan utföra uppgifter som att extrahera videor från bilder. Genom att följa den här steg-för-steg-guiden och använda Aspose.Slides-biblioteket kan du förbättra dina .NET-applikationer med kraftfulla PowerPoint-funktioner.

## Vanliga frågor (FAQ)

### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett bibliotek som gör det möjligt för .NET-applikationer att arbeta med PowerPoint-presentationer, inklusive att skapa, redigera och extrahera innehåll.

### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
Du kan hitta dokumentationen [här](https://reference.aspose.com/slides/net/).

### Finns Aspose.Slides för .NET tillgänglig för en gratis provperiod?
Ja, du kan få en gratis testversion från [här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Slides för .NET?
Du kan ansöka om en tillfällig licens från [den här länken](https://purchase.aspose.com/temporary-license/).

### Var kan jag få support för Aspose.Slides för .NET?
Du kan hitta stöd på [Aspose.Slides-forum](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
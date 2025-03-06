---
title: Hur man extraherar video från bild med Aspose.Slides för .NET
linktitle: Extrahera video från Slide
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du extraherar videor från PowerPoint-bilder med Aspose.Slides för .NET. Denna steg-för-steg-guide förenklar processen för dig.
weight: 14
url: /sv/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man extraherar video från bild med Aspose.Slides för .NET


Aspose.Slides för .NET är ett kraftfullt bibliotek som låter dig arbeta med PowerPoint-presentationer i en .NET-miljö. En av de användbara funktionerna är möjligheten att extrahera videor från bilder. I den här steg-för-steg-guiden kommer vi att visa dig hur du extraherar en video från en PowerPoint-bild med Aspose.Slides för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

-  Aspose.Slides för .NET: Du måste ha Aspose.Slides för .NET installerat. Du kan få det från[hemsida](https://purchase.aspose.com/buy).

- En PowerPoint-presentation: Förbered en PowerPoint-presentation (t.ex. Video.pptx) som innehåller videon du vill extrahera.

## Importera namnområden

Du måste importera de nödvändiga namnområdena för att arbeta med Aspose.Slides för .NET. Så här kan du göra det:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Låt oss nu dela upp processen att extrahera en video från en bild i flera steg.

## Steg 1: Ställ in dokumentkatalogen

```csharp
string dataDir = "Your Document Directory";
```

 Byta ut`"Your Document Directory"` med sökvägen till katalogen där din PowerPoint-presentation finns.

## Steg 2: Ladda presentationen

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Den här koden initierar ett presentationsobjekt som representerar din PowerPoint-presentationsfil.

## Steg 3: Iterera genom diabilder och former

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Här går vi igenom varje bild i presentationen och itererar sedan genom formerna i den första bilden (ändra efter behov).

## Steg 4: Kontrollera om Shape är en videoram

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Det här steget kontrollerar om formen på bilden är en videoram.

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

När du har slutfört dessa steg kommer du att ha extraherat en video från en PowerPoint-bild med Aspose.Slides för .NET.

## Slutsats

Aspose.Slides för .NET förenklar processen att arbeta med PowerPoint-presentationer, så att du enkelt kan utföra uppgifter som att extrahera videor från bilder. Genom att följa denna steg-för-steg-guide och använda Aspose.Slides-biblioteket kan du förbättra dina .NET-applikationer med kraftfulla PowerPoint-funktioner.

## Vanliga frågor (FAQs)

### Vad är Aspose.Slides för .NET?
Aspose.Slides för .NET är ett bibliotek som gör det möjligt för .NET-applikationer att arbeta med PowerPoint-presentationer, inklusive att skapa, redigera och extrahera innehåll.

### Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
 Du hittar dokumentationen[här](https://reference.aspose.com/slides/net/).

### Är Aspose.Slides för .NET tillgängligt för en gratis provperiod?
 Ja, du kan få en gratis testversion från[här](https://releases.aspose.com/).

### Hur kan jag få en tillfällig licens för Aspose.Slides för .NET?
 Du kan begära en tillfällig licens från[den här länken](https://purchase.aspose.com/temporary-license/).

### Var kan jag få support för Aspose.Slides för .NET?
 Du kan hitta support på[Aspose.Slides forum](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

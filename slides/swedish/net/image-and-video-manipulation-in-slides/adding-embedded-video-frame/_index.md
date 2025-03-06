---
title: Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer
linktitle: Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Förbättra dina presentationer med inbäddade videor med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för sömlös integration.
weight: 19
url: /sv/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer

## Introduktion
I presentationens dynamiska värld kan integrering av multimediaelement avsevärt öka engagemanget. Aspose.Slides för .NET ger en kraftfull lösning för att integrera inbäddade videoramar i dina presentationsbilder. Den här handledningen guidar dig genom processen och delar upp varje steg för att säkerställa en sömlös upplevelse.
## Förutsättningar
Innan vi dyker in i handledningen, se till att du har följande:
-  Aspose.Slides för .NET Library: Ladda ner och installera biblioteket från[släppsidan](https://releases.aspose.com/slides/net/).
- Medieinnehåll: Ha en videofil (t.ex. "Wildlife.mp4") som du vill bädda in i din presentation.
## Importera namnområden
Börja med att importera de nödvändiga namnområdena i ditt .NET-projekt:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera kataloger
Se till att ditt projekt har de nödvändiga katalogerna för dokument- och mediefiler:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Skapa katalog om den inte redan finns.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Steg 2: Instantera presentationsklass
Skapa en instans av klassen Presentation för att representera PPTX-filen:
```csharp
using (Presentation pres = new Presentation())
{
    // Få den första bilden
    ISlide sld = pres.Slides[0];
```
## Steg 3: Bädda in video i presentationen
Använd följande kod för att bädda in en video i presentationen:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Steg 4: Lägg till videoram
Lägg nu till en videoram till bilden:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Steg 5: Ställ in videoegenskaper
Ställ in videon på videoramen och konfigurera uppspelningsläge och volym:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Steg 6: Spara presentationen
Slutligen, spara PPTX-filen på disken:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Upprepa dessa steg för varje video du vill bädda in i din presentation.
## Slutsats
Grattis! Du har framgångsrikt lagt till en inbäddad videoram till din presentation med Aspose.Slides för .NET. Denna dynamiska funktion kan lyfta dina presentationer till nya höjder och fängsla din publik med multimediaelement som är sömlöst integrerade i dina bilder.
## Vanliga frågor
### Kan jag bädda in videor i valfri bild i presentationen?
 Ja, du kan välja vilken bild som helst genom att ändra indexet i`pres.Slides[index]`.
### Vilka videoformat stöds?
Aspose.Slides stöder en mängd olika videoformat, inklusive MP4, AVI och WMV.
### Kan jag anpassa storleken och placeringen av videoramen?
 Absolut! Justera parametrarna i`AddVideoFrame(x, y, width, height, video)` efter behov.
### Finns det en gräns för hur många videor jag kan bädda in?
Antalet inbäddade videor är vanligtvis begränsat av kapaciteten hos ditt presentationsprogram.
### Hur kan jag söka ytterligare hjälp eller dela med mig av mina erfarenheter?
 Besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd och diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Förbättra dina presentationer med inbäddade videor med Aspose.Slides för .NET. Följ vår steg-för-steg-guide för sömlös integration."
"linktitle": "Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer"
"url": "/sv/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Lägga till inbäddade videor i .NET-presentationer

## Introduktion
I presentationernas dynamiska värld kan integration av multimediaelement avsevärt öka engagemanget. Aspose.Slides för .NET erbjuder en kraftfull lösning för att integrera inbäddade videobildrutor i dina presentationsbilder. Den här handledningen guidar dig genom processen och bryter ner varje steg för att säkerställa en sömlös upplevelse.
## Förkunskapskrav
Innan vi går in i handledningen, se till att du har följande:
- Aspose.Slides för .NET-biblioteket: Ladda ner och installera biblioteket från [släppsida](https://releases.aspose.com/slides/net/).
- Medieinnehåll: Ha en videofil (t.ex. "Wildlife.mp4") som du vill bädda in i din presentation.
## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna i ditt .NET-projekt:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera kataloger
Se till att ditt projekt har de kataloger som krävs för dokument- och mediefiler:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Skapa katalog om den inte redan finns.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Steg 2: Instansiera presentationsklassen
Skapa en instans av Presentation-klassen för att representera PPTX-filen:
```csharp
using (Presentation pres = new Presentation())
{
    // Hämta den första bilden
    ISlide sld = pres.Slides[0];
```
## Steg 3: Bädda in video i presentationen
Använd följande kod för att bädda in en video i presentationen:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Steg 4: Lägg till videobildruta
Lägg nu till en videobildruta i bilden:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Steg 5: Ställ in videoegenskaper
Ställ in videon på videobildrutan och konfigurera uppspelningsläge och volym:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Steg 6: Spara presentationen
Slutligen, spara PPTX-filen på disk:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Upprepa dessa steg för varje video du vill bädda in i din presentation.
## Slutsats
Grattis! Du har lagt till en inbäddad videobildruta i din presentation med Aspose.Slides för .NET. Den här dynamiska funktionen kan lyfta dina presentationer till nya höjder och fängsla din publik med multimediaelement som är sömlöst integrerade i dina bilder.
## Vanliga frågor
### Kan jag bädda in videor i vilken bild som helst i presentationen?
Ja, du kan välja vilken bild som helst genom att ändra indexet i `pres.Slides[index]`.
### Vilka videoformat stöds?
Aspose.Slides stöder en mängd olika videoformat, inklusive MP4, AVI och WMV.
### Kan jag anpassa storleken och positionen för videobildrutan?
Absolut! Justera parametrarna i `AddVideoFrame(x, y, width, height, video)` efter behov.
### Finns det en gräns för hur många videor jag kan bädda in?
Antalet inbäddade videor begränsas vanligtvis av kapaciteten hos din presentationsprogramvara.
### Hur kan jag söka ytterligare hjälp eller dela med mig av mina erfarenheter?
Besök [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) för stöd och diskussioner i samhället.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
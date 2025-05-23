---
"description": "Verrijk uw presentaties met ingebedde video's met Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding voor naadloze integratie."
"linktitle": "Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties"
"url": "/nl/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties

## Invoering
In de dynamische wereld van presentaties kan de integratie van multimedia-elementen de betrokkenheid aanzienlijk vergroten. Aspose.Slides voor .NET biedt een krachtige oplossing voor het integreren van ingebedde videoframes in uw presentatieslides. Deze tutorial leidt u door het proces en legt elke stap uit voor een naadloze ervaring.
## Vereisten
Voordat we met de tutorial beginnen, moet u ervoor zorgen dat u het volgende heeft:
- Aspose.Slides voor .NET-bibliotheek: download en installeer de bibliotheek vanuit de [releasepagina](https://releases.aspose.com/slides/net/).
- Media-inhoud: Wilt u een videobestand (bijv. 'Wildlife.mp4') in uw presentatie insluiten?
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw .NET-project:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Stap 1: Mappen instellen
Zorg ervoor dat uw project de vereiste mappen voor document- en mediabestanden heeft:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Maak een map aan als deze nog niet bestaat.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Stap 2: Instantieer presentatieklasse
Maak een instantie van de Presentation-klasse om het PPTX-bestand te vertegenwoordigen:
```csharp
using (Presentation pres = new Presentation())
{
    // Ontvang de eerste dia
    ISlide sld = pres.Slides[0];
```
## Stap 3: Video in de presentatie insluiten
Gebruik de volgende code om een video in de presentatie in te sluiten:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Stap 4: Videoframe toevoegen
Voeg nu een videoframe toe aan de dia:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Stap 5: Video-eigenschappen instellen
Stel de video in op het videoframe en configureer de afspeelmodus en het volume:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Stap 6: Sla de presentatie op
Sla ten slotte het PPTX-bestand op schijf op:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Herhaal deze stappen voor elke video die u in uw presentatie wilt insluiten.
## Conclusie
Gefeliciteerd! Je hebt met succes een ingebed videoframe aan je presentatie toegevoegd met Aspose.Slides voor .NET. Deze dynamische functie tilt je presentaties naar een hoger niveau en boeit je publiek met multimedia-elementen die naadloos in je dia's zijn geïntegreerd.
## Veelgestelde vragen
### Kan ik video's in elke dia van de presentatie insluiten?
Ja, u kunt elke dia kiezen door de index in te stellen `pres.Slides[index]`.
### Welke videoformaten worden ondersteund?
Aspose.Slides ondersteunt verschillende videoformaten, waaronder MP4, AVI en WMV.
### Kan ik de grootte en positie van het videoframe aanpassen?
Absoluut! Pas de parameters aan in `AddVideoFrame(x, y, width, height, video)` indien nodig.
### Zit er een limiet aan het aantal video's dat ik kan insluiten?
Het aantal ingesloten video's wordt doorgaans beperkt door de capaciteit van uw presentatiesoftware.
### Hoe kan ik verdere hulp krijgen of mijn ervaringen delen?
Bezoek de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) voor ondersteuning en discussies vanuit de gemeenschap.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
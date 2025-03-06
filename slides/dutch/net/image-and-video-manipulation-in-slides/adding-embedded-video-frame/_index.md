---
title: Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties
linktitle: Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Verbeter uw presentaties met ingesloten video's met Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 19
url: /nl/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Ingesloten video's toevoegen in .NET-presentaties

## Invoering
In de dynamische wereld van presentaties kan het integreren van multimedia-elementen de betrokkenheid aanzienlijk vergroten. Aspose.Slides voor .NET biedt een krachtige oplossing voor het opnemen van ingebedde videoframes in uw presentatiedia's. Deze tutorial begeleidt u door het proces, waarbij elke stap wordt opgesplitst om een naadloze ervaring te garanderen.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:
-  Aspose.Slides voor .NET Library: Download en installeer de bibliotheek van de[pagina vrijgeven](https://releases.aspose.com/slides/net/).
- Media-inhoud: zorg dat u een videobestand (bijvoorbeeld "Wildlife.mp4") hebt dat u in uw presentatie wilt insluiten.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw .NET-project:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Stap 1: Mappen instellen
Zorg ervoor dat uw project over de vereiste mappen voor document- en mediabestanden beschikt:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Maak een directory aan als deze nog niet aanwezig is.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Stap 2: Instantie van de presentatieklas
Maak een exemplaar van de klasse Presentation om het PPTX-bestand weer te geven:
```csharp
using (Presentation pres = new Presentation())
{
    // Haal de eerste dia
    ISlide sld = pres.Slides[0];
```
## Stap 3: Video insluiten in presentatie
Gebruik de volgende code om een video in de presentatie in te sluiten:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Stap 4: Videoframe toevoegen
Voeg nu een videoframe toe aan de dia:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Stap 5: Stel video-eigenschappen in
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
Gefeliciteerd! U hebt met succes een ingesloten videoframe aan uw presentatie toegevoegd met Aspose.Slides voor .NET. Deze dynamische functie kan uw presentaties naar nieuwe hoogten tillen en uw publiek boeien met multimedia-elementen die naadloos in uw dia's zijn geïntegreerd.
## Veelgestelde vragen
### Kan ik video's in elke dia van de presentatie insluiten?
 Ja, u kunt elke dia kiezen door de index aan te passen`pres.Slides[index]`.
### Welke videoformaten worden ondersteund?
Aspose.Slides ondersteunt verschillende videoformaten, waaronder MP4, AVI en WMV.
### Kan ik de grootte en positie van het videoframe aanpassen?
 Absoluut! Pas de parameters aan`AddVideoFrame(x, y, width, height, video)` indien nodig.
### Is er een limiet aan het aantal video's dat ik kan insluiten?
Het aantal ingesloten video's wordt doorgaans beperkt door de capaciteit van uw presentatiesoftware.
### Hoe kan ik verdere hulp zoeken of mijn ervaring delen?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapsondersteuning en discussies.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

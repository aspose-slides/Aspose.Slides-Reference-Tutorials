---
title: Video uit dia extraheren met Aspose.Slides voor .NET
linktitle: Extraheer video uit dia
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u video's uit PowerPoint-dia's kunt extraheren met Aspose.Slides voor .NET. Deze stapsgewijze handleiding vereenvoudigt het proces voor u.
weight: 14
url: /nl/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Video uit dia extraheren met Aspose.Slides voor .NET


Aspose.Slides voor .NET is een krachtige bibliotheek waarmee u met PowerPoint-presentaties kunt werken in een .NET-omgeving. Een van de handige functies die het biedt, is de mogelijkheid om video's uit dia's te extraheren. In deze stapsgewijze handleiding laten we u zien hoe u een video uit een PowerPoint-dia kunt extraheren met Aspose.Slides voor .NET.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Slides voor .NET: Aspose.Slides voor .NET moet geïnstalleerd zijn. U kunt deze verkrijgen bij de[website](https://purchase.aspose.com/buy).

- Een PowerPoint-presentatie: bereid een PowerPoint-presentatie voor (bijvoorbeeld Video.pptx) die de video bevat die u wilt extraheren.

## Naamruimten importeren

U moet de benodigde naamruimten importeren om met Aspose.Slides voor .NET te kunnen werken. Hier ziet u hoe u het kunt doen:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Laten we nu het proces van het extraheren van een video uit een dia in meerdere stappen opsplitsen.

## Stap 1: Stel de documentmap in

```csharp
string dataDir = "Your Document Directory";
```

 Vervangen`"Your Document Directory"` met het pad naar de map waar uw PowerPoint-presentatie zich bevindt.

## Stap 2: Laad de presentatie

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Deze code initialiseert een presentatieobject dat uw PowerPoint-presentatiebestand vertegenwoordigt.

## Stap 3: Herhaal dia's en vormen

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Hier doorlopen we elke dia in de presentatie en doorlopen we vervolgens de vormen in de eerste dia (wijzigen we indien nodig).

## Stap 4: Controleer of de vorm een videoframe is

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Met deze stap wordt gecontroleerd of de vorm op de dia een videoframe is.

## Stap 5: Videogegevens extraheren

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Deze code extraheert informatie over de video, inclusief het inhoudstype en binaire gegevens.

## Stap 6: Sla de video op

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Ten slotte slaat deze stap de video op in een nieuw bestand in de opgegeven map.

Zodra u deze stappen heeft voltooid, heeft u met succes een video uit een PowerPoint-dia geëxtraheerd met behulp van Aspose.Slides voor .NET.

## Conclusie

Aspose.Slides voor .NET vereenvoudigt het werken met PowerPoint-presentaties, waardoor u met gemak taken kunt uitvoeren, zoals het extraheren van video's uit dia's. Door deze stapsgewijze handleiding te volgen en gebruik te maken van de Aspose.Slides-bibliotheek, kunt u uw .NET-applicaties uitbreiden met krachtige PowerPoint-functies.

## Veelgestelde vragen (FAQ's)

### Wat is Aspose.Slides voor .NET?
Aspose.Slides voor .NET is een bibliotheek waarmee .NET-toepassingen met PowerPoint-presentaties kunnen werken, inclusief het maken, bewerken en extraheren van inhoud.

### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
 U kunt de documentatie vinden[hier](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides voor .NET beschikbaar voor een gratis proefperiode?
 Ja, u kunt een gratis proefversie krijgen van[hier](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Slides voor .NET?
 Een tijdelijke licentie kunt u aanvragen bij[deze link](https://purchase.aspose.com/temporary-license/).

### Waar kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Ondersteuning vindt u op de[Aspose.Slides-forum](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Leer hoe je video's uit PowerPoint-dia's haalt met Aspose.Slides voor .NET. Deze stapsgewijze handleiding maakt het proces eenvoudiger voor je."
"linktitle": "Video uit dia extraheren"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Video uit een dia extraheren met Aspose.Slides voor .NET"
"url": "/nl/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Video uit een dia extraheren met Aspose.Slides voor .NET


Aspose.Slides voor .NET is een krachtige bibliotheek waarmee u PowerPoint-presentaties kunt gebruiken in een .NET-omgeving. Een van de handige functies is de mogelijkheid om video's uit dia's te halen. In deze stapsgewijze handleiding laten we u zien hoe u een video uit een PowerPoint-dia haalt met Aspose.Slides voor .NET.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

- Aspose.Slides voor .NET: U moet Aspose.Slides voor .NET geïnstalleerd hebben. U kunt het downloaden via de [website](https://purchase.aspose.com/buy).

- Een PowerPoint-presentatie: bereid een PowerPoint-presentatie voor (bijv. Video.pptx) met de video die u wilt extraheren.

## Naamruimten importeren

Je moet de benodigde naamruimten importeren om met Aspose.Slides voor .NET te kunnen werken. Zo doe je dat:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Laten we het proces voor het extraheren van een video uit een dia opsplitsen in meerdere stappen.

## Stap 1: Stel de documentmap in

```csharp
string dataDir = "Your Document Directory";
```

Vervangen `"Your Document Directory"` met het pad naar de map waarin uw PowerPoint-presentatie zich bevindt.

## Stap 2: Laad de presentatie

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Deze code initialiseert een Presentation-object dat uw PowerPoint-presentatiebestand vertegenwoordigt.

## Stap 3: Door dia's en vormen heen itereren

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Hierbij doorlopen we elke dia in de presentatie en itereren we vervolgens door de vormen in de eerste dia (waar nodig aanpassend).

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

Tot slot wordt de video met deze stap opgeslagen in een nieuw bestand in de opgegeven directory.

Wanneer u deze stappen hebt voltooid, hebt u met succes een video uit een PowerPoint-dia gehaald met behulp van Aspose.Slides voor .NET.

## Conclusie

Aspose.Slides voor .NET vereenvoudigt het werken met PowerPoint-presentaties, waardoor u taken zoals het extraheren van video's uit dia's eenvoudig kunt uitvoeren. Door deze stapsgewijze handleiding te volgen en gebruik te maken van de Aspose.Slides-bibliotheek, kunt u uw .NET-applicaties uitbreiden met krachtige PowerPoint-functies.

## Veelgestelde vragen (FAQ's)

### Wat is Aspose.Slides voor .NET?
Aspose.Slides voor .NET is een bibliotheek waarmee .NET-toepassingen kunnen werken met PowerPoint-presentaties. U kunt hiermee onder andere inhoud maken, bewerken en extraheren.

### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
De documentatie vindt u hier [hier](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides voor .NET gratis beschikbaar als proefversie?
Ja, u kunt een gratis proefversie krijgen van [hier](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie voor Aspose.Slides voor .NET verkrijgen?
U kunt een tijdelijke vergunning aanvragen bij [deze link](https://purchase.aspose.com/temporary-license/).

### Waar kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
U kunt ondersteuning vinden op de [Aspose.Slides forum](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: PowerPoint-animaties beheersen met Aspose.Slides .NET
linktitle: Herhaal animatie op dia
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Verbeter PowerPoint-presentaties met Aspose.Slides voor .NET. Beheer animaties moeiteloos, boeien uw publiek en laat een blijvende indruk achter.
weight: 12
url: /nl/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Invoering
In de dynamische wereld van presentaties speelt de mogelijkheid om animaties te besturen een cruciale rol bij het boeien en vasthouden van de aandacht van het publiek. Aspose.Slides voor .NET stelt ontwikkelaars in staat de animatietypes binnen dia's in eigen hand te nemen, waardoor een meer interactieve en visueel aantrekkelijke presentatie mogelijk wordt. In deze zelfstudie onderzoeken we stap voor stap hoe u animatietypen op een dia kunt beheren met Aspose.Slides voor .NET.
## Vereisten
Voordat we in de tutorial duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
1.  Aspose.Slides voor .NET Library: Download en installeer de bibliotheek van[hier](https://releases.aspose.com/slides/net/).
2. .NET-ontwikkelomgeving: Stel een .NET-ontwikkelomgeving in op uw computer.
## Naamruimten importeren
Begin in uw .NET-project met het importeren van de benodigde naamruimten om gebruik te maken van de functionaliteiten van Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Stap 1: Stel het project in
Maak een nieuwe map voor uw project en instantiëer de klasse Presentation om het presentatiebestand weer te geven.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Je code komt hier
}
```
## Stap 2: Toegang tot effectenreeks
Haal de effectreeks voor de eerste dia op met behulp van de eigenschap MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Stap 3: Toegang tot het eerste effect
Verkrijg het eerste effect van de hoofdreeks om de eigenschappen ervan te manipuleren.
```csharp
IEffect effect = effectsSequence[0];
```
## Stap 4: Wijzig de herhaalinstellingen
Wijzig de eigenschap Timing/Repeat van het effect in 'Tot einde dia'.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Stap 5: Sla de presentatie op
Sla de gewijzigde presentatie op om de wijzigingen te visualiseren.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Herhaal deze stappen voor extra effecten of pas ze aan uw presentatievereisten aan.
## Conclusie
Het opnemen van dynamische animaties in uw PowerPoint-presentaties is nog nooit zo eenvoudig geweest met Aspose.Slides voor .NET. Deze stapsgewijze handleiding geeft u de kennis om animatietypes te beheren, zodat uw dia's een blijvende indruk op uw publiek achterlaten.
## Veel Gestelde Vragen
### Kan ik deze animaties toepassen op specifieke objecten binnen een dia?
Ja, u kunt specifieke objecten targeten door toegang te krijgen tot hun individuele effecten binnen de reeks.
### Is Aspose.Slides compatibel met de nieuwste PowerPoint-versies?
Aspose.Slides biedt ondersteuning voor een breed scala aan PowerPoint-versies, waardoor compatibiliteit met zowel oude als nieuwe versies wordt gegarandeerd.
### Waar kan ik aanvullende voorbeelden en bronnen vinden?
 Ontdek de[documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide voorbeelden en gedetailleerde uitleg.
### Hoe kan ik een tijdelijke licentie voor Aspose.Slides verkrijgen?
 Bezoek[hier](https://purchase.aspose.com/temporary-license/) voor informatie over het verkrijgen van een tijdelijke licentie.
### Hulp nodig of meer vragen?
 Neem contact op met de Aspose.Slides-community op de[Helpforum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

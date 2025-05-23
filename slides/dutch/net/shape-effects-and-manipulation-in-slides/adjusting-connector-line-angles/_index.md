---
"description": "Leer hoe u de hoeken van verbindingslijnen in PowerPoint-dia's kunt aanpassen met Aspose.Slides voor .NET. Verbeter uw presentaties met precisie en gemak."
"linktitle": "Het aanpassen van verbindingslijnhoeken in presentatieslides met Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Pas de hoeken van verbindingslijnen aan in PowerPoint met Aspose.Slides"
"url": "/nl/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Pas de hoeken van verbindingslijnen aan in PowerPoint met Aspose.Slides

## Invoering
Het maken van visueel aantrekkelijke presentatieslides vereist vaak nauwkeurige aanpassingen aan verbindingslijnen. In deze tutorial laten we zien hoe je de hoeken van verbindingslijnen in presentatieslides kunt aanpassen met Aspose.Slides voor .NET. Aspose.Slides is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PowerPoint-bestanden kunnen werken en uitgebreide mogelijkheden biedt voor het maken, aanpassen en bewerken van presentaties.
## Vereisten
Voordat we met de tutorial beginnen, moet u ervoor zorgen dat u het volgende hebt:
- Basiskennis van de programmeertaal C#.
- Visual Studio of een andere C#-ontwikkelomgeving geïnstalleerd.
- Aspose.Slides voor .NET-bibliotheek. Je kunt het downloaden. [hier](https://releases.aspose.com/slides/net/).
- Een PowerPoint-presentatiebestand met verbindingslijnen die u wilt aanpassen.
## Naamruimten importeren
Om te beginnen moet u ervoor zorgen dat u de benodigde naamruimten in uw C#-code opneemt:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Stap 1: Stel uw project in
Maak een nieuw C#-project in Visual Studio en installeer het Aspose.Slides NuGet-pakket. Stel de projectstructuur in met een verwijzing naar de Aspose.Slides-bibliotheek.
## Stap 2: Laad de presentatie
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
Laad uw PowerPoint-presentatiebestand in de `Presentation` object. Vervang "Uw documentenmap" door het daadwerkelijke pad naar uw bestand.
## Stap 3: Toegang tot de dia en vormen
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Ga naar de eerste dia in de presentatie en initialiseer een variabele om de vormen op de dia weer te geven.
## Stap 4: Herhaal de vormen
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Code voor het verwerken van verbindingslijnen
}
```
Doorloop elke vorm op de dia om verbindingslijnen te identificeren en verwerken.
## Stap 5: Pas de hoeken van de verbindingslijnen aan
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Code voor het verwerken van AutoVormen
}
else if (shape is Connector)
{
    // Code voor het verwerken van connectoren
}
Console.WriteLine(dir);
```
Bepaal of de vorm een AutoVorm of een Connector is en pas de hoeken van de connectorlijnen aan met behulp van de meegeleverde `getDirection` methode.
## Stap 6: Definieer de `getDirection` Methode
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Code voor het berekenen van de richting
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
Implementeer de `getDirection` Methode om de hoek van de verbindingslijn te berekenen op basis van de afmetingen en oriëntatie.
## Conclusie
Met deze stappen kunt u de hoeken van verbindingslijnen in uw PowerPoint-presentatie programmatisch aanpassen met Aspose.Slides voor .NET. Deze tutorial biedt een basis voor het verbeteren van de visuele aantrekkingskracht van uw dia's.
## Veelgestelde vragen
### Is Aspose.Slides geschikt voor zowel Windows als webapplicaties?
Ja, Aspose.Slides kan zowel in Windows- als in webapplicaties worden gebruikt.
### Kan ik een gratis proefversie van Aspose.Slides downloaden voordat ik koop?
Ja, u kunt een gratis proefversie downloaden [hier](https://releases.aspose.com/).
### Waar kan ik uitgebreide documentatie voor Aspose.Slides voor .NET vinden?
De documentatie is beschikbaar [hier](https://reference.aspose.com/slides/net/).
### Hoe kan ik een tijdelijke licentie voor Aspose.Slides verkrijgen?
U kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).
### Is er een ondersteuningsforum voor Aspose.Slides?
Ja, u kunt het ondersteuningsforum bezoeken [hier](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
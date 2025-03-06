---
title: Aspose.Slides - Vormen naadloos verbinden in .NET
linktitle: Vormen verbinden met behulp van connectoren in de presentatie
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Ontdek de kracht van Aspose.Slides voor .NET, waarmee u vormen moeiteloos met elkaar verbindt in uw presentaties. Til uw dia's naar een hoger niveau met dynamische connectoren.
type: docs
weight: 29
url: /nl/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Invoering
In de dynamische wereld van presentaties voegt de mogelijkheid om vormen met elkaar te verbinden met behulp van verbindingsstukken een laagje verfijning toe aan uw dia's. Aspose.Slides voor .NET stelt ontwikkelaars in staat dit naadloos te bereiken. Deze tutorial begeleidt u door het proces, waarbij elke stap wordt opgesplitst om een duidelijk begrip te garanderen.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je over het volgende beschikt:
- Basiskennis van C# en .NET framework.
-  Aspose.Slides voor .NET geïnstalleerd. Zo niet, download het dan[hier](https://releases.aspose.com/slides/net/).
- Een ontwikkelomgeving opgezet.
## Naamruimten importeren
Begin in uw C#-code met het importeren van de benodigde naamruimten:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Stel de documentmap in
Begin met het definiëren van de map voor uw document:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Presenteer de presentatieklas
Maak een exemplaar van de klasse Presentation om uw PPTX-bestand weer te geven:
```csharp
using (Presentation input = new Presentation())
{
    // Toegang tot de vormencollectie voor de geselecteerde dia
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Voeg vormen toe aan de dia
Voeg de benodigde vormen toe aan uw dia, zoals ellips en rechthoek:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Voeg connectorvorm toe
Neem een verbindingsvorm op in de vormencollectie van de dia:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Vormen verbinden met Connector
Geef de vormen op die door de connector moeten worden verbonden:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Connector opnieuw routeren
Roep de omleidingsmethode aan om het automatische kortste pad tussen vormen in te stellen:
```csharp
connector.Reroute();
```
## 7. Presentatie opslaan
Sla uw presentatie op om de verbonden vormen te bekijken:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Conclusie
Gefeliciteerd! U hebt met succes vormen verbonden met behulp van verbindingslijnen in presentatiedia's met behulp van Aspose.Slides voor .NET. Verbeter uw presentaties met deze geavanceerde functie en fascineer uw publiek.
## Veelgestelde vragen
### Is Aspose.Slides voor .NET compatibel met het nieuwste .NET-framework?
Ja, Aspose.Slides voor .NET wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworkversies te garanderen.
### Kan ik meer dan twee vormen verbinden met één enkele connector?
Absoluut, u kunt meerdere vormen verbinden door de connectorlogica in uw code uit te breiden.
### Zijn er beperkingen op de vormen die ik kan verbinden?
Aspose.Slides voor .NET ondersteunt het verbinden van verschillende vormen, waaronder basisvormen, slimme kunst en aangepaste vormen.
### Hoe kan ik het uiterlijk van de connector aanpassen?
Verken de Aspose.Slides-documentatie voor methoden om het uiterlijk van connectoren aan te passen, zoals lijnstijl en kleur.
### Is er een communityforum voor ondersteuning voor Aspose.Slides?
 Ja, u kunt hulp vinden en uw ervaringen delen in de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
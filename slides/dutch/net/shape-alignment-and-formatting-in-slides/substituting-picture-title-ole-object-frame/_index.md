---
title: OLE Objects Guide insluiten met Aspose.Slides voor .NET
linktitle: Vervanging van de afbeeldingstitel van het OLE-objectframe in presentatiedia's
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u uw presentatiedia's kunt verbeteren met dynamische OLE-objecten met behulp van Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 15
url: /nl/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Invoering
Het maken van dynamische en boeiende presentatiedia's omvat vaak de integratie van verschillende multimedia-elementen. In deze zelfstudie onderzoeken we hoe u de afbeeldingstitel van een OLE-objectframe (Object Linking and Embedding) in presentatiedia's kunt vervangen met behulp van de krachtige Aspose.Slides voor .NET-bibliotheek. Aspose.Slides vereenvoudigt het proces van het verwerken van OLE-objecten, waardoor ontwikkelaars de tools krijgen om hun presentaties gemakkelijk te verbeteren.
## Vereisten
Voordat we ingaan op de stapsgewijze handleiding, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Slides voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Slides voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van de[Aspose.Slides .NET-documentatie](https://reference.aspose.com/slides/net/).
- Voorbeeldgegevens: maak een voorbeeld van een Excel-bestand (bijvoorbeeld "ExcelObject.xlsx") dat u als OLE-object in de presentatie wilt insluiten. Zorg bovendien voor een afbeeldingsbestand (bijvoorbeeld "Image.png") dat zal dienen als pictogram voor het OLE-object.
- Ontwikkelomgeving: Zet een ontwikkelomgeving op met de benodigde tools, zoals Visual Studio of een andere gewenste IDE voor .NET-ontwikkeling.
## Naamruimten importeren
Zorg ervoor dat u in uw .NET-project de vereiste naamruimten importeert om met Aspose.Slides te werken:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Stap 1: Stel de documentmap in
```csharp
string dataDir = "Your Document Directory";
```
Zorg ervoor dat u "Uw documentenmap" vervangt door het daadwerkelijke pad naar uw documentmap.
## Stap 2: Definieer OLE-bronbestand en pictogrambestandspaden
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Werk deze paden bij met de daadwerkelijke paden naar uw voorbeeld-Excel-bestand en afbeeldingsbestand.
## Stap 3: Maak een presentatie-instantie
```csharp
using (Presentation pres = new Presentation())
{
    // Code voor volgende stappen komt hier te staan
}
```
 Initialiseer een nieuw exemplaar van het`Presentation` klas.
## Stap 4: OLE-objectframe toevoegen
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Voeg een OLE-objectframe toe aan de dia en geef de positie en afmetingen op.
## Stap 5: Afbeeldingsobject toevoegen
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Lees het afbeeldingsbestand en voeg het als afbeeldingsobject toe aan de presentatie.
## Stap 6: Stel bijschrift in op OLE-pictogram
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Stel het gewenste bijschrift voor het OLE-pictogram in.
## Conclusie
Het opnemen van OLE-objecten in uw presentatiedia's met Aspose.Slides voor .NET is een eenvoudig proces. In deze zelfstudie wordt u door de essentiële stappen geleid, van het instellen van de documentmap tot het toevoegen en aanpassen van OLE-objecten. Experimenteer met verschillende bestandstypen en bijschriften om de visuele aantrekkingskracht van uw presentaties te vergroten.
## Veelgestelde vragen
### Kan ik andere typen bestanden insluiten als OLE-objecten met Aspose.Slides?
Ja, Aspose.Slides ondersteunt het insluiten van verschillende soorten bestanden, zoals Excel-spreadsheets, Word-documenten en meer.
### Is het OLE-objectpictogram aanpasbaar?
Absoluut. U kunt het standaardpictogram vervangen door een afbeelding naar keuze, zodat deze beter bij het thema van uw presentatie past.
### Biedt Aspose.Slides ondersteuning voor animaties met OLE-objecten?
Vanaf de nieuwste versie richt Aspose.Slides zich op het insluiten en weergeven van OLE-objecten en verwerkt het niet rechtstreeks animaties binnen de OLE-objecten.
### Kan ik OLE-objecten programmatisch manipuleren nadat ik ze aan een dia heb toegevoegd?
Zeker. U heeft volledige programmatische controle over OLE-objecten, zodat u hun eigenschappen en uiterlijk indien nodig kunt wijzigen.
### Zijn er beperkingen aan de grootte van de ingesloten OLE-objecten?
Hoewel er beperkingen zijn qua grootte, zijn ze over het algemeen genereus. Het wordt aanbevolen om te testen met uw specifieke gebruiksscenario om optimale prestaties te garanderen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

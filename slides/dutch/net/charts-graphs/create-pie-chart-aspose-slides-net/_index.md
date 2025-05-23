---
"date": "2025-04-15"
"description": "Leer hoe u programmatisch cirkeldiagrammen aan uw presentaties kunt toevoegen met Aspose.Slides voor .NET, waarmee u moeiteloos uw gegevensvisualisatie kunt verbeteren."
"title": "Maak een cirkeldiagram in PowerPoint met Aspose.Slides voor .NET"
"url": "/nl/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Een cirkeldiagram maken en toevoegen aan een presentatie met Aspose.Slides voor .NET
## Invoering
Het maken van boeiende presentaties omvat vaak meer dan alleen tekst; visuele elementen zoals grafieken kunnen de impact van uw data storytelling aanzienlijk vergroten. Als u dynamische cirkeldiagrammen programmatisch aan uw PowerPoint-presentaties wilt toevoegen, **Aspose.Slides voor .NET** is een krachtige tool die deze taak naadloos en efficiënt maakt. Deze tutorial begeleidt je bij het toevoegen van een cirkeldiagram aan een presentatieslide en het configureren ervan met externe gegevensbronnen.

### Wat je zult leren
- Een nieuwe presentatie maken met Aspose.Slides voor .NET
- Een cirkeldiagram toevoegen aan uw eerste dia
- Een externe werkmap-URL instellen als gegevensbron voor uw grafiek
- Uw presentatie opslaan in PPTX-formaat
Laten we eens kijken hoe u dit eenvoudig kunt bereiken, te beginnen met de vereisten.
## Vereisten
Zorg ervoor dat u het volgende bij de hand heeft voordat u begint:
- **Aspose.Slides voor .NET** bibliotheek geïnstalleerd. Je hebt een versie nodig die compatibel is met .NET Framework of .NET Core/.NET 5+.
- Basiskennis van C#-programmering en vertrouwdheid met Visual Studio IDE.
- Een ontwikkelomgeving op uw computer (Windows, macOS of Linux).
## Aspose.Slides instellen voor .NET
### Installatie-instructies
Aspose.Slides voor .NET kan op verschillende manieren aan uw project worden toegevoegd:
**.NET CLI**
```shell
dotnet add package Aspose.Slides
```
**Pakketbeheerconsole**
```powershell
Install-Package Aspose.Slides
```
**NuGet Package Manager-gebruikersinterface**
1. Open de NuGet Package Manager in Visual Studio.
2. Zoek naar "Aspose.Slides".
3. Installeer de nieuwste versie.
### Licentieverwerving
Om Aspose.Slides te gebruiken, kunt u beginnen met een gratis proeflicentie om de functies zonder beperkingen te verkennen. Voor productieomgevingen kunt u overwegen een commerciële licentie aan te schaffen of een tijdelijke licentie aan te schaffen voor uitgebreide tests. Ga naar [De aankooppagina van Aspose](https://purchase.aspose.com/buy) voor meer details.
### Basisinitialisatie
Om Aspose.Slides in uw project te gebruiken, moet u het initialiseren met uw licentie (indien beschikbaar):
```csharp
// Initialiseer de bibliotheek
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Implementatiegids
Nu u alles hebt ingesteld, gaan we stap voor stap elke functie doornemen.
### Een grafiek maken en toevoegen aan een presentatie
#### Overzicht
We beginnen met het maken van een presentatie en voegen een cirkeldiagram toe aan de eerste dia.
#### Stappen:
1. **Initialiseer de presentatie**
   Begin met het maken van een exemplaar van de `Presentation` klasse, die uw PowerPoint-bestand vertegenwoordigt.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Hier voegen we onze grafiek toe.
   }
   ```
2. **Voeg een cirkeldiagram toe**
   Gebruik de `Shapes.AddChart` Methode om een cirkeldiagram op specifieke coördinaten in uw dia in te voegen.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Externe werkmap instellen voor grafiekgegevens
#### Overzicht
Laten we nu het cirkeldiagram configureren om gegevens uit een externe werkmap te gebruiken.
#### Stappen:
1. **Toegang tot grafiekgegevens**
   Haal de grafiekgegevensinterface op waar u de URL van uw externe gegevensbron opgeeft.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **URL voor externe werkmap instellen**
   Stel de URL voor uw gegevensbron in met behulp van `SetExternalWorkbook`In dit voorbeeld wordt een tijdelijke URL gebruikt, die moet worden vervangen door het pad naar uw daadwerkelijke gegevensbron.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://pad/bestaat/niet", false);
   ```
### Presentatie opslaan in bestand
#### Overzicht
Sla ten slotte de presentatie op in PPTX-formaat op de gewenste locatie.
#### Stappen:
1. **Sla de presentatie op**
   Gebruik de `Save` methode van de `Presentation` klasse om het bestand naar schijf te schrijven.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Praktische toepassingen
- **Bedrijfsrapporten**: Genereer automatisch grafieken voor kwartaallijkse prestatiebeoordelingen.
- **Gegevensdashboards**: Integreer met gegevensbronnen om visuele rapporten in realtime bij te werken.
- **Educatieve inhoud**:Maak dynamische presentaties met de nieuwste gegevens uit externe onderzoeken of onderzoeksrapporten.
Door Aspose.Slides te integreren, kunt u uw presentatiecreatieproces op verschillende domeinen automatiseren en verbeteren.
## Prestatieoverwegingen
Bij het werken met grote datasets of talrijke grafieken:
- Optimaliseer het resourcegebruik door geheugen effectief te beheren binnen .NET.
- Afvoeren `Presentation` objecten op de juiste manier om bronnen vrij te maken.
- Gebruik waar mogelijk asynchrone bewerkingen om de responsiviteit van applicaties te verbeteren.
## Conclusie
Door deze tutorial te volgen, hebt u geleerd hoe u programmatisch presentaties met cirkeldiagrammen kunt maken met Aspose.Slides voor .NET. U beschikt nu over de tools om het maken van diagrammen te automatiseren en externe gegevensbronnen efficiënt te beheren.
### Volgende stappen
Ontdek meer door de grafiekstijl aan te passen, meer grafiektypen toe te voegen of andere Aspose-componenten zoals Aspose.Cells te integreren voor uitgebreidere mogelijkheden voor gegevensmanipulatie.
## FAQ-sectie
1. **Wat is Aspose.Slides?**  
   Een robuuste bibliotheek voor het programmatisch bewerken van PowerPoint-presentaties in .NET.
2. **Kan ik Aspose.Slides gebruiken zonder licentie?**  
   Ja, maar met beperkingen. Overweeg een gratis proefversie of koop een licentie voor alle functies.
3. **Hoe kan ik grafiekgegevens dynamisch bijwerken?**  
   Gebruik externe werkmappen en stel hun URL's in de `SetExternalWorkbook` methode.
4. **Kan Aspose.Slides op meerdere platforms gebruikt worden?**  
   Ja, het ondersteunt .NET Framework en .NET Core/.NET 5+ op Windows, macOS en Linux.
5. **Welke andere grafiektypen worden ondersteund?**  
   Naast cirkeldiagrammen kunt u met Aspose.Slides ook staafdiagrammen, lijndiagrammen en meer maken.
## Bronnen
- [Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/)
- [Download nieuwste versie](https://releases.aspose.com/slides/net/)
- [Aankooplicentie](https://purchase.aspose.com/buy)
- [Gratis proefperiode](https://releases.aspose.com/slides/net/)
- [Tijdelijke licentie](https://purchase.aspose.com/temporary-license/)
- [Ondersteuningsforum](https://forum.aspose.com/c/slides/11)
Integreer Aspose.Slides vandaag nog in uw projecten en verbeter en automatiseer uw PowerPoint-presentaties!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
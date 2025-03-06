---
title: Beheer ActiveX-besturingselement in PowerPoint
linktitle: Beheer ActiveX-besturingselement in PowerPoint
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-presentaties kunt verbeteren met ActiveX-besturingselementen met behulp van Aspose.Slides voor .NET. Onze stapsgewijze handleiding behandelt het invoegen, manipuleren, aanpassen, afhandelen van gebeurtenissen en meer.
weight: 13
url: /nl/net/slide-view-and-layout-manipulation/manage-activex-control/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

ActiveX-besturingselementen zijn krachtige elementen die de functionaliteit en interactiviteit van uw PowerPoint-presentaties kunnen verbeteren. Met deze besturingselementen kunt u objecten zoals multimediaspelers, formulieren voor gegevensinvoer en meer rechtstreeks in uw dia's insluiten en manipuleren. In dit artikel onderzoeken we hoe u ActiveX-besturingselementen in PowerPoint kunt beheren met Aspose.Slides voor .NET, een veelzijdige bibliotheek die naadloze integratie en manipulatie van PowerPoint-bestanden in uw .NET-toepassingen mogelijk maakt.

## ActiveX-besturingselementen toevoegen aan PowerPoint-dia's

Volg deze stappen om te beginnen met het opnemen van ActiveX-besturingselementen in uw PowerPoint-presentaties:

1.  Maak een nieuwe PowerPoint-presentatie: Maak eerst een nieuwe PowerPoint-presentatie met Aspose.Slides voor .NET. U kunt verwijzen naar de[Aspose.Slides voor .NET API-referentie](https://reference.aspose.com/slides/net/) voor begeleiding bij het werken met presentaties.

2. Een dia toevoegen: gebruik de bibliotheek om een nieuwe dia aan uw presentatie toe te voegen. Dit is de dia waarin u het ActiveX-besturingselement wilt invoegen.

3. Voeg het ActiveX-besturingselement in: Nu is het tijd om het ActiveX-besturingselement in de dia in te voegen. U kunt dit bereiken door de onderstaande voorbeeldcode te volgen:

```csharp
// Laad de presentatie
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Haal de dia op waar u het ActiveX-besturingselement wilt invoegen
ISlide slide = presentation.Slides[0];

// Definieer de eigenschappen van het ActiveX-besturingselement
int left = 100; // Geef de linkerpositie op
int top = 100; // Geef de bovenste positie op
int width = 200; // Geef de breedte op
int height = 100; // Geef de hoogte op
string progId = "YourActiveXControl.ProgID"; // Geef de ProgID van het ActiveX-besturingselement op

// Voeg het ActiveX-besturingselement toe aan de dia
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Zorg ervoor dat u vervangt`"YourActiveXControl.ProgID"` met de daadwerkelijke ProgID van het ActiveX-besturingselement dat u wilt invoegen.

4. Sla de presentatie op: Nadat u het ActiveX-besturingselement hebt ingevoegd, slaat u de presentatie op met de volgende code:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## ActiveX-besturingselementen programmatisch manipuleren

Nadat u het ActiveX-besturingselement aan uw dia hebt toegevoegd, wilt u dit wellicht programmatisch manipuleren. Hier ziet u hoe u het kunt doen:

1. Toegang tot het ActiveX-besturingselement: Om toegang te krijgen tot de eigenschappen en methoden van het ActiveX-besturingselement, hebt u een verwijzing ernaar nodig. Gebruik de volgende code om het besturingselement van de dia te krijgen:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Methoden aanroepen: u kunt methoden van het ActiveX-besturingselement aanroepen met behulp van de verkregen referentie. Als het ActiveX-besturingselement bijvoorbeeld een methode heeft met de naam 'Afspelen', kunt u deze als volgt aanroepen:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Eigenschappen instellen: u kunt de eigenschappen van het ActiveX-besturingselement ook programmatisch instellen. Als het besturingselement bijvoorbeeld de eigenschap 'Volume' heeft, kunt u deze als volgt instellen:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Eigenschappen van ActiveX-besturingselement aanpassen

Het aanpassen van de eigenschappen van uw ActiveX-besturingselement kan de gebruikerservaring van uw presentatie aanzienlijk verbeteren. U kunt deze eigenschappen als volgt aanpassen:

1.  Toegang tot eigenschappen: Zoals eerder vermeld, hebt u toegang tot de eigenschappen van het ActiveX-besturingselement met behulp van de`IOleObjectFrame` referentie.

2.  Eigenschappen instellen: gebruik de`SetProperty`methode om verschillende eigenschappen van het ActiveX-besturingselement in te stellen. U kunt de achtergrondkleur bijvoorbeeld als volgt wijzigen:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Gebeurtenissen verwerken die verband houden met ActiveX-besturingselementen

ActiveX-besturingselementen hebben vaak bijbehorende gebeurtenissen die acties kunnen activeren op basis van gebruikersinteracties. Zo kunt u deze gebeurtenissen afhandelen:

1. Abonneren op gebeurtenissen: Abonneer u eerst op de gewenste gebeurtenis van het ActiveX-besturingselement. Als het besturingselement bijvoorbeeld de gebeurtenis 'Geklikt' heeft, kunt u zich hierop als volgt abonneren:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Uw gebeurtenisafhandelingscode hier
};
```

## ActiveX-besturingselementen uit dia's verwijderen

Als u een ActiveX-besturingselement uit een dia wilt verwijderen, volgt u deze stappen:

1.  Toegang tot het besturingselement: verkrijg een verwijzing naar het ActiveX-besturingselement met behulp van de`IOleObjectFrame` referentie zoals eerder weergegeven.

2. Verwijder het besturingselement: Gebruik de volgende code om het besturingselement van de dia te verwijderen:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## De gewijzigde presentatie opslaan en exporteren

Nadat u alle noodzakelijke wijzigingen in uw presentatie heeft aangebracht, kunt u deze opslaan en exporteren met de volgende code:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Voordelen van het gebruik van Aspose.Slides voor .NET

Aspose.Slides voor .NET vereenvoudigt het proces van het werken met ActiveX-besturingselementen in PowerPoint-presentaties door een gebruiksvriendelijke API te bieden waarmee u deze besturingselementen naadloos kunt integreren en manipuleren. Enkele voordelen van het gebruik van Aspose.Slides voor .NET zijn:

- Gemakkelijk invoegen van ActiveX-besturingselementen op dia's.
- Uitgebreide methoden voor programmatische interactie met bedieningselementen.
- Vereenvoudigde aanpassing van besturingseigenschappen.
- Efficiënte gebeurtenisafhandeling voor interactieve presentaties.
- Gestroomlijnde verwijdering van bedieningselementen van dia's.

## Conclusie

Door ActiveX-besturingselementen in uw PowerPoint-presentaties op te nemen, kunt u de interactiviteit en betrokkenheid van uw publiek verhogen. Met Aspose.Slides voor .NET beschikt u over een krachtig hulpmiddel om ActiveX-besturingselementen naadloos te beheren, waardoor u dynamische en boeiende presentaties kunt maken die een blijvende indruk achterlaten.

## Veelgestelde vragen

### Hoe kan ik een ActiveX-besturingselement aan een specifieke dia toevoegen?

 Om een ActiveX-besturingselement aan een specifieke dia toe te voegen, kunt u de`AddOleObjectFrame` methode geleverd door Aspose.Slides voor .NET. Met deze methode kunt u de positie, grootte en ProgID opgeven van het ActiveX-besturingselement dat u wilt invoegen.

### Kan ik ActiveX-besturingselementen programmatisch manipuleren?

 Ja, u kunt ActiveX-besturingselementen programmatisch manipuleren met Aspose.Slides voor .NET. Door een verwijzing te verkrijgen naar de`IOleObjectFrame` die het besturingselement vertegenwoordigt, kunt u methoden aanroepen en eigenschappen instellen om dynamisch met het besturingselement te communiceren.

### Hoe ga ik om met gebeurtenissen

 geactiveerd door ActiveX-besturingselementen?

 kunt gebeurtenissen afhandelen die worden geactiveerd door ActiveX-besturingselementen door u te abonneren op de overeenkomstige gebeurtenissen met behulp van de`EventClick` (of soortgelijke) gebeurtenishandler. Hierdoor kunt u specifieke acties uitvoeren als reactie op gebruikersinteracties met de besturing.

### Is het mogelijk om het uiterlijk van ActiveX-besturingselementen aan te passen?

 Absoluut, u kunt het uiterlijk van ActiveX-besturingselementen aanpassen met behulp van de`SetProperty` methode geleverd door Aspose.Slides voor .NET. Met deze methode kunt u verschillende eigenschappen wijzigen, zoals de achtergrondkleur, de tekenstijl en meer.

### Kan ik een ActiveX-besturingselement uit een dia verwijderen?

 Ja, u kunt een ActiveX-besturingselement van een dia verwijderen met behulp van de`Remove` werkwijze van de`Shapes` verzameling. Geef de verwijzing door naar de`IOleObjectFrame` het besturingselement weergeven als een argument voor de`Remove` methode, en het besturingselement wordt van de dia verwijderd.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

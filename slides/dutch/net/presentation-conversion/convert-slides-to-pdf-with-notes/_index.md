---
"description": "Converteer presentatieslides met sprekersnotities moeiteloos naar PDF met Aspose.Slides voor .NET. Inhoud en context blijven naadloos behouden."
"linktitle": "Dia's converteren naar PDF met notities"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Dia's converteren naar PDF met notities"
"url": "/nl/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dia's converteren naar PDF met notities


# Schrijf een stapsgewijze handleiding voor het converteren van dia's naar PDF met notities met Aspose.Slides voor .NET

Bent u op zoek naar een betrouwbare manier om uw PowerPoint-dia's naar PDF-formaat te converteren en daarbij alle belangrijke notities te behouden? Zoek niet verder! In deze uitgebreide tutorial begeleiden we u stap voor stap door het gebruik van Aspose.Slides voor .NET.

## 1. Inleiding

Het converteren van PowerPoint-dia's naar PDF met notities kan een waardevolle tool zijn om presentaties te delen en tegelijkertijd te zorgen dat belangrijke context en opmerkingen behouden blijven. Aspose.Slides voor .NET biedt een krachtige oplossing voor deze taak.

## 2. Uw omgeving instellen

Voordat we beginnen met coderen, zorg ervoor dat je de juiste omgeving hebt ingesteld. Je hebt nodig:

- Visual Studio of uw favoriete .NET-ontwikkelomgeving.
- Aspose.Slides voor .NET-bibliotheek geïnstalleerd.
- Een PowerPoint-presentatie met notities die u wilt converteren.

## 3. De presentatie laden

In je C#-code moet je de PowerPoint-presentatie laden die je wilt converteren. Zo doe je dat:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. De dia klonen

Om ervoor te zorgen dat uw PDF alle benodigde dia's met notities bevat, kunt u ze vanuit de originele presentatie klonen. Zo doet u dat:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Diagrootte aanpassen

Mogelijk wilt u de diagrootte aanpassen aan uw PDF. Met Aspose.Slides voor .NET kunt u dit eenvoudig doen:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. PDF-opties configureren

Om te bepalen hoe uw notities in de PDF worden weergegeven, kunt u de PDF-opties configureren:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Opslaan als PDF met notities

Ten slotte kunt u uw presentatie opslaan als PDF met notities:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusie

Gefeliciteerd! U hebt uw PowerPoint-dia's succesvol geconverteerd naar PDF-formaat, met behoud van alle belangrijke notities. Aspose.Slides voor .NET maakt dit proces eenvoudig en efficiënt.

## 9. Veelgestelde vragen

### V1: Kan ik de lay-out van de notities in het PDF-bestand aanpassen?

Ja, u kunt de lay-out van de notities aanpassen met behulp van de `INotesCommentsLayoutingOptions` in de PDF-opties.

### V2: Ondersteunt Aspose.Slides voor .NET andere uitvoerformaten dan PDF?

Ja, Aspose.Slides voor .NET ondersteunt verschillende uitvoerformaten, waaronder PPTX, DOCX en meer.

### V3: Is er een proefversie beschikbaar voor Aspose.Slides voor .NET?

Ja, u kunt een gratis proefversie van Aspose.Slides voor .NET krijgen op [https://releases.aspose.com/](https://releases.aspose.com/).

### V4: Waar kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?

U kunt ondersteuning en discussies in de community vinden op [https://forum.aspose.com/](https://forum.aspose.com/).

### V5: Kan ik een tijdelijke licentie voor Aspose.Slides voor .NET kopen?

Ja, u kunt een tijdelijke licentie kopen bij [https://purchase.aspose.com/tijdelijke-licentie/](https://purchase.aspose.com/temporary-license/).

Kortom, met Aspose.Slides voor .NET kunt u PowerPoint-dia's eenvoudig converteren naar PDF-formaat, inclusief notities. Het is een waardevolle tool voor professionals die presentaties willen delen met collega's en klanten, zonder dat belangrijke context verloren gaat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
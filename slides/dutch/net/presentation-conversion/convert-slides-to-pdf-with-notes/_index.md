---
title: Converteer dia's naar PDF met Notes
linktitle: Converteer dia's naar PDF met Notes
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Converteer presentatiedia's met sprekernotities moeiteloos naar PDF met Aspose.Slides voor .NET. Bewaar inhoud en context naadloos.
weight: 18
url: /nl/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converteer dia's naar PDF met Notes


# Schrijf een stapsgewijze zelfstudie over het converteren van dia's naar PDF met Notes met behulp van Aspose.Slides voor .NET

Bent u op zoek naar een betrouwbare manier om uw PowerPoint-dia's naar PDF-formaat te converteren met behoud van alle belangrijke notities? Zoek niet verder! In deze uitgebreide zelfstudie begeleiden we u stap voor stap door het gebruik van Aspose.Slides voor .NET om deze taak te volbrengen.

## 1. Inleiding

Het converteren van PowerPoint-dia's naar PDF met notities kan een waardevol hulpmiddel zijn voor het delen van presentaties en tegelijkertijd ervoor zorgen dat belangrijke context en opmerkingen behouden blijven. Aspose.Slides voor .NET biedt een krachtige oplossing voor deze taak.

## 2. Uw omgeving instellen

Voordat we in het codeerproces duiken, moet je ervoor zorgen dat je de benodigde omgeving hebt ingesteld. Je hebt nodig:

- Visual Studio of uw favoriete .NET-ontwikkelomgeving.
- Aspose.Slides voor .NET-bibliotheek geïnstalleerd.
- Een PowerPoint-presentatie met aantekeningen die u wilt converteren.

## 3. De presentatie laden

In uw C#-code moet u de PowerPoint-presentatie laden die u wilt converteren. Hier ziet u hoe u het kunt doen:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. De dia klonen

Om ervoor te zorgen dat uw PDF alle benodigde dia's met notities bevat, kunt u deze uit de originele presentatie klonen. Hier is hoe:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Diagrootte aanpassen

Mogelijk wilt u het diaformaat aanpassen aan uw PDF. Met Aspose.Slides voor .NET kunt u dit eenvoudig doen:

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

## 7. Opslaan als PDF met Notes

Tenslotte kunt u uw presentatie opslaan als PDF met aantekeningen:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusie

Gefeliciteerd! U hebt uw PowerPoint-dia's met succes geconverteerd naar een PDF-formaat met behoud van alle belangrijke notities. Aspose.Slides voor .NET maakt dit proces eenvoudig en efficiënt.

## 9. Veelgestelde vragen

### V1: Kan ik de lay-out van de notities in de PDF aanpassen?

 Ja, u kunt de lay-out van de notities aanpassen met behulp van de`INotesCommentsLayoutingOptions` in de PDF-opties.

### V2: Ondersteunt Aspose.Slides voor .NET naast PDF ook andere uitvoerformaten?

Ja, Aspose.Slides voor .NET ondersteunt verschillende uitvoerformaten, waaronder PPTX, DOCX en meer.

### V3: Is er een proefversie beschikbaar voor Aspose.Slides voor .NET?

 Ja, u kunt een gratis proefversie van Aspose.Slides voor .NET krijgen op[https://releases.aspose.com/](https://releases.aspose.com/).

### V4: Waar kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?

 U kunt ondersteuning en communitydiscussies vinden op[https://forum.aspose.com/](https://forum.aspose.com/).

### V5: Kan ik een tijdelijke licentie kopen voor Aspose.Slides voor .NET?

 Ja, u kunt een tijdelijke licentie aanschaffen op[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Concluderend kunt u met Aspose.Slides voor .NET eenvoudig PowerPoint-dia's naar PDF-formaat converteren, terwijl de aantekeningen intact blijven. Het is een waardevol hulpmiddel voor professionals die presentaties moeten delen met collega's en klanten en er tegelijkertijd voor willen zorgen dat belangrijke context niet verloren gaat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Voeg bovenliggende opmerkingen toe aan de dia met Aspose.Slides
linktitle: Voeg ouderopmerkingen toe aan de dia
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u interactieve opmerkingen en antwoorden aan uw PowerPoint-presentaties kunt toevoegen met Aspose.Slides voor .NET. Verbeter de betrokkenheid en samenwerking.
weight: 12
url: /nl/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Wilt u uw PowerPoint-presentaties verbeteren met interactieve functies? Met Aspose.Slides voor .NET kunt u opmerkingen en antwoorden opnemen, waardoor een dynamische en boeiende ervaring voor uw publiek ontstaat. In deze stapsgewijze zelfstudie laten we u zien hoe u ouderopmerkingen aan dia's kunt toevoegen met behulp van Aspose.Slides voor .NET. Laten we erin duiken en deze opwindende functie verkennen.

## Vereisten

Voordat we aan de slag gaan, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Slides voor .NET: Zorg ervoor dat Aspose.Slides voor .NET is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/slides/net/).

2. Visual Studio: U hebt Visual Studio nodig om uw .NET-toepassing te maken en uit te voeren.

3. Basiskennis van C#: Deze tutorial gaat ervan uit dat je een basiskennis hebt van programmeren in C#.

Nu we aan de vereisten hebben voldaan, gaan we verder met het importeren van de benodigde naamruimten.

## Naamruimten importeren

Eerst moet u de relevante naamruimten in uw project importeren. Deze naamruimten bieden de klassen en methoden die nodig zijn voor het werken met Aspose.Slides voor .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Nu de vereisten en naamruimten aanwezig zijn, gaan we het proces opsplitsen in meerdere stappen voor het toevoegen van ouderopmerkingen aan een dia.

## Stap 1: Maak een presentatie

Om aan de slag te gaan, moet u een nieuwe presentatie maken met Aspose.Slides voor .NET. Deze presentatie is het canvas waarop u uw opmerkingen toevoegt.

```csharp
// Het pad naar de uitvoermap.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Uw code voor het toevoegen van opmerkingen komt hier terecht.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Vervang in de bovenstaande code`"Output Path"` met het gewenste pad voor uw uitvoerpresentatie.

## Stap 2: Voeg commentaarauteurs toe

Voordat u opmerkingen toevoegt, moet u de auteurs van deze opmerkingen definiëren. In dit voorbeeld hebben we twee auteurs, 'Auteur_1' en 'Auteur_2', elk vertegenwoordigd door een exemplaar van`ICommentAuthor`.

```csharp
// Voeg commentaar toe
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Antwoord voor commentaar toevoegen1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

In deze stap maken we twee auteurs van opmerkingen aan en voegen we de eerste opmerking en een antwoord aan de opmerking toe.

## Stap 3: voeg meer antwoorden toe

Als u een hiërarchische structuur van opmerkingen wilt maken, kunt u meer antwoorden toevoegen aan bestaande opmerkingen. Hier voegen we een tweede antwoord toe aan 'commentaar1'.

```csharp
// Antwoord voor commentaar toevoegen1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Hierdoor ontstaat er een gespreksstroom binnen uw presentatie.

## Stap 4: Geneste antwoorden toevoegen

Opmerkingen kunnen ook geneste antwoorden bevatten. Om dit aan te tonen, voegen we een antwoord toe aan 'antwoord 2 voor commentaar 1', waardoor een subantwoord ontstaat.

```csharp
// Voeg antwoord toe aan antwoord
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Deze stap benadrukt de veelzijdigheid van Aspose.Slides voor .NET bij het beheren van commentaarhiërarchieën.

## Stap 5: Meer opmerkingen en antwoorden

kunt indien nodig doorgaan met het toevoegen van meer opmerkingen en antwoorden. In dit voorbeeld voegen we nog twee opmerkingen toe en een antwoord op één ervan.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Deze stap laat zien hoe u boeiende en interactieve inhoud voor uw presentaties kunt maken.

## Stap 6: Geef de hiërarchie weer

Om de commentaarhiërarchie te visualiseren, kunt u deze op de console weergeven. Deze stap is optioneel, maar kan nuttig zijn voor het opsporen van fouten en het begrijpen van de structuur.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Stap 7: Reacties verwijderen

In sommige gevallen moet u mogelijk opmerkingen en hun antwoorden verwijderen. Het onderstaande codefragment laat zien hoe u "comment1" en alle bijbehorende antwoorden kunt verwijderen.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Deze stap is handig voor het beheren en bijwerken van de inhoud van uw presentatie.

Met deze stappen kunt u presentaties maken met interactieve opmerkingen en antwoorden met Aspose.Slides voor .NET. Of u nu uw publiek wilt betrekken of wilt samenwerken met teamleden, deze functie biedt een breed scala aan mogelijkheden.

## Conclusie

Aspose.Slides voor .NET biedt een krachtige set hulpmiddelen voor het verbeteren van uw PowerPoint-presentaties. Met de mogelijkheid om opmerkingen en antwoorden toe te voegen, kunt u dynamische en interactieve inhoud creëren die uw publiek boeit. Deze stapsgewijze handleiding heeft u laten zien hoe u bovenliggende opmerkingen aan dia's kunt toevoegen, hiërarchieën kunt instellen en zelfs opmerkingen kunt verwijderen wanneer dat nodig is. Door deze stappen te volgen en de Aspose.Slides-documentatie te verkennen[hier](https://reference.aspose.com/slides/net/)kunt u uw presentaties naar een hoger niveau tillen.

## Veelgestelde vragen

### Kan ik opmerkingen toevoegen aan specifieke dia's in mijn presentatie?
Ja, u kunt opmerkingen toevoegen aan elke dia in uw presentatie door de doeldia op te geven wanneer u een opmerking maakt.

### Is het mogelijk om de weergave van opmerkingen in de presentatie aan te passen?
Met Aspose.Slides voor .NET kunt u de weergave van opmerkingen aanpassen, inclusief de tekst, auteursinformatie en positie op de dia.

### Kan ik de opmerkingen en antwoorden naar een afzonderlijk bestand exporteren?
Ja, u kunt opmerkingen en antwoorden exporteren naar een afzonderlijk presentatiebestand, zoals gedemonstreerd in stap 7.

### Is Aspose.Slides voor .NET compatibel met de nieuwste versies van PowerPoint?
Aspose.Slides voor .NET is ontworpen om te werken met een breed scala aan PowerPoint-versies, waardoor compatibiliteit met de nieuwste releases wordt gegarandeerd.

### Zijn er licentieopties beschikbaar voor Aspose.Slides voor .NET?
 Ja, u kunt licentieopties, inclusief tijdelijke licenties, verkennen op de Aspose-website[hier](https://purchase.aspose.com/buy) of probeer de gratis proefperiode[hier](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Lägg till föräldrakommentarer till Slide med Aspose.Slides
linktitle: Lägg till föräldrars kommentarer till bild
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du lägger till interaktiva kommentarer och svar på dina PowerPoint-presentationer med Aspose.Slides för .NET. Förbättra engagemang och samarbete.
type: docs
weight: 12
url: /sv/net/slide-comments-manipulation/add-parent-comments/
---

Vill du förbättra dina PowerPoint-presentationer med interaktiva funktioner? Aspose.Slides för .NET låter dig infoga kommentarer och svar, vilket skapar en dynamisk och engagerande upplevelse för din publik. I denna steg-för-steg handledning kommer vi att visa dig hur du lägger till föräldrars kommentarer till bilder med Aspose.Slides för .NET. Låt oss dyka in och utforska denna spännande funktion.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1.  Aspose.Slides för .NET: Se till att du har Aspose.Slides för .NET installerat. Du kan ladda ner den[här](https://releases.aspose.com/slides/net/).

2. Visual Studio: Du behöver Visual Studio för att skapa och köra din .NET-applikation.

3. Grundläggande kunskaper om C#: Denna handledning förutsätter att du har en grundläggande förståelse för C#-programmering.

Nu när vi har täckta förutsättningarna, låt oss fortsätta att importera de nödvändiga namnrymden.

## Importera namnområden

Först måste du importera relevanta namnområden till ditt projekt. Dessa namnrymder tillhandahåller de klasser och metoder som krävs för att arbeta med Aspose.Slides för .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Med förutsättningarna och namnutrymmena på plats, låt oss dela upp processen i flera steg för att lägga till överordnade kommentarer till en bild.

## Steg 1: Skapa en presentation

För att komma igång måste du skapa en ny presentation med Aspose.Slides för .NET. Den här presentationen kommer att vara duken där du lägger dina kommentarer.

```csharp
// Sökvägen till utdatakatalogen.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Din kod för att lägga till kommentarer kommer hit.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 I koden ovan, ersätt`"Output Path"` med den önskade sökvägen för din utdatapresentation.

## Steg 2: Lägg till kommentarsförfattare

Innan du lägger till kommentarer måste du definiera författarna till dessa kommentarer. I det här exemplet har vi två författare, "Author_1" och "Author_2", var och en representerad av en instans av`ICommentAuthor`.

```csharp
// Lägg till kommentar
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Lägg till svar för kommentar1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

I det här steget skapar vi två kommentarsförfattare och lägger till den första kommentaren och ett svar på kommentaren.

## Steg 3: Lägg till fler svar

För att skapa en hierarkisk struktur av kommentarer kan du lägga till fler svar på befintliga kommentarer. Här lägger vi till ett andra svar på "kommentar1."

```csharp
// Lägg till svar för kommentar1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Detta skapar ett konversationsflöde i din presentation.

## Steg 4: Lägg till kapslade svar

Kommentarer kan också ha kapslade svar. För att visa detta lägger vi till ett svar på "svar 2 för kommentar 1", vilket skapar ett undersvar.

```csharp
// Lägg till svar till svar
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Det här steget belyser mångsidigheten hos Aspose.Slides för .NET för att hantera kommentarshierarkier.

## Steg 5: Fler kommentarer och svar

Du kan fortsätta att lägga till fler kommentarer och svar efter behov. I det här exemplet lägger vi till ytterligare två kommentarer och ett svar på en av dem.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Det här steget visar hur du kan skapa engagerande och interaktivt innehåll för dina presentationer.

## Steg 6: Visa hierarkin

För att visualisera kommentarhierarkin kan du visa den på konsolen. Det här steget är valfritt men kan vara till hjälp för att felsöka och förstå strukturen.

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

## Steg 7: Ta bort kommentarer

I vissa fall kan du behöva ta bort kommentarer och deras svar. Kodavsnittet nedan visar hur man tar bort "comment1" och alla dess svar.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Det här steget är användbart för att hantera och uppdatera ditt presentationsinnehåll.

Med dessa steg kan du skapa presentationer med interaktiva kommentarer och svar med Aspose.Slides för .NET. Oavsett om du vill engagera din publik eller samarbeta med teammedlemmar erbjuder den här funktionen ett brett utbud av möjligheter.

## Slutsats

Aspose.Slides för .NET tillhandahåller en kraftfull uppsättning verktyg för att förbättra dina PowerPoint-presentationer. Med möjligheten att lägga till kommentarer och svar kan du skapa dynamiskt och interaktivt innehåll som fängslar din publik. Den här steg-för-steg-guiden har visat dig hur du lägger till föräldrakommentarer till bilder, upprättar hierarkier och till och med tar bort kommentarer när det behövs. Genom att följa dessa steg och utforska Aspose.Slides-dokumentationen[här](https://reference.aspose.com/slides/net/), kan du ta dina presentationer till nästa nivå.

## Vanliga frågor

### Kan jag lägga till kommentarer till specifika bilder i min presentation?
Ja, du kan lägga till kommentarer till valfri bild i din presentation genom att ange målbilden när du skapar en kommentar.

### Är det möjligt att anpassa utseendet på kommentarer i presentationen?
Aspose.Slides för .NET låter dig anpassa utseendet på kommentarer, inklusive deras text, författarinformation och position på bilden.

### Kan jag exportera kommentarerna och svaren till en separat fil?
Ja, du kan exportera kommentarer och svar till en separat presentationsfil, som visas i steg 7.

### Är Aspose.Slides för .NET kompatibelt med de senaste versionerna av PowerPoint?
Aspose.Slides för .NET är designad för att fungera med ett brett utbud av PowerPoint-versioner, vilket säkerställer kompatibilitet med de senaste utgåvorna.

### Finns det några licensalternativ för Aspose.Slides för .NET?
 Ja, du kan utforska licensalternativ, inklusive tillfälliga licenser, på Asposes webbplats[här](https://purchase.aspose.com/buy) eller prova den kostnadsfria provperioden[här](https://releases.aspose.com/temporary-license/).
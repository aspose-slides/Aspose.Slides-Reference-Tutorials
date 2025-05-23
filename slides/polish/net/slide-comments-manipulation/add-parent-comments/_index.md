---
"description": "Dowiedz się, jak dodawać interaktywne komentarze i odpowiedzi do prezentacji PowerPoint za pomocą Aspose.Slides dla .NET. Zwiększ zaangażowanie i współpracę."
"linktitle": "Dodaj komentarze rodziców do slajdu"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Dodaj komentarze nadrzędne do slajdu za pomocą Aspose.Slides"
"url": "/pl/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj komentarze nadrzędne do slajdu za pomocą Aspose.Slides


Czy chcesz ulepszyć swoje prezentacje PowerPoint za pomocą interaktywnych funkcji? Aspose.Slides dla .NET pozwala na dodawanie komentarzy i odpowiedzi, tworząc dynamiczne i angażujące doświadczenie dla odbiorców. W tym samouczku krok po kroku pokażemy, jak dodawać komentarze nadrzędne do slajdów za pomocą Aspose.Slides dla .NET. Zanurzmy się i odkryjmy tę ekscytującą funkcję.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Aspose.Slides dla .NET: Upewnij się, że masz zainstalowany Aspose.Slides dla .NET. Możesz go pobrać [Tutaj](https://releases.aspose.com/slides/net/).

2. Visual Studio: Będziesz potrzebować programu Visual Studio, aby utworzyć i uruchomić aplikację .NET.

3. Podstawowa wiedza o języku C#: W tym samouczku zakładamy, że posiadasz podstawową wiedzę na temat programowania w języku C#.

Teraz, gdy spełniliśmy już wszystkie wymagania wstępne, możemy zaimportować niezbędne przestrzenie nazw.

## Importowanie przestrzeni nazw

Najpierw musisz zaimportować odpowiednie przestrzenie nazw do swojego projektu. Te przestrzenie nazw udostępniają klasy i metody wymagane do pracy z Aspose.Slides dla .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Mając już wymagania wstępne i przestrzenie nazw, możemy podzielić proces na kilka kroków w celu dodania komentarzy rodzica do slajdu.

## Krok 1: Utwórz prezentację

Aby rozpocząć, musisz utworzyć nową prezentację za pomocą Aspose.Slides dla .NET. Ta prezentacja będzie płótnem, na którym będziesz dodawać swoje komentarze.

```csharp
// Ścieżka do katalogu wyjściowego.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Tutaj znajdziesz kod umożliwiający dodawanie komentarzy.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

W powyższym kodzie zamień `"Output Path"` z żądaną ścieżką dla prezentacji wyjściowej.

## Krok 2: Dodaj autorów komentarzy

Przed dodaniem komentarzy należy zdefiniować autorów tych komentarzy. W tym przykładzie mamy dwóch autorów, „Author_1” i „Author_2”, każdy reprezentowany przez wystąpienie `ICommentAuthor`.

```csharp
// Dodaj komentarz
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Dodaj odpowiedź do komentarza 1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

W tym kroku tworzymy dwóch autorów komentarzy i dodajemy początkowy komentarz oraz odpowiedź na komentarz.

## Krok 3: Dodaj więcej odpowiedzi

Aby utworzyć hierarchiczną strukturę komentarzy, możesz dodać więcej odpowiedzi do istniejących komentarzy. Tutaj dodajemy drugą odpowiedź do „komentarza1”.

```csharp
// Dodaj odpowiedź do komentarza 1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Ustanawia to przepływ konwersacji w ramach prezentacji.

## Krok 4: Dodaj zagnieżdżone odpowiedzi

Komentarze mogą mieć również zagnieżdżone odpowiedzi. Aby to zademonstrować, dodajemy odpowiedź do „odpowiedzi 2 dla komentarza 1”, tworząc pododpowiedź.

```csharp
// Dodaj odpowiedź do odpowiedzi
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Ten krok podkreśla wszechstronność pakietu Aspose.Slides for .NET w zarządzaniu hierarchiami komentarzy.

## Krok 5: Więcej komentarzy i odpowiedzi

Możesz kontynuować dodawanie kolejnych komentarzy i odpowiedzi, jeśli to konieczne. W tym przykładzie dodajemy dwa kolejne komentarze i odpowiedź na jeden z nich.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

W tym kroku pokażemy Ci, jak możesz tworzyć angażujące i interaktywne treści do swoich prezentacji.

## Krok 6: Wyświetl hierarchię

Aby zwizualizować hierarchię komentarzy, możesz wyświetlić ją na konsoli. Ten krok jest opcjonalny, ale może być pomocny w debugowaniu i zrozumieniu struktury.

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

## Krok 7: Usuń komentarze

W niektórych przypadkach może być konieczne usunięcie komentarzy i odpowiedzi na nie. Poniższy fragment kodu pokazuje, jak usunąć „comment1” i wszystkie jego odpowiedzi.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Ten krok jest przydatny przy zarządzaniu treścią prezentacji i jej aktualizowaniu.

Dzięki tym krokom możesz tworzyć prezentacje z interaktywnymi komentarzami i odpowiedziami przy użyciu Aspose.Slides dla .NET. Niezależnie od tego, czy chcesz zaangażować odbiorców, czy współpracować z członkami zespołu, ta funkcja oferuje szeroki zakres możliwości.

## Wniosek

Aspose.Slides for .NET zapewnia potężny zestaw narzędzi do ulepszania prezentacji PowerPoint. Dzięki możliwości dodawania komentarzy i odpowiedzi możesz tworzyć dynamiczną i interaktywną treść, która oczaruje odbiorców. Ten przewodnik krok po kroku pokazał Ci, jak dodawać komentarze nadrzędne do slajdów, ustalać hierarchie, a nawet usuwać komentarze, gdy jest to konieczne. Wykonując te kroki i przeglądając dokumentację Aspose.Slides [Tutaj](https://reference.aspose.com/slides/net/), możesz przenieść swoje prezentacje na wyższy poziom.

## Często zadawane pytania

### Czy mogę dodawać komentarze do konkretnych slajdów prezentacji?
Tak, możesz dodawać komentarze do dowolnego slajdu w prezentacji, określając slajd docelowy podczas tworzenia komentarza.

### Czy można dostosować wygląd komentarzy w prezentacji?
Aspose.Slides for .NET umożliwia dostosowanie wyglądu komentarzy, w tym ich tekstu, informacji o autorze i położenia na slajdzie.

### Czy mogę wyeksportować komentarze i odpowiedzi do osobnego pliku?
Tak, możesz eksportować komentarze i odpowiedzi do osobnego pliku prezentacji, jak pokazano w kroku 7.

### Czy Aspose.Slides dla .NET jest zgodny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides for .NET został zaprojektowany do współpracy z szeroką gamą wersji programu PowerPoint, zapewniając zgodność z najnowszymi wersjami.

### Czy są dostępne jakieś opcje licencjonowania dla Aspose.Slides dla .NET?
Tak, możesz zapoznać się z opcjami licencjonowania, w tym licencjami tymczasowymi, na stronie internetowej Aspose [Tutaj](https://purchase.aspose.com/buy) lub wypróbuj bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
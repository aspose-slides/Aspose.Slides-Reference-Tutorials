---
title: Dodaj komentarze rodziców do slajdu za pomocą Aspose.Slides
linktitle: Dodaj komentarze rodziców do slajdu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodawać interaktywne komentarze i odpowiedzi do prezentacji programu PowerPoint za pomocą Aspose.Slides dla .NET. Zwiększ zaangażowanie i współpracę.
weight: 12
url: /pl/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Czy chcesz ulepszyć swoje prezentacje programu PowerPoint za pomocą funkcji interaktywnych? Aspose.Slides dla .NET umożliwia dołączanie komentarzy i odpowiedzi, tworząc dynamiczne i wciągające doświadczenie dla odbiorców. W tym samouczku krok po kroku pokażemy, jak dodawać komentarze nadrzędne do slajdów za pomocą Aspose.Slides dla .NET. Zanurzmy się i odkryjmy tę ekscytującą funkcję.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowany Aspose.Slides dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).

2. Visual Studio: Do utworzenia i uruchomienia aplikacji .NET potrzebny będzie program Visual Studio.

3. Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat programowania w języku C#.

Teraz, gdy mamy już spełnione wymagania wstępne, przejdźmy do importowania niezbędnych przestrzeni nazw.

## Importowanie przestrzeni nazw

Najpierw musisz zaimportować odpowiednie przestrzenie nazw do swojego projektu. Te przestrzenie nazw zapewniają klasy i metody wymagane do pracy z Aspose.Slides dla .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Po spełnieniu wymagań wstępnych i przestrzeni nazw podzielmy proces na wiele etapów dodawania komentarzy nadrzędnych do slajdu.

## Krok 1: Utwórz prezentację

Aby rozpocząć, musisz utworzyć nową prezentację za pomocą Aspose.Slides dla .NET. Ta prezentacja będzie kanwą, na której będziesz dodawać swoje komentarze.

```csharp
// Ścieżka do katalogu wyjściowego.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Twój kod do dodawania komentarzy zostanie umieszczony tutaj.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 W powyższym kodzie zamień`"Output Path"` z żądaną ścieżką prezentacji wyjściowej.

## Krok 2: Dodaj autorów komentarzy

Przed dodaniem komentarzy należy zdefiniować autorów tych komentarzy. W tym przykładzie mamy dwóch autorów, „Autora_1” i „Autora_2”, każdy reprezentowany przez instancję`ICommentAuthor`.

```csharp
// Dodaj komentarz
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Dodaj odpowiedź na komentarz 1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Na tym etapie tworzymy dwóch autorów komentarzy i dodajemy komentarz początkowy oraz odpowiedź na komentarz.

## Krok 3: Dodaj więcej odpowiedzi

Aby utworzyć hierarchiczną strukturę komentarzy, możesz dodać więcej odpowiedzi do istniejących komentarzy. Tutaj dodajemy drugą odpowiedź na „komentarz 1”.

```csharp
// Dodaj odpowiedź na komentarz 1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Ustala to przebieg rozmowy w prezentacji.

## Krok 4: Dodaj zagnieżdżone odpowiedzi

Komentarze mogą również zawierać zagnieżdżone odpowiedzi. Aby to zademonstrować, dodajemy odpowiedź do „odpowiedzi 2 na komentarz 1”, tworząc odpowiedź podrzędną.

```csharp
// Dodaj odpowiedź do odpowiedzi
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Ten krok podkreśla wszechstronność Aspose.Slides dla .NET w zarządzaniu hierarchiami komentarzy.

## Krok 5: Więcej komentarzy i odpowiedzi

razie potrzeby możesz nadal dodawać więcej komentarzy i odpowiedzi. W tym przykładzie dodajemy jeszcze dwa komentarze i odpowiedź na jeden z nich.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Na tym etapie pokazano, jak tworzyć angażujące i interaktywne treści do prezentacji.

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

W niektórych przypadkach może być konieczne usunięcie komentarzy i odpowiedzi na nie. Poniższy fragment kodu pokazuje, jak usunąć „komentarz1” i wszystkie jego odpowiedzi.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Ten krok jest przydatny do zarządzania treścią prezentacji i jej aktualizowania.

Wykonując te kroki, możesz tworzyć prezentacje z interaktywnymi komentarzami i odpowiedziami za pomocą Aspose.Slides dla .NET. Niezależnie od tego, czy chcesz zaangażować odbiorców, czy współpracować z członkami zespołu, ta funkcja oferuje szeroki zakres możliwości.

## Wniosek

Aspose.Slides dla .NET zapewnia potężny zestaw narzędzi do ulepszania prezentacji PowerPoint. Dzięki możliwości dodawania komentarzy i odpowiedzi możesz tworzyć dynamiczne i interaktywne treści, które przykują uwagę odbiorców. W tym przewodniku krok po kroku pokazano, jak dodawać komentarze nadrzędne do slajdów, ustalać hierarchie, a nawet usuwać komentarze, jeśli to konieczne. Wykonując poniższe kroki i przeglądając dokumentację Aspose.Slides[Tutaj](https://reference.aspose.com/slides/net/)możesz przenieść swoje prezentacje na wyższy poziom.

## Często zadawane pytania

### Czy mogę dodawać komentarze do konkretnych slajdów w mojej prezentacji?
Tak, możesz dodawać komentarze do dowolnego slajdu w prezentacji, określając slajd docelowy podczas tworzenia komentarza.

### Czy można dostosować wygląd komentarzy w prezentacji?
Aspose.Slides dla .NET pozwala dostosować wygląd komentarzy, w tym ich tekst, informacje o autorze i położenie na slajdzie.

### Czy mogę wyeksportować komentarze i odpowiedzi do osobnego pliku?
Tak, możesz wyeksportować komentarze i odpowiedzi do osobnego pliku prezentacji, jak pokazano w kroku 7.

### Czy Aspose.Slides for .NET jest kompatybilny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides dla .NET został zaprojektowany do współpracy z szeroką gamą wersji programu PowerPoint, zapewniając kompatybilność z najnowszymi wydaniami.

### Czy są dostępne opcje licencjonowania dla Aspose.Slides dla .NET?
 Tak, możesz zapoznać się z opcjami licencjonowania, w tym licencjami tymczasowymi, na stronie internetowej Aspose[Tutaj](https://purchase.aspose.com/buy) lub wypróbuj bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

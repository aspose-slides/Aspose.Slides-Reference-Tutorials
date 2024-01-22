---
title: Manipulacja hiperłączami w Aspose.Slides
linktitle: Manipulacja hiperłączami w Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodawać i usuwać hiperłącza w Aspose.Slides dla .NET. Z łatwością ulepsz swoje prezentacje za pomocą interaktywnych łączy.
type: docs
weight: 10
url: /pl/net/hyperlink-manipulation/hyperlink-manipulation/
---

Hiperłącza są niezbędnym elementem prezentacji, ponieważ zapewniają wygodny sposób poruszania się między slajdami lub uzyskiwania dostępu do zasobów zewnętrznych. Aspose.Slides dla .NET oferuje zaawansowane funkcje dodawania i usuwania hiperłączy na slajdach prezentacji. W tym samouczku przeprowadzimy Cię przez proces manipulacji hiperłączami przy użyciu Aspose.Slides dla .NET. Omówimy dodawanie hiperłączy do slajdu i usuwanie hiperłączy ze slajdu. Zatem zanurzmy się!

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Slides dla .NET: Musisz mieć zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides dla .NET. Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/net/) i pobierz go z[ten link](https://releases.aspose.com/slides/net/).

2. Twój katalog dokumentów: Potrzebujesz katalogu, w którym będziesz przechowywać pliki prezentacji. Pamiętaj, aby określić ścieżkę do tego katalogu w kodzie.

3. Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat programowania w języku C#.

Teraz, gdy masz już wymagania wstępne, przejdźmy do przewodnika krok po kroku dotyczącego manipulacji hiperłączami przy użyciu Aspose.Slides dla .NET.

## Dodawanie hiperłączy do slajdu

### Krok 1: Zainicjuj prezentację

Aby rozpocząć, musisz zainicjować prezentację za pomocą Aspose.Slides. Można to zrobić za pomocą następującego kodu:

```csharp
using (Presentation presentation = new Presentation())
{
    // Twój kod tutaj
}
```

### Krok 2: Dodaj ramkę tekstową

Teraz dodajmy ramkę tekstową do slajdu. Ten kod tworzy prostokątny kształt z tekstem:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Krok 3: Dodaj hiperłącze

Następnie dodasz hiperłącze do tekstu w utworzonym kształcie. Oto jak możesz to zrobić:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Krok 4: Zapisz prezentację

Na koniec zapisz prezentację z dodanym hiperłączem:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Gratulacje! Pomyślnie dodałeś hiperłącze do slajdu przy użyciu Aspose.Slides dla .NET.

## Usuwanie hiperłączy ze slajdu

### Krok 1: Zainicjuj prezentację

Aby usunąć hiperłącza ze slajdu, musisz otworzyć istniejącą prezentację:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Krok 2: Usuń hiperłącza

Teraz usuń wszystkie hiperłącza z prezentacji, używając następującego kodu:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Krok 3: Zapisz prezentację

Po usunięciu hiperłączy zapisz prezentację:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

I to wszystko! Pomyślnie usunąłeś hiperłącza ze slajdu za pomocą Aspose.Slides dla .NET.

Podsumowując, Aspose.Slides dla .NET zapewnia skuteczny sposób manipulowania hiperłączami w prezentacjach, umożliwiając tworzenie interaktywnych i wciągających slajdów. Niezależnie od tego, czy chcesz dodać hiperłącza do zasobów zewnętrznych, czy je usunąć, Aspose.Slides upraszcza proces i zwiększa możliwości tworzenia prezentacji.

 Dziękujemy, że dołączyłeś do nas w tym samouczku na temat manipulacji hiperłączami w Aspose.Slides dla .NET. Jeśli masz jakieś pytania lub potrzebujesz dalszej pomocy, nie krępuj się zapoznać z naszą stroną[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) lub skontaktuj się ze społecznością Aspose na stronie[forum wsparcia](https://forum.aspose.com/).

---

## Wniosek

W tym samouczku nauczyliśmy się manipulować hiperłączami w prezentacjach za pomocą Aspose.Slides dla .NET. Omówiliśmy zarówno dodawanie, jak i usuwanie hiperłączy, umożliwiając tworzenie dynamicznych i interaktywnych prezentacji. Aspose.Slides upraszcza ten proces, ułatwiając ulepszanie slajdów za pomocą hiperłączy do zasobów zewnętrznych.

Czy masz więcej pytań na temat pracy z Aspose.Slides lub innych aspektów projektowania prezentacji? Aby uzyskać więcej informacji, zapoznaj się z poniższymi często zadawanymi pytaniami.

## Często zadawane pytania (często zadawane pytania)

### Jakie są kluczowe zalety korzystania z Aspose.Slides dla .NET?
Aspose.Slides dla .NET oferuje szeroką gamę funkcji do tworzenia, manipulowania i konwertowania prezentacji. Zapewnia kompleksowy zestaw narzędzi do dodawania treści, animacji i interakcji do slajdów.

### Czy w Aspose.Slides mogę dodawać hiperłącza do obiektów innych niż tekst?
Tak, Aspose.Slides umożliwia dodawanie hiperłączy do różnych obiektów, w tym kształtów, obrazów i tekstu, co zapewnia elastyczność w tworzeniu interaktywnych prezentacji.

### Czy Aspose.Slides jest kompatybilny z różnymi formatami plików PowerPoint?
Absolutnie. Aspose.Slides obsługuje różne formaty programu PowerPoint, w tym PPT, PPTX, PPS i inne. Zapewnia kompatybilność z różnymi wersjami programu Microsoft PowerPoint.

### Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Slides?
Aby uzyskać szczegółową dokumentację i wsparcie społeczności, odwiedź stronę[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) i[Forum wsparcia Aspose](https://forum.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
 Jeśli potrzebujesz tymczasowej licencji na Aspose.Slides, możesz ją uzyskać[Tutaj](https://purchase.aspose.com/temporary-license/).
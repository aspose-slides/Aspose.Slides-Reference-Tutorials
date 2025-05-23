---
"description": "Dowiedz się, jak dodawać i usuwać hiperłącza w Aspose.Slides dla .NET. Ulepszaj swoje prezentacje za pomocą interaktywnych łączy."
"linktitle": "Manipulacja hiperlinkami w Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Manipulacja hiperlinkami w Aspose.Slides"
"url": "/pl/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipulacja hiperlinkami w Aspose.Slides


Hiperłącza są niezbędnymi elementami prezentacji, ponieważ zapewniają wygodny sposób nawigowania między slajdami lub uzyskiwania dostępu do zasobów zewnętrznych. Aspose.Slides for .NET oferuje potężne funkcje dodawania i usuwania hiperłączy w slajdach prezentacji. W tym samouczku przeprowadzimy Cię przez proces manipulacji hiperłączami za pomocą Aspose.Slides for .NET. Omówimy dodawanie hiperłączy do slajdu i usuwanie hiperłączy ze slajdu. Więc zanurzmy się!

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Aspose.Slides dla .NET: Musisz mieć zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides dla .NET. Dokumentację znajdziesz [Tutaj](https://reference.aspose.com/slides/net/) i pobierz go z [ten link](https://releases.aspose.com/slides/net/).

2. Twój katalog dokumentów: Potrzebujesz katalogu, w którym będziesz przechowywać pliki prezentacji. Upewnij się, że w kodzie określono ścieżkę do tego katalogu.

3. Podstawowa wiedza o języku C#: W tym samouczku zakładamy, że posiadasz podstawową wiedzę na temat programowania w języku C#.

Teraz, gdy spełniłeś już wszystkie wymagania wstępne, możemy przejść do przewodnika krok po kroku dotyczącego manipulowania hiperlinkami za pomocą Aspose.Slides dla platformy .NET.

## Dodawanie hiperłączy do slajdu

### Krok 1: Zainicjuj prezentację

Aby rozpocząć, musisz zainicjować prezentację za pomocą Aspose.Slides. Możesz to zrobić za pomocą następującego kodu:

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

Na koniec zapisz prezentację, dodając hiperłącze:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Gratulacje! Udało Ci się dodać hiperłącze do slajdu za pomocą Aspose.Slides dla .NET.

## Usuwanie hiperłączy ze slajdu

### Krok 1: Zainicjuj prezentację

Aby usunąć hiperłącza ze slajdu, musisz otworzyć istniejącą prezentację:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Krok 2: Usuń hiperłącza

Teraz usuń wszystkie hiperłącza z prezentacji, korzystając z następującego kodu:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Krok 3: Zapisz prezentację

Po usunięciu hiperłączy zapisz prezentację:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

I to wszystko! Udało Ci się usunąć hiperłącza ze slajdu za pomocą Aspose.Slides dla .NET.

Podsumowując, Aspose.Slides dla .NET zapewnia wydajny sposób manipulowania hiperlinkami w prezentacjach, umożliwiając tworzenie interaktywnych i angażujących slajdów. Niezależnie od tego, czy chcesz dodać hiperlinki do zasobów zewnętrznych, czy je usunąć, Aspose.Slides upraszcza ten proces i zwiększa możliwości tworzenia prezentacji.

Dziękujemy za udział w tym samouczku dotyczącym manipulacji hiperlinkami w Aspose.Slides dla .NET. Jeśli masz jakieś pytania lub potrzebujesz dalszej pomocy, możesz swobodnie przejrzeć [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) lub skontaktuj się ze społecznością Aspose na [forum wsparcia](https://forum.aspose.com/).

---

## Wniosek

W tym samouczku nauczyliśmy się, jak manipulować hiperlinkami w prezentacjach za pomocą Aspose.Slides dla .NET. Omówiliśmy dodawanie i usuwanie hiperlinków, co pozwala tworzyć dynamiczne i interaktywne prezentacje. Aspose.Slides upraszcza ten proces, ułatwiając wzbogacanie slajdów o hiperlinki do zasobów zewnętrznych.

Masz więcej pytań dotyczących pracy z Aspose.Slides lub innych aspektów projektowania prezentacji? Sprawdź poniższe FAQ, aby uzyskać więcej informacji.

## FAQ (najczęściej zadawane pytania)

### Jakie są główne zalety korzystania z Aspose.Slides dla .NET?
Aspose.Slides for .NET oferuje szeroki zakres funkcji do tworzenia, manipulowania i konwertowania prezentacji. Zapewnia kompleksowy zestaw narzędzi do dodawania treści, animacji i interakcji do slajdów.

### Czy w Aspose.Slides mogę dodawać hiperłącza do obiektów innych niż tekst?
Tak, Aspose.Slides pozwala dodawać hiperłącza do różnych obiektów, w tym kształtów, obrazów i tekstu, co zapewnia elastyczność podczas tworzenia interaktywnych prezentacji.

### Czy Aspose.Slides jest kompatybilny z różnymi formatami plików PowerPoint?
Oczywiście. Aspose.Slides obsługuje różne formaty PowerPoint, w tym PPT, PPTX, PPS i inne. Zapewnia zgodność z różnymi wersjami Microsoft PowerPoint.

### Gdzie mogę znaleźć dodatkowe zasoby i pomoc dotyczącą Aspose.Slides?
Aby uzyskać szczegółową dokumentację i uzyskać wsparcie społeczności, odwiedź stronę [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) i [Forum wsparcia Aspose](https://forum.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
Jeśli potrzebujesz tymczasowej licencji na Aspose.Slides, możesz ją uzyskać [Tutaj](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
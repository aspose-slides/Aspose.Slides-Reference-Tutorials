---
"description": "Dowiedz się, jak dodawać hiperłącza do slajdów programu PowerPoint za pomocą Aspose.Slides dla .NET. Ulepsz swoje prezentacje za pomocą interaktywnych elementów."
"linktitle": "Dodaj hiperłącze do slajdu"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Dodawanie hiperłączy do slajdów w .NET przy użyciu Aspose.Slides"
"url": "/pl/net/hyperlink-manipulation/add-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie hiperłączy do slajdów w .NET przy użyciu Aspose.Slides


świecie prezentacji cyfrowych interaktywność jest kluczowa. Dodawanie hiperłączy do slajdów może sprawić, że prezentacja będzie bardziej angażująca i pouczająca. Aspose.Slides for .NET to potężna biblioteka, która umożliwia programowe tworzenie, modyfikowanie i manipulowanie prezentacjami PowerPoint. W tym samouczku pokażemy, jak dodawać hiperłącza do slajdów za pomocą Aspose.Slides for .NET. 

## Wymagania wstępne

Zanim przejdziemy do dodawania hiperłączy do slajdów, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio: Aby pisać i wykonywać kod .NET, na komputerze musi być zainstalowany program Visual Studio.

2. Aspose.Slides dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).

3. Podstawowa wiedza z zakresu języka C#: Znajomość programowania w języku C# będzie dodatkowym atutem.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw w swoim projekcie C#. W tym przypadku będziesz potrzebować następujących przestrzeni nazw z biblioteki Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Teraz podzielimy proces dodawania hiperłączy do slajdów na kilka kroków.

## Krok 1: Zainicjuj prezentację

Najpierw utwórz nową prezentację za pomocą Aspose.Slides. Oto jak możesz to zrobić:

```csharp
using (Presentation presentation = new Presentation())
{
    // Twój kod wpisz tutaj
}
```

Ten kod inicjuje nową prezentację programu PowerPoint.

## Krok 2: Dodaj ramkę tekstową

Teraz dodajmy ramkę tekstową do slajdu. Ta ramka tekstowa będzie służyć jako klikalny element na slajdzie. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Powyższy kod tworzy prostokątny kształt automatyczny i dodaje ramkę tekstową z tekstem „Aspose: API formatu pliku”.

## Krok 3: Dodaj hiperłącze

Następnie dodajmy hiperłącze do utworzonej ramki tekstowej. Dzięki temu tekst będzie klikalny.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

tym kroku ustawiamy adres URL hiperłącza na „https://www.aspose.com/” i podajemy podpowiedź z dodatkowymi informacjami. Możesz również sformatować wygląd hiperłącza, jak pokazano powyżej.

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację za pomocą dodanego hiperłącza.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Ten kod zapisuje prezentację jako „presentation-out.pptx”.

Teraz dodałeś hiperłącze do slajdu za pomocą Aspose.Slides dla .NET.

## Wniosek

W tym samouczku sprawdziliśmy, jak dodawać hiperłącza do slajdów w prezentacjach PowerPoint przy użyciu Aspose.Slides dla .NET. Wykonując te kroki, możesz sprawić, że Twoje prezentacje będą bardziej interaktywne i angażujące, zapewniając cenne linki do dodatkowych zasobów lub informacji.

Aby uzyskać bardziej szczegółowe informacje i dokumentację, odwiedź stronę [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/).

## Często zadawane pytania

### 1. Czy mogę dodawać hiperłącza do innych kształtów oprócz ramek tekstowych?

Tak, możesz dodawać hiperłącza do różnych kształtów, takich jak prostokąty, obrazy i inne, korzystając z Aspose.Slides dla .NET.

### 2. Jak usunąć hiperłącze z kształtu na slajdzie programu PowerPoint?

Możesz usunąć hiperłącze z kształtu, ustawiając `HyperlinkClick` nieruchomość do `null`.

### 3. Czy mogę dynamicznie zmieniać adres URL hiperłącza w swoim kodzie?

Oczywiście! Możesz zaktualizować adres URL hiperłącza w dowolnym miejscu swojego kodu, modyfikując `Hyperlink` nieruchomość.

### 4. Jakie inne interaktywne elementy mogę dodać do slajdów programu PowerPoint za pomocą Aspose.Slides?

Aspose.Slides oferuje szeroką gamę interaktywnych funkcji, w tym przyciski akcji, elementy multimedialne i animacje.

### 5. Czy Aspose.Slides jest dostępny dla innych języków programowania?

Tak, Aspose.Slides jest dostępny dla różnych języków programowania, w tym Java i Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
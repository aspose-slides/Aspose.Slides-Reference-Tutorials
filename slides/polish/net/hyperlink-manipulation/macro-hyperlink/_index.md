---
"description": "Dowiedz się, jak ustawić hiperłącza makro w prezentacjach za pomocą Aspose.Slides dla .NET. Zwiększ interaktywność i zaangażuj odbiorców."
"linktitle": "Zarządzanie hiperlinkami za pomocą makr"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Jak ustawić makro hiperłącza kliknięcia w Aspose.Slides dla .NET"
"url": "/pl/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić makro hiperłącza kliknięcia w Aspose.Slides dla .NET


W świecie nowoczesnego rozwoju oprogramowania tworzenie dynamicznych i interaktywnych prezentacji jest kluczowym aspektem. Aspose.Slides for .NET to potężna biblioteka, która umożliwia bezproblemową pracę z prezentacjami. Niezależnie od tego, czy tworzysz prezentację biznesową, czy edukacyjny pokaz slajdów, możliwość ustawiania kliknięć makro hiperłączy może znacznie poprawić wrażenia użytkownika. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces ustawiania kliknięcia makro hiperłącza za pomocą Aspose.Slides for .NET. 

## Wymagania wstępne

Zanim przejdziemy do szczegółowego samouczka, musisz spełnić kilka warunków wstępnych:

1.Visual Studio: Upewnij się, że na Twoim komputerze jest zainstalowany program Visual Studio, ponieważ będzie on służył jako środowisko programistyczne.

2.Aspose.Slides dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).

3. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna, aby móc uczestniczyć w tym samouczku.

## Importuj przestrzenie nazw

W pierwszym kroku zaimportujemy niezbędne przestrzenie nazw do pracy z Aspose.Slides:

### Krok 1: Importuj przestrzenie nazw

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Zaimportowaliśmy `Aspose.Slides` przestrzeń nazw, która jest podstawową przestrzenią nazw do pracy z prezentacjami i `Aspose.Slides.Export` przestrzeń nazw.

## Ustawienie makro hiperłącza Kliknij

Przejdźmy teraz do głównej części tego samouczka — skonfigurowania makra kliknięcia hiperłącza w prezentacji.

### Krok 2: Zainicjuj prezentację

Najpierw musimy zainicjować nową prezentację.

```csharp
using (Presentation presentation = new Presentation())
{
    // Twój kod będzie tutaj.
}
```

Za pomocą tego polecenia using tworzysz nowy obiekt prezentacji i wykonujesz w nim wszystkie operacje.

### Krok 3: Dodaj Autokształt

Aby ustawić makro hiperłącze kliknięcia, potrzebujesz obiektu, na który użytkownik może kliknąć. W tym przykładzie użyjemy AutoShape jako klikalnego elementu.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Tutaj tworzymy AutoShape z typem „BlankButton” na określonych współrzędnych (20, 20) i o wymiarach 80x30. Możesz dostosować te wartości, aby pasowały do układu prezentacji.

### Krok 4: Ustaw makro hiperłącza Kliknij

Teraz nadchodzi część, w której ustawiasz makro hiperłącza kliknięcia. Musisz podać nazwę makra jako parametr.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

W tym przykładzie ustawiliśmy makro hiperłącza click na „TestMacro”. Gdy użytkownik kliknie AutoShape, uruchomi to makro.

### Krok 5: Pobierz informacje

Możesz również pobrać informacje o ustawionym hiperłączu.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Te wiersze kodu umożliwiają wydrukowanie zewnętrznego adresu URL i typu akcji hiperłącza.

I to wszystko! Udało Ci się ustawić makro hiperłącze kliknięcia w prezentacji przy użyciu Aspose.Slides dla .NET.

## Wniosek

W tym samouczku nauczyliśmy się, jak ustawić makro hiperłącze kliknięcia w prezentacji za pomocą Aspose.Slides dla .NET. Może to być cenna funkcja do tworzenia interaktywnych i dynamicznych prezentacji, które angażują odbiorców. Dzięki Aspose.Slides dla .NET masz do dyspozycji potężne narzędzie, które pozwoli Ci przenieść rozwój prezentacji na wyższy poziom.

Teraz nadszedł czas, abyś poeksperymentował i stworzył fascynujące prezentacje z niestandardowymi hiperlinkami makro. Możesz swobodnie eksplorować [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/) aby uzyskać bardziej szczegółowe informacje i możliwości.

## FAQ (najczęściej zadawane pytania)

### Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Aspose.Slides jest przeznaczony przede wszystkim dla platformy .NET, ale Aspose oferuje podobne biblioteki dla innych języków programowania, np. Java.

### Czy Aspose.Slides dla .NET jest darmową biblioteką?
Aspose.Slides dla .NET to komercyjna biblioteka z dostępną bezpłatną wersją próbną. Można ją pobrać z [Tutaj](https://releases.aspose.com/).

### Czy istnieją jakieś ograniczenia w korzystaniu z makr w prezentacjach utworzonych za pomocą Aspose.Slides dla platformy .NET?
Aspose.Slides for .NET umożliwia pracę z makrami, jednak korzystając z makr w prezentacjach, należy pamiętać o kwestiach bezpieczeństwa i zgodności.

### Czy mogę dostosować wygląd Autokształtu używanego w hiperłączu?
Tak, możesz dostosować wygląd Autokształtu, zmieniając jego właściwości, takie jak rozmiar, kolor i czcionkę.

### Gdzie mogę uzyskać pomoc lub wsparcie dotyczące Aspose.Slides dla .NET?
Jeśli napotkasz problemy lub będziesz mieć pytania, możesz szukać pomocy na forum pomocy technicznej Aspose [Tutaj](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
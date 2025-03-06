---
title: Jak ustawić kliknięcie hiperłącza makra w Aspose.Slides dla .NET
linktitle: Zarządzanie hiperłączami za pomocą makr
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ustawić hiperłącza makr w prezentacjach za pomocą Aspose.Slides dla .NET. Zwiększ interaktywność i zaangażuj odbiorców.
weight: 13
url: /pl/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


W świecie nowoczesnego oprogramowania tworzenie dynamicznych i interaktywnych prezentacji jest kluczowym aspektem. Aspose.Slides dla .NET to potężna biblioteka, która pozwala na płynną pracę z prezentacjami. Niezależnie od tego, czy tworzysz prezentację biznesową, czy edukacyjny pokaz slajdów, możliwość ustawienia kliknięć makro hiperłączy może znacznie poprawić komfort użytkownika. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces ustawiania kliknięcia makro hiperłącza za pomocą Aspose.Slides dla .NET. 

## Warunki wstępne

Zanim przejdziemy do samouczka krok po kroku, musisz spełnić kilka warunków wstępnych:

1.Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio na swoim komputerze, ponieważ będzie to nasze środowisko programistyczne.

 2.Aspose.Slides dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

3.Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna do korzystania z tego samouczka.

## Importuj przestrzenie nazw

W pierwszym kroku zaimportujmy niezbędne przestrzenie nazw do pracy z Aspose.Slides:

### Krok 1: Importuj przestrzenie nazw

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Zaimportowaliśmy`Aspose.Slides` przestrzeń nazw, która jest podstawową przestrzenią nazw do pracy z prezentacjami, oraz`Aspose.Slides.Export` przestrzeń nazw.

## Ustawianie kliknięcia makro hiperłącza

Przejdźmy teraz do głównej części tego poradnika - ustawienia kliknięcia makro hiperłącza w prezentacji.

### Krok 2: Zainicjuj prezentację

Najpierw musimy zainicjować nową prezentację.

```csharp
using (Presentation presentation = new Presentation())
{
    // Twój kod trafi tutaj.
}
```

ramach tej instrukcji using tworzysz nowy obiekt prezentacji i wykonujesz w nim wszystkie operacje.

### Krok 3: Dodaj autokształt

Aby ustawić kliknięcie makro hiperłącza, potrzebny będzie obiekt, na który użytkownik będzie mógł kliknąć. W tym przykładzie użyjemy Autokształtu jako elementu klikalnego.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Tutaj tworzymy Autokształt z typem „BlankButton” o określonych współrzędnych (20, 20) i wymiarach 80x30. Możesz dostosować te wartości, aby dopasować je do układu prezentacji.

### Krok 4: Ustaw kliknięcie hiperłącza makro

Teraz następuje część, w której ustawiasz kliknięcie hiperłącza makra. Musisz podać nazwę makra jako parametr.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

W tym przykładzie ustawiliśmy kliknięcie hiperłącza makra na „TestMacro”. Kiedy użytkownik kliknie Autokształt, uruchomi to makro.

### Krok 5: Odzyskaj informacje

Możesz także pobrać informacje o ustawionym hiperłączu.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Te linie kodu umożliwiają wydrukowanie zewnętrznego adresu URL i typu działania hiperłącza.

I to wszystko! Pomyślnie ustawiłeś kliknięcie makro hiperłącza w swojej prezentacji przy użyciu Aspose.Slides dla .NET.

## Wniosek

W tym samouczku nauczyliśmy się, jak ustawić kliknięcie makro hiperłącza w prezentacji za pomocą Aspose.Slides dla .NET. Może to być cenna funkcja przy tworzeniu interaktywnych i dynamicznych prezentacji, które angażują odbiorców. Dzięki Aspose.Slides dla .NET masz do dyspozycji potężne narzędzie, które przeniesie Twoje tworzenie prezentacji na wyższy poziom.

 Teraz nadszedł czas, abyś poeksperymentował i stworzył urzekające prezentacje za pomocą niestandardowych hiperłączy do makr. Zapraszamy do eksploracji[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/) aby uzyskać bardziej szczegółowe informacje i możliwości.

## Często zadawane pytania (często zadawane pytania)

### Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Aspose.Slides jest przeznaczony głównie dla .NET, ale Aspose oferuje podobne biblioteki dla innych języków programowania, takich jak Java.

### Czy Aspose.Slides dla .NET jest bezpłatną biblioteką?
Aspose.Slides dla .NET to biblioteka komercyjna z dostępną bezpłatną wersją próbną. Można go pobrać z[Tutaj](https://releases.aspose.com/).

### Czy są jakieś ograniczenia w używaniu makr w prezentacjach tworzonych za pomocą Aspose.Slides dla .NET?
Aspose.Slides dla .NET umożliwia pracę z makrami, ale podczas używania makr w prezentacjach należy pamiętać o kwestiach bezpieczeństwa i kompatybilności.

### Czy mogę dostosować wygląd Autokształtu używanego w hiperłączu?
Tak, możesz dostosować wygląd Autokształtu, dostosowując jego właściwości, takie jak rozmiar, kolor i czcionka.

### Gdzie mogę uzyskać pomoc lub wsparcie dla Aspose.Slides dla .NET?
 Jeśli napotkasz problemy lub masz pytania, możesz szukać pomocy na forum pomocy technicznej Aspose[Tutaj](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

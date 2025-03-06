---
title: Dodawanie hiperłączy do slajdów w .NET przy użyciu Aspose.Slides
linktitle: Dodaj hiperłącze do slajdu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodawać hiperłącza do slajdów programu PowerPoint za pomocą Aspose.Slides dla .NET. Wzbogać swoje prezentacje elementami interaktywnymi.
weight: 12
url: /pl/net/hyperlink-manipulation/add-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


W świecie prezentacji cyfrowych interaktywność jest kluczowa. Dodanie hiperłączy do slajdów może sprawić, że prezentacja będzie bardziej wciągająca i pouczająca. Aspose.Slides dla .NET to potężna biblioteka, która umożliwia programowe tworzenie, modyfikowanie i manipulowanie prezentacjami programu PowerPoint. W tym samouczku pokażemy, jak dodać hiperłącza do slajdów za pomocą Aspose.Slides dla .NET. 

## Warunki wstępne

Zanim zajmiemy się dodawaniem hiperłączy do slajdów, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio: Aby móc pisać i wykonywać kod .NET, na komputerze powinien być zainstalowany program Visual Studio.

2. Aspose.Slides dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# będzie korzystna.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. W takim przypadku będziesz potrzebować następujących przestrzeni nazw z biblioteki Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Podzielmy teraz proces dodawania hiperłączy do slajdów na kilka etapów.

## Krok 1: Zainicjuj prezentację

Najpierw utwórz nową prezentację za pomocą Aspose.Slides. Oto jak możesz to zrobić:

```csharp
using (Presentation presentation = new Presentation())
{
    // Twój kod trafia tutaj
}
```

Ten kod inicjuje nową prezentację programu PowerPoint.

## Krok 2: Dodaj ramkę tekstową

Teraz dodajmy ramkę tekstową do slajdu. Ta ramka tekstowa będzie stanowić klikalny element slajdu. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Powyższy kod tworzy prostokątny automatyczny kształt i dodaje ramkę tekstową z tekstem „Aspose: API formatu pliku”.

## Krok 3: Dodaj hiperłącze

Następnie dodajmy hiperłącze do utworzonej ramki tekstowej. Dzięki temu tekst będzie klikalny.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

Na tym etapie ustawiamy adres URL hiperłącza na „https://www.aspose.com/” i udostępniamy podpowiedź zawierającą dodatkowe informacje. Możesz także sformatować wygląd hiperłącza, jak pokazano powyżej.

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację z dodanym hiperłączem.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Ten kod zapisuje prezentację jako „presentation-out.pptx”.

Teraz pomyślnie dodałeś hiperłącze do slajdu za pomocą Aspose.Slides dla .NET.

## Wniosek

W tym samouczku omówiliśmy, jak dodawać hiperłącza do slajdów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla .NET. Wykonując poniższe kroki, możesz uczynić swoje prezentacje bardziej interaktywnymi i wciągającymi, udostępniając cenne linki do dodatkowych zasobów lub informacji.

 Więcej szczegółowych informacji i dokumentacji można znaleźć na stronie[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).

## Często zadawane pytania

### 1. Czy mogę dodać hiperłącza do innych kształtów oprócz ramek tekstowych?

Tak, możesz dodawać hiperłącza do różnych kształtów, takich jak prostokąty, obrazy i inne, używając Aspose.Slides dla .NET.

### 2. Jak usunąć hiperłącze z kształtu na slajdzie programu PowerPoint?

 Hiperłącze można usunąć z kształtu, ustawiając opcję`HyperlinkClick` własność do`null`.

### 3. Czy mogę dynamicznie zmieniać adres URL hiperłącza w moim kodzie?

 Absolutnie! Możesz zaktualizować adres URL hiperłącza w dowolnym miejscu kodu, modyfikując plik`Hyperlink` nieruchomość.

### 4. Jakie inne elementy interaktywne mogę dodać do slajdów programu PowerPoint za pomocą Aspose.Slides?

Aspose.Slides oferuje szeroką gamę funkcji interaktywnych, w tym przyciski akcji, elementy multimedialne i animacje.

### 5. Czy Aspose.Slides jest dostępny dla innych języków programowania?

Tak, Aspose.Slides jest dostępny dla różnych języków programowania, w tym Java i Python.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Konwertuj prezentacje do formatu HTML za pomocą osadzonych czcionek
linktitle: Konwertuj prezentacje do formatu HTML za pomocą osadzonych czcionek
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Konwertuj prezentacje programu PowerPoint do formatu HTML z osadzonymi czcionkami przy użyciu Aspose.Slides dla .NET. Zachowaj oryginalność bezproblemowo.
type: docs
weight: 13
url: /pl/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

W dzisiejszej epoce cyfrowej udostępnianie prezentacji i dokumentów online stało się powszechną praktyką. Jednak często pojawiającym się wyzwaniem jest zapewnienie prawidłowego wyświetlania czcionek podczas konwersji prezentacji do formatu HTML. Ten samouczek krok po kroku poprowadzi Cię przez proces używania Aspose.Slides dla .NET do konwersji prezentacji do formatu HTML z osadzonymi czcionkami, zapewniając, że Twoje dokumenty będą wyglądać dokładnie tak, jak zamierzyłeś.

## Wprowadzenie do Aspose.Slides dla .NET

Zanim zagłębimy się w samouczek, krótko przedstawmy Aspose.Slides dla .NET. Jest to potężna biblioteka, która umożliwia programistom pracę z prezentacjami programu PowerPoint w aplikacjach .NET. Dzięki Aspose.Slides możesz programowo tworzyć, modyfikować i konwertować pliki programu PowerPoint.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Slides dla .NET: Powinieneś mieć zainstalowaną bibliotekę Aspose.Slides w swoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

## Krok 1: Skonfiguruj swój projekt

1. Utwórz nowy projekt lub otwórz istniejący w preferowanym środowisku programistycznym .NET.

2. Dodaj odwołanie do biblioteki Aspose.Slides w swoim projekcie.

3. Zaimportuj niezbędne przestrzenie nazw do swojego kodu:

   ```csharp
   using Aspose.Slides;
   ```

## Krok 2: Załaduj swoją prezentację

 Aby rozpocząć, musisz załadować prezentację, którą chcesz przekonwertować do formatu HTML. Zastępować`"Your Document Directory"` z rzeczywistym katalogiem, w którym znajduje się plik prezentacji.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Twój kod trafia tutaj
}
```

## Krok 3: Wyklucz domyślne czcionki prezentacyjne

W tym kroku możesz określić domyślne czcionki prezentacyjne, które chcesz wykluczyć z osadzania. Może to pomóc zoptymalizować rozmiar wynikowego pliku HTML.

```csharp
string[] fontNameExcludeList = { };
```

## Krok 4: Wybierz kontroler HTML

Teraz masz dwie możliwości osadzania czcionek w kodzie HTML:

### Opcja 1: Osadź wszystkie czcionki

 Aby osadzić wszystkie czcionki użyte w prezentacji, użyj metody`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opcja 2: Połącz wszystkie czcionki

 Aby utworzyć łącze do wszystkich czcionek użytych w prezentacji, użyj opcji`LinkAllFontsHtmlController`. Powinieneś określić katalog, w którym znajdują się czcionki w twoim systemie.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Krok 5: Zdefiniuj opcje HTML

 Stworzyć`HtmlOptions` obiekt i ustaw formater HTML na ten, który wybrałeś w poprzednim kroku.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Użyj embedFontsController do osadzania wszystkich czcionek
};
```

## Krok 6: Zapisz jako HTML

 Na koniec zapisz prezentację jako plik HTML. Możesz wybrać jedno i drugie`SaveFormat.Html` Lub`SaveFormat.Html5` w zależności od Twoich wymagań.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Wniosek

Gratulacje! Pomyślnie przekonwertowałeś swoją prezentację na HTML z osadzonymi czcionkami przy użyciu Aspose.Slides dla .NET. Gwarantuje to prawidłowe wyświetlanie czcionek podczas udostępniania prezentacji online.

Teraz możesz łatwo i pewnie udostępniać pięknie sformatowane prezentacje, wiedząc, że odbiorcy zobaczą je dokładnie tak, jak zamierzałeś.

 Aby uzyskać więcej informacji i szczegółowe odniesienia do API, sprawdź[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).

## Często zadawane pytania

### 1. Czy mogę konwertować prezentacje PowerPoint do formatu HTML przy użyciu Aspose.Slides dla .NET w trybie wsadowym?

Tak, możesz wsadowo konwertować wiele prezentacji do formatu HTML za pomocą Aspose.Slides dla .NET, przeglądając pliki prezentacji i stosując proces konwersji do każdego z nich.

### 2. Czy istnieje sposób na dostosowanie wyglądu wyników HTML?

Z pewnością! Aspose.Slides dla .NET zapewnia różne opcje dostosowywania wyglądu i formatowania danych wyjściowych HTML, takie jak dostosowywanie kolorów, czcionek i układu.

### 3. Czy są jakieś ograniczenia w osadzaniu czcionek w HTML przy użyciu Aspose.Slides dla .NET?

Chociaż Aspose.Slides dla .NET oferuje doskonałe możliwości osadzania czcionek, należy pamiętać, że rozmiar plików HTML może wzrosnąć podczas osadzania czcionek. Pamiętaj, aby zoptymalizować wybór czcionek pod kątem korzystania z Internetu.

### 4. Czy mogę konwertować prezentacje PowerPoint do innych formatów za pomocą Aspose.Slides dla .NET?

Tak, Aspose.Slides dla .NET obsługuje szeroką gamę formatów wyjściowych, w tym PDF, obrazy i inne. Możesz łatwo przekonwertować swoje prezentacje do wybranego formatu.

### 5. Gdzie mogę znaleźć dodatkowe zasoby i wsparcie dla Aspose.Slides dla .NET?

 Dostęp do wielu zasobów, w tym dokumentacji, można uzyskać na stronie[Aspose.Slides dla .NET API odniesienia](https://reference.aspose.com/slides/net/).

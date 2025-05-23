---
"description": "Konwertuj prezentacje PowerPoint do HTML z osadzonymi czcionkami za pomocą Aspose.Slides dla .NET. Zachowaj oryginalność bezproblemowo."
"linktitle": "Konwertuj prezentacje do formatu HTML z osadzonymi czcionkami"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Konwertuj prezentacje do formatu HTML z osadzonymi czcionkami"
"url": "/pl/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj prezentacje do formatu HTML z osadzonymi czcionkami


dzisiejszej erze cyfrowej udostępnianie prezentacji i dokumentów online stało się powszechną praktyką. Jednak często pojawia się wyzwanie, aby upewnić się, że czcionki są poprawnie wyświetlane podczas konwersji prezentacji do HTML. Ten samouczek krok po kroku przeprowadzi Cię przez proces używania Aspose.Slides dla .NET do konwersji prezentacji do HTML z osadzonymi czcionkami, zapewniając, że Twoje dokumenty będą wyglądać dokładnie tak, jak zamierzałeś.

## Wprowadzenie do Aspose.Slides dla .NET

Zanim przejdziemy do samouczka, krótko przedstawimy Aspose.Slides dla .NET. Jest to potężna biblioteka, która pozwala deweloperom pracować z prezentacjami PowerPoint w aplikacjach .NET. Dzięki Aspose.Slides możesz programowo tworzyć, modyfikować i konwertować pliki PowerPoint.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

- Aspose.Slides dla .NET: Biblioteka Aspose.Slides powinna być zainstalowana w projekcie. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).

## Krok 1: Skonfiguruj swój projekt

1. Utwórz nowy projekt lub otwórz istniejący w preferowanym środowisku programistycznym .NET.

2. Dodaj odwołanie do biblioteki Aspose.Slides w swoim projekcie.

3. Zaimportuj niezbędne przestrzenie nazw do swojego kodu:

   ```csharp
   using Aspose.Slides;
   ```

## Krok 2: Załaduj swoją prezentację

Na początek musisz załadować prezentację, którą chcesz przekonwertować na HTML. Zastąp `"Your Document Directory"` z faktycznym katalogiem, w którym znajduje się plik prezentacji.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Twój kod wpisz tutaj
}
```

## Krok 3: Wyklucz domyślne czcionki prezentacyjne

W tym kroku możesz określić dowolne domyślne czcionki prezentacji, które chcesz wykluczyć z osadzania. Może to pomóc zoptymalizować rozmiar wynikowego pliku HTML.

```csharp
string[] fontNameExcludeList = { };
```

## Krok 4: Wybierz kontroler HTML

Teraz masz dwie opcje osadzania czcionek w kodzie HTML:

### Opcja 1: Osadź wszystkie czcionki

Aby osadzić wszystkie czcionki użyte w prezentacji, użyj `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opcja 2: Połącz wszystkie czcionki

Aby połączyć się ze wszystkimi czcionkami użytymi w prezentacji, użyj `LinkAllFontsHtmlController`Powinieneś określić katalog, w którym znajdują się czcionki w twoim systemie.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Krok 5: Zdefiniuj opcje HTML

Utwórz `HtmlOptions` obiekt i ustaw formater HTML na ten, który wybrałeś w poprzednim kroku.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Użyj embedFontsController do osadzania wszystkich czcionek
};
```

## Krok 6: Zapisz jako HTML

Na koniec zapisz prezentację jako plik HTML. Możesz wybrać albo `SaveFLubmat.Html` or `SaveFormat.Html5` w zależności od Twoich wymagań.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Wniosek

Gratulacje! Udało Ci się przekonwertować prezentację do HTML z osadzonymi czcionkami przy użyciu Aspose.Slides dla .NET. Dzięki temu czcionki będą wyświetlane poprawnie podczas udostępniania prezentacji online.

Teraz możesz łatwo udostępniać pięknie sformatowane prezentacje, mając pewność, że odbiorcy zobaczą je dokładnie tak, jak zamierzałeś.

Aby uzyskać więcej informacji i szczegółowe odniesienia do interfejsu API, zapoznaj się z [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/).

## Często zadawane pytania

### 1. Czy mogę konwertować prezentacje PowerPoint do formatu HTML za pomocą Aspose.Slides dla .NET w trybie wsadowym?

Tak, możesz dokonać konwersji wielu prezentacji do formatu HTML za pomocą Aspose.Slides dla .NET, przechodząc przez pliki prezentacji i stosując proces konwersji do każdego z nich.

### 2. Czy istnieje sposób na dostosowanie wyglądu wyjścia HTML?

Oczywiście! Aspose.Slides dla .NET oferuje różne opcje dostosowywania wyglądu i formatowania wyjścia HTML, takie jak dostosowywanie kolorów, czcionek i układu.

### 3. Czy istnieją jakieś ograniczenia w osadzaniu czcionek w kodzie HTML przy użyciu Aspose.Slides dla platformy .NET?

Chociaż Aspose.Slides dla .NET oferuje doskonałe możliwości osadzania czcionek, pamiętaj, że rozmiar plików HTML może się zwiększyć podczas osadzania czcionek. Upewnij się, że optymalizujesz wybór czcionek pod kątem wykorzystania w sieci.

### 4. Czy mogę konwertować prezentacje PowerPoint do innych formatów za pomocą Aspose.Slides dla .NET?

Tak, Aspose.Slides dla .NET obsługuje szeroki zakres formatów wyjściowych, w tym PDF, obrazy i inne. Możesz łatwo przekonwertować swoje prezentacje do wybranego formatu.

### 5. Gdzie mogę znaleźć dodatkowe zasoby i pomoc dotyczącą Aspose.Slides dla platformy .NET?

Na stronie można uzyskać dostęp do wielu zasobów, w tym dokumentacji. [Aspose.Slides dla .NET API Reference](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
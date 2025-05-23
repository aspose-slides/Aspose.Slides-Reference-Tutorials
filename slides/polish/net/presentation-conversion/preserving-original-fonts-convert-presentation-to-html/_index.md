---
"description": "Dowiedz się, jak zachować oryginalne czcionki podczas konwersji prezentacji do HTML za pomocą Aspose.Slides dla .NET. Zapewnij spójność czcionek i efekt wizualny bez wysiłku."
"linktitle": "Zachowywanie oryginalnych czcionek - konwersja prezentacji do HTML"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Zachowywanie oryginalnych czcionek - konwersja prezentacji do HTML"
"url": "/pl/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zachowywanie oryginalnych czcionek - konwersja prezentacji do HTML


W tym kompleksowym przewodniku przeprowadzimy Cię przez proces zachowywania oryginalnych czcionek podczas konwersji prezentacji do HTML przy użyciu Aspose.Slides dla .NET. Dostarczymy Ci niezbędny kod źródłowy C# i wyjaśnimy każdy krok szczegółowo. Pod koniec tego samouczka będziesz w stanie upewnić się, że czcionki w przekonwertowanym dokumencie HTML pozostaną wierne oryginalnej prezentacji.

## 1. Wprowadzenie

Podczas konwersji prezentacji PowerPoint do HTML, kluczowe jest zachowanie oryginalnych czcionek, aby zapewnić wizualną spójność treści. Aspose.Slides dla .NET zapewnia potężne rozwiązanie, aby to osiągnąć. W tym samouczku przeprowadzimy Cię przez kroki niezbędne do zachowania oryginalnych czcionek podczas procesu konwersji.

## 2. Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Na Twoim komputerze zainstalowano program Visual Studio.
- Biblioteka Aspose.Slides dla .NET została dodana do projektu.

## 3. Konfigurowanie projektu

Aby rozpocząć, utwórz nowy projekt w programie Visual Studio i dodaj bibliotekę Aspose.Slides for .NET jako odniesienie.

## 4. Ładowanie prezentacji

Użyj poniższego kodu, aby załadować prezentację PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Twój kod tutaj
}
```

Zastępować `"Your Document Directory"` ze ścieżką do pliku prezentacji.

## 5. Wykluczanie domyślnych czcionek

Aby wykluczyć domyślne czcionki, takie jak Calibri i Arial, użyj następującego kodu:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Możesz dostosować tę listę według swoich potrzeb.

## 6. Osadzanie wszystkich czcionek

Następnie osadzimy wszystkie czcionki w dokumencie HTML. Dzięki temu oryginalne czcionki zostaną zachowane. Użyj następującego kodu:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Zapisywanie jako HTML

Teraz zapisz prezentację jako dokument HTML z osadzonymi czcionkami:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Zastępować `"output.html"` z wybraną nazwą pliku wyjściowego.

## 8. Wnioski

W tym samouczku pokazaliśmy, jak zachować oryginalne czcionki podczas konwersji prezentacji PowerPoint do HTML przy użyciu Aspose.Slides dla .NET. Postępując zgodnie z tymi krokami, możesz mieć pewność, że przekonwertowany dokument HTML zachowuje integralność wizualną oryginalnej prezentacji.

## 9. Często zadawane pytania

### P1: Czy mogę dostosować listę wykluczonych czcionek?

Tak, możesz. Modyfikuj `fontNameExcludeList` tablicę umożliwiającą uwzględnienie lub wykluczenie konkretnych czcionek zgodnie z Twoimi wymaganiami.

### P2: Co zrobić, jeśli nie chcę osadzać wszystkich czcionek?

Jeśli chcesz osadzić tylko określone czcionki, możesz odpowiednio zmodyfikować kod. Zapoznaj się z dokumentacją Aspose.Slides for .NET, aby uzyskać więcej szczegółów.

### P3: Czy istnieją jakieś wymagania licencyjne dotyczące korzystania z Aspose.Slides dla platformy .NET?

Tak, możesz potrzebować ważnej licencji, aby używać Aspose.Slides dla .NET w swoich projektach. Zapoznaj się z informacjami o licencjonowaniu na stronie internetowej Aspose.

### P4: Czy mogę konwertować inne formaty plików do formatu HTML za pomocą Aspose.Slides dla .NET?

Aspose.Slides for .NET koncentruje się głównie na prezentacjach PowerPoint. Aby przekonwertować inne formaty plików na HTML, możesz potrzebować innych produktów Aspose dostosowanych do tych formatów.

### P5: Gdzie mogę uzyskać dostęp do dodatkowych zasobów i wsparcia?

Więcej dokumentacji, samouczków i pomocy znajdziesz na stronie internetowej Aspose. Odwiedź [Dokumentacja Aspose.Slides dla .NET](https://reference.aspose.com/slides/net/) Aby uzyskać szczegółowe informacje.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
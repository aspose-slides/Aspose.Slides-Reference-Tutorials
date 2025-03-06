---
title: Zachowywanie oryginalnych czcionek — Konwertuj prezentację do formatu HTML
linktitle: Zachowywanie oryginalnych czcionek — Konwertuj prezentację do formatu HTML
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak zachować oryginalne czcionki podczas konwersji prezentacji do formatu HTML za pomocą Aspose.Slides dla .NET. Bez wysiłku zapewnij spójność czcionki i efekt wizualny.
weight: 14
url: /pl/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


W tym obszernym przewodniku przeprowadzimy Cię przez proces zachowywania oryginalnych czcionek podczas konwersji prezentacji do formatu HTML przy użyciu Aspose.Slides dla .NET. Dostarczymy Ci niezbędny kod źródłowy C# i szczegółowo wyjaśnimy każdy krok. Pod koniec tego samouczka będziesz mieć pewność, że czcionki w przekonwertowanym dokumencie HTML pozostaną wierne oryginalnej prezentacji.

## 1. Wstęp

Podczas konwertowania prezentacji programu PowerPoint do formatu HTML niezwykle ważne jest zachowanie oryginalnych czcionek, aby zapewnić wizualną spójność treści. Aspose.Slides dla .NET zapewnia potężne rozwiązanie umożliwiające osiągnięcie tego celu. W tym samouczku przeprowadzimy Cię przez kroki niezbędne do zachowania oryginalnych czcionek podczas procesu konwersji.

## 2. Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Program Visual Studio zainstalowany na Twoim komputerze.
- Do Twojego projektu dodano bibliotekę Aspose.Slides for .NET.

## 3. Konfigurowanie projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj bibliotekę Aspose.Slides for .NET jako odniesienie.

## 4. Ładowanie prezentacji

Użyj poniższego kodu, aby załadować prezentację programu PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Twój kod tutaj
}
```

 Zastępować`"Your Document Directory"` ze ścieżką do pliku prezentacji.

## 5. Z wyłączeniem czcionek domyślnych

Aby wykluczyć czcionki domyślne, takie jak Calibri i Arial, użyj następującego kodu:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Możesz dostosować tę listę według potrzeb.

## 6. Osadzanie wszystkich czcionek

Następnie osadzimy wszystkie czcionki w dokumencie HTML. Dzięki temu zachowane zostaną oryginalne czcionki. Użyj następującego kodu:

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

 Zastępować`"output.html"` z żądaną nazwą pliku wyjściowego.

## 8. Wniosek

W tym samouczku pokazaliśmy, jak zachować oryginalne czcionki podczas konwertowania prezentacji programu PowerPoint do formatu HTML przy użyciu Aspose.Slides dla .NET. Wykonując poniższe kroki, możesz mieć pewność, że przekonwertowany dokument HTML zachowuje wizualną integralność oryginalnej prezentacji.

## 9. Często zadawane pytania

### P1: Czy mogę dostosować listę wykluczonych czcionek?

 Tak, możesz. Zmodyfikuj`fontNameExcludeList`array, aby uwzględnić lub wykluczyć określone czcionki zgodnie z Twoimi wymaganiami.

### P2: Co się stanie, jeśli nie chcę osadzać wszystkich czcionek?

Jeśli chcesz osadzić tylko określone czcionki, możesz odpowiednio zmodyfikować kod. Więcej szczegółów znajdziesz w dokumentacji Aspose.Slides for .NET.

### P3: Czy istnieją jakieś wymagania licencyjne dotyczące korzystania z Aspose.Slides dla .NET?

Tak, możesz potrzebować ważnej licencji, aby używać Aspose.Slides for .NET w swoich projektach. Informacje licencyjne można znaleźć na stronie internetowej Aspose.

### P4: Czy mogę przekonwertować inne formaty plików na HTML za pomocą Aspose.Slides dla .NET?

Aspose.Slides dla .NET skupia się przede wszystkim na prezentacjach programu PowerPoint. Aby przekonwertować inne formaty plików na HTML, może być konieczne zapoznanie się z innymi produktami Aspose dostosowanymi do tych formatów.

### P5: Gdzie mogę uzyskać dostęp do dodatkowych zasobów i wsparcia?

 Więcej dokumentacji, samouczków i wsparcia można znaleźć na stronie internetowej Aspose. Odwiedzać[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

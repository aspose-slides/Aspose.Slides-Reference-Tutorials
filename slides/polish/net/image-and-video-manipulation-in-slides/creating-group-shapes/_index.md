---
"description": "Dowiedz się, jak tworzyć kształty grupowe w programie PowerPoint za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby tworzyć atrakcyjne wizualnie prezentacje."
"linktitle": "Tworzenie kształtów grupowych w slajdach prezentacji za pomocą Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Aspose.Slides — tworzenie kształtów grupowych w .NET"
"url": "/pl/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — tworzenie kształtów grupowych w .NET

## Wstęp
Jeśli chcesz poprawić atrakcyjność wizualną slajdów prezentacji i wydajniej organizować zawartość, włączenie kształtów grupowych jest potężnym rozwiązaniem. Aspose.Slides dla .NET zapewnia bezproblemowy sposób tworzenia i manipulowania kształtami grupowymi w prezentacjach PowerPoint. W tym samouczku przeprowadzimy Cię przez proces tworzenia kształtów grupowych za pomocą Aspose.Slides, dzieląc go na łatwe do wykonania kroki.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące rzeczy:
- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides. Możesz ją pobrać ze strony [strona internetowa](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj środowisko robocze przy użyciu środowiska IDE zgodnego z platformą .NET, np. Visual Studio.
- Podstawowa wiedza o języku C#: Zapoznaj się z podstawami języka programowania C#.
## Importuj przestrzenie nazw
W swoim projekcie C# zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Utwórz klasę prezentacji

Utwórz instancję `Presentation` klasę i określ katalog, w którym przechowywane są Twoje dokumenty:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Kontynuuj następujące kroki w tym bloku
}
```

## Krok 2: Dostęp do pierwszego slajdu

Pobierz pierwszy slajd z prezentacji:

```csharp
ISlide sld = pres.Slides[0];
```

## Krok 3: Dostęp do kolekcji kształtów

Uzyskaj dostęp do kolekcji kształtów na slajdzie:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Krok 4: Dodawanie kształtu grupy

Dodaj kształt grupy do slajdu:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Krok 5: Dodawanie kształtów wewnątrz kształtu grupy

Wypełnij kształt grupy pojedynczymi kształtami:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Krok 6: Dodawanie ramki kształtu grupy

Zdefiniuj ramkę dla całego kształtu grupy:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Krok 7: Zapisz prezentację

Zapisz zmodyfikowaną prezentację w określonym katalogu:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Powtórz te kroki w swojej aplikacji C#, aby pomyślnie utworzyć kształty grupowe w slajdach prezentacji za pomocą Aspose.Slides.

## Wniosek
W tym samouczku zbadaliśmy proces tworzenia kształtów grupowych za pomocą Aspose.Slides dla .NET. Wykonując te kroki, możesz poprawić atrakcyjność wizualną i organizację swoich prezentacji PowerPoint.
## Często zadawane pytania
### Czy Aspose.Slides jest kompatybilny z najnowszą wersją .NET?
Tak, Aspose.Slides jest regularnie aktualizowany, aby obsługiwać najnowsze wersje .NET. Sprawdź [dokumentacja](https://reference.aspose.com/slides/net/) Aby uzyskać szczegóły dotyczące zgodności.
### Czy mogę wypróbować Aspose.Slides przed zakupem?
Oczywiście! Możesz pobrać bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Slides?
Odwiedź Aspose.Slides [forum](https://forum.aspose.com/c/slides/11) w celu uzyskania wsparcia społeczności i dyskusji.
### Jak uzyskać tymczasową licencję na Aspose.Slides?
Możesz uzyskać tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę nabyć pełną licencję na Aspose.Slides?
Możesz kupić licencję od [strona zakupu](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
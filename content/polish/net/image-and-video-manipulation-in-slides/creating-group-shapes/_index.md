---
title: Aspose.Slides - Tworzenie kształtów grupowych w .NET
linktitle: Tworzenie kształtów grupowych na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak tworzyć kształty grupowe w programie PowerPoint za pomocą Aspose.Slides dla platformy .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać atrakcyjne wizualnie prezentacje.
type: docs
weight: 11
url: /pl/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Wstęp
Jeśli chcesz poprawić atrakcyjność wizualną slajdów prezentacji i efektywniej organizować zawartość, włączenie kształtów grupowych jest potężnym rozwiązaniem. Aspose.Slides dla .NET zapewnia płynny sposób tworzenia i manipulowania kształtami grup w prezentacjach programu PowerPoint. W tym samouczku omówimy proces tworzenia kształtów grupowych za pomocą Aspose.Slides, dzieląc go na łatwe do wykonania kroki.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides. Można go pobrać z[strona internetowa](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: Skonfiguruj środowisko pracy z IDE zgodnym z platformą .NET, takim jak Visual Studio.
- Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.
## Importuj przestrzenie nazw
W projekcie C# rozpocznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Utwórz instancję klasy prezentacji

 Utwórz instancję`Presentation` class i określ katalog, w którym przechowywane są dokumenty:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Kontynuuj następujące kroki w tym bloku
}
```

## Krok 2: Uzyskaj dostęp do pierwszego slajdu

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

## Krok 5: Dodawanie kształtów do kształtu grupy

Wypełnij kształt grupy indywidualnymi kształtami:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Krok 6: Dodawanie ramki kształtu grupy

Zdefiniuj ramkę dla kształtu całej grupy:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Krok 7: Zapisz prezentację

Zapisz zmodyfikowaną prezentację w określonym katalogu:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Powtórz te kroki w aplikacji C#, aby pomyślnie utworzyć kształty grupowe na slajdach prezentacji przy użyciu Aspose.Slides.

## Wniosek
W tym samouczku omówiliśmy proces tworzenia kształtów grup za pomocą Aspose.Slides dla .NET. Wykonując poniższe kroki, możesz poprawić atrakcyjność wizualną i organizację prezentacji programu PowerPoint.
## Często Zadawane Pytania
### Czy Aspose.Slides jest kompatybilny z najnowszą wersją .NET?
 Tak, Aspose.Slides jest regularnie aktualizowany, aby obsługiwał najnowsze wersje .NET. Sprawdź[dokumentacja](https://reference.aspose.com/slides/net/) aby poznać szczegóły dotyczące kompatybilności.
### Czy mogę wypróbować Aspose.Slides przed zakupem?
 Absolutnie! Możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Slides?
 Odwiedź Aspose.Slides[forum](https://forum.aspose.com/c/slides/11) za wsparcie społeczności i dyskusje.
### Jak uzyskać tymczasową licencję na Aspose.Slides?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić pełną licencję na Aspose.Slides?
 Licencję możesz kupić na stronie[strona zakupu](https://purchase.aspose.com/buy).

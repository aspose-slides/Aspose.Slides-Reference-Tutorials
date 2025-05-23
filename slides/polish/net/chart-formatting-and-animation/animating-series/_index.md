---
"description": "Dowiedz się, jak animować serie wykresów za pomocą Aspose.Slides dla .NET. Zaangażuj odbiorców za pomocą dynamicznych prezentacji. Zacznij teraz!"
"linktitle": "Animowanie serii na wykresie"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Animuj serie wykresów za pomocą Aspose.Slides dla .NET"
"url": "/pl/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animuj serie wykresów za pomocą Aspose.Slides dla .NET


Chcesz dodać trochę blasku swoim prezentacjom za pomocą animowanych wykresów? Aspose.Slides dla .NET jest tutaj, aby ożywić Twoje wykresy. W tym przewodniku krok po kroku pokażemy Ci, jak animować serie na wykresie za pomocą Aspose.Slides dla .NET. Ale zanim przejdziemy do działania, omówmy wymagania wstępne.

## Wymagania wstępne

Aby pomyślnie animować serie na wykresie przy użyciu Aspose.Slides dla platformy .NET, potrzebne będą następujące elementy:

### 1. Biblioteka Aspose.Slides dla .NET

Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for .NET. Jeśli jeszcze jej nie masz, możesz ją pobrać ze strony [Aspose.Slides dla witryny .NET](https://releases.aspose.com/slides/net/).

### 2. Istniejąca prezentacja z wykresem

Przygotuj prezentację PowerPoint (PPTX) zawierającą istniejący wykres, który chcesz animować.

Teraz, gdy omówiliśmy już wszystkie wymagania wstępne, możemy podzielić proces na kilka kroków, aby utworzyć animację serii wykresów.


## Krok 1: Importuj niezbędne przestrzenie nazw

Aby pracować z Aspose.Slides dla platformy .NET, musisz zaimportować wymagane przestrzenie nazw w kodzie C#:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Krok 2: Załaduj istniejącą prezentację

W tym kroku załaduj istniejącą prezentację programu PowerPoint (PPTX) zawierającą wykres, który chcesz animować.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "Your Document Directory";

// Utwórz klasę prezentacji reprezentującą plik prezentacji 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Twój kod wpisz tutaj
}
```

## Krok 3: Uzyskaj odniesienie do obiektu wykresu

Aby móc pracować z wykresem w prezentacji, musisz uzyskać odwołanie do obiektu wykresu:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Krok 4: Animuj serię

Teraz czas dodać efekty animacji do serii wykresów. Dodamy efekt zanikania do całego wykresu i sprawimy, że każda seria pojawi się jedna po drugiej.

```csharp
// Animuj wykres
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Dodaj animację do każdej serii
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Krok 5: Zapisz zmodyfikowaną prezentację

Po dodaniu efektów animacji do wykresu zapisz zmodyfikowaną prezentację na dysku.

```csharp
// Zapisz zmodyfikowaną prezentację
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się stworzyć animowaną serię na wykresie przy użyciu Aspose.Slides dla .NET.

## Wniosek

W tym samouczku przeprowadziliśmy Cię przez proces animowania serii na wykresie przy użyciu Aspose.Slides dla .NET. Dzięki tej potężnej bibliotece możesz tworzyć angażujące i dynamiczne prezentacje, które zachwycą Twoją publiczność.

Jeśli masz jakiekolwiek pytania lub potrzebujesz dalszej pomocy, nie wahaj się skontaktować ze społecznością Aspose.Slides na ich stronie internetowej. [forum wsparcia](https://forum.aspose.com/).

## Często zadawane pytania

### Czy za pomocą Aspose.Slides dla .NET mogę animować inne elementy wykresu oprócz serii?
Tak, możesz animować różne elementy wykresu, w tym punkty danych, osie i legendy, korzystając z Aspose.Slides dla .NET.

### Czy Aspose.Slides dla .NET jest zgodny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides dla platformy .NET obsługuje różne wersje programu PowerPoint, w tym PowerPoint 2007 i nowsze, zapewniając zgodność z większością najnowszych wersji.

### Czy mogę dostosować efekty animacji dla każdej serii wykresów osobno?
Tak, możesz dostosować efekty animacji dla każdej serii wykresów, aby tworzyć wyjątkowe i angażujące prezentacje.

### Czy jest dostępna wersja próbna Aspose.Slides dla .NET?
Tak, możesz wypróbować bibliotekę za darmo, korzystając z wersji próbnej dostępnej na stronie [Aspose.Slides dla witryny .NET](https://releases.aspose.com/).

### Gdzie mogę nabyć licencję na Aspose.Slides dla .NET?
Licencję na Aspose.Slides dla .NET można nabyć na stronie zakupu [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
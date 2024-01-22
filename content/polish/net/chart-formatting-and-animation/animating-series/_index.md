---
title: Animuj serię wykresów za pomocą Aspose.Slides dla platformy .NET
linktitle: Animacja serii na wykresie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak animować serie wykresów za pomocą Aspose.Slides dla .NET. Zaangażuj odbiorców dynamicznymi prezentacjami. Zacznij teraz!
type: docs
weight: 12
url: /pl/net/chart-formatting-and-animation/animating-series/
---

Czy chcesz urozmaicić swoje prezentacje za pomocą animowanych wykresów? Aspose.Slides dla .NET jest tutaj, aby ożywić Twoje wykresy. W tym przewodniku krok po kroku pokażemy, jak animować serie na wykresie za pomocą Aspose.Slides dla .NET. Zanim jednak przejdziemy do akcji, omówmy warunki wstępne.

## Warunki wstępne

Aby pomyślnie animować serie na wykresie za pomocą Aspose.Slides dla .NET, będziesz potrzebować:

### 1. Aspose.Slides dla biblioteki .NET

 Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for .NET. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go ze strony[Aspose.Slides dla witryny .NET](https://releases.aspose.com/slides/net/).

### 2. Istniejąca prezentacja z wykresem

Przygotuj prezentację programu PowerPoint (PPTX) z istniejącym wykresem, który chcesz animować.

Skoro już omówiliśmy wymagania wstępne, podzielmy proces na serię kroków, aby animować serię wykresów.


## Krok 1: Zaimportuj niezbędne przestrzenie nazw

Aby móc pracować z Aspose.Slides dla .NET, będziesz musiał zaimportować wymagane przestrzenie nazw do swojego kodu C#:

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

//Klasa prezentacji instancji, która reprezentuje plik prezentacji
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Twój kod trafia tutaj
}
```

## Krok 3: Uzyskaj odniesienie do obiektu wykresu

Aby pracować z wykresem w prezentacji, musisz uzyskać odniesienie do obiektu wykresu:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Krok 4: Animuj serię

Teraz czas dodać efekty animacji do serii wykresów. Dodamy efekt zanikania do całego wykresu i sprawimy, że każda seria będzie pojawiać się jedna po drugiej.

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

Otóż to! Udało Ci się animować seriale na wykresie przy użyciu Aspose.Slides dla .NET.

## Wniosek

W tym samouczku przeprowadziliśmy Cię przez proces animowania serii na wykresie przy użyciu Aspose.Slides dla .NET. Dzięki tej potężnej bibliotece możesz tworzyć wciągające i dynamiczne prezentacje, które przykują uwagę odbiorców.

 Jeśli masz jakieś pytania lub potrzebujesz dalszej pomocy, nie wahaj się skontaktować ze społecznością Aspose.Slides na jej stronie[forum wsparcia](https://forum.aspose.com/).

## Często zadawane pytania

### Czy mogę animować inne elementy wykresu oprócz serii przy użyciu Aspose.Slides dla .NET?
Tak, możesz animować różne elementy wykresu, w tym punkty danych, osie i legendy, używając Aspose.Slides dla .NET.

### Czy Aspose.Slides for .NET jest kompatybilny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides dla .NET obsługuje różne wersje programu PowerPoint, w tym PowerPoint 2007 i nowsze, zapewniając kompatybilność z najnowszymi wersjami.

### Czy mogę indywidualnie dostosować efekty animacji dla każdej serii wykresów?
Tak, możesz dostosować efekty animacji dla każdej serii wykresów, aby stworzyć unikalne i wciągające prezentacje.

### Czy dostępna jest wersja próbna Aspose.Slides dla .NET?
 Tak, możesz wypróbować bibliotekę w ramach bezpłatnego okresu próbnego w witrynie[Aspose.Slides dla witryny .NET](https://releases.aspose.com/).

### Gdzie mogę kupić licencję na Aspose.Slides dla .NET?
 Licencję na Aspose.Slides dla .NET możesz nabyć na stronie zakupu[Tutaj](https://purchase.aspose.com/buy).
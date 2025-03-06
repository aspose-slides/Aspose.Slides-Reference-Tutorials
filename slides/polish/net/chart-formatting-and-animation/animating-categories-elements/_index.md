---
title: Potężne animacje wykresów z Aspose.Slides dla .NET
linktitle: Animowanie elementów kategorii na wykresie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naucz się animować elementy wykresów w programie PowerPoint za pomocą Aspose.Slides dla .NET. Przewodnik krok po kroku dotyczący oszałamiających prezentacji.
weight: 11
url: /pl/net/chart-formatting-and-animation/animating-categories-elements/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


świecie prezentacji animacje mogą ożywić Twoje treści, szczególnie w przypadku wykresów. Aspose.Slides dla .NET oferuje szereg zaawansowanych funkcji, które pozwalają tworzyć wspaniałe animacje dla wykresów. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces animowania elementów kategorii na wykresie za pomocą Aspose.Slides dla .NET.

## Warunki wstępne

Zanim przejdziemy do samouczka, powinieneś spełnić następujące wymagania wstępne:

-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowany Aspose.Slides dla .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go z[Tutaj](https://releases.aspose.com/slides/net/).

- Istniejąca prezentacja: Powinieneś mieć prezentację programu PowerPoint z wykresem, który chcesz animować. Jeśli go nie masz, utwórz przykładową prezentację z wykresem do celów testowych.

Teraz, gdy już wszystko masz na swoim miejscu, zacznijmy animować te elementy wykresu!

## Importuj przestrzenie nazw

Pierwszym krokiem jest zaimportowanie niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides. Dodaj do swojego projektu następujące przestrzenie nazw:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Krok 1: Załaduj prezentację

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Uzyskaj odniesienie do obiektu wykresu
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

Na tym etapie ładujemy istniejącą prezentację PowerPoint zawierającą wykres, który chcesz animować. Następnie uzyskujemy dostęp do obiektu wykresu na pierwszym slajdzie.

## Krok 2: Animuj elementy kategorii

```csharp
// Animuj elementy kategorii
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Ten krok dodaje efekt animacji „Zanikanie” do całego wykresu, dzięki czemu pojawia się on po poprzedniej animacji.

Następnie dodamy animację do poszczególnych elementów w ramach każdej kategorii wykresu. To tutaj dzieje się prawdziwa magia.

## Krok 3: Animuj poszczególne elementy

Animację poszczególnych elementów w każdej kategorii podzielimy na następujące kroki:

### Krok 3.1: Animowanie elementów w kategorii 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Tutaj animujemy poszczególne elementy w ramach kategorii 0 wykresu, sprawiając, że pojawiają się one jeden po drugim. W tej animacji używany jest efekt „Wygląd”.

### Krok 3.2: Animowanie elementów w kategorii 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Proces powtarza się dla kategorii 1, animując jej poszczególne elementy za pomocą efektu „Wygląd”.

### Krok 3.3: Animowanie elementów w kategorii 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Ten sam proces jest kontynuowany w przypadku kategorii 2, indywidualnie animując jej elementy.

## Krok 4: Zapisz prezentację

```csharp
// Zapisz plik prezentacji na dysku
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

W ostatnim kroku zapisujemy prezentację z nowo dodanymi animacjami. Teraz elementy wykresu będą pięknie animowane po uruchomieniu prezentacji.

## Wniosek

Animowanie elementów kategorii na wykresie może poprawić atrakcyjność wizualną prezentacji. Dzięki Aspose.Slides dla .NET proces ten staje się prosty i wydajny. Nauczyłeś się importować przestrzenie nazw, ładować prezentację i dodawać animacje zarówno do całego wykresu, jak i jego poszczególnych elementów. Bądź kreatywny i spraw, aby Twoje prezentacje były bardziej wciągające dzięki Aspose.Slides dla .NET.

## Często zadawane pytania

### 1. Jak mogę pobrać Aspose.Slides dla .NET?
 Możesz pobrać Aspose.Slides dla .NET z[ten link](https://releases.aspose.com/slides/net/).

### 2. Czy potrzebuję doświadczenia w kodowaniu, aby korzystać z Aspose.Slides dla .NET?
Chociaż doświadczenie w kodowaniu jest pomocne, Aspose.Slides dla .NET zapewnia obszerną dokumentację i przykłady, które mogą pomóc użytkownikom na wszystkich poziomach umiejętności.

### 3. Czy mogę używać Aspose.Slides for .NET z dowolną wersją programu PowerPoint?
Aspose.Slides dla .NET jest przeznaczony do współpracy z różnymi wersjami programu PowerPoint, zapewniając kompatybilność.

### 4. Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla .NET?
 Możesz uzyskać tymczasową licencję na Aspose.Slides dla .NET[Tutaj](https://purchase.aspose.com/temporary-license/).

### 5. Czy istnieje forum społecznościowe dla Aspose.Slides dla obsługi .NET?
 Tak, możesz znaleźć wspierające forum społeczności dla Aspose.Slides dla .NET[Tutaj](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

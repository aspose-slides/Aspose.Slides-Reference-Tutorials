---
title: Aspose.Slides의 차트 서식 및 애니메이션
linktitle: Aspose.Slides의 차트 서식 및 애니메이션
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides에서 차트 형식을 지정하고 애니메이션을 적용하여 매력적인 시각적 요소로 프레젠테이션을 향상시키는 방법을 알아보세요.
weight: 10
url: /ko/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides의 차트 서식 및 애니메이션


동적 차트와 애니메이션을 사용하여 매력적인 프레젠테이션을 만들면 메시지의 영향력을 크게 높일 수 있습니다. .NET용 Aspose.Slides를 사용하면 바로 그 목표를 달성할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 차트에 애니메이션을 적용하고 서식을 지정하는 과정을 안내합니다. 개념을 철저하게 이해할 수 있도록 단계를 관리 가능한 섹션으로 나누어 보겠습니다.

## 전제 조건

Aspose.Slides를 사용하여 차트 서식 지정 및 애니메이션을 시작하기 전에 다음이 필요합니다.

1.  .NET용 Aspose.Slides: .NET용 Aspose.Slides를 설치했는지 확인하세요. 아직 하지 않았다면 다음을 수행할 수 있습니다.[여기에서 다운로드하십시오](https://releases.aspose.com/slides/net/).

2. 기존 프레젠테이션: 서식을 지정하고 애니메이션을 적용하려는 차트가 포함된 기존 프레젠테이션이 있습니다.

3. 기본 C# 지식: C#에 익숙하면 단계를 구현하는 데 도움이 됩니다.

이제 시작해 보겠습니다.

## 네임스페이스 가져오기

시작하려면 Aspose.Slides 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다. C# 프로젝트에서 다음을 추가합니다.

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## 차트의 범주 요소에 애니메이션 적용

### 1단계: 프레젠테이션 로드 및 차트 액세스

먼저 기존 프레젠테이션을 로드하고 애니메이션을 적용하려는 차트에 액세스하세요. 이 예에서는 차트가 프레젠테이션의 첫 번째 슬라이드에 있다고 가정합니다.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### 2단계: 카테고리 요소에 애니메이션 추가

이제 카테고리 요소에 애니메이션을 추가해 보겠습니다. 이 예에서는 페이드인 효과를 사용하고 있습니다.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### 3단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## 차트의 시리즈 애니메이션

### 1단계: 프레젠테이션 로드 및 차트 액세스

이전 예와 마찬가지로 프레젠테이션을 로드하고 차트에 액세스합니다.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### 2단계: 시리즈에 애니메이션 추가

이제 차트 시리즈에 애니메이션을 추가해 보겠습니다. 여기서도 페이드인 효과를 사용하고 있습니다.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### 3단계: 프레젠테이션 저장

애니메이션 시리즈와 함께 수정된 프레젠테이션을 저장합니다.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## 차트의 시리즈 요소에 애니메이션 적용하기

### 1단계: 프레젠테이션 로드 및 차트 액세스

이전과 마찬가지로 프레젠테이션을 로드하고 차트에 액세스합니다.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### 2단계: 시리즈 요소에 애니메이션 추가

이 단계에서는 시리즈 요소에 애니메이션을 추가하여 인상적인 시각 효과를 만들어 보겠습니다.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### 3단계: 프레젠테이션 저장

애니메이션 시리즈 요소가 포함된 프레젠테이션을 저장하는 것을 잊지 마세요.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

축하해요! 이제 .NET용 Aspose.Slides에서 차트의 형식을 지정하고 애니메이션을 적용하는 방법을 배웠습니다. 이러한 기술을 사용하면 프레젠테이션을 더욱 매력적이고 유익하게 만들 수 있습니다.

## 결론

.NET용 Aspose.Slides는 차트 서식 지정 및 애니메이션을 위한 강력한 도구를 제공하여 청중을 사로잡는 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다. 이 단계별 가이드를 따르면 차트 애니메이션 기술을 익히고 프레젠테이션을 향상시킬 수 있습니다.

## 자주 묻는 질문

### 1. .NET용 Aspose.Slides에 대한 설명서는 어디서 찾을 수 있나요?

 다음에서 문서에 액세스할 수 있습니다.[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. .NET용 Aspose.Slides를 어떻게 다운로드하나요?

 .NET용 Aspose.Slides는 다음에서 다운로드할 수 있습니다.[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. 무료 평가판이 있나요?

 예, 다음에서 .NET용 Aspose.Slides의 무료 평가판을 받을 수 있습니다.[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Aspose.Slides for .NET의 임시 라이선스를 구입할 수 있나요?

 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Aspose.Slides for .NET에 대한 지원이나 질문은 어디서 받을 수 있나요?

 지원 및 질문이 있는 경우 Aspose.Slides 포럼을 방문하세요.[https://forum.aspose.com/](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

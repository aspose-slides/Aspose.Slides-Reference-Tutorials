---
title: .NET용 Aspose.Slides를 사용한 강력한 차트 애니메이션
linktitle: 차트의 범주 요소에 애니메이션 적용
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint의 차트 요소에 애니메이션을 적용하는 방법을 알아보세요. 멋진 프레젠테이션을 위한 단계별 가이드입니다.
type: docs
weight: 11
url: /ko/net/chart-formatting-and-animation/animating-categories-elements/
---

프레젠테이션 세계에서 애니메이션은 특히 차트를 다룰 때 콘텐츠에 생기를 불어넣을 수 있습니다. .NET용 Aspose.Slides는 차트에 멋진 애니메이션을 만들 수 있는 다양한 강력한 기능을 제공합니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 차트의 카테고리 요소에 애니메이션을 적용하는 과정을 안내합니다.

## 전제조건

튜토리얼을 시작하기 전에 다음 전제조건을 갖추어야 합니다.

-  .NET용 Aspose.Slides: 개발 환경에 .NET용 Aspose.Slides가 설치되어 있는지 확인하세요. 아직 다운로드하지 않았다면 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

- 기존 프리젠테이션: 애니메이션을 적용할 차트가 포함된 PowerPoint 프리젠테이션이 있어야 합니다. 차트가 없으면 테스트 목적으로 차트가 포함된 샘플 프레젠테이션을 만드세요.

이제 모든 것이 준비되었으므로 차트 요소에 애니메이션을 적용해 보겠습니다.

## 네임스페이스 가져오기

첫 번째 단계는 Aspose.Slides의 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것입니다. 프로젝트에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## 1단계: 프레젠테이션 로드

```csharp
// 문서 디렉터리 경로
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // 차트 개체의 참조 가져오기
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

이 단계에서는 애니메이션을 적용하려는 차트가 포함된 기존 PowerPoint 프레젠테이션을 로드합니다. 그런 다음 첫 번째 슬라이드 내의 차트 개체에 액세스합니다.

## 2단계: 카테고리 요소에 애니메이션 적용

```csharp
// 카테고리 요소에 애니메이션 적용
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

이 단계에서는 전체 차트에 "페이드" 애니메이션 효과를 추가하여 이전 애니메이션 뒤에 나타나게 합니다.

다음으로 차트의 각 카테고리 내 개별 요소에 애니메이션을 추가하겠습니다. 이것이 진짜 마법이 일어나는 곳입니다.

## 3단계: 개별 요소에 애니메이션 적용

각 카테고리 내 개별 요소의 애니메이션을 다음 단계로 분류하겠습니다.

### 3.1단계: 카테고리 0의 요소에 애니메이션 적용하기

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

여기서는 차트의 카테고리 0 내의 개별 요소에 애니메이션을 적용하여 차례로 표시되도록 합니다. 이 애니메이션에는 "표시" 효과가 사용됩니다.

### 3.2단계: 카테고리 1의 요소에 애니메이션 적용하기

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

범주 1에 대해 프로세스가 반복되며 "표시" 효과를 사용하여 개별 요소에 애니메이션을 적용합니다.

### 3.3단계: 카테고리 2의 요소에 애니메이션 적용하기

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

카테고리 2에 대해서도 동일한 프로세스가 계속되어 해당 요소에 개별적으로 애니메이션을 적용합니다.

## 4단계: 프레젠테이션 저장

```csharp
//프리젠테이션 파일을 디스크에 쓰기
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

마지막 단계에서는 새로 추가된 애니메이션으로 프레젠테이션을 저장합니다. 이제 프레젠테이션을 실행할 때 차트 요소가 아름답게 애니메이션됩니다.

## 결론

차트의 범주 요소에 애니메이션을 적용하면 프레젠테이션의 시각적 매력을 향상시킬 수 있습니다. .NET용 Aspose.Slides를 사용하면 이 프로세스가 간단하고 효율적이 됩니다. 네임스페이스를 가져오고, 프레젠테이션을 로드하고, 전체 차트와 개별 요소에 애니메이션을 추가하는 방법을 배웠습니다. .NET용 Aspose.Slides를 사용하여 창의력을 발휘하고 프레젠테이션을 더욱 매력적으로 만드세요.

## 자주 묻는 질문

### 1. .NET용 Aspose.Slides를 어떻게 다운로드할 수 있나요?
 .NET용 Aspose.Slides는 다음에서 다운로드할 수 있습니다.[이 링크](https://releases.aspose.com/slides/net/).

### 2. Aspose.Slides for .NET을 사용하려면 코딩 경험이 필요합니까?
코딩 경험은 도움이 되지만 Aspose.Slides for .NET은 모든 기술 수준의 사용자를 지원하기 위해 광범위한 문서와 예제를 제공합니다.

### 3. 모든 버전의 PowerPoint에서 Aspose.Slides for .NET을 사용할 수 있나요?
Aspose.Slides for .NET은 다양한 PowerPoint 버전과 작동하도록 설계되어 호환성을 보장합니다.

### 4. Aspose.Slides for .NET에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 .NET용 Aspose.Slides에 대한 임시 라이선스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).

### 5. .NET 지원을 위한 Aspose.Slides에 대한 커뮤니티 포럼이 있습니까?
 예, .NET용 Aspose.Slides에 대한 지원 커뮤니티 포럼을 찾을 수 있습니다.[여기](https://forum.aspose.com/).

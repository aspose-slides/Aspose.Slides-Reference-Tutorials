---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 시리즈 요소에 애니메이션을 적용하는 방법을 알아보세요. 소스 코드가 포함된 이 포괄적인 단계별 가이드를 따라 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"linktitle": "Java 슬라이드에서 시리즈 요소 애니메이션 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 시리즈 요소 애니메이션 만들기"
"url": "/ko/java/animation-and-layout/animating-series-elements-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 시리즈 요소 애니메이션 만들기


## Java 슬라이드에서 시리즈 요소 애니메이션 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 시리즈 요소에 애니메이션을 적용하는 방법을 안내합니다. 애니메이션은 프레젠테이션을 더욱 매력적이고 유익하게 만들어 줍니다. 이 예제에서는 PowerPoint 슬라이드의 차트에 애니메이션을 적용하는 방법을 중점적으로 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java 라이브러리용 Aspose.Slides가 설치되었습니다.
- 애니메이션을 적용하려는 차트가 있는 기존 PowerPoint 프레젠테이션입니다.
- Java 개발 환경 설정.

## 1단계: 프레젠테이션 로드

먼저, 애니메이션을 적용할 차트가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. `"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용합니다.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2단계: 차트에 대한 참조 가져오기

프레젠테이션이 로드되면 애니메이션을 적용할 차트의 참조를 가져옵니다. 이 예시에서는 차트가 첫 번째 슬라이드에 있다고 가정합니다.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## 3단계: 애니메이션 효과 추가

이제 차트 요소에 애니메이션 효과를 추가해 보겠습니다. `slide.getTimeline().getMainSequence().addEffect()` 차트가 어떻게 애니메이션화되어야 하는지 지정하는 방법입니다.

```java
// 차트 전체에 애니메이션을 적용합니다
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// 개별 시리즈 요소에 애니메이션을 적용합니다(이 부분은 사용자 정의 가능)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

위 코드에서는 먼저 전체 차트에 "페이드" 효과를 적용합니다. 그런 다음 차트 내 계열과 점을 반복하며 각 요소에 "나타남" 효과를 적용합니다. 필요에 따라 애니메이션 유형과 트리거를 사용자 지정할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 애니메이션이 적용된 수정된 프레젠테이션을 새 파일에 저장합니다.

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 시리즈 요소 애니메이션을 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 로드
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// 차트 객체의 참조를 가져옵니다
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// 애니메이션 시리즈 요소
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// 프레젠테이션 파일을 디스크에 쓰기 
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 시리즈 요소에 애니메이션을 적용하는 방법을 알아보았습니다. 애니메이션은 프레젠테이션을 더욱 돋보이게 하고 몰입도를 높여줍니다. 특정 요구 사항에 맞게 애니메이션 효과와 트리거를 사용자 정의하세요.

## 자주 묻는 질문

### 개별 차트 요소에 대한 애니메이션을 어떻게 사용자 지정할 수 있나요?

코드에서 애니메이션 유형과 트리거를 수정하여 개별 차트 요소의 애니메이션을 사용자 지정할 수 있습니다. 예시에서는 "나타남" 효과를 사용했지만, "페이드 인", "날아오기" 등 다양한 애니메이션 유형 중에서 선택하고 "클릭 시", "이전 효과 이후", "이전 효과와 함께" 등 다양한 트리거를 지정할 수 있습니다.

### PowerPoint 슬라이드의 다른 개체에 애니메이션을 적용할 수 있나요?

네, PowerPoint 슬라이드의 차트뿐만 아니라 다양한 개체에도 애니메이션을 적용할 수 있습니다. `addEffect` 애니메이션을 적용하려는 객체와 원하는 애니메이션 속성을 지정하는 방법입니다.

### Java용 Aspose.Slides를 내 프로젝트에 통합하려면 어떻게 해야 하나요?

Java용 Aspose.Slides를 프로젝트에 통합하려면 빌드 경로에 라이브러리를 포함하거나 Maven이나 Gradle과 같은 종속성 관리 도구를 사용해야 합니다. 자세한 통합 지침은 Aspose.Slides 문서를 참조하세요.

### PowerPoint 응용 프로그램에서 애니메이션을 미리 볼 수 있는 방법이 있나요?

네, 프레젠테이션을 저장한 후 PowerPoint 앱에서 열어 애니메이션을 미리 보고 필요한 경우 추가 조정할 수 있습니다. PowerPoint는 이러한 목적으로 미리 보기 모드를 제공합니다.

### Java용 Aspose.Slides에서 더욱 고급 애니메이션 옵션을 사용할 수 있나요?

네, Aspose.Slides for Java는 모션 경로, 타이밍, 인터랙티브 애니메이션 등 다양한 고급 애니메이션 옵션을 제공합니다. Aspose.Slides에서 제공하는 설명서와 예제를 활용하여 프레젠테이션에 고급 애니메이션을 구현할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
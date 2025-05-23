---
"description": "Aspose.Slides for Java에서 시리즈 애니메이션을 활용하여 프레젠테이션을 최적화하세요. 소스 코드 예제가 포함된 단계별 가이드를 따라 매력적인 PowerPoint 애니메이션을 제작해 보세요."
"linktitle": "Java 슬라이드에서 시리즈 애니메이션 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 시리즈 애니메이션 만들기"
"url": "/ko/java/animation-and-layout/animating-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 시리즈 애니메이션 만들기


## Java용 Aspose.Slides에서 시리즈 애니메이션 소개

이 가이드에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드에 시리즈 애니메이션을 적용하는 과정을 안내합니다. 이 라이브러리를 사용하면 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있습니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- Java 라이브러리용 Aspose.Slides.
- Java 개발 환경 설정.

## 1단계: 프레젠테이션 로드

먼저 차트가 포함된 기존 PowerPoint 프레젠테이션을 로드해야 합니다. `"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 포함합니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 Presentation 클래스를 인스턴스화합니다. 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2단계: 차트에 액세스

다음으로, 프레젠테이션 내에서 차트에 접근해 보겠습니다. 이 예시에서는 차트가 첫 번째 슬라이드에 있고 해당 슬라이드의 첫 번째 도형이라고 가정합니다.

```java
// 차트 객체에 대한 참조를 가져옵니다
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## 3단계: 애니메이션 추가

이제 차트 내 시리즈에 애니메이션을 추가해 보겠습니다. 페이드인 효과를 사용하여 각 시리즈가 차례로 나타나도록 하겠습니다.

```java
// 차트 전체에 애니메이션을 적용합니다
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// 각 시리즈에 애니메이션을 추가합니다(시리즈가 4개라고 가정)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

위의 코드에서는 차트 전체에 페이드인 효과를 사용한 다음 루프를 사용하여 각 시리즈에 차례로 "나타남" 효과를 추가합니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Java용 Aspose.Slides에서 시리즈 애니메이션을 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 Presentation 클래스를 인스턴스화합니다. 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// 차트 객체의 참조를 가져옵니다
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// 시리즈를 애니메이션으로 만들다
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// 수정된 프레젠테이션을 디스크에 기록합니다. 
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 차트에 시리즈 애니메이션을 성공적으로 적용했습니다. 이를 통해 프레젠테이션을 더욱 매력적이고 시각적으로 멋지게 만들 수 있습니다. 더 많은 애니메이션 옵션을 살펴보고 필요에 따라 프레젠테이션을 세부적으로 조정해 보세요.

## 자주 묻는 질문

### 시리즈 애니메이션의 순서를 어떻게 제어합니까?

시리즈 애니메이션의 순서를 제어하려면 다음을 사용하세요. `EffectTriggerType.AfterPrevious` 효과를 추가할 때 매개변수를 설정합니다. 이렇게 하면 이전 애니메이션이 완료된 후 각 시리즈 애니메이션이 시작됩니다.

### 각 시리즈에 다른 애니메이션을 적용할 수 있나요?

예, 다른 애니메이션을 지정하여 각 시리즈에 다른 애니메이션을 적용할 수 있습니다. `EffectType` 그리고 `EffectSubtype` 효과를 추가할 때의 값.

### 프레젠테이션에 시리즈가 4개 이상 있는 경우는 어떻게 되나요?

3단계에서 루프를 확장하여 차트의 모든 계열에 애니메이션을 추가할 수 있습니다. 루프의 조건을 적절히 조정하기만 하면 됩니다.

### 애니메이션 지속 시간과 지연 시간을 어떻게 사용자 지정할 수 있나요?

애니메이션 효과의 속성을 설정하여 애니메이션 지속 시간과 지연 시간을 사용자 지정할 수 있습니다. 사용 가능한 사용자 지정 옵션에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 참조하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
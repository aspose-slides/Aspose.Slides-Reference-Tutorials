---
title: Java 슬라이드의 애니메이션 시리즈
linktitle: Java 슬라이드의 애니메이션 시리즈
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java의 시리즈 애니메이션으로 프레젠테이션을 최적화하세요. 매력적인 PowerPoint 애니메이션을 만들려면 소스 코드 예제가 포함된 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/java/animation-and-layout/animating-series-java-slides/
---

## Aspose.Slides for Java의 애니메이션 시리즈 소개

이 가이드에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 시리즈에 애니메이션을 적용하는 과정을 안내합니다. 이 라이브러리를 사용하면 프로그래밍 방식으로 PowerPoint 프레젠테이션을 작업할 수 있습니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Aspose.Slides for Java 라이브러리.
- Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 로드

 먼저 차트가 포함된 기존 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 사용하세요.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프리젠테이션 파일을 나타내는 프리젠테이션 클래스 인스턴스화
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2단계: 차트에 액세스

다음으로 프레젠테이션 내의 차트에 액세스하겠습니다. 이 예에서는 차트가 첫 번째 슬라이드에 있고 해당 슬라이드의 첫 번째 셰이프라고 가정합니다.

```java
// 차트 개체에 대한 참조 가져오기
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## 3단계: 애니메이션 추가

이제 차트 내의 시리즈에 애니메이션을 추가해 보겠습니다. 페이드인 효과를 사용하여 각 시리즈가 차례로 나타나도록 하겠습니다.

```java
// 전체 차트에 애니메이션 적용
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// 각 시리즈에 애니메이션 추가(4개 시리즈가 있다고 가정)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

위 코드에서는 전체 차트에 페이드인 효과를 사용한 다음 루프를 사용하여 각 시리즈에 "표시" 효과를 차례로 추가합니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Java용 Aspose.Slides의 애니메이션 시리즈에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프리젠테이션 파일을 나타내는 프리젠테이션 클래스 인스턴스화
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// 차트 개체의 참조 가져오기
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// 시리즈에 애니메이션을 적용하세요
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
	// 수정된 프레젠테이션을 디스크에 쓰기
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 차트에 성공적으로 애니메이션 시리즈를 만들었습니다. 이렇게 하면 프레젠테이션을 더욱 매력적이고 시각적으로 매력적으로 만들 수 있습니다. 더 많은 애니메이션 옵션을 살펴보고 필요에 따라 프레젠테이션을 미세 조정하세요.

## FAQ

### 시리즈 애니메이션의 순서를 어떻게 제어하나요?

 시리즈 애니메이션의 순서를 제어하려면`EffectTriggerType.AfterPrevious` 효과를 추가할 때 매개변수입니다. 이렇게 하면 각 시리즈 애니메이션이 이전 애니메이션이 끝난 후 시작됩니다.

### 시리즈마다 다른 애니메이션을 적용할 수 있나요?

 예, 서로 다른 설정을 지정하여 각 시리즈에 서로 다른 애니메이션을 적용할 수 있습니다.`EffectType` 그리고`EffectSubtype` 효과를 추가할 때의 값입니다.

### 프레젠테이션에 4개 이상의 시리즈가 있으면 어떻게 되나요?

3단계의 루프를 확장하여 차트의 모든 계열에 대한 애니메이션을 추가할 수 있습니다. 그에 따라 루프의 상태를 조정하십시오.

### 애니메이션 지속 시간과 지연을 어떻게 사용자 정의할 수 있나요?

애니메이션 효과에 대한 속성을 설정하여 애니메이션 지속 시간과 지연을 사용자 정의할 수 있습니다. 사용 가능한 사용자 정의 옵션에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 확인하세요.
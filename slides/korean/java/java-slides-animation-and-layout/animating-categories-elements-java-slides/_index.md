---
title: Java 슬라이드의 카테고리 요소 애니메이션
linktitle: Java 슬라이드의 카테고리 요소 애니메이션
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java로 Java 프레젠테이션을 최적화하세요. PowerPoint 슬라이드의 카테고리 요소에 애니메이션을 적용하는 방법을 단계별로 알아보세요.
weight: 10
url: /ko/java/animation-and-layout/animating-categories-elements-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드의 카테고리 요소 애니메이션 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 카테고리 요소에 애니메이션을 적용하는 과정을 안내합니다. 이 단계별 가이드에서는 이 애니메이션 효과를 얻는 데 도움이 되는 소스 코드와 설명을 제공합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java API용 Aspose.Slides가 설치되었습니다.
- 차트가 포함된 기존 PowerPoint 프레젠테이션입니다. 이 차트의 카테고리 요소에 애니메이션을 적용해 보겠습니다.

## 1단계: Aspose.Slides 라이브러리 가져오기

시작하려면 Aspose.Slides 라이브러리를 Java 프로젝트로 가져옵니다. 라이브러리를 다운로드하여 프로젝트의 클래스 경로에 추가할 수 있습니다. 필요한 종속성이 설정되어 있는지 확인하세요.

## 2단계: 프레젠테이션 로드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 이 코드에서는 애니메이션을 적용하려는 차트가 포함된 기존 PowerPoint 프레젠테이션을 로드합니다. 바꾸다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 3단계: 차트 개체에 대한 참조 가져오기

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

프레젠테이션의 첫 번째 슬라이드에서 차트 개체에 대한 참조를 얻습니다. 슬라이드 인덱스 조정(`get_Item(0)`) 및 형상 지수(`get_Item(0)`) 필요에 따라 특정 차트에 액세스할 수 있습니다.

## 4단계: 카테고리 요소에 애니메이션 적용

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

차트 내의 카테고리 요소에 애니메이션을 적용합니다. 이 코드는 전체 차트에 페이드 효과를 추가한 다음 각 카테고리 내의 각 요소에 "표시" 효과를 추가합니다. 필요에 따라 효과 유형과 하위 유형을 조정합니다.

## 5단계: 프레젠테이션 저장

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 마지막으로 애니메이션 차트가 포함된 수정된 프레젠테이션을 새 파일에 저장합니다. 바꾸다`"AnimatingCategoriesElements_out.pptx"` 원하는 출력 파일 이름으로.


## Java 슬라이드의 카테고리 요소에 애니메이션을 적용하기 위한 완전한 소스 코드
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// 차트 개체의 참조 가져오기
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// 카테고리 요소에 애니메이션 적용
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// 프리젠테이션 파일을 디스크에 쓰기
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 Java 슬라이드의 카테고리 요소에 성공적으로 애니메이션을 적용했습니다. 이 단계별 가이드에서는 PowerPoint 프레젠테이션에서 이러한 애니메이션 효과를 얻는 데 필요한 소스 코드와 설명을 제공했습니다. 다양한 효과와 설정을 실험하여 애니메이션을 더욱 맞춤화해 보세요.

## FAQ

### 애니메이션 효과를 어떻게 사용자 정의할 수 있나요?

 애니메이션 효과를 변경하여 사용자 정의할 수 있습니다.`EffectType` 그리고`EffectSubtype` 차트 요소에 효과를 추가할 때 매개변수입니다. 사용 가능한 애니메이션 효과에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 참조하세요.

### 이러한 애니메이션을 다른 유형의 차트에 적용할 수 있나요?

예, 애니메이션을 적용하려는 특정 차트 요소를 대상으로 코드를 수정하여 다른 유형의 차트에 유사한 애니메이션을 적용할 수 있습니다. 그에 따라 루프 구조와 매개변수를 조정합니다.

### Java용 Aspose.Slides에 대해 자세히 알아보려면 어떻게 해야 합니까?

 포괄적인 문서 및 추가 리소스를 보려면 다음을 방문하세요.[Java API 참조용 Aspose.Slides](https://reference.aspose.com/slides/java/) . 다음에서 라이브러리를 다운로드할 수도 있습니다.[여기](https://releases.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

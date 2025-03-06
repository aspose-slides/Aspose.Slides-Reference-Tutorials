---
title: Java 슬라이드에서 레이아웃 모드 설정
linktitle: Java 슬라이드에서 레이아웃 모드 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java 슬라이드의 레이아웃 모드를 설정하는 방법을 알아보세요. 소스 코드가 포함된 이 단계별 가이드를 통해 차트 위치와 크기를 맞춤설정하세요.
weight: 23
url: /ko/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 레이아웃 모드 설정


## Java 슬라이드의 레이아웃 모드 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 레이아웃 모드를 설정하는 방법을 알아봅니다. 레이아웃 모드는 슬라이드 내 차트의 위치와 크기를 결정합니다.

## 전제 조건

 시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 만들기

먼저, 새로운 프레젠테이션을 만들어야 합니다.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드 및 차트 추가

다음으로 슬라이드와 차트를 추가하겠습니다. 이 예에서는 묶은 세로 막대형 차트를 만듭니다.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 3단계: 차트 레이아웃 설정

 이제 차트의 레이아웃을 설정해 보겠습니다. 다음을 사용하여 슬라이드 내 차트의 위치와 크기를 조정하겠습니다.`setX`, `setY`, `setWidth`, `setHeight` 행동 양식. 추가적으로, 우리는`LayoutTargetType` 레이아웃 모드를 결정합니다.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

이 예에서는 차트의 레이아웃 대상 유형을 "내부"로 설정했습니다. 즉, 차트의 위치와 크기가 슬라이드의 내부 영역을 기준으로 지정됩니다.

## 4단계: 프레젠테이션 저장

마지막으로 차트 레이아웃 설정으로 프레젠테이션을 저장해 보겠습니다.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 레이아웃 모드 설정에 대한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 레이아웃 모드를 설정하는 방법을 배웠습니다. 다음의 값을 조정하여 특정 요구 사항에 따라 차트의 위치와 크기를 사용자 정의할 수 있습니다.`setX`, `setY`, `setWidth`, `setHeight` , 그리고`setLayoutTargetType`행동 양식. 이를 통해 슬라이드 내의 차트 배치를 제어할 수 있습니다.

## FAQ

### Aspose.Slides for Java에서 차트의 레이아웃 모드를 어떻게 변경합니까?

 Aspose.Slides for Java에서 차트의 레이아웃 모드를 변경하려면 다음을 사용할 수 있습니다.`setLayoutTargetType` 차트의 플롯 영역에 대한 메서드입니다. 다음 중 하나로 설정할 수 있습니다.`LayoutTargetType.Inner` 또는`LayoutTargetType.Outer` 원하는 레이아웃에 따라.

### 슬라이드 내 차트의 위치와 크기를 맞춤설정할 수 있나요?

 예, 다음을 사용하여 슬라이드 내 차트의 위치와 크기를 사용자 정의할 수 있습니다.`setX`, `setY`, `setWidth` , 그리고`setHeight` 차트의 플롯 영역에 대한 메소드. 요구 사항에 따라 차트의 위치와 크기를 조정하려면 이러한 값을 조정하세요.

### Aspose.Slides for Java에 대한 자세한 정보는 어디서 찾을 수 있나요?

 Aspose.Slides for Java에 대한 자세한 내용은 다음에서 확인할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/slides/java/). 여기에는 Java에서 슬라이드와 차트를 효과적으로 작업하는 데 도움이 되는 자세한 API 참조와 예제가 포함되어 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Aspose.Slides를 사용하여 Java 슬라이드의 레이아웃 모드를 설정하는 방법을 알아보세요. 소스 코드와 함께 제공되는 단계별 가이드를 통해 차트 위치 및 크기를 사용자 정의해 보세요."
"linktitle": "Java Slides에서 레이아웃 모드 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 레이아웃 모드 설정"
"url": "/ko/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 레이아웃 모드 설정


## Java Slides에서 레이아웃 모드 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 레이아웃 모드를 설정하는 방법을 알아봅니다. 레이아웃 모드는 슬라이드 내 차트의 위치와 크기를 결정합니다.

## 필수 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. 라이브러리는 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 만들기

먼저, 새로운 프레젠테이션을 만들어야 합니다.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드와 차트 추가

다음으로, 슬라이드와 차트를 추가해 보겠습니다. 이 예시에서는 클러스터형 세로 막대형 차트를 만들어 보겠습니다.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 3단계: 차트 레이아웃 설정

이제 차트 레이아웃을 설정해 보겠습니다. 슬라이드 내에서 차트의 위치와 크기를 조정합니다. `setX`, `setY`, `setWidth`, `setHeight` 방법. 또한, 우리는 다음을 설정합니다. `LayoutTargetType` 레이아웃 모드를 결정합니다.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

이 예에서 차트의 레이아웃 대상 유형을 "내부"로 설정했습니다. 즉, 슬라이드의 내부 영역을 기준으로 위치와 크기가 조정됩니다.

## 4단계: 프레젠테이션 저장

마지막으로 차트 레이아웃 설정으로 프레젠테이션을 저장해 보겠습니다.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Java Slides에서 레이아웃 모드 설정을 위한 전체 소스 코드

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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드 차트의 레이아웃 모드를 설정하는 방법을 알아보았습니다. `setX`, `setY`, `setWidth`, `setHeight`, 그리고 `setLayoutTargetType` 방법을 통해 슬라이드 내 차트 배치를 제어할 수 있습니다.

## 자주 묻는 질문

### Java용 Aspose.Slides에서 차트의 레이아웃 모드를 어떻게 변경합니까?

Java용 Aspose.Slides에서 차트의 레이아웃 모드를 변경하려면 다음을 사용할 수 있습니다. `setLayoutTargetType` 차트의 플롯 영역에서 메서드를 설정합니다. 다음 중 하나로 설정할 수 있습니다. `LayoutTargetType.Inner` 또는 `LayoutTargetType.Outer` 원하는 레이아웃에 따라 다릅니다.

### 슬라이드 내에서 차트의 위치와 크기를 사용자 지정할 수 있나요?

예, 슬라이드 내에서 차트의 위치와 크기를 사용자 정의할 수 있습니다. `setX`, `setY`, `setWidth`, 그리고 `setHeight` 차트의 플롯 영역에 대한 메서드를 사용합니다. 이 값을 조정하여 필요에 따라 차트의 위치와 크기를 조정합니다.

### Java용 Aspose.Slides에 대한 자세한 정보는 어디에서 찾을 수 있나요?

Java용 Aspose.Slides에 대한 자세한 내용은 다음에서 찾을 수 있습니다. [선적 서류 비치](https://reference.aspose.com/slides/java/)Java에서 슬라이드와 차트를 효과적으로 사용하는 데 도움이 되는 자세한 API 참조와 예제가 포함되어 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
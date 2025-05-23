---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 차트를 사용자 지정하는 방법을 알아보세요. 두 번째 플롯 옵션을 살펴보고 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"linktitle": "Java 슬라이드 차트의 두 번째 플롯 옵션"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드 차트의 두 번째 플롯 옵션"
"url": "/ko/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드 차트의 두 번째 플롯 옵션


## Java Slides 차트의 두 번째 플롯 옵션 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에 두 번째 플롯 옵션을 추가하는 방법을 살펴보겠습니다. 두 번째 플롯 옵션을 사용하면 특히 원형 차트와 같은 상황에서 차트의 모양과 동작을 사용자 지정할 수 있습니다. 이를 위한 단계별 지침과 소스 코드 예제를 제공합니다. 

## 필수 조건
시작하기에 앞서 Aspose.Slides for Java가 설치되어 있고 Java 프로젝트에 설정되어 있는지 확인하세요.

## 1단계: 프레젠테이션 만들기
새로운 프레젠테이션을 만들어 보겠습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드에 차트 추가
다음으로, 슬라이드에 차트를 추가해 보겠습니다. 이 예시에서는 원형 차트를 만들어 보겠습니다.

```java
// 슬라이드에 차트 추가
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 3단계: 차트 속성 사용자 지정
이제 두 번째 플롯 옵션을 포함하여 차트의 다양한 속성을 설정해 보겠습니다.

```java
// 첫 번째 시리즈의 데이터 레이블 표시
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 두 번째 파이의 크기를 설정합니다(백분율)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// 파이를 백분율로 나누세요
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// 분할 위치 설정
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 4단계: 프레젠테이션 저장
마지막으로 차트와 두 번째 플롯 옵션을 사용하여 프레젠테이션을 저장합니다.

```java
// 디스크에 프레젠테이션 쓰기
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 두 번째 플롯 옵션에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
// 슬라이드에 차트 추가
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// 다양한 속성 설정
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// 디스크에 프레젠테이션 쓰기
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides 차트에 두 번째 플롯 옵션을 추가하는 방법을 알아보았습니다. 다양한 속성을 사용자 지정하여 차트의 모양과 기능을 향상시키고, 프레젠테이션을 더욱 유익하고 시각적으로 매력적으로 만들 수 있습니다.

## 자주 묻는 질문

### 원형 차트에서 두 번째 원형의 크기를 어떻게 변경할 수 있나요?

원형 차트에서 두 번째 원형의 크기를 변경하려면 다음을 사용하세요. `setSecondPieSize` 위 코드 예제와 같은 메서드입니다. 값을 조정하여 크기를 백분율로 지정합니다.

### 무엇을 `PieSplitBy` 원형 차트의 컨트롤?

그만큼 `PieSplitBy` 속성은 원형 차트 분할 방식을 제어합니다. 다음 중 하나로 설정할 수 있습니다. `PieSplitType.ByPercentage` 또는 `PieSplitType.ByValue` 차트를 백분율이나 특정 값으로 각각 나눕니다.

### 원형 차트에서 분할 위치를 어떻게 설정합니까?

원형 차트에서 분할 위치를 설정하려면 다음을 사용하십시오. `setPieSplitPosition` 메서드. 값을 조정하여 원하는 위치를 지정하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Java 슬라이드에 추가된 차트 레이아웃 확인
linktitle: Java 슬라이드에 추가된 차트 레이아웃 확인
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 마스터 차트 레이아웃 유효성 검사. 멋진 프레젠테이션을 위해 프로그래밍 방식으로 차트를 조작하는 방법을 알아보세요.
weight: 10
url: /ko/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에 추가된 차트 레이아웃 확인


## Aspose.Slides for Java의 차트 레이아웃 유효성 검사 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트 레이아웃의 유효성을 검사하는 방법을 살펴보겠습니다. 이 라이브러리를 사용하면 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있으므로 차트를 포함한 다양한 요소를 쉽게 조작하고 확인할 수 있습니다.

## 1단계: 프레젠테이션 초기화

 먼저 프레젠테이션 개체를 초기화하고 기존 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 프리젠테이션 파일의 실제 경로(`test.pptx` 이 예에서는).

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 2단계: 차트 추가

 다음으로 프레젠테이션에 차트를 추가하겠습니다. 이 예에서는 묶은 세로 막대형 차트를 추가하지만`ChartType` 필요에 따라.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## 3단계: 차트 레이아웃 유효성 검사

 이제 다음을 사용하여 차트 레이아웃의 유효성을 검사하겠습니다.`validateChartLayout()` 방법. 이렇게 하면 차트가 슬라이드 내에서 올바르게 배치됩니다.

```java
chart.validateChartLayout();
```

## 4단계: 차트 위치 및 크기 검색

차트 레이아웃의 유효성을 검사한 후 해당 위치와 크기에 대한 정보를 검색할 수 있습니다. 실제 X 및 Y 좌표는 물론 차트 플롯 영역의 너비와 높이도 얻을 수 있습니다.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## 5단계: 프레젠테이션 저장

 마지막으로 수정된 프레젠테이션을 저장하는 것을 잊지 마세요. 이 예에서는 다음 이름으로 저장합니다.`Result.pptx`이지만 필요한 경우 다른 파일 이름을 지정할 수 있습니다.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에 추가된 차트 레이아웃 유효성 검사를 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// 프레젠테이션 저장 중
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 차트 작업 세계를 탐구했습니다. 차트 레이아웃의 유효성을 검사하고, 위치와 크기를 검색하고, 수정된 프레젠테이션을 저장하는 필수 단계를 다루었습니다. 다음은 간단한 요약입니다.

## FAQ

### 차트 종류를 어떻게 변경하나요?

 차트 유형을 변경하려면 간단히 바꾸십시오.`ChartType.ClusteredColumn`원하는 차트 유형을`addChart()` 방법.

### 차트 데이터를 맞춤설정할 수 있나요?

예, 데이터 계열, 범주 및 값을 추가하고 수정하여 차트 데이터를 사용자 정의할 수 있습니다. 자세한 내용은 Aspose.Slides 문서를 참조하세요.

### 다른 차트 속성을 수정하려면 어떻게 해야 하나요?

다양한 차트 속성에 액세스하고 요구 사항에 따라 사용자 정의할 수 있습니다. 차트 조작에 대한 포괄적인 정보를 보려면 Aspose.Slides 문서를 살펴보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Java 슬라이드의 지도 차트
linktitle: Java 슬라이드의 지도 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 멋진 지도 차트를 만들어 보세요. Java 개발자를 위한 단계별 가이드 및 소스 코드입니다.
weight: 15
url: /ko/java/chart-elements/map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 지도 차트


## Aspose.Slides for Java를 사용하여 Java 슬라이드의 지도 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 지도 차트를 만드는 과정을 안내합니다. 지도 차트는 프레젠테이션에서 지리적 데이터를 시각화하는 좋은 방법입니다.

## 전제 조건

 시작하기 전에 Java 프로젝트에 통합된 Java용 Aspose.Slides 라이브러리가 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 프로젝트 설정

Java 프로젝트를 설정하고 프로젝트의 클래스 경로에 Aspose.Slides for Java 라이브러리를 추가했는지 확인하세요.

## 2단계: PowerPoint 프레젠테이션 만들기

먼저 새 PowerPoint 프레젠테이션을 만들어 보겠습니다.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## 3단계: 지도 차트 추가

이제 프레젠테이션에 지도 차트를 추가하겠습니다.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## 4단계: 지도 차트에 데이터 추가

지도 차트에 일부 데이터를 추가해 보겠습니다. 시리즈를 만들고 여기에 데이터 포인트를 추가하겠습니다.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## 5단계: 카테고리 추가

다양한 지리적 영역을 나타내는 범주를 지도 차트에 추가해야 합니다.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## 6단계: 데이터 포인트 사용자 정의

개별 데이터 포인트를 사용자 정의할 수 있습니다. 이 예에서는 특정 데이터 포인트의 색상과 값을 변경합니다.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 7단계: 프레젠테이션 저장

마지막으로 지도 차트를 사용하여 프레젠테이션을 저장합니다.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 지도 차트를 만들었습니다. 차트를 추가로 사용자 정의하고 Aspose.Slides가 제공하는 다른 기능을 탐색하여 프레젠테이션을 향상시킬 수 있습니다.

## Java 슬라이드의 지도 차트에 대한 완전한 소스 코드

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//빈 차트 만들기
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//계열 및 소수의 데이터 포인트 추가
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//카테고리 추가
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//데이터 포인트 값 변경
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//데이터 포인트 모양 설정
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 지도 차트를 만드는 과정을 살펴보았습니다. 지도 차트는 지리 데이터를 시각화하여 프레젠테이션을 더욱 매력적이고 유익하게 만드는 효과적인 방법입니다. 주요 단계를 요약해 보겠습니다.

## FAQ

### 지도 차트 유형을 어떻게 변경할 수 있나요?

 대체하여 차트 유형을 변경할 수 있습니다.`ChartType.Map` 3단계에서 차트 생성 시 원하는 차트 종류로 변경하세요.

### 지도 차트의 모양을 어떻게 사용자 정의할 수 있나요?

 속성을 수정하여 차트 모양을 사용자 정의할 수 있습니다.`dataPoint` 6단계의 개체입니다. 색상, 값 등을 변경할 수 있습니다.

### 더 많은 데이터 포인트와 카테고리를 추가할 수 있나요?

 예, 필요한 만큼 데이터 포인트와 카테고리를 추가할 수 있습니다. 간단히`series.getDataPoints().addDataPointForMapSeries()` 그리고`chart.getChartData().getCategories().add()` 추가하는 방법입니다.

### Java용 Aspose.Slides를 내 프로젝트에 어떻게 통합하나요?

 다음에서 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/slides/java/) 프로젝트의 클래스 경로에 추가하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

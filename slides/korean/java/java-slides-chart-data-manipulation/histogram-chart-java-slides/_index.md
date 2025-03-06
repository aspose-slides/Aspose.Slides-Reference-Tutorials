---
title: Java 슬라이드의 히스토그램 차트
linktitle: Java 슬라이드의 히스토그램 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 방법을 알아보세요. 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다.
weight: 19
url: /ko/java/chart-data-manipulation/histogram-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides를 사용하는 Java 슬라이드의 히스토그램 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 과정을 안내합니다. 히스토그램 차트는 연속 간격에 대한 데이터 분포를 나타내는 데 사용됩니다.

## 전제 조건

 시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/slides/java/).

## 1단계: 프로젝트 초기화

Java 프로젝트를 만들고 프로젝트 종속성에 Aspose.Slides 라이브러리를 포함합니다.

## 2단계: 필요한 라이브러리 가져오기

```java
import com.aspose.slides.*;
```

## 3단계: 기존 프레젠테이션 로드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 꼭 교체하세요`"Your Document Directory"` PowerPoint 문서의 실제 경로를 사용합니다.

## 4단계: 히스토그램 차트 만들기

이제 프레젠테이션의 슬라이드에 히스토그램 차트를 만들어 보겠습니다.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // 계열에 데이터 포인트 추가
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // 가로 축 집계 유형을 자동으로 설정
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // 프레젠테이션 저장
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 이 코드에서는 먼저 차트에서 기존 범주와 계열을 모두 지웁니다. 그런 다음 다음을 사용하여 계열에 데이터 포인트를 추가합니다.`getDataPoints().addDataPointForHistogramSeries` 방법. 마지막으로 가로축 집계 유형을 자동으로 설정하고 프레젠테이션을 저장합니다.

## Java 슬라이드의 히스토그램 차트에 대한 완전한 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 방법을 살펴보았습니다. 히스토그램 차트는 지속적인 간격에 따른 데이터 분포를 시각화하는 데 유용한 도구이며, 특히 통계 또는 분석 콘텐츠를 다룰 때 프레젠테이션에 강력한 추가 기능이 될 수 있습니다.

## FAQ

### Java용 Aspose.Slides를 어떻게 설치하나요?

 Java 라이브러리용 Aspose.Slides를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/). 해당 웹 사이트에 제공된 설치 지침을 따르십시오.

### 히스토그램 차트는 어떤 용도로 사용되나요?

히스토그램 차트는 연속적인 간격에 따른 데이터 분포를 시각화하는 데 사용됩니다. 빈도 분포를 나타내기 위해 통계에서 일반적으로 사용됩니다.

### 히스토그램 차트의 모양을 사용자 정의할 수 있나요?

예, Aspose.Slides API를 사용하여 색상, 레이블, 축을 포함한 차트의 모양을 사용자 정의할 수 있습니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

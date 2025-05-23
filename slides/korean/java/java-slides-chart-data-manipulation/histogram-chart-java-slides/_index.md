---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 방법을 알아보세요. 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드의 히스토그램 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 히스토그램 차트"
"url": "/ko/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 히스토그램 차트


## Aspose.Slides를 사용하여 Java Slides에서 히스토그램 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 과정을 안내합니다. 히스토그램 차트는 연속 구간에 대한 데이터 분포를 나타내는 데 사용됩니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [Aspose 웹사이트](https://releases.aspose.com/slides/java/).

## 1단계: 프로젝트 초기화

Java 프로젝트를 만들고 프로젝트의 종속성에 Aspose.Slides 라이브러리를 포함합니다.

## 2단계: 필요한 라이브러리 가져오기

```java
import com.aspose.slides.*;
```

## 3단계: 기존 프레젠테이션 로드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

교체를 꼭 해주세요 `"Your Document Directory"` PowerPoint 문서의 실제 경로를 사용합니다.

## 4단계: 히스토그램 차트 만들기

이제 프레젠테이션의 슬라이드에 히스토그램 차트를 만들어 보겠습니다.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // 시리즈에 데이터 포인트 추가
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // 수평 축 집계 유형을 자동으로 설정
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // 프레젠테이션을 저장하세요
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

이 코드에서는 먼저 차트에서 기존 범주와 시리즈를 지웁니다. 그런 다음 다음을 사용하여 시리즈에 데이터 포인트를 추가합니다. `getDataPoints().addDataPointForHistogramSeries` 마지막으로, 가로축 집계 유형을 '자동'으로 설정하고 프레젠테이션을 저장합니다.

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

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 히스토그램 차트를 만드는 방법을 살펴보았습니다. 히스토그램 차트는 연속적인 구간에 걸친 데이터 분포를 시각화하는 데 유용한 도구이며, 특히 통계 또는 분석 내용을 다룰 때 프레젠테이션에 강력한 기능을 더할 수 있습니다.

## 자주 묻는 질문

### Java용 Aspose.Slides를 어떻게 설치합니까?

Java용 Aspose.Slides 라이브러리를 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/). 해당 웹사이트에 제공된 설치 지침을 따르세요.

### 히스토그램 차트는 무엇에 사용되나요?

히스토그램 차트는 연속 구간에 걸친 데이터 분포를 시각화하는 데 사용됩니다. 통계학에서는 빈도 분포를 나타내는 데 흔히 사용됩니다.

### 히스토그램 차트의 모양을 사용자 지정할 수 있나요?

네, Aspose.Slides API를 사용하면 색상, 레이블, 축을 비롯한 차트 모양을 사용자 지정할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
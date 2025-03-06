---
title: Java 슬라이드 차트의 기본 마커
linktitle: Java 슬라이드 차트의 기본 마커
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 차트의 기본 마커로 Java 슬라이드를 만드는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 16
url: /ko/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Java 슬라이드 차트의 기본 마커 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 기본 마커가 있는 차트를 만드는 방법을 살펴보겠습니다. 기본 마커는 차트의 데이터 포인트를 강조 표시하기 위해 추가된 기호 또는 모양입니다. 데이터를 시각화하기 위해 마커가 포함된 꺾은선형 차트를 만들어 보겠습니다.

## 전제 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요.

## 1단계: 프레젠테이션 만들기

먼저 프레젠테이션을 만들고 여기에 슬라이드를 추가해 보겠습니다. 그런 다음 슬라이드에 차트를 추가하겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 2단계: 마커가 있는 선형 차트 추가

이제 마커가 있는 꺾은선형 차트를 슬라이드에 추가해 보겠습니다. 또한 차트에서 기본 데이터를 모두 지웁니다.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 3단계: 차트 데이터 채우기

샘플 데이터로 차트를 채울 것입니다. 이 예에서는 데이터 요소와 범주가 포함된 두 개의 계열을 만듭니다.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 시리즈 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// 시리즈 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 계열 데이터 채우기
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 4단계: 차트 사용자 정의

범례를 추가하고 모양을 조정하는 등 차트를 추가로 사용자 정의할 수 있습니다.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 5단계: 프레젠테이션 저장

마지막으로 차트가 포함된 프레젠테이션을 원하는 위치에 저장하세요.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 기본 마커가 있는 꺾은선형 차트를 만들었습니다.

## Java 슬라이드 차트의 기본 마커에 대한 전체 소스 코드

```java
        // 문서 디렉터리의 경로입니다.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //두 번째 차트 시리즈 가져오기
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //이제 계열 데이터를 채우는 중입니다.
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 결론

이 포괄적인 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트의 기본 마커로 Java 슬라이드를 만드는 방법을 배웠습니다. 프레젠테이션 설정부터 차트 모양 맞춤 설정, 결과 저장까지 전체 과정을 다루었습니다.

## FAQ

### 마커 기호를 어떻게 변경할 수 있나요?

각 데이터 포인트에 대한 마커 스타일을 설정하여 마커 기호를 사용자 정의할 수 있습니다. 사용`IDataPoint.setMarkerStyle()` 마커 기호를 변경하려면

### 차트 색상을 어떻게 조정하나요?

 차트 색상을 수정하려면`IChartSeriesFormat` 그리고`IShapeFillFormat` 채우기 및 선 속성을 설정하는 인터페이스입니다.

### 데이터 포인트에 라벨을 추가할 수 있나요?

 예, 다음을 사용하여 데이터 포인트에 라벨을 추가할 수 있습니다.`IDataPoint.getLabel()` 방법을 선택하고 필요에 따라 맞춤설정하세요.
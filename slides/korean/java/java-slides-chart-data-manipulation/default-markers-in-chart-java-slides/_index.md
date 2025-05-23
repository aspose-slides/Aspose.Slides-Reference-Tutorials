---
"description": "Aspose.Slides for Java를 사용하여 차트에 기본 마커가 포함된 Java 슬라이드를 만드는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드 차트의 기본 마커"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드 차트의 기본 마커"
"url": "/ko/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드 차트의 기본 마커


## Java 슬라이드 차트의 기본 마커 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 기본 마커가 있는 차트를 만드는 방법을 살펴보겠습니다. 기본 마커는 차트의 데이터 요소에 추가되어 강조 표시되는 기호나 도형입니다. 데이터를 시각화하기 위해 마커가 있는 선형 차트를 만들어 보겠습니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있고 Java 프로젝트에 설정되어 있는지 확인하세요.

## 1단계: 프레젠테이션 만들기

먼저 프레젠테이션을 만들고 슬라이드를 추가해 보겠습니다. 그런 다음 슬라이드에 차트를 추가해 보겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 2단계: 마커가 있는 선형 차트 추가

이제 슬라이드에 마커가 있는 선형 차트를 추가해 보겠습니다. 차트에서 기본 데이터도 모두 삭제하겠습니다.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 3단계: 차트 데이터 채우기

차트에 샘플 데이터를 채워 보겠습니다. 이 예에서는 데이터 포인트와 범주를 포함하는 두 개의 시리즈를 만들어 보겠습니다.

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

// 시리즈 데이터 채우기
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 4단계: 차트 사용자 지정

범례를 추가하거나 모양을 조정하는 등 차트를 더욱 세부적으로 사용자 지정할 수 있습니다.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 5단계: 프레젠테이션 저장

마지막으로 차트가 포함된 프레젠테이션을 원하는 위치에 저장합니다.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

이제 Aspose.Slides for Java를 사용하여 기본 마커가 포함된 선형 차트를 만들었습니다.

## Java Slides 차트의 기본 마커에 대한 전체 소스 코드

```java
        // 문서 디렉토리의 경로입니다.
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
            //두 번째 차트 시리즈를 가져가세요
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //이제 시리즈 데이터를 채우고 있습니다
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

이 포괄적인 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에 기본 마커가 포함된 Java 슬라이드를 만드는 방법을 알아보았습니다. 프레젠테이션 설정부터 차트 모양 사용자 지정 및 결과 저장까지 전체 과정을 다루었습니다.

## 자주 묻는 질문

### 마커 기호를 어떻게 변경할 수 있나요?

각 데이터 포인트에 대한 마커 스타일을 설정하여 마커 기호를 사용자 지정할 수 있습니다. `IDataPoint.setMarkerStyle()` 마커 기호를 변경합니다.

### 차트의 색상을 어떻게 조정하나요?

차트의 색상을 수정하려면 다음을 사용할 수 있습니다. `IChartSeriesFormat` 그리고 `IShapeFillFormat` 채우기 및 선 속성을 설정하는 인터페이스입니다.

### 데이터 포인트에 라벨을 추가할 수 있나요?

예, 다음을 사용하여 데이터 포인트에 레이블을 추가할 수 있습니다. `IDataPoint.getLabel()` 방법을 배우고 필요에 따라 사용자 정의합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
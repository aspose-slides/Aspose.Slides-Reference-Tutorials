---
title: Java 슬라이드에서 간격 너비 설정
linktitle: Java 슬라이드에서 간격 너비 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 간격 너비를 설정하는 방법을 알아보세요. PowerPoint 프레젠테이션의 차트 시각적 효과를 향상하세요.
weight: 21
url: /ko/java/data-manipulation/set-gap-width-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java의 간격 너비 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트의 간격 너비를 설정하는 과정을 안내합니다. 간격 너비는 차트의 열이나 막대 사이의 간격을 결정하여 차트의 시각적 모양을 제어할 수 있습니다.

## 전제 조건

 시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. Aspose 웹사이트에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 단계별 가이드

Aspose.Slides for Java를 사용하여 차트에서 간격 너비를 설정하려면 다음 단계를 따르세요.

### 1. 빈 프레젠테이션 만들기

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
```

### 2. 첫 번째 슬라이드에 액세스

```java
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. 기본 데이터가 포함된 차트 추가

```java
// 기본 데이터가 포함된 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. 차트 데이터 시트의 인덱스 설정

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
```

### 5. 차트 데이터 통합 문서 받기

```java
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. 차트에 시리즈 추가

```java
// 차트에 계열 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. 차트에 카테고리 추가

```java
// 차트에 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. 시리즈 데이터 채우기

```java
// 계열 데이터 채우기
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// 계열 데이터 포인트 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. 간격 너비 설정

```java
// 간격 너비 값 설정
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. 프레젠테이션 저장

```java
// 프레젠테이션을 차트와 함께 저장
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 간격 너비 설정에 대한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
// 기본 데이터가 포함된 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 두 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// 이제 계열 데이터를 채우는 중입니다.
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// GapWidth 값 설정
series.getParentSeriesGroup().setGapWidth(50);
// 차트와 함께 프레젠테이션 저장
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트의 간격 너비를 설정하는 방법을 배웠습니다. 간격 너비를 조정하면 차트의 열이나 막대 사이의 간격을 제어하여 데이터의 시각적 표현을 향상시킬 수 있습니다.

## FAQ

### 간격 너비 값을 어떻게 변경합니까?

 간격 너비를 변경하려면`setGapWidth` 에 대한 방법`ParentSeriesGroup`차트 시리즈 중 제공된 예에서는 Gap Width를 50으로 설정했지만 이 값을 원하는 간격으로 조정할 수 있습니다.

### 다른 차트 속성을 사용자 지정할 수 있나요?

예, Aspose.Slides for Java는 차트 사용자 정의를 위한 광범위한 기능을 제공합니다. 색상, 레이블, 제목 등과 같은 다양한 차트 속성을 수정할 수 있습니다. 차트 사용자 정의 옵션에 대한 자세한 내용은 API 참조를 확인하세요.

### 더 많은 리소스와 문서는 어디에서 찾을 수 있나요?

 Aspose.Slides for Java에 대한 포괄적인 문서와 추가 리소스는 다음 페이지에서 찾을 수 있습니다.[Aspose 웹사이트](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

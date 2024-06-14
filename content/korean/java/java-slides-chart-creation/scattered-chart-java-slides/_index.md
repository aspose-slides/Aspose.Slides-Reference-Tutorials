---
title: Java 슬라이드의 분산형 차트
linktitle: Java 슬라이드의 분산형 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java에서 분산형 차트를 만드는 방법을 알아보세요. 프레젠테이션의 데이터 시각화를 위한 Java 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 11
url: /ko/java/chart-creation/scattered-chart-java-slides/
---

## Aspose.Slides for Java의 분산형 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 분산형 차트를 만드는 과정을 안내합니다. 분산형 차트는 2차원 평면에서 데이터 요소를 시각화하는 데 유용합니다. 귀하의 편의를 위해 단계별 지침을 제공하고 Java 소스 코드를 포함하겠습니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. [Java용 Aspose.Slides](https://products.aspose.com/slides/java) 설치되었습니다.
2. Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 초기화

먼저 필요한 라이브러리를 가져오고 새 프레젠테이션을 만듭니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// 새 프레젠테이션 만들기
Presentation pres = new Presentation();
```

## 2단계: 슬라이드 추가 및 분산형 차트 만들기

 다음으로 슬라이드를 추가하고 그 위에 분산형 차트를 만듭니다. 우리는`ScatterWithSmoothLines`이 예에서는 차트 유형입니다.

```java
// 첫 번째 슬라이드 가져오기
ISlide slide = pres.getSlides().get_Item(0);

// 분산형 차트 만들기
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 3단계: 차트 데이터 준비

이제 분산형 차트에 사용할 데이터를 준비하겠습니다. 각각 여러 데이터 요소가 있는 두 개의 계열을 추가하겠습니다.

```java
// 기본 차트 데이터 워크시트 색인 가져오기
int defaultWorksheetIndex = 0;

// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 데모 시리즈 삭제
chart.getChartData().getSeries().clear();

// 첫 번째 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// 첫 번째 차트 시리즈를 살펴보세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 첫 번째 계열에 데이터 포인트 추가
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// 시리즈 유형 편집
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // 마커 크기 변경
series.getMarker().setSymbol(MarkerStyleType.Star); // 마커 기호 변경

// 두 번째 차트 시리즈 살펴보기
series = chart.getChartData().getSeries().get_Item(1);

// 두 번째 계열에 데이터 포인트 추가
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// 두 번째 계열의 표식 스타일 변경
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 4단계: 프레젠테이션 저장

마지막으로 분산형 차트가 포함된 프레젠테이션을 PPTX 파일로 저장합니다.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 분산형 차트를 성공적으로 만들었습니다. 이제 특정 데이터 및 디자인 요구 사항에 맞게 이 예를 추가로 사용자 정의할 수 있습니다.

## Java 슬라이드의 분산형 차트에 대한 전체 소스 코드
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//기본 차트 만들기
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// 기본 차트 데이터 워크시트 색인 가져오기
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 데모 시리즈 삭제
chart.getChartData().getSeries().clear();
// 새 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// 첫 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 거기에 새로운 포인트(1:3)를 추가하세요.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// 새 포인트 추가(2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// 시리즈 유형 편집
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// 차트 시리즈 마커 변경하기
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// 두 번째 차트 시리즈 가져오기
series = chart.getChartData().getSeries().get_Item(1);
// 거기에 새로운 포인트(5:2)를 추가하세요.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// 새 포인트 추가(3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// 새 포인트 추가(2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// 새 포인트 추가(5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// 차트 시리즈 마커 변경하기
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 분산형 차트를 만드는 과정을 안내했습니다. 분산형 차트는 2차원 공간에서 데이터 포인트를 시각화하는 강력한 도구로, 복잡한 데이터 관계를 더 쉽게 분석하고 이해할 수 있도록 해줍니다.

## FAQ

### 차트 유형을 어떻게 변경할 수 있나요?

 차트 유형을 변경하려면`setType` 차트 시리즈에 메소드를 적용하고 원하는 차트 유형을 제공합니다. 예를 들어,`series.setType(ChartType.Line)` 계열을 꺾은선형 차트로 변경합니다.

### 마커 크기와 스타일을 어떻게 사용자 정의합니까?

 다음을 사용하여 마커 크기와 스타일을 변경할 수 있습니다.`getMarker` 시리즈에 대한 메서드를 지정한 다음 크기와 기호 속성을 설정합니다. 예를 들어:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java 문서에서 더 많은 사용자 정의 옵션을 자유롭게 살펴보세요.

 교체하는 것을 기억하세요`"Your Document Directory"` 프레젠테이션을 저장하려는 실제 경로를 사용하세요.
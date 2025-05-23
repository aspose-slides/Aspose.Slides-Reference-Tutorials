---
"description": "Aspose.Slides를 사용하여 Java로 분산형 차트를 만드는 방법을 알아보세요. Java 소스 코드를 활용한 단계별 가이드를 통해 프레젠테이션에서 데이터를 시각화하는 방법을 알아보세요."
"linktitle": "Java 슬라이드의 분산형 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 분산형 차트"
"url": "/ko/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 분산형 차트


## Java용 Aspose.Slides의 산점 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 분산형 차트를 만드는 과정을 안내합니다. 분산형 차트는 2차원 평면에서 데이터 요소를 시각화하는 데 유용합니다. 단계별 지침을 제공하고 사용자의 편의를 위해 Java 소스 코드를 포함합니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. [Java용 Aspose.Slides](https://products.aspose.com/slides/java) 설치됨.
2. Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 초기화

먼저, 필요한 라이브러리를 가져와서 새로운 프레젠테이션을 만듭니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";

// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// 새로운 프레젠테이션을 만드세요
Presentation pres = new Presentation();
```

## 2단계: 슬라이드 추가 및 산점 차트 만들기

다음으로, 슬라이드를 추가하고 그 위에 분산형 차트를 만듭니다. `ScatterWithSmoothLines` 이 예에서는 차트 유형을 사용합니다.

```java
// 첫 번째 슬라이드를 받으세요
ISlide slide = pres.getSlides().get_Item(0);

// 산점도 만들기
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 3단계: 차트 데이터 준비

이제 분산형 차트에 사용할 데이터를 준비하겠습니다. 여러 개의 데이터 포인트를 포함하는 두 개의 시리즈를 추가합니다.

```java
// 기본 차트 데이터 워크시트 인덱스 가져오기
int defaultWorksheetIndex = 0;

// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 데모 시리즈 삭제
chart.getChartData().getSeries().clear();

// 첫 번째 시리즈를 추가합니다
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// 첫 번째 차트 시리즈를 살펴보세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 첫 번째 시리즈에 데이터 포인트 추가
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// 시리즈 유형 편집
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // 마커 크기 변경
series.getMarker().setSymbol(MarkerStyleType.Star); // 마커 기호 변경

// 두 번째 차트 시리즈를 살펴보세요
series = chart.getChartData().getSeries().get_Item(1);

// 두 번째 시리즈에 데이터 포인트 추가
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// 두 번째 시리즈의 마커 스타일 변경
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 4단계: 프레젠테이션 저장

마지막으로, 분산형 차트가 포함된 프레젠테이션을 PPTX 파일로 저장합니다.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

이것으로 끝입니다! Aspose.Slides for Java를 사용하여 분산형 차트를 성공적으로 만들었습니다. 이제 특정 데이터 및 디자인 요구 사항에 맞게 이 예제를 추가로 사용자 지정할 수 있습니다.

## Java 슬라이드의 분산형 차트에 대한 완전한 소스 코드
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// 기본 차트 만들기
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// 기본 차트 데이터 워크시트 인덱스 가져오기
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 데모 시리즈 삭제
chart.getChartData().getSeries().clear();
// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// 첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 거기에 새로운 지점(1:3)을 추가합니다.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// 새로운 포인트 추가 (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// 시리즈 유형 편집
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// 차트 시리즈 마커 변경
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// 두 번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(1);
// 거기에 새로운 지점(5:2)을 추가합니다.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// 새로운 지점 추가 (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// 새로운 지점 추가 (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// 새로운 지점 추가 (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// 차트 시리즈 마커 변경
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 분산형 차트를 만드는 과정을 안내해 드렸습니다. 분산형 차트는 2차원 공간에서 데이터 요소를 시각화하는 강력한 도구로, 복잡한 데이터 관계를 더 쉽게 분석하고 이해할 수 있도록 도와줍니다.

## 자주 묻는 질문

### 차트 유형을 어떻게 변경할 수 있나요?

차트 유형을 변경하려면 다음을 사용하세요. `setType` 차트 시리즈에서 메서드를 사용하고 원하는 차트 유형을 제공합니다. 예를 들어, `series.setType(ChartType.Line)` 시리즈를 선형 차트로 변경합니다.

### 마커 크기와 스타일을 사용자 지정하려면 어떻게 해야 하나요?

다음을 사용하여 마커 크기와 스타일을 변경할 수 있습니다. `getMarker` 시리즈에 메서드를 적용한 다음 크기 및 기호 속성을 설정합니다. 예:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java 설명서에서 더 많은 사용자 정의 옵션을 살펴보세요.

교체하는 것을 잊지 마세요 `"Your Document Directory"` 프레젠테이션을 저장하려는 실제 경로를 입력합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
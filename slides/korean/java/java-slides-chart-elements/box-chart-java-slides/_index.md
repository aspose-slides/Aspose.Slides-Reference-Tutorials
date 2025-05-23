---
"description": "Aspose.Slides를 사용하여 Java 프레젠테이션에서 상자형 차트를 만드는 방법을 알아보세요. 효과적인 데이터 시각화를 위한 단계별 가이드와 소스 코드가 포함되어 있습니다."
"linktitle": "Java 슬라이드의 상자 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 상자 차트"
"url": "/ko/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 상자 차트


## Java용 Aspose.Slides의 박스 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 상자 차트를 만드는 과정을 안내합니다. 상자 차트는 다양한 사분위수와 이상치를 포함하는 통계 데이터를 시각화하는 데 유용합니다. 시작하는 데 도움이 되도록 소스 코드와 함께 단계별 지침을 제공합니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java 라이브러리용 Aspose.Slides를 설치하고 구성했습니다.
- Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 초기화

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

이 단계에서는 기존 PowerPoint 파일(이 예에서는 "test.pptx")의 경로를 사용하여 프레젠테이션 객체를 초기화합니다.

## 2단계: 상자 차트 만들기

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

이 단계에서는 프레젠테이션의 첫 번째 슬라이드에 상자형 차트 도형을 만듭니다. 또한 차트에서 기존 범주와 계열을 모두 지웁니다.

## 3단계: 범주 정의

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

이 단계에서는 상자 차트의 범주를 정의합니다. `IChartDataWorkbook` 카테고리를 추가하고 그에 따라 라벨을 지정합니다.

## 4단계: 시리즈 만들기

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

여기서는 차트에 대한 BoxAndWhisker 시리즈를 만들고 사분위수 방법, 평균선, 평균 마커, 내부 점, 이상치 점과 같은 다양한 옵션을 구성합니다.

## 5단계: 데이터 포인트 추가

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

이 단계에서는 BoxAndWhisker 시리즈에 데이터 포인트를 추가합니다. 이 데이터 포인트는 차트의 통계 데이터를 나타냅니다.

## 6단계: 프레젠테이션 저장

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

마지막으로, 상자 차트가 포함된 프레젠테이션을 "BoxAndWhisker.pptx"라는 이름의 새 PowerPoint 파일에 저장합니다.

축하합니다! Aspose.Slides for Java를 사용하여 상자형 차트를 성공적으로 만들었습니다. 필요에 따라 다양한 속성을 조정하고 데이터 요소를 추가하여 차트를 더욱 세부적으로 사용자 지정할 수 있습니다.

## Java Slides의 상자 차트에 대한 완전한 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 상자 차트를 만드는 방법을 알아보았습니다. 상자 차트는 사분위수와 이상치를 포함한 통계 데이터를 시각화하는 데 유용한 도구입니다. Java 애플리케이션에서 상자 차트를 만드는 데 도움이 되도록 소스 코드와 함께 단계별 가이드를 제공했습니다.

## 자주 묻는 질문

### 상자 차트의 모양을 어떻게 바꿀 수 있나요?

선 스타일, 색상, 글꼴 등의 속성을 수정하여 상자 차트의 모양을 사용자 지정할 수 있습니다. 차트 사용자 지정에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 참조하세요.

### 박스 차트에 추가 데이터 시리즈를 추가할 수 있나요?

예, 추가적으로 생성하여 상자 차트에 여러 데이터 시리즈를 추가할 수 있습니다. `IChartSeries` 객체를 추가하고 객체에 데이터 포인트를 추가합니다.

### QuartileMethodType.Exclusive는 무엇을 의미하나요?

그만큼 `QuartileMethodType.Exclusive` 이 설정은 사분위수 계산이 배타적 방법을 사용하여 수행되어야 함을 지정합니다. 데이터와 요구 사항에 따라 다양한 사분위수 계산 방법을 선택할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
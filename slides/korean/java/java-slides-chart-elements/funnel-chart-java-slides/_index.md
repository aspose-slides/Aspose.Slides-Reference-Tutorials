---
"description": "단계별 튜토리얼을 통해 Aspose.Slides for Java를 살펴보고, 멋진 퍼널 차트 등을 제작해 보세요."
"linktitle": "Java 슬라이드의 퍼널 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 퍼널 차트"
"url": "/ko/java/chart-elements/funnel-chart-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 퍼널 차트


## Java 슬라이드의 퍼널 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 퍼널 차트를 만드는 방법을 보여드리겠습니다. 퍼널 차트는 판매 전환이나 고객 확보와 같이 단계적으로 좁혀지는 순차적 프로세스를 시각화하는 데 유용합니다.

## 필수 조건

시작하기 전에 Aspose.Slides 라이브러리가 Java 프로젝트에 추가되었는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 초기화

먼저 프레젠테이션을 초기화하고, 여기에 깔때기형 차트를 넣을 슬라이드를 추가해 보겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

교체를 꼭 해주세요 `"Your Document Directory"` 프로젝트 디렉토리의 실제 경로를 사용합니다.

## 2단계: 깔때기 차트 만들기

이제 깔때기형 차트를 만들고 슬라이드에 크기를 설정해 보겠습니다.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

위의 코드에서는 첫 번째 슬라이드에 좌표 (50, 50)에 너비 500, 높이 400픽셀의 깔때기형 차트를 추가합니다.

## 3단계: 차트 데이터 정의

다음으로, 깔때기형 차트의 데이터를 정의하고, 차트의 범주와 계열을 설정합니다.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

여기에서는 기존 데이터를 지우고, 카테고리(이 경우에는 깔때기의 단계)를 추가하고, 라벨을 설정합니다.

## 4단계: 데이터 포인트 추가

이제 깔때기형 차트 시리즈에 데이터 포인트를 추가해 보겠습니다.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

이 단계에서는 깔때기형 차트에 대한 시리즈를 만들고 깔때기의 각 단계의 값을 나타내는 데이터 포인트를 추가합니다.

## 5단계: 프레젠테이션 저장

마지막으로, 깔때기형 차트가 포함된 프레젠테이션을 PowerPoint 파일로 저장합니다.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

교체를 꼭 해주세요 `"Your Document Directory"` 원하는 저장 위치로 이동하세요.

## Java Slides의 Funnel Chart에 대한 완전한 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 깔때기형 차트를 만드는 방법을 보여드렸습니다. 색상, 레이블 및 기타 속성을 사용자의 필요에 맞게 조정하여 차트를 더욱 세부적으로 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### 깔때기형 차트의 모양을 어떻게 사용자 지정할 수 있나요?

차트, 시리즈 및 데이터 포인트의 속성을 수정하여 깔때기형 차트의 모양을 사용자 지정할 수 있습니다. 자세한 사용자 지정 옵션은 Aspose.Slides 설명서를 참조하세요.

### 퍼널 차트에 더 많은 카테고리나 데이터 포인트를 추가할 수 있나요?

네, 3단계와 4단계의 코드를 적절히 확장하여 퍼널 차트에 더 많은 카테고리와 데이터 포인트를 추가할 수 있습니다.

### 차트 유형을 깔때기형이 아닌 다른 유형으로 변경할 수 있나요?

네, Aspose.Slides는 다양한 차트 유형을 지원합니다. 차트 유형을 변경하려면 다음을 수행하세요. `ChartType.Funnel` 2단계에서 원하는 차트 유형을 선택합니다.

### Aspose.Slides를 사용하는 동안 오류나 예외를 어떻게 처리합니까?

표준 Java 예외 처리 메커니즘을 사용하여 오류와 예외를 처리할 수 있습니다. 예상치 못한 상황을 원활하게 처리하려면 코드에 적절한 오류 처리 기능이 있는지 확인하세요.

### Java용 Aspose.Slides에 대한 더 많은 예제와 문서는 어디에서 찾을 수 있나요?

Java용 Aspose.Slides 사용에 대한 더 많은 예제와 자세한 문서는 다음에서 찾을 수 있습니다. [선적 서류 비치](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
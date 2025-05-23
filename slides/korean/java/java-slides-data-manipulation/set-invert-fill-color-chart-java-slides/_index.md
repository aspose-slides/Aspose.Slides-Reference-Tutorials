---
"description": "Aspose.Slides를 사용하여 Java Slides 차트의 채우기 색상 반전을 설정하는 방법을 알아보세요. 이 단계별 가이드와 소스 코드를 활용하여 차트 시각화를 더욱 향상시켜 보세요."
"linktitle": "Java 슬라이드에서 채우기 색상 반전 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 채우기 색상 반전 설정"
"url": "/ko/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 채우기 색상 반전 설정


## Java 슬라이드에서 채우기 색상 반전 차트 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 차트의 채우기 색상 반전을 설정하는 방법을 보여드립니다. 채우기 색상 반전은 차트에서 음수 값을 특정 색상으로 강조하고 싶을 때 유용한 기능입니다. 이를 위한 단계별 지침과 소스 코드를 제공합니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java 라이브러리용 Aspose.Slides가 설치되었습니다.
2. Java 개발 환경 설정.

## 1단계: 프레젠테이션 만들기

먼저 차트를 추가할 프레젠테이션을 만들어야 합니다. 다음 코드를 사용하여 프레젠테이션을 만들 수 있습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

다음으로, 프레젠테이션에 클러스터형 세로 막대형 차트를 추가해 보겠습니다. 방법은 다음과 같습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 3단계: 차트 데이터 설정

이제 시리즈와 카테고리를 포함한 차트 데이터를 설정해 보겠습니다.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 새로운 시리즈 및 카테고리 추가
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## 4단계: 시리즈 데이터 채우기

이제 차트의 시리즈 데이터를 채워 보겠습니다.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 5단계: 채우기 색상 반전 설정

차트 시리즈의 채우기 색상 반전을 설정하려면 다음 코드를 사용할 수 있습니다.

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

위의 코드에서 음수 값에 대한 채우기 색상을 반전하도록 시리즈를 설정하고 반전된 채우기에 대한 색상을 지정합니다.

## 6단계: 프레젠테이션 저장

마지막으로 차트와 함께 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 채우기 색상 반전 설정 차트에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// 새로운 시리즈 및 카테고리 추가
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// 첫 번째 차트 시리즈를 가져와서 시리즈 데이터를 채웁니다.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides 차트의 채우기 색상 반전을 설정하는 방법을 살펴보았습니다. 이 기능을 사용하면 차트에서 음수 값을 특정 색상으로 강조 표시하여 데이터를 시각적으로 더욱 효과적으로 표현할 수 있습니다.

## 자주 묻는 질문

이 섹션에서는 Aspose.Slides for Java를 사용하여 Java Slides의 차트에 대한 채우기 색상 반전을 설정하는 것과 관련된 몇 가지 일반적인 질문에 답하겠습니다.

### Java용 Aspose.Slides를 어떻게 설치합니까?

Java 프로젝트에 Aspose.Slides JAR 파일을 포함하면 Java용 Aspose.Slides를 설치할 수 있습니다. 라이브러리는 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/). 해당 개발 환경에 맞는 설명서에 제공된 설치 지침을 따르세요.

### 차트 시리즈의 반전 채우기 색상을 사용자 정의할 수 있나요?

네, 차트 시리즈의 반전 채우기 색상을 사용자 지정할 수 있습니다. 제공된 코드 예제에서는 `series.getInvertedSolidFillColor().setColor(Color.RED)` 선은 반전된 채우기의 색상을 빨간색으로 설정합니다. 바꿀 수 있습니다. `Color.RED` 원하는 다른 색상으로 변경하세요.

### Java용 Aspose.Slides에서 차트 유형을 어떻게 수정할 수 있나요?

차트 유형을 변경하여 수정할 수 있습니다. `ChartType` 프레젠테이션에 차트를 추가할 때 매개변수를 사용합니다. 코드 예제에서는 `ChartType.ClusteredColumn`적절한 차트 유형을 지정하여 선형 차트, 막대형 차트, 원형 차트 등 다른 차트 유형을 탐색할 수 있습니다. `ChartType` 열거형 값.

### 차트에 여러 개의 데이터 시리즈를 추가하려면 어떻게 해야 하나요?

차트에 여러 데이터 시리즈를 추가하려면 다음을 사용할 수 있습니다. `chart.getChartData().getSeries().add(...)` 추가하려는 각 계열에 대해 메서드를 사용해야 합니다. 차트에 여러 계열을 채우려면 각 계열에 적합한 데이터 요소와 레이블을 제공해야 합니다.

### 차트 모양의 다른 측면을 사용자 지정할 수 있는 방법이 있나요?

네, Aspose.Slides for Java를 사용하면 축 레이블, 제목, 범례 등 차트 모양의 다양한 요소를 사용자 지정할 수 있습니다. 차트 요소 및 모양 사용자 지정에 대한 자세한 내용은 해당 설명서를 참조하세요.

### 차트를 다른 형식으로 저장할 수 있나요?

네, Aspose.Slides for Java를 사용하여 차트를 다양한 형식으로 저장할 수 있습니다. 제공된 코드 예제에서는 프레젠테이션을 PPTX 파일로 저장했습니다. `SaveFormat` 요구 사항에 따라 PDF, PNG, SVG 등 다른 형식으로 저장하는 옵션도 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
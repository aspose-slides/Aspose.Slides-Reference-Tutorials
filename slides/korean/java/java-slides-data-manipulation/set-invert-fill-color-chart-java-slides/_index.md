---
title: Java 슬라이드에서 반전 채우기 색상 차트 설정
linktitle: Java 슬라이드에서 반전 채우기 색상 차트 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java 슬라이드 차트의 채우기 색상 반전을 설정하는 방법을 알아보세요. 이 단계별 가이드와 소스 코드를 사용하여 차트 시각화를 강화하세요.
weight: 22
url: /ko/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드에서 반전 채우기 색상 차트 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 반전 채우기 색상을 설정하는 방법을 보여줍니다. 채우기 색상 반전은 차트에서 특정 색상으로 음수 값을 강조 표시하려는 경우 유용한 기능입니다. 이를 달성하기 위한 단계별 지침과 소스 코드를 제공할 것입니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java 라이브러리용 Aspose.Slides가 설치되었습니다.
2. Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 만들기

먼저 차트를 추가할 프레젠테이션을 만들어야 합니다. 다음 코드를 사용하여 프레젠테이션을 만들 수 있습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

다음으로 프레젠테이션에 클러스터형 세로 막대형 차트를 추가하겠습니다. 방법은 다음과 같습니다.

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

## 4단계: 계열 데이터 채우기

이제 차트의 계열 데이터를 채워 보겠습니다.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 5단계: 채우기 색상 반전 설정

차트 계열의 채우기 색상 반전을 설정하려면 다음 코드를 사용할 수 있습니다.

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

위의 코드에서는 음수 값에 대해 채우기 색상을 반전하도록 계열을 설정하고 반전된 채우기에 대한 색상을 지정했습니다.

## 6단계: 프레젠테이션 저장

마지막으로 차트와 함께 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 반전 채우기 색상 차트 설정에 대한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
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
// 첫 번째 차트 계열을 가져와 계열 데이터를 채웁니다.
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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 반전 채우기 색상을 설정하는 방법을 보여주었습니다. 이 기능을 사용하면 차트의 음수 값을 특정 색상으로 강조 표시하여 데이터를 시각적으로 더욱 유익하게 만들 수 있습니다.

## FAQ

이 섹션에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트의 채우기 색상 반전 설정과 관련된 몇 가지 일반적인 질문을 다룹니다.

### Java용 Aspose.Slides를 어떻게 설치하나요?

 Java 프로젝트에 Aspose.Slides JAR 파일을 포함시켜 Java용 Aspose.Slides를 설치할 수 있습니다. 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose.Slides for Java 다운로드 페이지](https://releases.aspose.com/slides/java/). 특정 개발 환경에 대한 설명서에 제공된 설치 지침을 따르십시오.

### 차트 시리즈의 반전 채우기 색상을 사용자 정의할 수 있나요?

예, 차트 시리즈의 반전된 채우기 색상을 사용자 정의할 수 있습니다. 제공된 코드 예제에서는`series.getInvertedSolidFillColor().setColor(Color.RED)` 선은 반전된 채우기에 대해 색상을 빨간색으로 설정합니다. 교체할 수 있습니다`Color.RED` 원하는 다른 색상으로.

### Aspose.Slides for Java에서 차트 유형을 어떻게 수정합니까?

 다음을 변경하여 차트 유형을 수정할 수 있습니다.`ChartType` 프레젠테이션에 차트를 추가할 때 매개변수입니다. 코드 예제에서는 다음을 사용했습니다.`ChartType.ClusteredColumn` . 적절한 항목을 지정하여 선 차트, 막대 차트, 원형 차트 등과 같은 다른 차트 유형을 탐색할 수 있습니다.`ChartType` 열거형 값.

### 여러 데이터 시리즈를 차트에 어떻게 추가하나요?

 차트에 여러 데이터 시리즈를 추가하려면 다음을 사용할 수 있습니다.`chart.getChartData().getSeries().add(...)` 추가하려는 각 시리즈에 대한 방법입니다. 차트를 여러 시리즈로 채우려면 각 시리즈에 적절한 데이터 요소와 레이블을 제공해야 합니다.

### 차트 모양의 다른 측면을 사용자 정의할 수 있는 방법이 있습니까?

예, Aspose.Slides for Java를 사용하면 축 레이블, 제목, 범례 등을 포함하여 차트 모양의 다양한 측면을 사용자 정의할 수 있습니다. 차트 요소 및 모양 사용자 정의에 대한 자세한 지침은 설명서를 참조하세요.

### 차트를 다른 형식으로 저장할 수 있나요?

 예, Aspose.Slides for Java를 사용하여 다양한 형식으로 차트를 저장할 수 있습니다. 제공된 코드 예제에서는 프레젠테이션을 PPTX 파일로 저장했습니다. 당신은 다른 사용할 수 있습니다`SaveFormat` 요구 사항에 따라 PDF, PNG 또는 SVG와 같은 다른 형식으로 저장할 수 있는 옵션이 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

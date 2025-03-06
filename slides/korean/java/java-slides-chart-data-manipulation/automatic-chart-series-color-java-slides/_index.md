---
title: Java 슬라이드의 자동 차트 시리즈 색상
linktitle: Java 슬라이드의 자동 차트 시리즈 색상
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 자동 시리즈 색상으로 동적 차트를 만드는 방법을 알아보세요. 손쉽게 데이터 시각화를 향상하세요.
weight: 14
url: /ko/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java의 자동 차트 시리즈 색상 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트가 포함된 PowerPoint 프레젠테이션을 만들고 차트 시리즈의 자동 채우기 색상을 설정하는 방법을 살펴보겠습니다. 자동 채우기 색상을 사용하면 차트를 시각적으로 더욱 매력적으로 만들고 라이브러리에서 색상을 선택하도록 하여 시간을 절약할 수 있습니다.

## 전제 조건

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 새 프레젠테이션 만들기

먼저 새 PowerPoint 프레젠테이션을 만들고 여기에 슬라이드를 추가하겠습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

다음으로 슬라이드에 묶은 세로 막대형 차트를 추가하겠습니다. 또한 값을 표시하도록 첫 번째 계열을 설정합니다.

```java
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
// 기본 데이터가 포함된 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 첫 번째 계열을 값 표시로 설정
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 3단계: 차트 데이터 채우기

이제 차트를 데이터로 채워보겠습니다. 기본으로 생성된 시리즈와 카테고리를 삭제한 다음 새 시리즈와 카테고리를 추가하는 것부터 시작하겠습니다.

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 기본 생성된 시리즈 및 카테고리 삭제
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 새 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 4단계: 계열 데이터 채우기

시리즈 1과 시리즈 2 모두에 대한 시리즈 데이터를 채울 것입니다.

```java
// 첫 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 이제 계열 데이터를 채우는 중입니다.
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 두 번째 차트 시리즈 가져오기
series = chart.getChartData().getSeries().get_Item(1);
// 이제 계열 데이터를 채우는 중입니다.
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 5단계: 시리즈의 자동 채우기 색상 설정

이제 차트 시리즈의 자동 채우기 색상을 설정해 보겠습니다. 이렇게 하면 도서관에서 우리를 위해 색상을 선택하게 됩니다.

```java
// 시리즈의 자동 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 6단계: 프레젠테이션 저장

마지막으로 차트가 포함된 프레젠테이션을 PowerPoint 파일로 저장하겠습니다.

```java
// 차트와 함께 프레젠테이션 저장
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 자동 차트 시리즈 색상에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
try
{
	// 첫 번째 슬라이드에 액세스
	ISlide slide = presentation.getSlides().get_Item(0);
	// 기본 데이터가 포함된 차트 추가
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// 첫 번째 계열을 값 표시로 설정
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// 차트 데이터 시트의 인덱스 설정
	int defaultWorksheetIndex = 0;
	// 차트 데이터 워크시트 가져오기
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// 기본 생성된 시리즈 및 카테고리 삭제
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// 새로운 시리즈 추가
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// 새 카테고리 추가
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// 첫 번째 차트 시리즈 가져오기
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// 이제 계열 데이터를 채우는 중입니다.
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// 시리즈의 자동 채우기 색상 설정
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// 두 번째 차트 시리즈 가져오기
	series = chart.getChartData().getSeries().get_Item(1);
	// 이제 계열 데이터를 채우는 중입니다.
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// 계열의 채우기 색상 설정
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// 차트와 함께 프레젠테이션 저장
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트가 포함된 PowerPoint 프레젠테이션을 만들고 차트 시리즈의 자동 채우기 색상을 설정하는 방법을 배웠습니다. 자동 색상은 차트의 시각적 매력을 향상시키고 프레젠테이션을 더욱 매력적으로 만들 수 있습니다. 특정 요구 사항에 따라 필요에 따라 차트를 추가로 사용자 정의할 수 있습니다.

## FAQ

### Aspose.Slides for Java에서 차트 시리즈의 자동 채우기 색상을 어떻게 설정합니까?

Aspose.Slides for Java에서 차트 시리즈의 자동 채우기 색상을 설정하려면 다음 코드를 사용하세요.

```java
// 시리즈의 자동 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

이 코드를 사용하면 라이브러리에서 차트 시리즈의 색상을 자동으로 선택할 수 있습니다.

### 필요한 경우 차트 색상을 맞춤설정할 수 있나요?

 예, 필요에 따라 차트 색상을 맞춤설정할 수 있습니다. 제공된 예에서는 자동 채우기 색상을 사용했지만`FillType` 그리고`SolidFillColor` 시리즈 형식의 속성입니다.

### 차트에 계열이나 범주를 추가하려면 어떻게 해야 합니까?

 차트에 계열이나 범주를 추가하려면`getSeries()` 그리고`getCategories()` 차트의 메소드`ChartData` 물체. 데이터와 레이블을 지정하여 새 계열과 범주를 추가할 수 있습니다.

### 차트와 라벨의 형식을 추가로 지정할 수 있나요?

예, 필요에 따라 차트, 계열 및 레이블의 서식을 추가로 지정할 수 있습니다. Aspose.Slides for Java는 글꼴, 색상, 스타일 등을 포함하여 차트에 대한 광범위한 서식 옵션을 제공합니다. 서식 지정 옵션에 대한 자세한 내용은 설명서를 참조하세요.

### Aspose.Slides for Java 작업에 대한 자세한 정보는 어디서 찾을 수 있나요?

 Aspose.Slides for Java에 대한 자세한 내용과 자세한 문서를 보려면 참조 문서를 방문하세요.[여기](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

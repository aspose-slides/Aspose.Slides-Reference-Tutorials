---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 자동 계열 색상이 적용된 동적 차트를 만드는 방법을 알아보세요. 데이터 시각화를 손쉽게 향상시켜 보세요."
"linktitle": "Java 슬라이드에서 차트 시리즈 자동 색상 지정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 차트 시리즈 자동 색상 지정"
"url": "/ko/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 차트 시리즈 자동 색상 지정


## Java용 Aspose.Slides에서 자동 차트 시리즈 색상 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트가 포함된 PowerPoint 프레젠테이션을 만들고 차트 시리즈에 자동 채우기 색상을 설정하는 방법을 살펴봅니다. 자동 채우기 색상을 사용하면 차트를 시각적으로 더욱 돋보이게 만들 수 있으며, 라이브러리에서 색상을 자동으로 선택해 주므로 작업 시간을 절약할 수 있습니다.

## 필수 조건

시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 새 프레젠테이션 만들기

먼저, 새로운 PowerPoint 프레젠테이션을 만들고 슬라이드를 추가해 보겠습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

다음으로, 슬라이드에 클러스터형 세로 막대형 차트를 추가하겠습니다. 또한 첫 번째 계열에 값을 표시하도록 설정하겠습니다.

```java
// 첫 번째 슬라이드에 접근하세요
ISlide slide = presentation.getSlides().get_Item(0);
// 기본 데이터로 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 첫 번째 시리즈를 값 표시로 설정
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 3단계: 차트 데이터 채우기

이제 차트에 데이터를 채워 보겠습니다. 먼저 기본적으로 생성된 시리즈와 카테고리를 삭제한 다음 새 시리즈와 카테고리를 추가합니다.

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 기본으로 생성된 시리즈 및 카테고리 삭제
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 새로운 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 4단계: 시리즈 데이터 채우기

시리즈 1과 시리즈 2 모두에 대한 시리즈 데이터를 채웁니다.

```java
// 첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 두 번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(1);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 5단계: 시리즈에 대한 자동 채우기 색상 설정

이제 차트 시리즈에 자동 채우기 색상을 설정해 보겠습니다. 이렇게 하면 라이브러리가 자동으로 색상을 선택합니다.

```java
// 시리즈에 대한 자동 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 6단계: 프레젠테이션 저장

마지막으로 차트가 포함된 프레젠테이션을 PowerPoint 파일로 저장합니다.

```java
// 차트와 함께 프레젠테이션 저장
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 자동 차트 시리즈 색상을 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
try
{
	// 첫 번째 슬라이드에 접근하세요
	ISlide slide = presentation.getSlides().get_Item(0);
	// 기본 데이터로 차트 추가
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// 첫 번째 시리즈를 값 표시로 설정
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// 차트 데이터 시트의 인덱스 설정
	int defaultWorksheetIndex = 0;
	// 차트 데이터 워크시트 가져오기
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// 기본으로 생성된 시리즈 및 카테고리 삭제
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// 새로운 시리즈 추가
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// 새로운 카테고리 추가
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// 첫 번째 차트 시리즈를 가져가세요
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// 이제 시리즈 데이터를 채우고 있습니다
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// 시리즈에 대한 자동 채우기 색상 설정
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// 두 번째 차트 시리즈를 가져가세요
	series = chart.getChartData().getSeries().get_Item(1);
	// 이제 시리즈 데이터를 채우고 있습니다
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// 시리즈의 채우기 색상 설정
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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트가 포함된 PowerPoint 프레젠테이션을 만들고 차트 시리즈에 자동 채우기 색상을 설정하는 방법을 알아보았습니다. 자동 색상은 차트의 시각적 효과를 높이고 프레젠테이션을 더욱 매력적으로 만들어 줍니다. 필요에 따라 특정 요구 사항에 맞게 차트를 추가로 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### Java용 Aspose.Slides에서 차트 시리즈의 자동 채우기 색상을 설정하려면 어떻게 해야 하나요?

Java용 Aspose.Slides에서 차트 시리즈의 자동 채우기 색상을 설정하려면 다음 코드를 사용하세요.

```java
// 시리즈에 대한 자동 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

이 코드를 사용하면 라이브러리가 차트 시리즈의 색상을 자동으로 선택할 수 있습니다.

### 필요한 경우 차트 색상을 사용자 정의할 수 있나요?

네, 필요에 따라 차트 색상을 사용자 지정할 수 있습니다. 제공된 예시에서는 자동 채우기 색상을 사용했지만, `FillType` 그리고 `SolidFillColor` 시리즈 형식의 속성입니다.

### 차트에 추가 시리즈나 카테고리를 추가하려면 어떻게 해야 하나요?

차트에 추가 시리즈나 카테고리를 추가하려면 다음을 사용하세요. `getSeries()` 그리고 `getCategories()` 차트의 방법 `ChartData` 객체입니다. 데이터와 레이블을 지정하여 새로운 시리즈와 범주를 추가할 수 있습니다.

### 차트와 라벨을 추가로 포맷할 수 있나요?

네, 필요에 따라 차트, 시리즈, 레이블의 서식을 추가로 지정할 수 있습니다. Aspose.Slides for Java는 글꼴, 색상, 스타일 등 차트에 대한 다양한 서식 옵션을 제공합니다. 서식 옵션에 대한 자세한 내용은 설명서를 참조하세요.

### Java용 Aspose.Slides 사용에 대한 자세한 정보는 어디에서 찾을 수 있나요?

Java용 Aspose.Slides에 대한 자세한 정보와 설명서는 참조 설명서를 참조하세요. [여기](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
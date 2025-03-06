---
title: Java 슬라이드에서 데이터 레이블 백분율 로그인 설정
linktitle: Java 슬라이드에서 데이터 레이블 백분율 로그인 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 백분율 기호로 데이터 레이블을 설정하는 방법을 알아보세요. 단계별 지침과 소스 코드를 사용하여 매력적인 차트를 만듭니다.
weight: 17
url: /ko/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java용 Aspose.Slides의 데이터 레이블 백분율 기호 설정 소개

이 가이드에서는 Aspose.Slides for Java를 사용하여 백분율 기호로 데이터 레이블을 설정하는 과정을 안내합니다. 누적 세로 막대형 차트가 포함된 PowerPoint 프레젠테이션을 만들고 백분율을 표시하도록 데이터 레이블을 구성하겠습니다.

## 전제 조건

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 추가되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 새 프레젠테이션 만들기

먼저 Aspose.Slides를 사용하여 새로운 PowerPoint 프레젠테이션을 만듭니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드 및 차트 추가

다음으로 프레젠테이션에 슬라이드와 누적 세로 막대형 차트를 추가합니다.

```java
// 슬라이드 참조 얻기
ISlide slide = presentation.getSlides().get_Item(0);

// 슬라이드에 PercentsStackedColumn 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 3단계: 축 번호 형식 구성

백분율을 표시하려면 차트의 세로 축에 대한 숫자 형식을 구성해야 합니다.

```java
// NumberFormatLinkedToSource를 false로 설정
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## 4단계: 차트 데이터 추가

시리즈와 데이터 포인트를 생성하여 차트에 데이터를 추가합니다. 이 예에서는 해당 데이터 요소가 있는 두 개의 계열을 추가합니다.

```java
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// 새 시리즈 추가
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// 새 시리즈 추가
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## 5단계: 데이터 레이블 사용자 정의

이제 데이터 레이블의 모양을 사용자 정의해 보겠습니다.

```java
// LabelFormat 속성 설정
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## 6단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 PowerPoint 파일로 저장합니다.

```java
// 프레젠테이션을 디스크에 쓰기
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

그게 다야! 누적 세로 막대형 차트가 포함된 PowerPoint 프레젠테이션을 성공적으로 만들고 Aspose.Slides for Java를 사용하여 백분율을 표시하도록 데이터 레이블을 구성했습니다.

## Java 슬라이드의 데이터 레이블 백분율 기호 설정을 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
// 슬라이드 참조 얻기
ISlide slide = presentation.getSlides().get_Item(0);
// 슬라이드에 PercentsStackedColumn 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// NumberFormatLinkedToSource를 false로 설정
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// 새 시리즈 추가
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// 시리즈 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// LabelFormat 속성 설정
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 새 시리즈 추가
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// 채우기 유형 및 색상 설정
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// 프레젠테이션을 디스크에 쓰기
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## 결론

이 가이드를 따르면 백분율 기반 데이터 레이블을 사용하여 매력적인 프레젠테이션을 만드는 방법을 배웠습니다. 이는 비즈니스 보고서, 교육 자료 등에서 정보를 효과적으로 전달하는 데 특히 유용할 수 있습니다.

## FAQ

### 차트 시리즈의 색상을 어떻게 변경할 수 있나요?

 다음을 사용하여 차트 시리즈의 채우기 색상을 변경할 수 있습니다.`setFill` 예제에 표시된 방법입니다.

### 데이터 레이블의 글꼴 크기를 사용자 정의할 수 있나요?

예, 다음을 설정하여 데이터 레이블의 글꼴 크기를 사용자 정의할 수 있습니다.`setFontHeight` 코드에 표시된 대로 속성을 사용합니다.

### 차트에 시리즈를 더 추가하려면 어떻게 해야 합니까?

 다음을 사용하여 차트에 계열을 추가할 수 있습니다.`add` 에 대한 방법`IChartSeriesCollection` 물체.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

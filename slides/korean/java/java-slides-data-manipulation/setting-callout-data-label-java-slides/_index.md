---
title: Java 슬라이드에서 데이터 레이블에 대한 콜아웃 설정
linktitle: Java 슬라이드에서 데이터 레이블에 대한 콜아웃 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides에서 데이터 레이블에 대한 콜아웃을 설정하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 25
url: /ko/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Aspose.Slides for Java에서 데이터 레이블에 대한 콜아웃 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트의 데이터 레이블에 대한 콜아웃을 설정하는 방법을 보여줍니다. 설명선은 차트의 특정 데이터 포인트를 강조 표시하는 데 유용할 수 있습니다. 코드를 단계별로 살펴보고 필요한 소스 코드를 제공하겠습니다.

## 전제 조건

- Java용 Aspose.Slides가 설치되어 있어야 합니다.
- Java 프로젝트를 생성하고 Aspose.Slides 라이브러리를 프로젝트에 추가합니다.

## 1단계: 프레젠테이션 만들기 및 차트 추가

 먼저 프레젠테이션을 만들고 슬라이드에 차트를 추가해야 합니다. 꼭 교체하세요`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 2단계: 차트 구성

다음으로 범례, 계열, 범주 등의 속성을 설정하여 차트를 구성하겠습니다.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// 시리즈 및 카테고리 구성(시리즈 및 카테고리 수 조정 가능)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // 여기에 데이터 포인트 추가
        // ...
        i++;
    }
    categoryIndex++;
}
```

## 3단계: 데이터 레이블 사용자 정의

이제 마지막 계열에 대한 콜아웃 설정을 포함하여 데이터 레이블을 사용자 정의하겠습니다.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // 데이터 포인트 형식 지정(채우기, 선 등)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //라벨 형식 지정(글꼴, 채우기 등)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // 콜아웃 활성화
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## 4단계: 프레젠테이션 저장

마지막으로 구성된 차트로 프레젠테이션을 저장합니다.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

이제 Aspose.Slides for Java를 사용하여 차트의 데이터 레이블에 대한 콜아웃을 성공적으로 설정했습니다. 특정 차트 및 데이터 요구 사항에 따라 코드를 사용자 정의하세요.

## Java 슬라이드의 데이터 레이블에 대한 콜아웃 설정을 위한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트의 데이터 레이블에 대한 콜아웃을 설정하는 방법을 살펴보았습니다. 콜아웃은 차트와 프리젠테이션에서 특정 데이터 포인트를 강조하는 데 유용한 도구입니다. 우리는 이러한 사용자 정의를 달성하는 데 도움이 되는 소스 코드와 함께 단계별 가이드를 제공했습니다.

## FAQ

### 데이터 레이블의 모양을 어떻게 사용자 정의합니까?

데이터 레이블의 모양을 사용자 정의하려면 글꼴, 채우기, 선 스타일 등의 속성을 수정하면 됩니다. 예를 들어:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### 데이터 레이블에 대한 콜아웃을 활성화하거나 비활성화하려면 어떻게 해야 합니까?

 데이터 레이블에 대한 콜아웃을 활성화하거나 비활성화하려면`setShowLabelAsDataCallout` 방법. 다음으로 설정하세요`true` 콜아웃을 활성화하고`false`비활성화합니다.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // 콜아웃 활성화
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // 콜아웃 비활성화
```

### 데이터 레이블의 지시선을 사용자 정의할 수 있습니까?

예, 선 스타일, 색상, 너비와 같은 속성을 사용하여 데이터 레이블의 지시선을 사용자 정의할 수 있습니다. 예를 들어:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // 지시선 활성화
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

다음은 Aspose.Slides for Java의 데이터 레이블 및 설명선에 대한 몇 가지 일반적인 사용자 정의 옵션입니다. 특정 요구 사항에 맞게 모양을 추가로 조정할 수 있습니다.
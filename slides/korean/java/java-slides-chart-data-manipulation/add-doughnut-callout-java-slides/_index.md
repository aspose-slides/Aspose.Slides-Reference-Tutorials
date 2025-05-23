---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드에 도넛 콜아웃을 추가하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드를 통해 더욱 향상된 프레젠테이션을 완성하세요."
"linktitle": "Java Slides에 도넛 콜아웃 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에 도넛 콜아웃 추가"
"url": "/ko/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에 도넛 콜아웃 추가


## Aspose.Slides for Java를 사용하여 Java Slides에 도넛 콜아웃을 추가하는 방법 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 슬라이드에 도넛 콜아웃을 추가하는 과정을 안내합니다. 도넛 콜아웃은 도넛 차트에서 특정 데이터 포인트를 강조하는 데 사용할 수 있는 차트 요소입니다. 편의를 위해 단계별 지침과 전체 소스 코드를 제공합니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. 자바 개발 환경
2. Java용 Aspose.Slides 라이브러리
3. Eclipse 또는 IntelliJ IDEA와 같은 통합 개발 환경(IDE)
4. 도넛 콜아웃을 추가하려는 PowerPoint 프레젠테이션

## 1단계: Java 프로젝트 설정

1. 선택한 IDE에서 새로운 Java 프로젝트를 만듭니다.
2. 프로젝트에 종속성으로 Aspose.Slides for Java 라이브러리를 추가합니다.

## 2단계: 프레젠테이션 초기화

시작하려면 PowerPoint 프레젠테이션을 초기화하고 도넛 콜아웃을 추가할 슬라이드를 만들어야 합니다. 이를 위한 코드는 다음과 같습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

교체를 꼭 해주세요 `"Your Document Directory"` PowerPoint 프레젠테이션 파일의 실제 경로를 포함합니다.

## 3단계: 도넛 차트 만들기

다음으로, 슬라이드에 도넛형 차트를 만들어 보겠습니다. 필요에 따라 차트의 위치와 크기를 사용자 지정할 수 있습니다. 도넛형 차트를 추가하는 코드는 다음과 같습니다.

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 4단계: 도넛 차트 사용자 지정

이제 도넛 차트를 사용자 지정할 차례입니다. 범례 제거, 구멍 크기 구성, 첫 번째 슬라이스 각도 조정 등 다양한 속성을 설정해 보겠습니다. 코드는 다음과 같습니다.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

이 코드 조각은 도넛형 차트의 속성을 설정합니다. 특정 요구 사항에 맞게 값을 조정할 수 있습니다.

## 5단계: 도넛 차트에 데이터 추가

이제 도넛 차트에 데이터를 추가해 보겠습니다. 데이터 포인트의 모양도 사용자 지정해 보겠습니다. 이 작업을 수행하는 코드는 다음과 같습니다.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // 여기에서 데이터 포인트 모양을 사용자 정의하세요
        i++;
    }
    categoryIndex++;
}
```

이 코드에서는 도넛 차트에 범주와 데이터 요소를 추가합니다. 필요에 따라 데이터 요소의 모양을 추가로 사용자 지정할 수 있습니다.

## 6단계: 프레젠테이션 저장

마지막으로, 도넛 콜아웃을 추가한 후에는 프레젠테이션을 저장하는 것을 잊지 마세요. 프레젠테이션을 저장하는 코드는 다음과 같습니다.

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

교체를 꼭 해주세요 `"chart.pptx"` 원하는 파일 이름으로.

축하합니다! Aspose.Slides for Java를 사용하여 Java 슬라이드에 도넛형 설명선을 성공적으로 추가했습니다. 이제 Java 애플리케이션을 실행하여 도넛형 차트와 설명선이 포함된 PowerPoint 프레젠테이션을 생성할 수 있습니다.

## Java 슬라이드에 도넛 콜아웃 추가를 위한 전체 소스 코드

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에 도넛 콜아웃을 추가하는 과정을 살펴보았습니다. 도넛 차트를 만들고, 모양을 사용자 지정하고, 데이터 포인트를 추가하는 방법을 알아보았습니다. 이 강력한 라이브러리를 활용하여 프레젠테이션을 더욱 풍성하게 만들고 더 많은 차트 기능을 활용해 보세요.

## 자주 묻는 질문

### 도넛 콜아웃의 모양을 어떻게 바꿀 수 있나요?

차트의 데이터 포인트 속성을 수정하여 도넛 콜아웃의 모양을 사용자 지정할 수 있습니다. 제공된 코드에서 데이터 포인트의 채우기 색, 선 색, 글꼴 스타일 및 기타 속성을 설정하는 방법을 확인할 수 있습니다.

### 도넛 차트에 더 많은 데이터 포인트를 추가할 수 있나요?

네, 도넛 차트에 필요한 만큼 데이터 포인트를 추가할 수 있습니다. 범주와 데이터 포인트가 추가되는 코드에서 루프를 확장하고 적절한 데이터와 형식을 제공하기만 하면 됩니다.

### 슬라이드에서 도넛형 차트의 위치와 크기를 어떻게 조정할 수 있나요?

도넛 차트의 위치와 크기는 매개변수를 수정하여 변경할 수 있습니다. `addChart` 이 방법의 네 숫자는 각각 차트의 왼쪽 상단 모서리의 X 및 Y 좌표와 너비, 높이에 해당합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 차트 데이터 레이블의 실제 위치를 가져오는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기"
"url": "/ko/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기


## Java 슬라이드에서 차트 데이터 레이블의 실제 위치를 가져오는 방법 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 데이터 레이블의 실제 위치를 가져오는 방법을 알아봅니다. 차트가 포함된 PowerPoint 프레젠테이션을 생성하고, 데이터 레이블을 사용자 정의하고, 이러한 데이터 레이블의 위치를 나타내는 도형을 추가하는 Java 프로그램을 만들어 보겠습니다.

## 필수 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설정되어 있는지 확인하세요.

## 1단계: PowerPoint 프레젠테이션 만들기

먼저, 새 PowerPoint 프레젠테이션을 만들고 차트를 추가해 보겠습니다. 차트의 데이터 레이블은 이 튜토리얼의 후반부에서 사용자 지정하겠습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 2단계: 데이터 레이블 사용자 지정
이제 차트 시리즈의 데이터 레이블을 사용자 지정해 보겠습니다. 레이블의 위치를 설정하고 값을 표시하겠습니다.

```java
try {
    // ... (이전 코드)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (나머지 코드)
} finally {
    if (pres != null) pres.dispose();
}
```

## 3단계: 데이터 레이블의 실제 위치 가져오기
이 단계에서는 차트 시리즈의 데이터 포인트를 반복하고 값이 4보다 큰 데이터 레이블의 실제 위치를 검색합니다. 그런 다음 이러한 위치를 나타내기 위해 줄임표를 추가합니다.

```java
try {
    // ... (이전 코드)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (나머지 코드)
} finally {
    if (pres != null) pres.dispose();
}
```

## 4단계: 프레젠테이션 저장
마지막으로, 생성된 프레젠테이션을 파일로 저장합니다.

```java
try {
    // ... (이전 코드)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java 슬라이드에서 차트 데이터 레이블의 실제 위치를 가져오기 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//할 일
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 차트 데이터 레이블의 실제 위치를 가져오는 방법을 알아보았습니다. 이제 이 지식을 활용하여 사용자 지정 데이터 레이블과 위치의 시각적 표현을 통해 PowerPoint 프레젠테이션을 더욱 풍부하게 만들 수 있습니다.

## 자주 묻는 질문

### 차트의 데이터 레이블을 사용자 지정하려면 어떻게 해야 하나요?

차트에서 데이터 레이블을 사용자 지정하려면 다음을 사용할 수 있습니다. `setDefaultDataLabelFormat` 차트 시리즈에서 메서드를 사용하고 위치 및 표시 여부와 같은 속성을 설정합니다. 예:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### 데이터 레이블 위치를 나타내는 모양을 추가하려면 어떻게 해야 하나요?

차트 시리즈의 데이터 포인트를 반복하고 다음을 사용할 수 있습니다. `getActualX`, `getActualY`, `getActualWidth`, 그리고 `getActualHeight` 데이터 레이블의 메서드를 사용하여 위치를 가져옵니다. 그런 다음 다음을 사용하여 모양을 추가할 수 있습니다. `addAutoShape` 방법입니다. 예를 들면 다음과 같습니다.
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 생성된 프레젠테이션을 어떻게 저장할 수 있나요?

생성된 프레젠테이션을 다음을 사용하여 저장할 수 있습니다. `save` 방법. 원하는 파일 경로와 `SaveFormat` 매개변수로 사용합니다. 예:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
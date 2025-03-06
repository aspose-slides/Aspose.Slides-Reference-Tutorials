---
title: Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기
linktitle: Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 데이터 레이블의 실제 위치를 얻는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
weight: 18
url: /ko/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기


## Java 슬라이드에서 차트 데이터 레이블의 실제 위치 가져오기 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 데이터 레이블의 실제 위치를 검색하는 방법을 배웁니다. 차트가 포함된 PowerPoint 프레젠테이션을 생성하고 데이터 레이블을 사용자 정의한 다음 이러한 데이터 레이블의 위치를 나타내는 모양을 추가하는 Java 프로그램을 만듭니다.

## 전제 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설정되어 있는지 확인하세요.

## 1단계: PowerPoint 프레젠테이션 만들기

먼저 새 PowerPoint 프레젠테이션을 만들고 여기에 차트를 추가해 보겠습니다. 튜토리얼의 뒷부분에서 차트의 데이터 레이블을 사용자 정의할 것입니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 2단계: 데이터 레이블 사용자 정의
이제 차트 계열의 데이터 레이블을 사용자 정의해 보겠습니다. 위치를 설정하고 값을 표시하겠습니다.

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
이 단계에서는 차트 시리즈의 데이터 포인트를 반복하고 4보다 큰 값을 갖는 데이터 레이블의 실제 위치를 검색합니다. 그런 다음 이러한 위치를 나타내는 타원을 추가합니다.

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
마지막으로 생성된 프레젠테이션을 파일에 저장합니다.

```java
try {
    // ... (이전 코드)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java 슬라이드에서 차트 데이터 레이블의 실제 위치를 얻기 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//할 것
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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 데이터 레이블의 실제 위치를 검색하는 방법을 배웠습니다. 이제 이 지식을 사용하여 사용자 정의된 데이터 레이블과 해당 위치의 시각적 표현으로 PowerPoint 프레젠테이션을 향상시킬 수 있습니다.

## FAQ

### 차트의 데이터 레이블을 어떻게 사용자 정의할 수 있나요?

 차트의 데이터 레이블을 사용자 정의하려면 다음을 사용할 수 있습니다.`setDefaultDataLabelFormat` 차트 시리즈에 대한 메서드를 사용하고 위치 및 가시성과 같은 속성을 설정합니다. 예를 들어:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### 데이터 레이블 위치를 나타내기 위해 도형을 추가하려면 어떻게 해야 합니까?

 차트 시리즈의 데이터 포인트를 반복하고`getActualX`, `getActualY`, `getActualWidth` , 그리고`getActualHeight`데이터 레이블의 메소드를 사용하여 해당 위치를 가져옵니다. 그런 다음`addAutoShape` 방법. 예는 다음과 같습니다.
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### 생성된 프레젠테이션을 어떻게 저장하나요?

 생성된 프리젠테이션을 다음을 사용하여 저장할 수 있습니다.`save` 방법. 원하는 파일 경로와`SaveFormat` 매개변수로. 예를 들어:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

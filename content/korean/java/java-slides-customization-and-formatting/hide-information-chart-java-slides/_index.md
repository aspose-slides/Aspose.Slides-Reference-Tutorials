---
title: Java 슬라이드의 차트에서 정보 숨기기
linktitle: Java 슬라이드의 차트에서 정보 숨기기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 요소를 숨기는 방법을 알아보세요. 단계별 지침과 소스 코드를 통해 명확성과 미학을 위해 프레젠테이션을 사용자 정의하세요.
type: docs
weight: 13
url: /ko/java/customization-and-formatting/hide-information-chart-java-slides/
---

## Java 슬라이드의 차트에서 정보 숨기기 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 차트에서 다양한 요소를 숨기는 방법을 살펴보겠습니다. 이 코드를 사용하여 프레젠테이션에 필요한 대로 차트를 사용자 정의할 수 있습니다.

## 1단계: 환경 설정

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 추가되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 2단계: 새 프레젠테이션 만들기

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3단계: 슬라이드에 차트 추가

마커가 있는 꺾은선형 차트를 슬라이드에 추가한 다음 차트의 다양한 요소를 숨기는 작업을 진행하겠습니다.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## 4단계: 차트 제목 숨기기

다음과 같이 차트 제목을 숨길 수 있습니다.

```java
chart.setTitle(false);
```

## 5단계: 값 축 숨기기

값 축(세로 축)을 숨기려면 다음 코드를 사용합니다.

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## 6단계: 카테고리 축 숨기기

범주 축(가로 축)을 숨기려면 다음 코드를 사용하세요.

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## 7단계: 범례 숨기기

다음과 같이 차트의 범례를 숨길 수 있습니다.

```java
chart.setLegend(false);
```

## 8단계: 주요 그리드선 숨기기

가로 축의 주요 그리드 선을 숨기려면 다음 코드를 사용할 수 있습니다.

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## 9단계: 시리즈 제거

차트에서 모든 계열을 제거하려면 다음과 같은 루프를 사용할 수 있습니다.

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## 10단계: 차트 시리즈 사용자 정의

필요에 따라 차트 시리즈를 사용자 정의할 수 있습니다. 이 예에서는 표식 스타일, 데이터 레이블 위치, 표식 크기, 선 색상 및 대시 스타일을 변경합니다.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## 11단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 파일에 저장합니다.

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 Java 슬라이드의 차트에서 다양한 요소를 성공적으로 숨겼습니다. 특정 요구 사항에 따라 필요에 따라 차트와 프리젠테이션을 추가로 사용자 정의할 수 있습니다.

## Java 슬라이드의 차트에서 정보 숨기기를 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//차트 제목 숨기기
	chart.setTitle(false);
	///값 축 숨기기
	chart.getAxes().getVerticalAxis().setVisible(false);
	//카테고리 축 가시성
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//숨겨진 전설
	chart.setLegend(false);
	//MajorGridLine 숨기기
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//계열선 색상 설정
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## 결론

이 단계별 가이드에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 차트에서 다양한 요소를 숨기는 방법을 살펴보았습니다. 이는 프레젠테이션을 위해 차트를 사용자 정의하고 시각적으로 더욱 매력적으로 만들거나 특정 요구 사항에 맞게 조정해야 할 때 매우 유용할 수 있습니다.

## FAQ

### 차트 요소의 모양을 추가로 사용자 정의하려면 어떻게 해야 합니까?

차트 시리즈, 마커, 레이블, 형식의 해당 속성에 접근하여 선 색상, 채우기 색상, 마커 스타일 등과 같은 차트 요소의 다양한 속성을 사용자 정의할 수 있습니다.

### 차트에서 특정 데이터 포인트를 숨길 수 있나요?

예, 차트 시리즈의 데이터를 조작하여 특정 데이터 포인트를 숨길 수 있습니다. 데이터 요소를 제거하거나 해당 값을 null로 설정하여 숨길 수 있습니다.

### 차트에 계열을 추가하려면 어떻게 해야 합니까?

 다음을 사용하여 차트에 더 많은 계열을 추가할 수 있습니다.`IChartData.getSeries().add` 방법을 사용하고 새 계열에 대한 데이터 포인트를 지정합니다.

### 차트 유형을 동적으로 변경할 수 있나요?

예, 원하는 유형의 새 차트를 만들고 이전 차트의 데이터를 새 차트에 복사하여 차트 유형을 동적으로 변경할 수 있습니다.

### 프로그래밍 방식으로 차트 제목과 축 레이블을 어떻게 변경할 수 있나요?

해당 속성에 액세스하고 원하는 텍스트와 서식을 설정하여 차트와 축의 제목과 레이블을 설정할 수 있습니다.
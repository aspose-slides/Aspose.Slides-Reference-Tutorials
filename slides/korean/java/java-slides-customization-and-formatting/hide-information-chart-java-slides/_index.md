---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 차트 요소를 숨기는 방법을 알아보세요. 단계별 가이드와 소스 코드를 활용하여 명확성과 미적인 요소를 고려하여 프레젠테이션을 맞춤 설정하세요."
"linktitle": "Java Slides에서 차트 정보 숨기기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 차트 정보 숨기기"
"url": "/ko/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 차트 정보 숨기기


## Java Slides에서 차트에서 정보 숨기기 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides 차트에서 다양한 요소를 숨기는 방법을 살펴보겠습니다. 이 코드를 사용하여 프레젠테이션에 맞게 차트를 사용자 지정할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Slides for Java 라이브러리가 프로젝트에 추가되었는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 2단계: 새 프레젠테이션 만들기

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3단계: 슬라이드에 차트 추가

슬라이드에 마커가 있는 선형 차트를 추가한 다음 차트의 다양한 요소를 숨기겠습니다.

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

값 축(수직 축)을 숨기려면 다음 코드를 사용하세요.

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## 6단계: 카테고리 축 숨기기

카테고리 축(수평 축)을 숨기려면 다음 코드를 사용하세요.

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## 7단계: 범례 숨기기

차트의 범례를 다음과 같이 숨길 수 있습니다.

```java
chart.setLegend(false);
```

## 8단계: 주요 격자선 숨기기

수평축의 주요 격자선을 숨기려면 다음 코드를 사용할 수 있습니다.

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## 9단계: 시리즈 제거

차트에서 모든 시리즈를 제거하려면 다음과 같은 루프를 사용할 수 있습니다.

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## 10단계: 차트 시리즈 사용자 지정

필요에 따라 차트 시리즈를 사용자 지정할 수 있습니다. 이 예시에서는 마커 스타일, 데이터 레이블 위치, 마커 크기, 선 색상, 그리고 점선 스타일을 변경해 보겠습니다.

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

마지막으로 프레젠테이션을 파일로 저장합니다.

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

이것으로 끝입니다! Aspose.Slides for Java를 사용하여 Java Slides 차트에서 다양한 요소를 성공적으로 숨겼습니다. 필요에 따라 차트와 프레젠테이션을 더욱 세부적으로 사용자 지정할 수 있습니다.

## Java 슬라이드에서 차트의 정보를 숨기기 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//차트 제목 숨기기
	chart.setTitle(false);
	///값 숨기기 축
	chart.getAxes().getVerticalAxis().setVisible(false);
	//카테고리 축 가시성
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//숨겨진 전설
	chart.setLegend(false);
	//주요 격자선 숨기기
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
	//시리즈 라인 색상 설정
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

이 단계별 가이드에서는 Aspose.Slides for Java API를 사용하여 Java Slides 차트에서 다양한 요소를 숨기는 방법을 살펴보았습니다. 이 기능은 프레젠테이션용 차트를 사용자 지정하고 시각적으로 더 매력적으로 만들거나 특정 요구 사항에 맞게 조정해야 할 때 매우 유용합니다.

## 자주 묻는 질문

### 차트 요소의 모양을 더욱 세부적으로 사용자 지정하려면 어떻게 해야 하나요?

차트 시리즈, 마커, 레이블 및 형식의 해당 속성에 액세스하여 선 색상, 채우기 색상, 마커 스타일 등 차트 요소의 다양한 속성을 사용자 지정할 수 있습니다.

### 차트에서 특정 데이터 포인트를 숨길 수 있나요?

네, 차트 시리즈의 데이터를 조작하여 특정 데이터 포인트를 숨길 수 있습니다. 데이터 포인트를 제거하거나 값을 null로 설정하여 숨길 수 있습니다.

### 차트에 추가 시리즈를 어떻게 추가할 수 있나요?

차트에 더 많은 시리즈를 추가하려면 다음을 사용하세요. `IChartData.getSeries().add` 방법을 선택하고 새로운 시리즈에 대한 데이터 포인트를 지정합니다.

### 차트 유형을 동적으로 변경할 수 있나요?

네, 원하는 유형의 새 차트를 만들고 이전 차트의 데이터를 새 차트로 복사하여 차트 유형을 동적으로 변경할 수 있습니다.

### 차트의 제목과 축 레이블을 프로그래밍 방식으로 변경하려면 어떻게 해야 합니까?

차트와 축의 제목과 레이블을 설정하려면 해당 속성에 액세스하고 원하는 텍스트와 서식을 설정하면 됩니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
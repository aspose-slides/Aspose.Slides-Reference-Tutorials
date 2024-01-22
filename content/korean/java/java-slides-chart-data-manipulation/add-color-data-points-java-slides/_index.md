---
title: Java 슬라이드의 데이터 포인트에 색상 추가
linktitle: Java 슬라이드의 데이터 포인트에 색상 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Java 슬라이드의 데이터 포인트에 색상 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 보여줍니다. 이 단계별 가이드에는 이 작업을 수행하는 데 도움이 되는 소스 코드 예제가 포함되어 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Aspose.Slides for Java 라이브러리

## 1단계: 새 프레젠테이션 만들기

먼저 Aspose.Slides for Java를 사용하여 새 프레젠테이션을 만듭니다. 이 프리젠테이션은 차트의 컨테이너 역할을 합니다.

```java
Presentation pres = new Presentation();
```

## 2단계: 햇살 차트 추가

이제 프레젠테이션에 Sunburst 차트를 추가해 보겠습니다. 차트 유형, 위치 및 크기를 지정합니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 3단계: 데이터 포인트에 액세스

 차트의 데이터 포인트를 수정하려면`IChartDataPointCollection` 물체.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 4단계: 데이터 포인트 사용자 정의

이 단계에서는 특정 데이터 포인트를 맞춤설정합니다. 여기서는 데이터 포인트의 색상을 변경하고 레이블 설정을 구성합니다.

```java
// 데이터 포인트 0 사용자 정의
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// 데이터 포인트 9 사용자 정의
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## 5단계: 프레젠테이션 저장

마지막으로 사용자 정의된 차트로 프레젠테이션을 저장하세요.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 Java 슬라이드의 특정 데이터 포인트에 색상을 성공적으로 추가했습니다.

## Java 슬라이드의 데이터 포인트에 색상을 추가하기 위한 완전한 소스 코드

```java
Presentation pres = new Presentation();
try
{
	// 문서 디렉터리의 경로입니다.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//할 것
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 배웠습니다. 특정 요구 사항에 따라 차트와 프리젠테이션을 추가로 사용자 정의할 수 있습니다.

## FAQ

### 다른 데이터 포인트의 색상을 어떻게 변경할 수 있나요?

다른 데이터 포인트의 색상을 변경하려면 4단계에 표시된 것과 유사한 접근 방식을 따를 수 있습니다. 사용자 정의하려는 데이터 포인트에 액세스하고 색상 및 레이블 설정을 수정합니다.

### 차트의 다른 측면을 사용자 정의할 수 있나요?

 예, 글꼴, 레이블, 제목 등을 포함하여 차트의 다양한 측면을 사용자 정의할 수 있습니다. 다음을 참조하세요.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 자세한 사용자 정의 옵션을 확인하세요.

### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?

 Aspose.Slides for Java 사용에 대한 더 많은 예제와 자세한 문서는 다음 페이지에서 찾을 수 있습니다.[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 웹사이트.
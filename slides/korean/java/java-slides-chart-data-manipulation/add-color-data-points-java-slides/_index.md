---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 알아보세요."
"linktitle": "Java 슬라이드에서 데이터 포인트에 색상 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 데이터 포인트에 색상 추가"
"url": "/ko/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 데이터 포인트에 색상 추가


## Java 슬라이드에서 데이터 포인트에 색상 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 보여드립니다. 이 단계별 가이드에는 이 작업을 수행하는 데 도움이 되는 소스 코드 예제가 포함되어 있습니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Java용 Aspose.Slides 라이브러리

## 1단계: 새 프레젠테이션 만들기

먼저, Aspose.Slides for Java를 사용하여 새 프레젠테이션을 만들어 보겠습니다. 이 프레젠테이션은 차트의 컨테이너 역할을 할 것입니다.

```java
Presentation pres = new Presentation();
```

## 2단계: 선버스트 차트 추가

이제 프레젠테이션에 선버스트 차트를 추가해 보겠습니다. 차트 유형, 위치, 크기를 지정합니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 3단계: 데이터 포인트 액세스

차트의 데이터 포인트를 수정하려면 다음에 액세스해야 합니다. `IChartDataPointCollection` 물체.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 4단계: 데이터 포인트 사용자 지정

이 단계에서는 특정 데이터 포인트를 사용자 지정해 보겠습니다. 여기서는 데이터 포인트의 색상을 변경하고 레이블 설정을 구성해 보겠습니다.

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

마지막으로, 사용자 정의된 차트로 프레젠테이션을 저장합니다.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

이제 끝입니다! Aspose.Slides for Java를 사용하여 Java 슬라이드의 특정 데이터 포인트에 색상을 추가하는 데 성공했습니다.

## Java 슬라이드에서 데이터 포인트에 색상을 추가하는 전체 소스 코드

```java
Presentation pres = new Presentation();
try
{
	// 문서 디렉토리의 경로입니다.
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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//할 일
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 데이터 포인트에 색상을 추가하는 방법을 알아보았습니다. 특정 요구 사항에 따라 차트와 프레젠테이션을 더욱 세부적으로 맞춤 설정할 수 있습니다.

## 자주 묻는 질문

### 다른 데이터 포인트의 색상을 어떻게 변경할 수 있나요?

다른 데이터 포인트의 색상을 변경하려면 4단계에서 보여준 것과 비슷한 방법을 따르면 됩니다. 사용자 지정하려는 데이터 포인트에 액세스하여 색상 및 레이블 설정을 수정합니다.

### 차트의 다른 측면을 사용자 정의할 수 있나요?

네, 글꼴, 레이블, 제목 등 차트의 다양한 부분을 사용자 지정할 수 있습니다. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 자세한 사용자 정의 옵션은 여기를 참조하세요.

### 더 많은 예와 문서는 어디에서 찾을 수 있나요?

Java용 Aspose.Slides 사용에 대한 더 많은 예제와 자세한 문서는 다음에서 찾을 수 있습니다. [Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 웹사이트.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
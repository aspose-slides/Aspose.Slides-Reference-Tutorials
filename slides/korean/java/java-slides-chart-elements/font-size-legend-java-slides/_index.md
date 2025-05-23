---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 더욱 멋지게 만들어 보세요. 단계별 가이드를 통해 범례 글꼴 크기 등을 사용자 지정하는 방법을 알아보세요."
"linktitle": "Java 슬라이드의 글꼴 크기 범례"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 글꼴 크기 범례"
"url": "/ko/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 글꼴 크기 범례


## Java Slides의 글꼴 크기 범례 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 범례 글꼴 크기를 사용자 지정하는 방법을 알아봅니다. 이 작업을 위한 단계별 지침과 소스 코드를 제공합니다.

## 필수 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. 라이브러리는 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 초기화

먼저, 필요한 클래스를 가져와서 PowerPoint 프레젠테이션을 초기화합니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

바꾸다 `"Your Document Directory"` PowerPoint 파일의 실제 경로를 사용합니다.

## 2단계: 차트 추가

다음으로, 슬라이드에 차트를 추가하고 범례의 글꼴 크기를 설정하겠습니다.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

이 코드에서는 첫 번째 슬라이드에 클러스터형 세로 막대형 차트를 만들고 범례 텍스트의 글꼴 크기를 20포인트로 설정합니다. `setFontHeight` 필요에 따라 글꼴 크기를 변경합니다.

## 3단계: 축 값 사용자 지정

이제 차트의 세로 축 값을 사용자 지정해 보겠습니다.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

여기서는 세로축의 최소값과 최대값을 설정합니다. 데이터 요구 사항에 따라 값을 수정할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 새 파일에 저장합니다.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

이 코드는 수정된 프레젠테이션을 지정된 디렉토리에 "output.pptx"라는 이름으로 저장합니다.

## Java Slides의 글꼴 크기 범례에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 Java PowerPoint 슬라이드의 범례 글꼴 크기를 성공적으로 사용자 지정했습니다. Aspose.Slides의 기능을 더욱 자세히 살펴보고 시각적으로 매력적인 인터랙티브 프레젠테이션을 만들어 보세요.

## 자주 묻는 질문

### 차트에서 범례 텍스트의 글꼴 크기를 변경하려면 어떻게 해야 하나요?

차트에서 범례 텍스트의 글꼴 크기를 변경하려면 다음 코드를 사용할 수 있습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

이 코드에서는 차트를 만들고 범례 텍스트의 글꼴 크기를 20포인트로 설정합니다. `setFontHeight` 글꼴 크기를 변경하는 값입니다.

### 차트의 범례에 대한 다른 속성을 사용자 정의할 수 있나요?

네, Aspose.Slides를 사용하여 차트의 범례 속성을 다양하게 사용자 지정할 수 있습니다. 사용자 지정할 수 있는 일반적인 속성으로는 텍스트 서식, 위치, 표시 여부 등이 있습니다. 예를 들어, 범례의 위치를 변경하려면 다음을 사용할 수 있습니다.

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

이 코드는 범례가 차트 하단에 표시되도록 설정합니다. 더 많은 사용자 지정 옵션은 Aspose.Slides 문서를 참조하세요.

### 차트의 세로축에 대한 최소값과 최대값을 어떻게 설정합니까?

차트의 세로 축에 대한 최소값과 최대값을 설정하려면 다음 코드를 사용할 수 있습니다.

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

여기서는 자동 축 크기 조정을 비활성화하고 세로 축의 최소값과 최대값을 지정합니다. 차트 데이터에 맞게 값을 조정하세요.

### Aspose.Slides에 대한 자세한 정보와 문서는 어디에서 찾을 수 있나요?

Aspose.Slides for Java에 대한 포괄적인 문서와 API 참조는 Aspose 문서 웹사이트에서 확인하실 수 있습니다. [여기](https://reference.aspose.com/slides/java/) 도서관 이용에 대한 자세한 내용은 여기를 참조하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
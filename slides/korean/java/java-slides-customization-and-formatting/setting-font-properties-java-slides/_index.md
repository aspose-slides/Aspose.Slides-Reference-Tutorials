---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드의 글꼴 속성을 설정하는 방법을 알아보세요. 이 단계별 가이드에는 코드 예제와 FAQ가 포함되어 있습니다."
"linktitle": "Java Slides에서 글꼴 속성 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 글꼴 속성 설정"
"url": "/ko/java/customization-and-formatting/setting-font-properties-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 글꼴 속성 설정


## Java Slides에서 글꼴 속성 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 텍스트 글꼴 속성을 설정하는 방법을 살펴보겠습니다. 굵기 및 글꼴 크기와 같은 글꼴 속성을 사용자 지정하여 슬라이드의 모양을 향상시킬 수 있습니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 프로젝트에 추가되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 초기화

먼저, 기존 PowerPoint 파일을 로드하여 프레젠테이션 객체를 초기화해야 합니다. `"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 2단계: 차트 추가

이 예제에서는 첫 번째 슬라이드에 차트를 적용해 보겠습니다. 필요에 따라 슬라이드 인덱스를 변경할 수 있습니다. 클러스터형 세로 막대형 차트를 추가하고 데이터 테이블을 활성화해 보겠습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## 3단계: 글꼴 속성 사용자 지정

이제 차트 데이터 테이블의 글꼴 속성을 사용자 지정해 보겠습니다. 글꼴을 굵게 설정하고 글꼴 높이(크기)를 조정해 보겠습니다.

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`이 줄은 글꼴을 굵게 설정합니다.
- `setFontHeight(20)`: 이 줄은 글꼴 높이를 20포인트로 설정합니다. 필요에 따라 이 값을 조정할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로, 수정된 프레젠테이션을 새 파일로 저장합니다. 출력 형식을 지정할 수 있는데, 여기서는 PPTX 파일로 저장합니다.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## Java Slides에서 글꼴 속성을 설정하기 위한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 텍스트 글꼴 속성을 설정하는 방법을 알아보았습니다. 이러한 기법을 적용하여 PowerPoint 프레젠테이션의 텍스트 모양을 향상시킬 수 있습니다.

## 자주 묻는 질문

### 글꼴 색상을 어떻게 바꾸나요?

글꼴 색상을 변경하려면 다음을 사용하세요. `setFontColor` 원하는 색상을 지정하세요. 예:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### 슬라이드에서 다른 텍스트의 글꼴을 변경할 수 있나요?

네, 슬라이드의 다른 텍스트 요소(예: 제목 및 레이블)의 글꼴을 변경할 수 있습니다. 적절한 개체와 메서드를 사용하여 특정 텍스트 요소의 글꼴 속성에 액세스하고 사용자 지정할 수 있습니다.

### 이탤릭체 글꼴 스타일을 어떻게 설정합니까?

글꼴 스타일을 기울임체로 설정하려면 다음을 사용하세요. `setFontItalic` 방법:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

조정하다 `NullableBool.True` 필요에 따라 매개변수를 사용하여 기울임체 스타일을 활성화하거나 비활성화할 수 있습니다.

### 차트의 데이터 레이블 글꼴을 어떻게 변경할 수 있나요?

차트에서 데이터 레이블의 글꼴을 변경하려면 적절한 방법을 사용하여 데이터 레이블 텍스트 형식에 접근해야 합니다. 예:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // 필요에 따라 인덱스를 변경하세요
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

이 코드는 첫 번째 시리즈의 데이터 레이블 글꼴을 굵게 설정합니다.

### 특정 텍스트 부분의 글꼴을 바꾸려면 어떻게 해야 하나요?

텍스트 요소 내 특정 텍스트 부분의 글꼴을 변경하려면 다음을 사용할 수 있습니다. `PortionFormat` 클래스. 수정하려는 부분에 접근한 후 원하는 글꼴 속성을 설정하세요.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // 필요에 따라 인덱스를 변경하세요
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // 필요에 따라 인덱스를 변경하세요
IPortion portion = paragraph.getPortions().get_Item(0); // 필요에 따라 인덱스를 변경하세요

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

이 코드는 도형 내 텍스트의 첫 번째 부분의 글꼴을 굵게 설정하고 글꼴 높이를 조정합니다.

### 프레젠테이션의 모든 슬라이드에 글꼴 변경 사항을 적용하려면 어떻게 해야 하나요?

프레젠테이션의 모든 슬라이드에 글꼴 변경 사항을 적용하려면 슬라이드를 반복하면서 필요에 따라 글꼴 속성을 조정하면 됩니다. 루프를 사용하여 각 슬라이드와 그 안의 텍스트 요소에 접근한 후 글꼴 속성을 사용자 지정하세요.

```java
for (ISlide slide : pres.getSlides()) {
    // 여기에서 텍스트 요소의 글꼴 속성에 액세스하고 사용자 정의하세요.
}
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
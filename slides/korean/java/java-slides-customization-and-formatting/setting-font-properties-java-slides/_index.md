---
title: Java 슬라이드에서 글꼴 속성 설정
linktitle: Java 슬라이드에서 글꼴 속성 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 글꼴 속성을 설정하는 방법을 알아보세요. 이 단계별 가이드에는 코드 예제와 FAQ가 포함되어 있습니다.
weight: 15
url: /ko/java/customization-and-formatting/setting-font-properties-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 글꼴 속성 설정


## Java 슬라이드의 글꼴 속성 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 텍스트에 대한 글꼴 속성을 설정하는 방법을 살펴보겠습니다. 굵기, 글꼴 크기 등의 글꼴 속성을 사용자 정의하여 슬라이드 모양을 향상시킬 수 있습니다.

## 전제 조건

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 추가되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 초기화

 먼저 기존 PowerPoint 파일을 로드하여 프레젠테이션 개체를 초기화해야 합니다. 바꾸다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 2단계: 차트 추가

이 예에서는 첫 번째 슬라이드의 차트를 사용하여 작업합니다. 필요에 따라 슬라이드 색인을 변경할 수 있습니다. 묶은 세로 막대형 차트를 추가하고 데이터 테이블을 활성화하겠습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## 3단계: 글꼴 속성 사용자 정의

이제 차트 데이터 테이블의 글꼴 속성을 사용자 정의해 보겠습니다. 글꼴을 굵게 설정하고 글꼴 높이(크기)를 조정하겠습니다.

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: 이 줄은 글꼴을 굵게 설정합니다.
- `setFontHeight(20)`: 이 줄은 글꼴 높이를 20포인트로 설정합니다. 필요에 따라 이 값을 조정할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 새 파일에 저장합니다. 출력 형식을 지정할 수 있습니다. 이 경우에는 PPTX 파일로 저장합니다.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 글꼴 속성을 설정하기 위한 전체 소스 코드

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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 텍스트에 대한 글꼴 속성을 설정하는 방법을 배웠습니다. 이러한 기술을 적용하여 PowerPoint 프레젠테이션의 텍스트 모양을 향상시킬 수 있습니다.

## FAQ

### 글꼴 색상을 어떻게 변경하나요?

 글꼴 색상을 변경하려면`setFontColor` 방법을 선택하고 원하는 색상을 지정하세요. 예를 들어:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### 슬라이드에 있는 다른 텍스트의 글꼴을 변경할 수 있나요?

예, 제목, 레이블 등 슬라이드의 다른 텍스트 요소에 대한 글꼴을 변경할 수 있습니다. 적절한 개체와 메서드를 사용하여 특정 텍스트 요소의 글꼴 속성에 액세스하고 사용자 정의합니다.

### 기울임꼴 글꼴 스타일을 어떻게 설정합니까?

 글꼴 스타일을 기울임꼴로 설정하려면`setFontItalic` 방법:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 조정하다`NullableBool.True` 이탤릭체 스타일을 활성화하거나 비활성화하는 데 필요한 매개변수입니다.

### 차트의 데이터 레이블 글꼴을 어떻게 변경합니까?

차트의 데이터 레이블 글꼴을 변경하려면 적절한 방법을 사용하여 데이터 레이블 텍스트 형식에 액세스해야 합니다. 예를 들어:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // 필요에 따라 색인을 변경하십시오.
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

이 코드는 첫 번째 계열의 데이터 레이블 글꼴을 굵게 설정합니다.

### 텍스트의 특정 부분에 대한 글꼴을 어떻게 변경합니까?

 텍스트 요소 내 텍스트의 특정 부분에 대한 글꼴을 변경하려면`PortionFormat` 수업. 수정하려는 부분에 접근한 후 원하는 글꼴 속성을 설정하세요.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // 필요에 따라 색인을 변경하십시오.
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // 필요에 따라 색인을 변경하십시오.
IPortion portion = paragraph.getPortions().get_Item(0); // 필요에 따라 색인을 변경하십시오.

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

이 코드는 도형 내 텍스트의 첫 번째 부분의 글꼴을 굵게 설정하고 글꼴 높이를 조정합니다.

### 프레젠테이션의 모든 슬라이드에 글꼴 변경 사항을 적용하려면 어떻게 해야 합니까?

프레젠테이션의 모든 슬라이드에 글꼴 변경 사항을 적용하려면 슬라이드를 반복하고 필요에 따라 글꼴 속성을 조정하면 됩니다. 루프를 사용하여 각 슬라이드와 그 안의 텍스트 요소에 액세스한 다음 글꼴 속성을 사용자 정의합니다.

```java
for (ISlide slide : pres.getSlides()) {
    // 여기에서 텍스트 요소의 글꼴 속성에 액세스하고 사용자 정의하세요.
}
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

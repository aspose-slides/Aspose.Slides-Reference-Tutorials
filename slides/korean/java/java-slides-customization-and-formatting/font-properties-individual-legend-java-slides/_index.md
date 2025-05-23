---
"description": "Aspose.Slides for Java를 사용하여 Java Slides의 개별 범례에 사용자 정의 글꼴 스타일, 크기 및 색상을 적용하여 PowerPoint 프레젠테이션을 향상시킵니다."
"linktitle": "Java 슬라이드의 개별 범례에 대한 글꼴 속성"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 개별 범례에 대한 글꼴 속성"
"url": "/ko/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 개별 범례에 대한 글꼴 속성


## Java 슬라이드의 개별 범례에 대한 글꼴 속성 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 개별 범례의 글꼴 속성을 설정하는 방법을 살펴보겠습니다. 글꼴 속성을 사용자 지정하면 PowerPoint 프레젠테이션에서 범례를 시각적으로 더욱 매력적이고 유익하게 만들 수 있습니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 프로젝트에 통합되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

## 1단계: 프레젠테이션 초기화 및 차트 추가

먼저, PowerPoint 프레젠테이션을 초기화하고 차트를 추가하는 것부터 시작해 보겠습니다. 이 예시에서는 클러스터형 세로 막대형 차트를 예로 들어 보겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // 나머지 코드는 여기에 있습니다
} finally {
    if (pres != null) pres.dispose();
}
```

바꾸다 `"Your Document Directory"` PowerPoint 문서가 있는 실제 디렉토리를 사용합니다.

## 2단계: 범례에 대한 글꼴 속성 사용자 지정

이제 차트 내 개별 범례 항목의 글꼴 속성을 사용자 지정해 보겠습니다. 이 예에서는 두 번째 범례 항목(인덱스 1)을 대상으로 하지만, 구체적인 요구 사항에 따라 인덱스를 조정할 수 있습니다.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

각 코드 줄의 기능은 다음과 같습니다.

- `get_Item(1)` 두 번째 범례 항목(인덱스 1)을 검색합니다. 다른 범례 항목을 대상으로 인덱스를 변경할 수 있습니다.
- `setFontBold(NullableBool.True)` 글꼴을 굵게 설정합니다.
- `setFontHeight(20)` 글꼴 크기를 20포인트로 설정합니다.
- `setFontItalic(NullableBool.True)` 글꼴을 기울임체로 설정합니다.
- `setFillType(FillType.Solid)` 범례 항목 텍스트가 단색으로 채워져야 함을 지정합니다.
- `getSolidFillColor().setColor(Color.BLUE)` 채우기 색상을 파란색으로 설정합니다. 바꿀 수 있습니다. `Color.BLUE` 원하는 색상으로.

## 3단계: 수정된 프레젠테이션 저장

마지막으로, 변경 사항을 보존하기 위해 수정된 프레젠테이션을 새 파일에 저장합니다.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

바꾸다 `"output.pptx"` 원하는 출력 파일 이름을 입력하세요.

이것으로 끝입니다! Aspose.Slides for Java를 사용하여 Java Slides 프레젠테이션의 개별 범례 항목에 대한 글꼴 속성을 성공적으로 사용자 지정했습니다.

## Java 슬라이드의 개별 범례에 대한 글꼴 속성에 대한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 개별 범례의 글꼴 속성을 사용자 지정하는 방법을 알아보았습니다. 글꼴 스타일, 크기, 색상을 조정하여 PowerPoint 프레젠테이션의 시각적인 매력과 명확성을 향상시킬 수 있습니다.

## 자주 묻는 질문

### 글꼴 색상을 어떻게 바꿀 수 있나요?

글꼴 색상을 변경하려면 다음을 사용하세요. `tf.getPortionFormat().getFontColor().setColor(yourColor)` 채우기 색상을 변경하는 대신. 바꾸기 `yourColor` 원하는 글꼴 색상으로.

### 다른 범례 속성을 수정하려면 어떻게 해야 하나요?

위치, 크기, 형식 등 범례의 다양한 속성을 수정할 수 있습니다. 범례 작업에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 참조하세요.

### 이러한 변경 사항을 여러 개의 범례 항목에 적용할 수 있나요?

예, 인덱스를 조정하여 범례 항목을 반복하고 이러한 변경 사항을 여러 항목에 적용할 수 있습니다. `get_Item(index)` 그리고 사용자 정의 코드를 반복합니다.

작업이 끝나면 리소스를 해제하기 위해 프레젠테이션 객체를 삭제하는 것을 잊지 마세요.

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
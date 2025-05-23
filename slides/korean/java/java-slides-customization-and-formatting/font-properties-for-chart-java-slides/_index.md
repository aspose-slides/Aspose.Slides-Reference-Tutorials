---
"description": "Aspose.Slides for Java를 사용하여 Java Slides의 차트 글꼴 속성을 강화하세요. 글꼴 크기, 스타일, 색상을 사용자 지정하여 인상적인 프레젠테이션을 만들어 보세요."
"linktitle": "Java 슬라이드 차트의 글꼴 속성"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드 차트의 글꼴 속성"
"url": "/ko/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드 차트의 글꼴 속성


## Java 슬라이드 차트의 글꼴 속성 소개

이 가이드에서는 Aspose.Slides를 사용하여 Java Slides에서 차트의 글꼴 속성을 설정하는 방법을 안내합니다. 차트 텍스트의 글꼴 크기와 모양을 사용자 지정하여 프레젠테이션의 시각적 효과를 높일 수 있습니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java API가 프로젝트에 통합되어 있는지 확인하세요. 아직 통합되어 있지 않다면 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

## 1단계: 프레젠테이션 만들기

먼저 다음 코드를 사용하여 새 프레젠테이션을 만듭니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

이제 프레젠테이션에 클러스터형 막대형 차트를 추가해 보겠습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

여기서는 첫 번째 슬라이드에 좌표 (100, 100)에 너비 500단위, 높이 400단위의 클러스터형 막대형 차트를 추가합니다.

## 3단계: 글꼴 속성 사용자 지정

다음으로, 차트의 글꼴 속성을 사용자 지정해 보겠습니다. 이 예에서는 모든 차트 텍스트의 글꼴 크기를 20으로 설정합니다.

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

이 코드는 차트 내 모든 텍스트의 글꼴 크기를 20포인트로 설정합니다.

## 4단계: 데이터 레이블 표시

다음 코드를 사용하여 차트에 데이터 레이블을 표시할 수도 있습니다.

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

이 코드 줄은 차트의 첫 번째 시리즈에 대한 데이터 레이블을 활성화하여 차트 열의 값을 표시합니다.

## 5단계: 프레젠테이션 저장

마지막으로 사용자 정의 차트 글꼴 속성으로 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

이 코드는 프레젠테이션을 지정된 디렉토리에 "FontPropertiesForChart.pptx"라는 파일 이름으로 저장합니다.

## Java Slides 차트의 글꼴 속성에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java Slides 차트의 글꼴 속성을 사용자 지정하는 방법을 알아보았습니다. 이러한 기법을 적용하여 차트와 프레젠테이션의 모양을 향상시킬 수 있습니다. 더 많은 옵션은 [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

## 자주 묻는 질문

### 글꼴 색상을 어떻게 바꿀 수 있나요?

차트 텍스트의 글꼴 색상을 변경하려면 다음을 사용하세요. `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, 교체 `Color.RED` 원하는 색상으로.

### 글꼴 스타일(굵게, 기울임꼴 등)을 변경할 수 있나요?

네, 글꼴 스타일을 변경할 수 있습니다. `chart.getTextFormat().getPortionFormat().setFontBold(true);` 글꼴을 굵게 만들려면 다음과 같이 하십시오. 마찬가지로 다음을 사용할 수 있습니다. `setFontItalic(true)` 이탤릭체로 만들려면.

### 특정 차트 요소에 대한 글꼴 속성을 사용자 지정하려면 어떻게 해야 하나요?

축 레이블이나 범례 텍스트와 같은 특정 차트 요소의 글꼴 속성을 사용자 지정하려면 위에 표시된 것과 유사한 방법을 사용하여 해당 요소에 액세스하고 글꼴 속성을 설정하면 됩니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
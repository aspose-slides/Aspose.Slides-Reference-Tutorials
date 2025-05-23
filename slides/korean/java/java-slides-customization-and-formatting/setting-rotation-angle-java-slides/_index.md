---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드를 최적화하세요. 텍스트 요소의 회전 각도를 설정하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드에서 회전 각도 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 회전 각도 설정"
"url": "/ko/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 회전 각도 설정


## Java Slides에서 회전 각도 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 차트 축 제목의 텍스트 회전 각도를 설정하는 방법을 살펴보겠습니다. 회전 각도를 조정하면 차트 축 제목의 모양을 프레젠테이션 요구에 맞게 사용자 지정할 수 있습니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 Java 프로젝트에 설치 및 설정되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드하고 설명서에 나와 있는 설치 지침을 따르세요.

## 1단계: 프레젠테이션 만들기

먼저 새 프레젠테이션을 만들거나 기존 프레젠테이션을 불러와야 합니다. 이 예시에서는 새 프레젠테이션을 만들어 보겠습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

다음으로, 슬라이드에 차트를 추가해 보겠습니다. 이 예시에서는 클러스터형 세로 막대형 차트를 추가합니다.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## 3단계: 축 제목에 대한 회전 각도 설정

축 제목의 회전 각도를 설정하려면 차트의 세로 축 제목에 접근하여 회전 각도를 조정해야 합니다. 방법은 다음과 같습니다.

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

이 코드 조각에서는 회전 각도를 90도로 설정하여 텍스트를 수직으로 회전합니다. 각도는 원하는 값으로 조정할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 PowerPoint 파일로 저장합니다.

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java 슬라이드에서 회전 각도 설정을 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 축 제목의 텍스트 회전 각도를 설정하는 방법을 알아보았습니다. 이 기능을 사용하면 차트의 모양을 사용자 지정하여 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다. 다양한 회전 각도를 실험하여 원하는 차트 모양을 만들어 보세요.

## 자주 묻는 질문

### 슬라이드에서 다른 텍스트 요소의 회전 각도를 어떻게 변경할 수 있나요?

비슷한 방식으로 도형이나 텍스트 상자와 같은 다른 텍스트 요소의 회전 각도를 변경할 수 있습니다. 요소의 텍스트 서식을 확인하고 필요에 따라 회전 각도를 설정하세요.

### 수평축 제목의 텍스트도 회전할 수 있나요?

네, 회전 각도를 조정하여 가로축 제목의 텍스트를 회전할 수 있습니다. 회전 각도를 원하는 값으로 설정하기만 하면 됩니다. 예를 들어 세로 텍스트는 90도, 가로 텍스트는 0도입니다.

### 차트 제목에 사용할 수 있는 다른 서식 옵션은 무엇입니까?

Aspose.Slides for Java는 글꼴 스타일, 색상, 정렬 등 차트 제목에 다양한 서식 옵션을 제공합니다. 차트 제목 사용자 지정에 대한 자세한 내용은 해당 설명서를 참조하세요.

### 차트 축 제목의 텍스트 회전을 애니메이션으로 표현할 수 있나요?

네, Aspose.Slides for Java를 사용하여 차트 축 제목을 포함한 텍스트 요소에 애니메이션 효과를 추가할 수 있습니다. 프레젠테이션에 애니메이션을 추가하는 방법에 대한 자세한 내용은 해당 설명서를 참조하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
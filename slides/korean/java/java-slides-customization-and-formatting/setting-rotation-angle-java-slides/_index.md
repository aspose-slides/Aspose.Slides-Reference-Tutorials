---
title: Java 슬라이드에서 회전 각도 설정
linktitle: Java 슬라이드에서 회전 각도 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java로 Java 슬라이드를 최적화하세요. 텍스트 요소의 회전 각도를 설정하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
weight: 17
url: /ko/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에서 회전 각도 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 차트 축 제목의 텍스트 회전 각도를 설정하는 방법을 살펴보겠습니다. 회전 각도를 조정하면 프레젠테이션 요구 사항에 더 적합하도록 차트 축 제목의 모양을 사용자 지정할 수 있습니다.

## 전제 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드하고 해당 문서에 제공된 설치 지침을 따를 수 있습니다.

## 1단계: 프레젠테이션 만들기

먼저 새 프레젠테이션을 만들거나 기존 프레젠테이션을 로드해야 합니다. 이 예에서는 새 프레젠테이션을 만듭니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

다음으로 슬라이드에 차트를 추가하겠습니다. 이 예에서는 묶은 세로 막대형 차트를 추가합니다.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## 3단계: 축 제목의 회전 각도 설정

축 제목의 회전 각도를 설정하려면 차트의 세로 축 제목에 액세스하여 회전 각도를 조정해야 합니다. 방법은 다음과 같습니다.

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

이 코드 조각에서는 회전 각도를 90도로 설정하여 텍스트를 수직으로 회전시킵니다. 원하는 값으로 각도를 조절할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 PowerPoint 파일에 저장합니다.

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Java 슬라이드에서 회전 각도를 설정하기 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 축 제목의 텍스트 회전 각도를 설정하는 방법을 배웠습니다. 이 기능을 사용하면 차트의 모양을 사용자 정의하여 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다. 원하는 차트 모양을 얻으려면 다양한 회전 각도를 실험해 보세요.

## FAQ

### 슬라이드에 있는 다른 텍스트 요소의 회전 각도를 어떻게 변경합니까?

비슷한 접근 방식을 사용하여 도형이나 텍스트 상자와 같은 다른 텍스트 요소의 회전 각도를 변경할 수 있습니다. 요소의 텍스트 형식에 액세스하고 필요에 따라 회전 각도를 설정합니다.

### 가로축 제목의 텍스트도 회전할 수 있나요?

예, 회전 각도를 조정하여 가로축 제목의 텍스트를 회전할 수 있습니다. 수직 텍스트의 경우 90도, 수평 텍스트의 경우 0도 등 원하는 값으로 회전 각도를 설정하기만 하면 됩니다.

### 차트 제목에 사용할 수 있는 다른 서식 옵션은 무엇입니까?

Aspose.Slides for Java는 글꼴 스타일, 색상, 정렬을 포함하여 차트 제목에 대한 다양한 서식 옵션을 제공합니다. 차트 제목 사용자 정의에 대한 자세한 내용은 설명서를 탐색할 수 있습니다.

### 차트 축 제목의 텍스트 회전에 애니메이션을 적용할 수 있나요?

예, Aspose.Slides for Java를 사용하여 차트 축 제목을 포함한 텍스트 요소에 애니메이션 효과를 추가할 수 있습니다. 프레젠테이션에 애니메이션을 추가하는 방법에 대한 자세한 내용은 설명서를 참조하세요.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

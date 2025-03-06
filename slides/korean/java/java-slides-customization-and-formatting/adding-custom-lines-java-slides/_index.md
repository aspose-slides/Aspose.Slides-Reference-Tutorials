---
title: Java 슬라이드에 사용자 정의 라인 추가
linktitle: Java 슬라이드에 사용자 정의 라인 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 사용자 정의 라인으로 Java 슬라이드를 향상시키세요. Aspose.Slides for Java를 사용하는 단계별 가이드입니다. 인상적인 시각적 자료를 위해 프레젠테이션에 줄을 추가하고 사용자 정의하는 방법을 알아보세요.
weight: 10
url: /ko/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에 사용자 정의 라인 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에 사용자 정의 라인을 추가하는 방법을 배웁니다. 사용자 지정 선을 사용하면 슬라이드의 시각적 표현을 향상하고 특정 콘텐츠를 강조할 수 있습니다. 이를 달성하기 위한 소스 코드와 함께 단계별 지침을 제공할 것입니다. 시작하자!

## 전제 조건

 시작하기 전에 Java 프로젝트에 Java용 Aspose.Slides 라이브러리가 설정되어 있는지 확인하세요. 다음 웹사이트에서 라이브러리를 다운로드할 수 있습니다.[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## 1단계: 프레젠테이션 초기화

먼저 새 프레젠테이션을 만들어야 합니다. 이 예에서는 빈 프레젠테이션을 만듭니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

다음으로 슬라이드에 차트를 추가하겠습니다. 이 예에서는 묶은 세로 막대형 차트를 추가합니다. 귀하의 필요에 맞는 차트 유형을 선택할 수 있습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## 3단계: 사용자 정의 라인 추가

 이제 차트에 사용자 정의 선을 추가해 보겠습니다. 우리는`IAutoShape` 유형의`ShapeType.Line` 차트 내에 위치를 지정합니다.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## 4단계: 라인 사용자 정의

속성을 설정하여 선의 모양을 사용자 정의할 수 있습니다. 이 예에서는 선 색상을 빨간색으로 설정합니다.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 5단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 원하는 위치에 저장합니다.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에 사용자 정의 라인을 추가하기 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

축하해요! Aspose.Slides for Java를 사용하여 Java 슬라이드에 사용자 정의 라인을 성공적으로 추가했습니다. 원하는 시각적 효과를 얻기 위해 선의 속성을 추가로 사용자 정의할 수 있습니다.

## FAQ

### 선 색상을 어떻게 바꾸나요?

선 색상을 변경하려면 다음 코드를 사용하십시오.
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 바꾸다`YOUR_COLOR` 원하는 색상으로.

### 다른 도형에 사용자 지정 선을 추가할 수 있나요?

 예, 차트뿐만 아니라 다양한 도형에 사용자 정의 선을 추가할 수 있습니다. 간단하게`IAutoShape` 필요에 따라 사용자 정의하세요.

### 선 두께를 어떻게 변경할 수 있나요?

 설정을 통해 선 두께를 변경할 수 있습니다.`Width` 라인 형식의 속성입니다. 예를 들어:
```java
shape.getLineFormat().setWidth(2); // 선 두께를 2포인트로 설정
```

### 슬라이드에 여러 줄을 추가할 수 있나요?

예, 이 튜토리얼에서 언급한 단계를 반복하여 슬라이드에 여러 줄을 추가할 수 있습니다. 각 라인은 독립적으로 사용자 정의할 수 있습니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

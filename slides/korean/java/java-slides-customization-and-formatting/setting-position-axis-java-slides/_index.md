---
title: Java 슬라이드에서 위치 축 설정
linktitle: Java 슬라이드에서 위치 축 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides를 사용하여 차트를 향상하세요. Java 슬라이드에서 위치 축을 설정하고, 멋진 프레젠테이션을 만들고, 차트 레이아웃을 쉽게 사용자 정의하는 방법을 알아보세요.
weight: 16
url: /ko/java/customization-and-formatting/setting-position-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java에서 위치 축 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에서 위치 축을 설정하는 방법을 알아봅니다. 차트의 모양과 레이아웃을 사용자 정의하려는 경우 축 위치를 지정하는 것이 유용할 수 있습니다. 군집형 세로 막대형 차트를 생성하고 카테고리 간 가로축 위치를 조정해 보겠습니다.

## 전제 조건

 시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 만들기

먼저 작업할 새 프레젠테이션을 만들어 보겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 꼭 교체하세요`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 2단계: 차트 추가

다음으로 슬라이드에 묶은 세로 막대형 차트를 추가하겠습니다. 차트 유형, 위치(x, y 좌표) 및 차트의 크기(너비 및 높이)를 지정합니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

여기서는 너비가 450, 높이가 300인 클러스터형 세로 막대형 차트를 위치 (50, 50)에 추가했습니다. 필요에 따라 이러한 값을 조정할 수 있습니다.

## 3단계: 위치 축 설정

카테고리 간 위치 축을 설정하려면 다음 코드를 사용할 수 있습니다.

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

이 코드는 카테고리 사이에 표시할 가로 축을 설정하며, 이는 특정 차트 레이아웃에 유용할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 차트와 함께 저장해 보겠습니다.

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 바꾸다`"AsposeClusteredColumnChart.pptx"` 원하는 파일명으로

그게 다야! 클러스터형 세로 막대형 차트를 성공적으로 생성하고 Aspose.Slides for Java를 사용하여 범주 간 위치 축을 설정했습니다.

## 완전한 소스 코드
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에서 위치 축을 설정하는 방법을 살펴보았습니다. 이 가이드에 설명된 단계를 수행하여 묶은 세로 막대형 차트를 만들고 범주 사이에 가로 축을 배치하여 모양을 사용자 지정하는 방법을 배웠습니다. Aspose.Slides for Java는 차트 및 프레젠테이션 작업을 위한 강력한 기능을 제공하므로 Java 개발자에게 유용한 도구입니다.

## FAQ

### 차트를 추가로 사용자 정의하려면 어떻게 해야 합니까?

데이터 시리즈, 차트 제목, 범례 등을 포함하여 차트의 다양한 측면을 사용자 정의할 수 있습니다. 다음을 참조하세요.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 자세한 지침과 예시를 확인하세요.

### 차트 유형을 변경할 수 있나요?

 예, 차트 유형을 수정하여 차트 유형을 변경할 수 있습니다.`ChartType` 차트를 추가할 때 매개변수입니다. Aspose.Slides for Java는 막대 차트, 꺾은선형 차트 등과 같은 다양한 차트 유형을 지원합니다.

### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?

 다음에서 포괄적인 문서와 더 많은 예제를 찾을 수 있습니다.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 페이지.

시스템 리소스를 해제하기 위해 작업을 마친 후에는 프레젠테이션 개체를 삭제해야 합니다.

```java
if (pres != null) pres.dispose();
```

이것이 이번 튜토리얼의 전부입니다. Aspose.Slides for Java를 사용하여 차트에서 위치 축을 설정하는 방법을 배웠습니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

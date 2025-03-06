---
title: Java 슬라이드의 축에서 값 및 단위 배율 가져오기
linktitle: Java 슬라이드의 축에서 값 및 단위 배율 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java Slides의 축에서 값과 단위 배율을 얻는 방법을 알아보세요. 데이터 분석 역량을 강화하세요.
weight: 20
url: /ko/java/data-manipulation/get-values-unit-scale-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드의 축에서 값 및 단위 스케일 가져오기 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 축에서 값과 단위 배율을 검색하는 방법을 살펴보겠습니다. 데이터 시각화 프로젝트를 진행 중이거나 Java 애플리케이션에서 차트 데이터를 분석해야 하는 경우 축 값에 액세스하는 방법을 이해하는 것이 필수적입니다. 코드 예제를 제공하면서 프로세스를 단계별로 안내해 드리겠습니다.

## 전제 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java 개발 환경: 시스템에 Java가 설치되어 있고 Java 프로그래밍 개념을 잘 알고 있는지 확인하십시오.

2.  Aspose.Slides for Java: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 만들기

시작하려면 Aspose.Slides for Java를 사용하여 새 프레젠테이션을 만들어 보겠습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 바꾸다`"Your Document Directory"` 프레젠테이션을 저장하려는 디렉토리 경로를 사용하세요.

## 2단계: 차트 추가

다음으로 프레젠테이션에 차트를 추가하겠습니다. 이 예에서는 영역 차트를 만듭니다.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
chart.validateChartLayout();
```

프레젠테이션의 첫 번째 슬라이드에 영역 차트를 추가했습니다. 필요에 따라 차트 유형과 위치를 사용자 정의할 수 있습니다.

## 3단계: 세로축 값 검색

이제 차트의 세로 축에서 값을 검색해 보겠습니다.

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

여기서는 세로축의 최대값과 최소값을 구합니다. 이러한 값은 다양한 데이터 분석 작업에 유용할 수 있습니다.

## 4단계: 가로 축 값 검색

마찬가지로 가로 축에서 값을 검색할 수 있습니다.

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

 그만큼`majorUnit` 그리고`minorUnit` 값은 각각 가로축의 주요 단위와 보조 단위를 나타냅니다.

## 5단계: 프레젠테이션 저장

축 값을 검색한 후에는 프레젠테이션을 저장할 수 있습니다.

```java
pres.save(dataDir + "ChartValues.pptx", SaveFormat.Pptx);
```

이 코드는 검색된 축 값이 포함된 프레젠테이션을 PowerPoint 파일에 저장합니다.

## Java 슬라이드의 축에서 값 및 단위 배율 가져오기에 대한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
	chart.validateChartLayout();
	double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
	double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
	double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
	double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
	// 프레젠테이션 저장 중
	pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 축에서 값과 단위 배율을 얻는 방법을 살펴보았습니다. 이는 Java 애플리케이션 내에서 차트로 작업하고 데이터를 분석할 때 매우 유용할 수 있습니다. Aspose.Slides for Java는 프로그래밍 방식으로 프레젠테이션 작업에 필요한 도구를 제공하여 차트 데이터 등을 제어할 수 있습니다.

## FAQ

### Aspose.Slides for Java에서 차트 유형을 어떻게 사용자 정의할 수 있나요?

 차트 유형을 맞춤설정하려면 간단히 바꾸세요.`ChartType.Area` 프레젠테이션에 차트를 추가할 때 원하는 차트 유형으로 변경하세요.

### 차트 축 레이블의 모양을 변경할 수 있나요?

예, Aspose.Slides for Java를 사용하여 차트 축 레이블의 모양을 사용자 정의할 수 있습니다. 자세한 지침은 설명서를 참조하세요.

### Aspose.Slides for Java는 최신 Java 버전과 호환됩니까?

Aspose.Slides for Java는 최신 Java 버전을 지원하도록 정기적으로 업데이트되어 최신 Java 개발과의 호환성을 보장합니다.

### 상용 프로젝트에서 Java용 Aspose.Slides를 사용할 수 있나요?

예, 상용 프로젝트에서 Java용 Aspose.Slides를 사용할 수 있습니다. 다양한 프로젝트 요구 사항에 맞는 라이센스 옵션을 제공합니다.

### Aspose.Slides for Java에 대한 추가 리소스와 문서는 어디서 찾을 수 있나요?

 다음에서 포괄적인 문서와 추가 리소스를 찾을 수 있습니다.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 웹사이트.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

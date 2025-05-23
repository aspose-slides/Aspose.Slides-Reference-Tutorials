---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 차트 플롯 영역 크기를 가져오는 방법을 알아보세요. PowerPoint 자동화 기술을 향상시켜 보세요."
"linktitle": "Java 슬라이드의 차트 플롯 영역에서 너비와 높이 가져오기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 차트 플롯 영역에서 너비와 높이 가져오기"
"url": "/ko/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 차트 플롯 영역에서 너비와 높이 가져오기


## 소개

차트는 PowerPoint 프레젠테이션에서 데이터를 시각화하는 강력한 방법입니다. 차트 내 요소의 크기 조정이나 위치 변경 등 다양한 이유로 차트 플롯 영역의 크기를 알아야 할 때가 있습니다. 이 가이드에서는 Java와 Aspose.Slides for Java를 사용하여 플롯 영역의 너비와 높이를 구하는 방법을 보여줍니다.

## 필수 조건

코드를 살펴보기 전에 Aspose.Slides for Java 라이브러리가 Java 프로젝트에 설치 및 설정되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 환경 설정

Java 프로젝트에 Aspose.Slides for Java 라이브러리가 추가되었는지 확인하세요. 프로젝트의 종속성에 라이브러리를 포함하거나 JAR 파일을 직접 추가하여 추가할 수 있습니다.

## 2단계: PowerPoint 프레젠테이션 만들기

먼저 PowerPoint 프레젠테이션을 만들고 슬라이드를 추가해 보겠습니다. 이 슬라이드는 차트를 담는 컨테이너 역할을 할 것입니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

바꾸다 `"Your Document Directory"` 문서 디렉토리 경로를 포함합니다.

## 3단계: 차트 추가

이제 슬라이드에 클러스터형 세로 막대형 차트를 추가해 보겠습니다. 또한 차트 레이아웃의 유효성도 검사해 보겠습니다.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

이 코드는 위치(100, 100)에 크기(500, 350)를 가진 클러스터형 막대형 차트를 만듭니다.

## 4단계: 플롯 영역 치수 가져오기

차트의 플롯 영역의 너비와 높이를 검색하려면 다음 코드를 사용할 수 있습니다.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

이제 변수들 `x`, `y`, `w`, 그리고 `h` 플롯 영역의 X 좌표, Y 좌표, 너비, 높이에 대한 각각의 값을 포함합니다.

## 5단계: 프레젠테이션 저장

마지막으로 차트와 함께 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

교체를 꼭 해주세요 `"Chart_out.pptx"` 원하는 출력 파일 이름을 입력하세요.

## Java 슬라이드의 차트 플롯 영역에서 너비와 높이를 가져오기 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// 차트와 함께 프레젠테이션 저장
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 글에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 차트 플롯 영역의 너비와 높이를 구하는 방법을 살펴보았습니다. 이 정보는 PowerPoint 프레젠테이션에서 차트 레이아웃을 동적으로 조정해야 할 때 유용하게 활용할 수 있습니다.

## 자주 묻는 질문

### 차트 유형을 묶은 막대형이 아닌 다른 유형으로 변경하려면 어떻게 해야 하나요?

차트 유형을 바꾸려면 다음을 수행하세요. `ChartType.ClusteredColumn` 원하는 차트 유형 열거형과 같은 `ChartType.Line` 또는 `ChartType.Pie`.

### 차트의 다른 속성을 수정할 수 있나요?

네, Aspose.Slides for Java API를 사용하여 데이터, 레이블, 서식 등 차트의 다양한 속성을 수정할 수 있습니다. 자세한 내용은 설명서를 참조하세요.

### Aspose.Slides for Java는 전문적인 PowerPoint 자동화에 적합합니까?

네, Aspose.Slides for Java는 Java 애플리케이션에서 PowerPoint 작업을 자동화하는 강력한 라이브러리입니다. 프레젠테이션, 슬라이드, 도형, 차트 등을 작업하는 데 필요한 다양한 기능을 제공합니다.

### Java용 Aspose.Slides에 대해 자세히 알아보려면 어떻게 해야 하나요?

Aspose.Slides for Java 문서 페이지에서 광범위한 문서와 예제를 찾을 수 있습니다. [여기](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
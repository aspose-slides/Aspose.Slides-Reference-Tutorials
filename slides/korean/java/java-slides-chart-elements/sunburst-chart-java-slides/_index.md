---
"description": "Aspose.Slides를 사용하여 Java Slides에서 멋진 선버스트 차트를 만들어 보세요. 단계별 차트 생성 및 데이터 조작 방법을 익혀보세요."
"linktitle": "Java 슬라이드의 선버스트 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 선버스트 차트"
"url": "/ko/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 선버스트 차트


## Aspose.Slides를 이용한 Java Slides의 Sunburst 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 선버스트 차트를 만드는 방법을 알아봅니다. 선버스트 차트는 계층적 데이터를 표현하는 데 사용되는 방사형 차트입니다. 소스 코드와 함께 단계별 지침을 제공합니다.

## 필수 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 구성되어 있는지 확인하세요. 라이브러리는 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 필요한 라이브러리 가져오기

먼저 Aspose.Slides를 사용하는 데 필요한 라이브러리를 가져와서 Java 애플리케이션에서 Sunburst 차트를 만듭니다.

```java
import com.aspose.slides.*;
```

## 2단계: 프레젠테이션 초기화

PowerPoint 프레젠테이션을 초기화하고 프레젠테이션 파일이 저장될 디렉토리를 지정합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3단계: 선버스트 차트 만들기

슬라이드에 선버스트 차트를 만듭니다. 차트의 위치(X, Y)와 크기(너비, 높이)를 지정합니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## 4단계: 차트 데이터 준비

차트에서 기존 범주 및 시리즈 데이터를 지우고 차트에 대한 데이터 통합 문서를 만듭니다.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## 5단계: 차트 계층 구조 정의

선버스트 차트의 계층 구조를 정의합니다. 가지, 줄기, 잎을 범주로 추가할 수 있습니다.

```java
// 지점 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// 지점 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## 6단계: 차트에 데이터 추가

Sunburst 차트 시리즈에 데이터 포인트를 추가합니다.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## 7단계: 프레젠테이션 저장

마지막으로, Sunburst 차트로 프레젠테이션을 저장합니다.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Java Slides에서 선버스트 차트를 위한 완전한 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//지점 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//지점 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션에서 선버스트 차트를 만드는 방법을 알아보았습니다. 프레젠테이션을 초기화하고, 차트를 생성하고, 차트 계층 구조를 정의하고, 데이터 포인트를 추가하고, 프레젠테이션을 저장하는 방법을 살펴보았습니다. 이제 이 지식을 활용하여 Java 애플리케이션에서 인터랙티브하고 유익한 선버스트 차트를 만들 수 있습니다.

## 자주 묻는 질문

### Sunburst 차트의 모양을 사용자 지정하려면 어떻게 해야 하나요?

색상, 레이블, 스타일 등의 속성을 수정하여 선버스트 차트의 모양을 사용자 지정할 수 있습니다. 자세한 사용자 지정 옵션은 Aspose.Slides 설명서를 참조하세요.

### 차트에 더 많은 데이터 포인트를 추가할 수 있나요?

예, 다음을 사용하여 차트에 더 많은 데이터 포인트를 추가할 수 있습니다. `series.getDataPoints().addDataPointForSunburstSeries()` 포함하려는 각 데이터 포인트에 대한 방법입니다.

### 선버스트 차트에 도구 설명을 추가하려면 어떻게 해야 하나요?

선버스트 차트에 도구 설명을 추가하려면 차트 세그먼트 위에 마우스를 올려 놓았을 때 값이나 설명과 같은 추가 정보가 표시되도록 데이터 레이블 형식을 설정하면 됩니다.

### 하이퍼링크를 사용하여 대화형 Sunburst 차트를 만드는 것이 가능합니까?

네, 특정 차트 요소나 세그먼트에 하이퍼링크를 추가하여 하이퍼링크가 포함된 대화형 선버스트 차트를 만들 수 있습니다. 하이퍼링크 추가에 대한 자세한 내용은 Aspose.Slides 설명서를 참조하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
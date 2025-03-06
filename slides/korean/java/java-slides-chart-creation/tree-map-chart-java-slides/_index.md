---
title: Java 슬라이드의 트리 맵 차트
linktitle: Java 슬라이드의 트리 맵 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 트리 맵 차트를 만듭니다. 계층적 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다.
weight: 13
url: /ko/java/chart-creation/tree-map-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드의 트리 맵 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 트리 맵 차트를 만드는 방법을 보여줍니다. 트리 맵 차트는 계층적 데이터를 시각화하는 효과적인 방법입니다.

## 전제 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설정되어 있는지 확인하세요.

## 1단계: 필수 라이브러리 가져오기

```java
import com.aspose.slides.*;
```

## 2단계: 프레젠테이션 로드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3단계: 트리 맵 차트 만들기

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // 분기 1 만들기
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // 분기 2 만들기
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // 데이터 포인트 추가
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // 트리 맵 차트로 프레젠테이션을 저장하세요.
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Java 슬라이드의 트리 맵 차트에 대한 완전한 소스 코드
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 트리 맵 차트를 만드는 방법을 배웠습니다. 트리 맵 차트는 계층적 데이터를 시각화하여 프레젠테이션을 더욱 유익하고 매력적으로 만드는 유용한 도구입니다.

## FAQ

### 트리 맵 차트에 데이터를 어떻게 추가하나요?

 트리 맵 차트에 데이터를 추가하려면`series.getDataPoints().addDataPointForTreemapSeries()` 메소드, 데이터 값을 매개변수로 전달합니다.

### 트리 맵 차트의 모양을 어떻게 사용자 정의할 수 있나요?

 다양한 속성을 수정하여 트리 맵 차트의 모양을 사용자 정의할 수 있습니다.`chart` 그리고`series`색상, 레이블, 레이아웃과 같은 개체.

### 단일 프레젠테이션에서 여러 개의 트리 맵 차트를 만들 수 있나요?

예, 동일한 단계를 따르고 다른 슬라이드 위치를 지정하여 단일 프레젠테이션에서 여러 트리 맵 차트를 만들 수 있습니다.

### 트리 맵 차트가 포함된 프레젠테이션을 어떻게 저장하나요?

 사용`pres.save()` 프리젠테이션을 트리 맵 차트와 함께 원하는 형식(예: PPTX)으로 저장하는 방법입니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

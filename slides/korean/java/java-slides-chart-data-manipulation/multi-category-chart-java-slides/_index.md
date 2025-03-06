---
title: Java 슬라이드의 다중 범주 차트
linktitle: Java 슬라이드의 다중 범주 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 다중 카테고리 차트를 만듭니다. 프레젠테이션에서 인상적인 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다.
weight: 20
url: /ko/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides를 사용한 Java 슬라이드의 다중 범주 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드에서 다중 카테고리 차트를 만드는 방법을 알아봅니다. 이 가이드는 소스 코드와 함께 단계별 지침을 제공하여 여러 범주와 계열이 포함된 클러스터형 세로 막대형 차트를 만드는 데 도움이 됩니다.

## 전제 조건
시작하기 전에 Java 개발 환경에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요.

## 1단계: 환경 설정
먼저 필요한 클래스를 가져오고 슬라이드 작업에 사용할 새 프레젠테이션 개체를 만듭니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 슬라이드 및 차트 추가
다음으로 슬라이드를 만들고 여기에 묶은 세로 막대형 차트를 추가합니다.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 3단계: 기존 데이터 지우기
차트에서 기존 데이터를 모두 지웁니다.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## 4단계: 데이터 범주 설정
이제 차트의 데이터 범주를 설정해 보겠습니다. 여러 카테고리를 생성하고 그룹화하겠습니다.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// 카테고리를 추가하고 그룹화하세요.
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## 5단계: 시리즈 추가
이제 데이터 요소와 함께 차트에 계열을 추가해 보겠습니다.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 차트와 함께 저장합니다.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides를 사용하여 Java 슬라이드에 다중 범주 차트를 성공적으로 만들었습니다. 특정 요구 사항에 맞게 이 차트를 추가로 사용자 정의할 수 있습니다.

## Java 슬라이드의 다중 범주 차트에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// 시리즈 추가
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// 차트와 함께 프레젠테이션 저장
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드에 다중 카테고리 차트를 만드는 방법을 배웠습니다. 여러 범주와 계열이 포함된 클러스터형 세로 막대형 차트를 만들기 위해 소스 코드가 포함된 단계별 가이드를 진행했습니다.

## FAQ

### 차트 모양을 어떻게 사용자 정의할 수 있나요?

색상, 글꼴, 스타일과 같은 속성을 수정하여 차트 모양을 사용자 정의할 수 있습니다. 자세한 사용자 정의 옵션은 Aspose.Slides 문서를 참조하세요.

### 차트에 시리즈를 더 추가할 수 있나요?

예, 5단계에 표시된 유사한 프로세스에 따라 차트에 계열을 추가할 수 있습니다.

### 차트 종류를 어떻게 변경하나요?

 차트 유형을 변경하려면`ChartType.ClusteredColumn` 2단계에서 차트를 추가할 때 원하는 차트 유형으로 변경하세요.

### 차트에 제목을 어떻게 추가하나요?

 다음을 사용하여 차트에 제목을 추가할 수 있습니다.`ch.getChartTitle().getTextFrame().setText("Chart Title");` 방법.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

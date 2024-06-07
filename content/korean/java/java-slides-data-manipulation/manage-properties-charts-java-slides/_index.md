---
title: Java 슬라이드에서 속성 차트 관리
linktitle: Java 슬라이드에서 속성 차트 관리
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 멋진 차트를 만들고 Java 슬라이드의 속성을 관리하는 방법을 알아보세요. 강력한 프레젠테이션을 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 13
url: /ko/java/data-manipulation/manage-properties-charts-java-slides/
---

## Aspose.Slides를 사용하여 Java 슬라이드의 속성 및 차트 관리 소개

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 속성을 관리하고 차트를 만드는 방법을 살펴보겠습니다. Aspose.Slides는 PowerPoint 프레젠테이션 작업을 위한 강력한 Java API입니다. 소스 코드 예제를 포함하여 단계별 프로세스를 살펴보겠습니다.

## 전제조건

 시작하기 전에 프로젝트에 Java용 Aspose.Slides 라이브러리가 설치 및 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 슬라이드에 차트 추가

슬라이드에 차트를 추가하려면 다음 단계를 따르세요.

1. 필요한 클래스를 가져오고 프레젠테이션 클래스의 인스턴스를 만듭니다.

```java
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
```

2. 차트를 추가하려는 슬라이드에 접근합니다. 이 예에서는 첫 번째 슬라이드에 액세스합니다.

```java
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
```

3. 기본 데이터가 포함된 차트를 추가합니다. 이 경우 StackedColumn3D 차트를 추가합니다.

```java
// 기본 데이터가 포함된 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## 차트 데이터 설정

차트 데이터를 설정하려면 차트 데이터 통합 문서를 만들고 시리즈와 카테고리를 추가해야 합니다. 다음과 같이하세요:

4. 차트 데이터시트의 인덱스를 설정합니다.

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
```

5. 차트 데이터 통합 문서를 가져옵니다.

```java
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. 차트에 계열을 추가합니다. 이 예에서는 "시리즈 1"과 "시리즈 2"라는 두 개의 시리즈를 추가합니다.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. 차트에 카테고리를 추가합니다. 여기에 세 가지 카테고리를 추가합니다.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D 회전 속성 설정

이제 차트의 3D 회전 속성을 설정해 보겠습니다.

8. 직각 축을 설정합니다.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X축과 Y축의 회전 각도를 설정합니다. 이 예에서는 X를 40도, Y를 270도 회전합니다.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 깊이 백분율을 150으로 설정합니다.

```java
chart.getRotation3D().setDepthPercents(150);
```

## 계열 데이터 채우기

11. 두 번째 차트 시리즈를 가져와서 데이터 포인트로 채웁니다.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// 계열 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 오버랩 조정

12. 시리즈의 중복 값을 설정합니다. 예를 들어 겹치지 않도록 100으로 설정할 수 있습니다.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## 프레젠테이션 저장

마지막으로 프레젠테이션을 디스크에 저장합니다.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

그게 다야! Java에서 Aspose.Slides를 사용하여 사용자 정의 속성이 포함된 3D 누적 세로 막대형 차트를 성공적으로 만들었습니다.

## Java 슬라이드의 속성 차트 관리를 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
// 기본 데이터가 포함된 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D 속성 설정
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// 두 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//이제 계열 데이터를 채우는 중입니다.
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap 값 설정
series.getParentSeriesGroup().setOverlap((byte) 100);
// 프레젠테이션을 디스크에 쓰기
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 속성을 관리하고 차트를 만드는 세계를 탐구했습니다. Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 효율적으로 작업할 수 있도록 지원하는 강력한 Java API입니다. 우리는 필수 단계를 다루고 프로세스를 안내하는 소스 코드 예제를 제공했습니다.

## FAQ

### 차트 유형을 어떻게 변경할 수 있나요?

 차트 유형을 수정하여 차트 유형을 변경할 수 있습니다.`ChartType`차트를 추가할 때 매개변수입니다. 사용 가능한 차트 유형은 Aspose.Slides 설명서를 참조하세요.

### 차트 색상을 사용자 정의할 수 있나요?

예, 계열 데이터 포인트 또는 범주의 채우기 속성을 설정하여 차트 색상을 사용자 정의할 수 있습니다.

### 시리즈에 더 많은 데이터 포인트를 추가하려면 어떻게 해야 합니까?

 다음을 사용하여 계열에 더 많은 데이터 요소를 추가할 수 있습니다.`series.getDataPoints().addDataPointForBarSeries()` 방법을 사용하고 데이터 값이 포함된 셀을 지정합니다.

### 다른 회전 각도를 어떻게 설정하나요?

 X축과 Y축에 대해 다른 회전 각도를 설정하려면 다음을 사용합니다.`chart.getRotation3D().setRotationX()` 그리고`chart.getRotation3D().setRotationY()` 원하는 각도 값으로

### 사용자 정의할 수 있는 다른 3D 속성은 무엇입니까?

Aspose.Slides 문서를 참조하여 깊이, 원근감, 조명 등 차트의 다른 3D 속성을 탐색할 수 있습니다.
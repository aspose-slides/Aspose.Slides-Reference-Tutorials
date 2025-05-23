---
"description": "Aspose.Slides를 사용하여 멋진 차트를 만들고 Java 슬라이드의 속성을 관리하는 방법을 알아보세요. 강력한 프레젠테이션을 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에서 속성 차트 관리"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 속성 차트 관리"
"url": "/ko/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 속성 차트 관리


## Aspose.Slides를 사용하여 Java Slides에서 속성 및 차트 관리 소개

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 속성을 관리하고 차트를 만드는 방법을 살펴보겠습니다. Aspose.Slides는 PowerPoint 프레젠테이션 작업을 위한 강력한 Java API입니다. 소스 코드 예제를 포함하여 단계별 과정을 안내해 드리겠습니다.

## 필수 조건

시작하기 전에 Java용 Aspose.Slides 라이브러리가 프로젝트에 설치 및 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 슬라이드에 차트 추가

슬라이드에 차트를 추가하려면 다음 단계를 따르세요.

1. 필요한 클래스를 가져와서 Presentation 클래스의 인스턴스를 만듭니다.

```java
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
```

2. 차트를 추가할 슬라이드에 접근하세요. 이 예시에서는 첫 번째 슬라이드에 접근합니다.

```java
// 첫 번째 슬라이드에 접근하세요
ISlide slide = presentation.getSlides().get_Item(0);
```

3. 기본 데이터가 포함된 차트를 추가합니다. 여기서는 StackedColumn3D 차트를 추가합니다.

```java
// 기본 데이터로 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## 차트 데이터 설정

차트 데이터를 설정하려면 차트 데이터 통합 문서를 만들고 시리즈와 범주를 추가해야 합니다. 다음 단계를 따르세요.

4. 차트 데이터 시트의 인덱스를 설정합니다.

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
```

5. 차트 데이터 통합 문서를 받으세요.

```java
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. 차트에 시리즈를 추가합니다. 이 예에서는 "시리즈 1"과 "시리즈 2"라는 두 개의 시리즈를 추가합니다.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. 차트에 범주를 추가합니다. 여기서는 세 가지 범주를 추가합니다.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D 회전 속성 설정

이제 차트에 대한 3D 회전 속성을 설정해 보겠습니다.

8. 직각축을 설정합니다.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X축과 Y축의 회전 각도를 설정합니다. 이 예에서는 X축을 40도, Y축을 270도 회전합니다.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. 깊이 백분율을 150으로 설정합니다.

```java
chart.getRotation3D().setDepthPercents(150);
```

## 시리즈 데이터 채우기

11. 두 번째 차트 시리즈를 가져와 데이터 포인트로 채웁니다.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// 시리즈 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 오버랩 조정

12. 계열의 중복 값을 설정합니다. 예를 들어, 중복이 발생하지 않도록 100으로 설정할 수 있습니다.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## 프레젠테이션 저장

마지막으로 프레젠테이션을 디스크에 저장합니다.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

이제 끝입니다! Java에서 Aspose.Slides를 사용하여 사용자 지정 속성을 적용한 3D 누적 세로 막대형 차트를 성공적으로 만들었습니다.

## Java Slides에서 속성 차트 관리를 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
// 첫 번째 슬라이드에 접근하세요
ISlide slide = presentation.getSlides().get_Item(0);
// 기본 데이터로 차트 추가
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
// 두 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// OverLap 값 설정
series.getParentSeriesGroup().setOverlap((byte) 100);
// 디스크에 프레젠테이션 쓰기
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 속성을 관리하고 차트를 만드는 방법을 자세히 살펴보았습니다. Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 효율적으로 작업할 수 있도록 지원하는 강력한 Java API입니다. 핵심 단계를 설명하고 소스 코드 예제를 제공하여 프로세스를 안내해 드렸습니다.

## 자주 묻는 질문

### 차트 유형을 어떻게 변경할 수 있나요?

차트 유형을 수정하여 변경할 수 있습니다. `ChartType` 차트를 추가할 때 매개변수를 사용합니다. 사용 가능한 차트 유형은 Aspose.Slides 설명서를 참조하세요.

### 차트 색상을 사용자 지정할 수 있나요?

네, 시리즈 데이터 포인트나 범주의 채우기 속성을 설정하여 차트 색상을 사용자 지정할 수 있습니다.

### 시리즈에 더 많은 데이터 포인트를 추가하려면 어떻게 해야 하나요?

다음을 사용하여 시리즈에 더 많은 데이터 포인트를 추가할 수 있습니다. `series.getDataPoints().addDataPointForBarSeries()` 방법과 데이터 값이 포함된 셀을 지정합니다.

### 다른 회전 각도를 어떻게 설정할 수 있나요?

X축과 Y축에 대해 다른 회전 각도를 설정하려면 다음을 사용하세요. `chart.getRotation3D().setRotationX()` 그리고 `chart.getRotation3D().setRotationY()` 원하는 각도 값으로.

### 사용자 정의가 가능한 다른 3D 속성은 무엇입니까?

Aspose.Slides 설명서를 참조하면 깊이, 원근감, 조명 등 차트의 다른 3D 속성을 살펴볼 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
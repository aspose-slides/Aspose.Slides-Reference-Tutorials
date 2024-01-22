---
title: Java 슬라이드의 기존 차트
linktitle: Java 슬라이드의 기존 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 향상하세요. 기존 차트를 프로그래밍 방식으로 수정하는 방법을 알아보세요. 차트 사용자 정의를 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 12
url: /ko/java/chart-elements/existing-chart-java-slides/
---

## Aspose.Slides for Java를 사용하여 Java 슬라이드의 기존 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 수정하는 방법을 보여줍니다. 차트 데이터, 카테고리 이름, 시리즈 이름을 변경하고 차트에 새 시리즈를 추가하는 단계를 살펴보겠습니다. 프로젝트에 Java용 Aspose.Slides가 설정되어 있는지 확인하세요.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. 프로젝트에 포함된 Java 라이브러리용 Aspose.Slides.
2. 수정하려는 차트가 포함된 기존 PowerPoint 프레젠테이션.
3. Java 개발 환경이 설정되었습니다.

## 1단계: 프레젠테이션 로드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// PPTX 파일을 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2단계: 슬라이드 및 차트에 액세스

```java
// 첫 번째 슬라이드에 액세스
ISlide sld = pres.getSlides().get_Item(0);

// 슬라이드의 차트에 액세스
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 3단계: 차트 데이터 및 카테고리 이름 변경

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;

//차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 차트 카테고리 이름 변경
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 4단계: 첫 번째 차트 시리즈 업데이트

```java
// 첫 번째 차트 시리즈를 살펴보세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 시리즈 이름 업데이트
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// 시리즈 데이터 업데이트
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 5단계: 두 번째 차트 시리즈 업데이트

```java
// 두 번째 차트 시리즈 살펴보기
series = chart.getChartData().getSeries().get_Item(1);

// 시리즈 이름 업데이트
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// 시리즈 데이터 업데이트
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## 6단계: 차트에 새 시리즈 추가

```java
// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// 세 번째 차트 시리즈 살펴보기
series = chart.getChartData().getSeries().get_Item(2);

// 계열 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 7단계: 차트 유형 변경

```java
//차트 유형을 클러스터형 원통형으로 변경합니다.
chart.setType(ChartType.ClusteredCylinder);
```

## 8단계: 수정된 프리젠테이션 저장

```java
// 수정된 차트로 프레젠테이션을 저장하세요.
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 성공적으로 수정했습니다. 이제 이 코드를 사용하여 PowerPoint 프레젠테이션의 차트를 프로그래밍 방식으로 사용자 지정할 수 있습니다.

## Java 슬라이드의 기존 차트에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 Instantiate Presentation 클래스// PPTX 파일을 나타내는 Instantiate Presentation 클래스
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// 첫 번째 슬라이드 마커에 액세스
ISlide sld = pres.getSlides().get_Item(0);
// 기본 데이터가 포함된 차트 추가
IChart chart = (IChart) sld.getShapes().get_Item(0);
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
//차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 차트 카테고리 이름 변경
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// 첫 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 현재 시리즈 데이터를 업데이트 중입니다.
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// 시리즈 이름 수정
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// 두 번째 차트 시리즈 가져오기
series = chart.getChartData().getSeries().get_Item(1);
// 현재 시리즈 데이터를 업데이트 중입니다.
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// 시리즈 이름 수정
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// 이제 새로운 시리즈가 추가됩니다
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// 세 번째 차트 시리즈 가져오기
series = chart.getChartData().getSeries().get_Item(2);
// 이제 계열 데이터를 채우는 중입니다.
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// 차트와 함께 프레젠테이션 저장
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 결론

이 포괄적인 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 수정하는 방법을 배웠습니다. 단계별 가이드를 따르고 소스 코드 예제를 활용하면 특정 요구 사항에 맞게 차트를 쉽게 사용자 정의하고 업데이트할 수 있습니다. 우리가 다룬 내용을 요약하면 다음과 같습니다.

## FAQ

### 차트 유형을 어떻게 변경할 수 있나요?

 다음을 사용하여 차트 유형을 변경할 수 있습니다.`chart.setType(ChartType.ChartTypeHere)` 방법. 바꾸다`ChartTypeHere` 다음과 같은 원하는 차트 유형으로`ChartType.ClusteredCylinder` 우리의 예에서는.

### 시리즈에 더 많은 데이터 포인트를 추가할 수 있나요?

 예, 다음을 사용하여 시리즈에 더 많은 데이터 포인트를 추가할 수 있습니다.`series.getDataPoints().addDataPointForBarSeries(cell)` 방법. 적절한 셀 데이터를 제공했는지 확인하세요.

### 카테고리 이름을 어떻게 업데이트하나요?

 다음을 사용하여 카테고리 이름을 업데이트할 수 있습니다.`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 새 카테고리 이름을 설정합니다.

### 시리즈 이름을 수정하려면 어떻게 해야 하나요?

 시리즈 이름을 수정하려면 다음을 사용하세요.`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 새로운 시리즈 이름을 설정합니다.

### 차트에서 계열을 제거하는 방법이 있나요?

 예, 다음을 사용하여 차트에서 계열을 제거할 수 있습니다.`chart.getChartData().getSeries().removeAt(index)` 방법, 여기서`index`제거하려는 시리즈의 인덱스입니다.
---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 더욱 풍성하게 만들어 보세요. 기존 차트를 프로그래밍 방식으로 수정하는 방법을 알아보세요. 차트 사용자 정의를 위한 소스 코드가 포함된 단계별 가이드도 제공됩니다."
"linktitle": "Java Slides의 기존 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides의 기존 차트"
"url": "/ko/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides의 기존 차트


## Aspose.Slides for Java를 사용하여 Java 슬라이드의 기존 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 수정하는 방법을 보여드리겠습니다. 차트 데이터, 범주 이름, 시리즈 이름을 변경하고 차트에 새 시리즈를 추가하는 단계를 살펴보겠습니다. 프로젝트에 Aspose.Slides for Java가 설치되어 있는지 확인하세요.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

1. 프로젝트에 Java용 Aspose.Slides 라이브러리가 포함되어 있습니다.
2. 수정하려는 차트가 있는 기존 PowerPoint 프레젠테이션입니다.
3. Java 개발 환경 설정.

## 1단계: 프레젠테이션 로드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";

// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2단계: 슬라이드 및 차트에 액세스

```java
// 첫 번째 슬라이드에 접근하세요
ISlide sld = pres.getSlides().get_Item(0);

// 슬라이드의 차트에 접근하세요
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 3단계: 차트 데이터 및 범주 이름 변경

```java
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;

// 차트 데이터 워크시트 가져오기
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
// 두 번째 차트 시리즈를 살펴보세요
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

// 세 번째 차트 시리즈를 살펴보세요
series = chart.getChartData().getSeries().get_Item(2);

// 시리즈 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 7단계: 차트 유형 변경

```java
// 차트 유형을 클러스터형 원통형으로 변경합니다.
chart.setType(ChartType.ClusteredCylinder);
```

## 8단계: 수정된 프레젠테이션 저장

```java
// 수정된 차트로 프레젠테이션을 저장합니다.
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 성공적으로 수정했습니다. 이제 이 코드를 사용하여 PowerPoint 프레젠테이션의 차트를 프로그래밍 방식으로 사용자 지정할 수 있습니다.

## Java Slides의 기존 차트에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// 첫 번째 슬라이드 마커에 접근하세요
ISlide sld = pres.getSlides().get_Item(0);
// 기본 데이터로 차트 추가
IChart chart = (IChart) sld.getShapes().get_Item(0);
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 차트 카테고리 이름 변경
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// 첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 이제 시리즈 데이터를 업데이트합니다
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// 시리즈 이름 수정
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// 두 번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(1);
// 이제 시리즈 데이터를 업데이트합니다
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// 시리즈 이름 수정
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// 이제 새로운 시리즈를 추가합니다
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// 3번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(2);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// 차트와 함께 프레젠테이션 저장
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## 결론

이 포괄적인 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기존 차트를 수정하는 방법을 알아보았습니다. 단계별 가이드를 따라 하고 소스 코드 예제를 활용하면 특정 요구 사항에 맞게 차트를 쉽게 사용자 지정하고 업데이트할 수 있습니다. 배운 내용을 요약하면 다음과 같습니다.

## 자주 묻는 질문

### 차트 유형을 어떻게 변경할 수 있나요?

차트 유형은 다음을 사용하여 변경할 수 있습니다. `chart.setType(ChartType.ChartTypeHere)` 방법. 교체 `ChartTypeHere` 원하는 차트 유형(예: `ChartType.ClusteredCylinder` 우리의 예에서.

### 시리즈에 더 많은 데이터 포인트를 추가할 수 있나요?

예, 다음을 사용하여 시리즈에 더 많은 데이터 포인트를 추가할 수 있습니다. `series.getDataPoints().addDataPointForBarSeries(cell)` 메서드입니다. 적절한 셀 데이터를 제공해야 합니다.

### 카테고리 이름을 어떻게 업데이트합니까?

다음을 사용하여 카테고리 이름을 업데이트할 수 있습니다. `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 새로운 카테고리 이름을 설정합니다.

### 시리즈 이름을 어떻게 수정합니까?

시리즈 이름을 수정하려면 다음을 사용하세요. `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` 새로운 시리즈 이름을 설정합니다.

### 차트에서 시리즈를 제거하는 방법이 있나요?

예, 다음을 사용하여 차트에서 시리즈를 제거할 수 있습니다. `chart.getChartData().getSeries().removeAt(index)` 방법, 여기서 `index` 제거하려는 시리즈의 인덱스입니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
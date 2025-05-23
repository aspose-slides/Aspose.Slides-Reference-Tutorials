---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드에서 일반 차트를 만들어 보세요. PowerPoint 프레젠테이션에서 차트를 만들고, 사용자 지정하고, 저장하는 방법에 대한 단계별 가이드와 소스 코드를 제공합니다."
"linktitle": "Java 슬라이드의 일반 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 일반 차트"
"url": "/ko/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 일반 차트


## Java 슬라이드의 정규 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 일반 차트를 만드는 과정을 살펴보겠습니다. 단계별 지침과 소스 코드를 사용하여 PowerPoint 프레젠테이션에서 클러스터형 세로 막대형 차트를 만드는 방법을 보여드리겠습니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java API용 Aspose.Slides가 설치되었습니다.
2. Java 개발 환경이 설정되었습니다.
3. Java 프로그래밍에 대한 기본 지식.

## 1단계: 프로젝트 설정

프로젝트 디렉터리를 만드세요. 코드에 언급된 대로 "문서 디렉터리"라고 부르겠습니다. 이 디렉터리를 프로젝트 디렉터리의 실제 경로로 바꿔도 됩니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## 2단계: 프레젠테이션 만들기

이제 PowerPoint 프레젠테이션을 만들고 첫 번째 슬라이드에 접근해 보겠습니다.

```java
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation();
// 첫 번째 슬라이드에 접근하세요
ISlide sld = pres.getSlides().get_Item(0);
```

## 3단계: 차트 추가

슬라이드에 클러스터형 막대형 차트를 추가하고 제목을 설정합니다.

```java
// 기본 데이터로 차트 추가
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 차트 제목 설정
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 4단계: 차트 데이터 설정

다음으로, 시리즈와 카테고리를 정의하여 차트 데이터를 설정합니다.

```java
// 첫 번째 시리즈를 값 표시로 설정
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;

// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 기본으로 생성된 시리즈 및 카테고리 삭제
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// 새로운 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 5단계: 시리즈 데이터 채우기

이제 차트의 시리즈 데이터 포인트를 채워 보겠습니다.

```java
// 첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 시리즈 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// 시리즈의 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// 두 번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(1);

// 시리즈 데이터 채우기
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// 시리즈의 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 6단계: 라벨 사용자 정의

차트 시리즈의 데이터 레이블을 사용자 지정해 보겠습니다.

```java
// 첫 번째 레이블에는 카테고리 이름이 표시됩니다.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// 시리즈 이름과 구분 기호를 사용하여 세 번째 레이블의 값을 표시합니다.
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## 7단계: 프레젠테이션 저장

마지막으로 차트가 포함된 프레젠테이션을 프로젝트 디렉토리에 저장합니다.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

이것으로 끝입니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 클러스터형 세로 막대형 차트를 성공적으로 만들었습니다. 이 차트는 필요에 따라 추가로 사용자 지정할 수 있습니다.

## Java Slides의 일반 차트에 대한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation();
// 첫 번째 슬라이드에 접근하세요
ISlide sld = pres.getSlides().get_Item(0);
// 기본 데이터로 차트 추가
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// 차트 제목 설정
// Chart.getChartTitle().getTextFrameForOverriding().setText("샘플 제목");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// 첫 번째 시리즈를 값 표시로 설정
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// 기본으로 생성된 시리즈 및 카테고리 삭제
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// 새로운 카테고리 추가
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// 첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// 시리즈의 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// 두 번째 차트 시리즈를 가져가세요
series = chart.getChartData().getSeries().get_Item(1);
// 이제 시리즈 데이터를 채우고 있습니다
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// 시리즈의 채우기 색상 설정
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// 첫 번째 레이블에는 카테고리 이름이 표시됩니다.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// 세 번째 레이블의 값 표시
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// 차트와 함께 프레젠테이션 저장
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 일반 차트를 만드는 방법을 알아보았습니다. 소스 코드를 사용하여 PowerPoint 프레젠테이션에서 클러스터형 세로 막대형 차트를 만드는 단계별 가이드를 살펴보았습니다.

## 자주 묻는 질문

### 차트 유형을 어떻게 변경할 수 있나요?

차트 유형을 변경하려면 다음을 수정하세요. `ChartType` 차트를 추가할 때 매개변수 사용 `sld.getShapes().addChart()`Aspose.Slides에서 제공하는 다양한 차트 유형 중에서 선택할 수 있습니다.

### 차트 시리즈의 색상을 변경할 수 있나요?

예, 각 시리즈의 채우기 색상을 설정하여 차트 시리즈의 색상을 변경할 수 있습니다. `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### 차트에 카테고리나 시리즈를 더 추가하려면 어떻게 해야 하나요?

새로운 데이터 포인트와 레이블을 추가하여 차트에 더 많은 범주나 시리즈를 추가할 수 있습니다. `chart.getChartData().getCategories().add()` 그리고 `chart.getChartData().getSeries().add()` 행동 양식.

### 차트 제목을 더 세부적으로 사용자 지정하려면 어떻게 해야 하나요?

차트 제목을 추가로 사용자 정의하려면 속성을 수정하세요. `chart.getChartTitle()` 예를 들어 텍스트 정렬, 글꼴 크기, 색상 등이 있습니다.

### 차트를 다른 파일 형식으로 저장하려면 어떻게 해야 하나요?

차트를 다른 파일 형식으로 저장하려면 다음을 변경하세요. `SaveFormat` 매개변수 `pres.save()` 원하는 형식(예: PDF, PNG, JPEG)으로 변환하는 방법입니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
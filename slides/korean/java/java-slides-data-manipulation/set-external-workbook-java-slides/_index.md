---
title: Java 슬라이드에서 외부 통합 문서 설정
linktitle: Java 슬라이드에서 외부 통합 문서 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java Slides에서 외부 통합 문서를 설정하는 방법을 알아보세요. Excel 데이터 통합으로 동적 프레젠테이션을 만드세요.
weight: 19
url: /ko/java/data-manipulation/set-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에서 외부 통합 문서 설정 소개

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 외부 통합 문서를 설정하는 방법을 살펴보겠습니다. 외부 Excel 통합 문서의 데이터를 참조하는 차트를 사용하여 PowerPoint 프레젠테이션을 만드는 방법을 배웁니다. 이 가이드를 마치면 외부 데이터를 Java 슬라이드 프레젠테이션에 통합하는 방법을 명확하게 이해하게 될 것입니다.

## 전제 조건

구현을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- 프로젝트에 Java 라이브러리용 Aspose.Slides가 추가되었습니다.
- 프레젠테이션에서 참조하려는 데이터가 포함된 Excel 통합 문서입니다.

## 1단계: 새 프레젠테이션 만들기

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Aspose.Slides를 사용하여 새로운 PowerPoint 프레젠테이션을 만드는 것부터 시작합니다.

## 2단계: 차트 추가

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

다음으로 프레젠테이션에 원형 차트를 삽입합니다. 필요에 따라 차트 유형과 위치를 사용자 정의할 수 있습니다.

## 3단계: 외부 통합 문서에 액세스

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 외부 통합 문서에 액세스하려면 다음을 사용합니다.`setExternalWorkbook` 메서드를 지정하고 데이터가 포함된 Excel 통합 문서에 대한 경로를 제공합니다.

## 4단계: 차트 데이터 바인딩

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

계열 및 범주에 대한 셀 참조를 지정하여 차트를 외부 통합 문서의 데이터에 바인딩합니다.

## 5단계: 프레젠테이션 저장

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

마지막으로 외부 통합 문서 참조가 포함된 프레젠테이션을 PowerPoint 파일로 저장합니다.

## Java 슬라이드의 외부 통합 문서 설정에 대한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides를 사용하여 Java 슬라이드에서 외부 통합 문서를 설정하는 방법을 배웠습니다. 이제 Excel 통합 문서의 데이터를 동적으로 참조하는 프레젠테이션을 만들어 슬라이드의 유연성과 상호 작용성을 향상시킬 수 있습니다.

## FAQ

### Java용 Aspose.Slides를 어떻게 설치하나요?

Aspose.Slides for Java는 Java 프로젝트에 라이브러리를 추가하여 설치할 수 있습니다. Aspose 웹사이트에서 라이브러리를 다운로드하고 설명서에 제공된 설치 지침을 따를 수 있습니다.

### 외부 통합 문서에 다양한 차트 유형을 사용할 수 있나요?

예, Aspose.Slides에서 지원하는 다양한 차트 유형을 사용하고 이를 외부 통합 문서의 데이터에 바인딩할 수 있습니다. 선택한 차트 유형에 따라 프로세스가 약간 다를 수 있습니다.

### 외부 통합 문서의 데이터 구조가 변경되면 어떻게 되나요?

외부 통합 문서의 데이터 구조가 변경되면 차트 데이터가 정확하게 유지되도록 Java 코드에서 셀 참조를 업데이트해야 할 수도 있습니다.

### Aspose.Slides는 최신 Java 버전과 호환됩니까?

Aspose.Slides for Java는 최신 Java 버전과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다. 최적의 성능과 호환성을 위해 업데이트를 확인하고 최신 버전의 라이브러리를 사용하십시오.

### 동일한 외부 통합 문서를 참조하는 여러 차트를 추가할 수 있나요?

예, 프레젠테이션에 여러 차트를 추가할 수 있으며 모두 동일한 외부 통합 문서를 참조합니다. 생성하려는 각 차트에 대해 이 튜토리얼에 설명된 단계를 반복하기만 하면 됩니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

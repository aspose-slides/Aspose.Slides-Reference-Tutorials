---
"description": "Aspose.Slides를 사용하여 Java Slides에서 Excel 통합 문서의 차트 데이터를 설정하는 방법을 알아보세요. 동적 프레젠테이션을 위한 코드 예제가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드에서 통합 문서의 차트 데이터 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 통합 문서의 차트 데이터 설정"
"url": "/ko/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 통합 문서의 차트 데이터 설정


## Java 슬라이드에서 통합 문서의 차트 데이터 설정 소개

Aspose.Slides for Java는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있도록 지원하는 강력한 라이브러리입니다. PowerPoint 슬라이드를 만들고, 조작하고, 관리하는 데 필요한 다양한 기능을 제공합니다. 프레젠테이션 작업 시 일반적으로 필요한 작업 중 하나는 Excel 통합 문서와 같은 외부 데이터 소스에서 차트 데이터를 동적으로 설정하는 것입니다. 이 튜토리얼에서는 Java를 사용하여 이를 구현하는 방법을 보여줍니다.

## 필수 조건

구현에 들어가기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Java 라이브러리용 Aspose.Slides가 프로젝트에 추가되었습니다.
- 차트에 사용할 데이터가 있는 Excel 통합 문서입니다.

## 1단계: 프레젠테이션 만들기

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

먼저 Aspose.Slides for Java를 사용하여 새로운 PowerPoint 프레젠테이션을 만듭니다.

## 2단계: 차트 추가

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

다음으로, 프레젠테이션의 슬라이드 중 하나에 차트를 추가합니다. 이 예시에서는 원형 차트를 추가하지만, 필요에 맞는 차트 유형을 선택할 수 있습니다.

## 3단계: 차트 데이터 지우기

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Excel 통합 문서의 새 데이터에 맞춰 차트의 기존 데이터를 모두 지웁니다.

## 4단계: Excel 통합 문서 로드

```java
Workbook workbook = new Workbook("Your Document Directory";
```

차트에 사용할 데이터가 포함된 Excel 통합 문서를 로드합니다. 바꾸기 `"book1.xlsx"` Excel 파일의 경로를 포함합니다.

## 5단계: 통합 문서 스트림을 차트 데이터에 쓰기

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Excel 통합 문서 데이터를 스트림으로 변환하여 차트 데이터에 기록합니다.

## 6단계: 차트 데이터 범위 설정

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

차트 데이터로 사용할 Excel 통합 문서의 셀 범위를 지정합니다. 필요에 따라 데이터의 범위를 조정하세요.

## 7단계: 차트 시리즈 사용자 지정

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

차트 시리즈의 다양한 속성을 필요에 맞게 사용자 지정할 수 있습니다. 이 예시에서는 차트 시리즈에 다양한 색상을 적용해 보겠습니다.

## 8단계: 프레젠테이션 저장

```java
pres.save(outPath, SaveFormat.Pptx);
```

마지막으로 업데이트된 차트 데이터가 포함된 프레젠테이션을 지정된 출력 경로에 저장합니다.

## Java 슬라이드의 통합 문서에서 차트 데이터 설정을 위한 전체 소스 코드

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 Java Slides에서 Excel 통합 문서의 차트 데이터를 설정하는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 소스 코드 예제를 활용하면 동적 차트 데이터를 PowerPoint 프레젠테이션에 쉽게 통합할 수 있습니다.

## 자주 묻는 질문

### 프레젠테이션에서 차트의 모양을 사용자 지정하려면 어떻게 해야 하나요?

색상, 글꼴, 레이블 등의 속성을 수정하여 차트 모양을 사용자 지정할 수 있습니다. 차트 사용자 지정 옵션에 대한 자세한 내용은 Aspose.Slides for Java 설명서를 참조하세요.

### 다른 Excel 파일의 데이터를 차트에 사용할 수 있나요?

네, 코드에서 통합 문서를 로드할 때 올바른 파일 경로를 지정하면 모든 Excel 파일의 데이터를 사용할 수 있습니다.

### Aspose.Slides for Java를 사용하여 어떤 다른 유형의 차트를 만들 수 있나요?

Aspose.Slides for Java는 막대형 차트, 선형 차트, 분산형 차트 등 다양한 차트 유형을 지원합니다. 데이터 표현 요구 사항에 가장 적합한 차트 유형을 선택할 수 있습니다.

### 실행 중인 프레젠테이션에서 차트 데이터를 동적으로 업데이트할 수 있나요?

네, 기본 통합 문서를 수정한 다음 차트 데이터를 새로 고쳐 프레젠테이션에서 차트 데이터를 동적으로 업데이트할 수 있습니다.

### Java용 Aspose.Slides를 사용하는 데 필요한 더 많은 예제와 리소스는 어디에서 찾을 수 있나요?

추가 예제와 리소스를 탐색할 수 있습니다. [Aspose 웹사이트](https://www.aspose.com/)또한, Aspose.Slides for Java 설명서에서는 라이브러리 작업에 대한 포괄적인 지침을 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
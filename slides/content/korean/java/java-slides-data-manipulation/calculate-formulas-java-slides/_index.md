---
title: Java 슬라이드에서 수식 계산
linktitle: Java 슬라이드에서 수식 계산
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java Slides에서 수식을 계산하는 방법을 알아보세요. 동적 PowerPoint 프레젠테이션을 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/java/data-manipulation/calculate-formulas-java-slides/
---

## Aspose.Slides를 사용하여 Java 슬라이드에서 수식 계산 소개

이 가이드에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드에서 수식을 계산하는 방법을 보여줍니다. Aspose.Slides는 PowerPoint 프레젠테이션 작업을 위한 강력한 라이브러리이며 슬라이드 내에서 차트를 조작하고 수식 계산을 수행하는 기능을 제공합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- 자바 개발 환경
-  Aspose.Slides for Java 라이브러리(다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)
- Java 프로그래밍에 대한 기본 지식

## 1단계: 새 프레젠테이션 만들기

먼저 새 PowerPoint 프레젠테이션을 만들고 여기에 슬라이드를 추가해 보겠습니다. 이 예에서는 단일 슬라이드로 작업하겠습니다.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

이제 슬라이드에 묶은 세로 막대형 차트를 추가해 보겠습니다. 이 차트를 사용하여 수식 계산을 보여 드리겠습니다.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## 3단계: 수식 및 값 설정

다음으로 Aspose.Slides API를 사용하여 차트 데이터 셀의 수식과 값을 설정하겠습니다. 이 셀의 공식을 계산하겠습니다.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// A1 셀의 수식 설정
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// 셀 A2의 값 설정
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// B2 셀의 수식 설정
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// C2 셀의 수식 설정
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// A1 셀의 수식을 다시 설정하세요.
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## 4단계: 프레젠테이션 저장

마지막으로 계산된 수식을 사용하여 수정된 프레젠테이션을 저장해 보겠습니다.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Java 슬라이드의 수식 계산을 위한 완전한 소스 코드

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 가이드에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 수식을 계산하는 방법을 배웠습니다. 새 프레젠테이션을 만들고 여기에 차트를 추가하고 차트 데이터 셀의 수식과 값을 설정하고 계산된 수식으로 프레젠테이션을 저장했습니다.

## FAQ

### 차트 데이터 셀에 대한 수식을 어떻게 설정합니까?

 다음을 사용하여 차트 데이터 셀에 대한 수식을 설정할 수 있습니다.`setFormula` 의 방법`IChartDataCell` Aspose.Slides에서.

### 차트 데이터 셀의 값을 어떻게 설정합니까?

 다음을 사용하여 차트 데이터 셀의 값을 설정할 수 있습니다.`setValue` 의 방법`IChartDataCell` Aspose.Slides에서.

### 통합 문서에서 수식을 어떻게 계산하나요?

 다음을 사용하여 통합 문서의 수식을 계산할 수 있습니다.`calculateFormulas` 의 방법`IChartDataWorkbook` Aspose.Slides에서.

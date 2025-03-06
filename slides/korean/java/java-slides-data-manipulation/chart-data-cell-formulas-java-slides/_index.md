---
title: Java 슬라이드의 차트 데이터 셀 수식
linktitle: Java 슬라이드의 차트 데이터 셀 수식
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 차트 데이터 셀 수식을 설정하는 방법을 알아보세요. 수식을 사용하여 동적 차트를 만듭니다.
weight: 11
url: /ko/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 차트 데이터 셀 수식


## Aspose.Slides for Java의 차트 데이터 셀 수식 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 데이터 셀 수식으로 작업하는 방법을 살펴보겠습니다. Aspose.Slides를 사용하면 데이터 셀에 대한 수식 설정을 포함하여 PowerPoint 프레젠테이션에서 차트를 만들고 조작할 수 있습니다.

## 전제 조건

 시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 1단계: PowerPoint 프레젠테이션 만들기

먼저 새 PowerPoint 프레젠테이션을 만들고 여기에 차트를 추가해 보겠습니다.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // 첫 번째 슬라이드에 차트 추가
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // 차트 데이터에 대한 통합 문서 가져오기
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // 데이터 셀 작업 계속하기
    // ...
    
    // 프레젠테이션 저장
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 2단계: 데이터 셀에 대한 수식 설정

이제 차트의 특정 데이터 셀에 대한 수식을 설정해 보겠습니다. 이 예에서는 두 개의 서로 다른 셀에 대한 수식을 설정합니다.

### 셀 1: A1 표기법 사용

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

위 코드에서는 A1 표기법을 사용하여 셀 B2에 대한 수식을 설정했습니다. 이 수식은 셀 F2부터 H5까지의 합계를 계산하고 그 결과에 1을 더합니다.

### 셀 2: R1C1 표기법 사용

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

여기서는 R1C1 표기법을 사용하여 셀 C2에 대한 수식을 설정했습니다. 이 공식은 R2C6~R5C8 범위 내에서 최대값을 계산한 다음 이를 3으로 나눕니다.

## 3단계: 수식 계산

수식을 설정한 후에는 다음 코드를 사용하여 계산하는 것이 중요합니다.

```java
workbook.calculateFormulas();
```

이 단계를 수행하면 차트에 수식을 기반으로 업데이트된 값이 반영됩니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 파일에 저장합니다.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Java 슬라이드의 차트 데이터 셀 수식에 대한 완전한 소스 코드

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java에서 차트 데이터 셀 수식을 사용하는 방법을 살펴보았습니다. 우리는 PowerPoint 프레젠테이션 만들기, 차트 추가, 데이터 셀에 대한 수식 설정, 수식 계산 및 프레젠테이션 저장에 대해 다루었습니다. 이제 이러한 기능을 활용하여 프레젠테이션에서 동적 데이터 기반 차트를 만들 수 있습니다.

## 자주 묻는 질문

### 특정 슬라이드에 차트를 어떻게 추가하나요?

 특정 슬라이드에 차트를 추가하려면`getSlides().get_Item(slideIndex)` 방법을 사용하여 원하는 슬라이드에 액세스한 다음`addChart` 차트를 추가하는 방법입니다.

### 데이터 셀에서 다양한 유형의 수식을 사용할 수 있나요?

예, 데이터 셀 수식에서는 수학 연산, 함수, 다른 셀에 대한 참조 등 다양한 유형의 수식을 사용할 수 있습니다.

### 차트 종류를 어떻게 변경하나요?

 다음을 사용하여 차트 유형을 변경할 수 있습니다.`setChartType` 에 대한 방법`IChart` 객체를 지정하고 원하는 것을 지정`ChartType`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

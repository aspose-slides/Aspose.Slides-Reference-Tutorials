---
"description": "Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 차트 데이터 셀 수식을 설정하는 방법을 알아보세요. 수식을 사용하여 동적 차트를 만들어 보세요."
"linktitle": "Java 슬라이드의 차트 데이터 셀 수식"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 차트 데이터 셀 수식"
"url": "/ko/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 차트 데이터 셀 수식


## Aspose.Slides for Java의 차트 데이터 셀 수식 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트 데이터 셀 수식을 사용하는 방법을 살펴보겠습니다. Aspose.Slides를 사용하면 PowerPoint 프레젠테이션에서 차트를 만들고 조작할 수 있으며, 데이터 셀 수식 설정도 가능합니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: PowerPoint 프레젠테이션 만들기

먼저, 새로운 PowerPoint 프레젠테이션을 만들고 차트를 추가해 보겠습니다.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // 첫 번째 슬라이드에 차트 추가
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // 차트 데이터에 대한 통합 문서 가져오기
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // 데이터 셀 작업을 계속합니다.
    // ...
    
    // 프레젠테이션을 저장하세요
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 2단계: 데이터 셀에 대한 수식 설정

이제 차트의 특정 데이터 셀에 수식을 설정해 보겠습니다. 이 예제에서는 두 개의 서로 다른 셀에 수식을 설정해 보겠습니다.

### 셀 1: A1 표기법 사용

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

위 코드에서는 A1 표기법을 사용하여 B2 셀에 수식을 설정했습니다. 이 수식은 F2부터 H5 셀까지의 합계를 계산하고 그 결과에 1을 더합니다.

### 셀 2: R1C1 표기법 사용

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

여기서는 R1C1 표기법을 사용하여 C2 셀에 수식을 설정합니다. 이 수식은 R2C6에서 R5C8 사이의 범위 내에서 최댓값을 계산한 다음 3으로 나눕니다.

## 3단계: 수식 계산

공식을 설정한 후에는 다음 코드를 사용하여 공식을 계산하는 것이 필수입니다.

```java
workbook.calculateFormulas();
```

이 단계에서는 수식에 따라 업데이트된 값이 차트에 반영되도록 합니다.

## 4단계: 프레젠테이션 저장

마지막으로 수정된 프레젠테이션을 파일로 저장합니다.

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

이 튜토리얼에서는 Aspose.Slides for Java에서 차트 데이터 셀 수식을 사용하는 방법을 살펴보았습니다. PowerPoint 프레젠테이션 만들기, 차트 추가, 데이터 셀 수식 설정, 수식 계산, 프레젠테이션 저장 방법을 다루었습니다. 이제 이러한 기능을 활용하여 프레젠테이션에서 동적이고 데이터 기반의 차트를 만들 수 있습니다.

## 자주 묻는 질문

### 특정 슬라이드에 차트를 추가하려면 어떻게 해야 하나요?

특정 슬라이드에 차트를 추가하려면 다음을 사용할 수 있습니다. `getSlides().get_Item(slideIndex)` 원하는 슬라이드에 액세스하는 방법을 사용한 다음 `addChart` 차트를 추가하는 방법입니다.

### 데이터 셀에서 다양한 유형의 수식을 사용할 수 있나요?

네, 수학 연산, 함수, 다른 셀에 대한 참조 등 다양한 유형의 수식을 데이터 셀 수식에 사용할 수 있습니다.

### 차트 유형을 어떻게 변경합니까?

차트 유형은 다음을 사용하여 변경할 수 있습니다. `setChartType` 방법에 대한 `IChart` 객체를 지정하고 원하는 것을 지정합니다. `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
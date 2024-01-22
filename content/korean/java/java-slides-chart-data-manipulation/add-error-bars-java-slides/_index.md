---
title: Java 슬라이드에 오류 막대 추가
linktitle: Java 슬라이드에 오류 막대 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java의 PowerPoint 차트에 오류 막대를 추가하는 방법을 알아보세요. 오류 막대를 사용자 정의하기 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 13
url: /ko/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Aspose.Slides를 사용하여 Java 슬라이드에 오류 막대 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 차트에 오류 막대를 추가하는 방법을 보여줍니다. 오차 막대는 차트에 있는 데이터 포인트의 변동성 또는 불확실성에 대한 귀중한 정보를 제공합니다. 거품형 차트를 만들고 여기에 오류 막대를 추가해 보겠습니다. 시작하자!

## 전제조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://downloads.aspose.com/slides/java).

## 1단계: 빈 프레젠테이션 만들기

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
```

이 단계에서는 오류 막대가 있는 차트를 추가할 빈 프레젠테이션을 만듭니다.

## 2단계: 거품형 차트 만들기

```java
// 거품형 차트 만들기
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

여기에서는 버블 차트를 만들고 슬라이드에서 위치와 크기를 지정합니다.

## 3단계: 오차 막대 추가 및 형식 설정

```java
// 오류 막대 추가 및 형식 설정
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

이 단계에서는 차트에 오류 막대를 추가하고 형식을 설정합니다. 값, 유형 및 기타 속성을 변경하여 오류 막대를 사용자 정의할 수 있습니다.

- `errBarX` X축을 따라 오류 막대를 나타냅니다.
- `errBarY` Y축을 따라 오류 막대를 나타냅니다.
- X 및 Y 오류 막대를 모두 표시합니다.
- `setValueType` 오류 막대의 값 유형(예: 고정 또는 백분율)을 지정합니다.
- `setValue` 오류 막대의 값을 설정합니다.
- `setType` 오류 막대의 유형(예: 플러스 또는 마이너스)을 정의합니다.
-  다음을 사용하여 오차 막대 선의 너비를 설정합니다.`getFormat().getLine().setWidth(2)`.
- `setEndCap`오류 막대에 끝 대문자를 포함할지 여부를 지정합니다.

## 4단계: 프레젠테이션 저장

```java
// 프레젠테이션 저장 중
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

마지막으로 오류 막대가 추가된 프레젠테이션을 지정된 위치에 저장합니다.

그게 다야! Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 차트에 오류 막대를 성공적으로 추가했습니다.

## Java 슬라이드에 오류 막대 추가를 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
try
{
	// 거품형 차트 만들기
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// 오류 막대 추가 및 형식 설정
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// 프레젠테이션 저장 중
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에 오류 막대를 추가하여 PowerPoint 프레젠테이션을 향상시키는 방법을 살펴보았습니다. 오차 막대는 데이터 변동성과 불확실성에 대한 귀중한 통찰력을 제공하여 프레젠테이션을 더욱 유익하고 시각적으로 매력적으로 만듭니다.

## FAQ

### 오류 막대의 모양을 추가로 사용자 정의하려면 어떻게 해야 합니까?

3단계에 설명된 대로 선 스타일, 색상, 너비 등의 속성을 수정하여 오류 막대를 사용자 정의할 수 있습니다.

### 다른 차트 유형에 오류 막대를 추가할 수 있나요?

예, Aspose.Slides for Java가 지원하는 다양한 차트 유형에 오류 막대를 추가할 수 있습니다. 원하는 차트 유형을 만들고 동일한 오류 막대 사용자 정의 단계를 따르기만 하면 됩니다.

### 슬라이드에서 차트의 위치와 크기를 어떻게 조정하나요?

 매개변수를 조정하여 차트의 위치와 크기를 제어할 수 있습니다.`addChart` 2단계에 표시된 대로 방법을 사용합니다.

### Aspose.Slides for Java에 대한 자세한 정보는 어디서 찾을 수 있나요?

 당신은[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 도서관 이용에 대한 자세한 내용은
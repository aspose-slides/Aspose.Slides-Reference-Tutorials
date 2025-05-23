---
"description": "Aspose.Slides를 사용하여 Java Slides의 PowerPoint 차트에 사용자 지정 오차 막대를 추가하는 방법을 알아보세요. 정확한 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에 사용자 정의 오류 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에 사용자 정의 오류 추가"
"url": "/ko/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에 사용자 정의 오류 추가


## Aspose.Slides를 사용하여 Java 슬라이드에 사용자 정의 오차 막대 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 차트에 사용자 지정 오차 막대를 추가하는 방법을 알아봅니다. 오차 막대는 차트에서 데이터 요소의 변동성이나 불확실성을 표시하는 데 유용합니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- 프로젝트에 Java 라이브러리용 Aspose.Slides를 설치하고 구성했습니다.
- Java 개발 환경이 설정되었습니다.

## 1단계: 빈 프레젠테이션 만들기

먼저, 빈 PowerPoint 프레젠테이션을 만듭니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
```

## 2단계: 거품형 차트 추가

다음으로, 프레젠테이션에 거품형 차트를 추가해 보겠습니다.

```java
// 버블 차트 만들기
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 3단계: 사용자 정의 오차 막대 추가

이제 차트 시리즈에 사용자 지정 오차 막대를 추가해 보겠습니다.

```java
// 사용자 정의 오류 막대 추가 및 형식 설정
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## 4단계: 오차 막대 데이터 설정

이 단계에서는 차트 시리즈 데이터 포인트에 액세스하여 각 포인트에 대한 사용자 지정 오차 막대 값을 설정합니다.

```java
// 차트 시리즈 데이터 포인트에 액세스하고 개별 포인트에 대한 오차 막대 값 설정
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// 차트 시리즈 포인트에 대한 오차 막대 설정
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## 5단계: 프레젠테이션 저장

마지막으로 사용자 정의 오차 막대를 적용하여 프레젠테이션을 저장합니다.

```java
// 프레젠테이션 저장
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

이제 끝났습니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 차트에 사용자 지정 오차 막대를 성공적으로 추가했습니다.

## Java 슬라이드에 사용자 정의 오류 추가를 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 빈 프레젠테이션 만들기
Presentation presentation = new Presentation();
try
{
	// 버블 차트 만들기
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// 사용자 정의 오류 막대 추가 및 형식 설정
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// 차트 시리즈 데이터 포인트에 액세스하고 개별 포인트에 대한 오차 막대 값 설정
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// 차트 시리즈 포인트에 대한 오차 막대 설정
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// 프레젠테이션 저장
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 포괄적인 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트에 사용자 지정 오차 막대를 추가하여 PowerPoint 프레젠테이션을 개선하는 방법을 알아보았습니다. 오차 막대는 데이터 변동성과 불확실성에 대한 귀중한 통찰력을 제공하여 차트를 더욱 유익하고 시각적으로 매력적으로 만들어 줍니다.

## 자주 묻는 질문

### 오차 막대의 모양을 사용자 지정하려면 어떻게 해야 하나요?

속성을 수정하여 오차 막대의 모양을 사용자 정의할 수 있습니다. `IErrorBarsFormat` 선 스타일, 선 색상, 오차 막대 너비 등의 개체입니다.

### 다른 차트 유형에 오차 막대를 추가할 수 있나요?

네, Aspose.Slides for Java에서 지원하는 다양한 차트 유형(막대형 차트, 선형 차트, 분산형 차트 등)에 오차 막대를 추가할 수 있습니다.

### 각 데이터 포인트에 대해 다른 오차 막대 값을 설정하려면 어떻게 해야 합니까?

위 코드에 표시된 대로 데이터 포인트를 반복하고 각 포인트에 대해 사용자 지정 오차 막대 값을 설정할 수 있습니다.

### 특정 데이터 포인트에 대한 오차 막대를 숨길 수 있나요?

예, 개별 데이터 포인트에 대한 오차 막대의 가시성을 설정하여 제어할 수 있습니다. `setVisible` 의 재산 `IErrorBarsFormat` 물체.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
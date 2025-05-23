---
"description": "Aspose.Slides for Java API를 사용하여 Java PowerPoint 프레젠테이션에서 레이더 차트를 만드는 방법을 알아보세요."
"linktitle": "Java 슬라이드로 레이더 차트 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드로 레이더 차트 만들기"
"url": "/ko/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드로 레이더 차트 만들기


## Java Slides에서 레이더 차트 만들기 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 방사형 차트를 만드는 과정을 안내합니다. 방사형 차트는 데이터를 원형 패턴으로 시각화하여 여러 데이터 시리즈를 쉽게 비교할 수 있도록 도와줍니다. Java 소스 코드와 함께 단계별 지침을 제공합니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 프로젝트에 통합되어 있는지 확인하세요. 라이브러리는 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 프레젠테이션 설정

먼저, 새로운 PowerPoint 프레젠테이션을 설정하고 슬라이드를 추가해 보겠습니다.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## 2단계: 레이더 차트 추가

다음으로, 슬라이드에 레이더 차트를 추가하겠습니다. 차트의 위치와 크기를 지정하겠습니다.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## 3단계: 차트 데이터 설정

이제 차트 데이터를 설정하겠습니다. 여기에는 데이터 통합 문서를 만들고, 범주를 추가하고, 계열을 추가하는 작업이 포함됩니다.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// 차트 제목 설정
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// 기본으로 생성된 시리즈 및 카테고리 삭제
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// 새로운 카테고리 추가
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// 새로운 시리즈 추가
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## 4단계: 시리즈 데이터 채우기

이제 레이더 차트에 대한 시리즈 데이터를 채워보겠습니다.

```java
// 시리즈 1에 대한 시리즈 데이터 채우기
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// 시리즈 색상 설정
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// 시리즈 2에 대한 시리즈 데이터 채우기
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// 시리즈 색상 설정
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## 5단계: 축 및 범례 사용자 정의

레이더 차트의 축과 범례를 사용자 지정해 보겠습니다.

```java
// 범례 위치 설정
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// 카테고리 축 텍스트 속성 설정
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// 범례 텍스트 속성 설정
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// 값 축 텍스트 속성 설정
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// 설정 값 축 번호 형식
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// 차트 주요 단위 값 설정
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## 6단계: 프레젠테이션 저장

마지막으로, 레이더 차트와 함께 생성된 프레젠테이션을 저장합니다.

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

이것으로 끝입니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 레이더 차트를 성공적으로 만들었습니다. 이제 이 예제를 사용자의 특정 요구에 맞게 추가로 사용자 지정할 수 있습니다.

## Java 슬라이드로 레이더 차트를 만드는 전체 소스 코드

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// 첫 번째 슬라이드에 접근하세요
	ISlide sld = pres.getSlides().get_Item(0);
	// 레이더 차트 추가
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// 차트 데이터 시트의 인덱스 설정
	int defaultWorksheetIndex = 0;
	// 차트 데이터 가져오기 워크시트
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// 차트 제목 설정
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// 기본으로 생성된 시리즈 및 카테고리 삭제
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// 새로운 카테고리 추가
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// 새로운 시리즈 추가
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// 이제 시리즈 데이터를 채우고 있습니다
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// 시리즈 색상 설정
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// 이제 다른 시리즈 데이터를 채웁니다.
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// 시리즈 색상 설정
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// 범례 위치 설정
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// 카테고리 축 텍스트 속성 설정
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// 범례 텍스트 속성 설정
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// 값 축 텍스트 속성 설정
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// 설정 값 축 번호 형식
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// 차트 주요 단위 값 설정
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// 생성된 프레젠테이션 저장
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 레이더 차트를 만드는 방법을 알아보았습니다. 이러한 개념을 적용하여 Java 애플리케이션에서 데이터를 효과적으로 시각화하고 표현할 수 있습니다.

## 자주 묻는 질문

### 차트 제목을 어떻게 바꿀 수 있나요?

차트 제목을 변경하려면 다음 줄을 수정하세요.
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### 레이더 차트에 더 많은 데이터 시리즈를 추가할 수 있나요?

네, 추가하려는 각 시리즈에 대해 "3단계"와 "4단계"의 단계에 따라 더 많은 데이터 시리즈를 추가할 수 있습니다.

### 차트 색상을 사용자 지정하려면 어떻게 해야 하나요?

시리즈 색상을 설정하는 선을 수정하여 시리즈 색상을 사용자 정의할 수 있습니다. `SolidFillColor` 각 시리즈의 속성입니다. 예:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### 축 레이블과 서식을 어떻게 변경할 수 있나요?

글꼴 크기와 색상을 포함하여 축 레이블과 서식을 사용자 지정하려면 "5단계"를 참조하세요.

### 차트를 다른 파일 형식으로 저장하려면 어떻게 해야 하나요?

파일 확장자를 수정하여 출력 형식을 변경할 수 있습니다. `outPath` 변수와 적절한 것을 사용하여 `SaveFormat`예를 들어 PDF로 저장하려면 다음을 사용하세요. `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
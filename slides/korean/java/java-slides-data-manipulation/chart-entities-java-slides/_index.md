---
"description": "Aspose.Slides를 사용하여 Java Slides 차트를 만들고 사용자 지정하는 방법을 알아보세요. 강력한 차트 엔터티로 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"linktitle": "Java 슬라이드의 차트 엔터티"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 차트 엔터티"
"url": "/ko/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 차트 엔터티


## Java 슬라이드의 차트 엔터티 소개

차트는 프레젠테이션에서 데이터를 시각화하는 강력한 도구입니다. 비즈니스 보고서, 학술 프레젠테이션 또는 기타 형태의 콘텐츠를 만들 때 차트는 정보를 효과적으로 전달하는 데 도움이 됩니다. Aspose.Slides for Java는 차트 작업을 위한 강력한 기능을 제공하여 Java 개발자에게 필수적인 선택입니다.

## 필수 조건

차트 엔터티의 세계로 들어가기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Java Development Kit(JDK) 설치됨
- Java용 Aspose.Slides 라이브러리가 다운로드되어 프로젝트에 추가되었습니다.
- 자바 프로그래밍에 대한 기본 지식

이제 Aspose.Slides for Java를 사용하여 차트를 만들고 사용자 지정하는 작업을 시작해 보겠습니다.

## 1단계: 프레젠테이션 만들기

첫 번째 단계는 차트를 추가할 새 프레젠테이션을 만드는 것입니다. 프레젠테이션을 만드는 코드는 다음과 같습니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

프레젠테이션을 준비했으면 이제 차트를 추가할 차례입니다. 이 예시에서는 마커가 있는 간단한 선형 차트를 추가해 보겠습니다. 방법은 다음과 같습니다.

```java
// 첫 번째 슬라이드에 접근하기
ISlide slide = pres.getSlides().get_Item(0);

// 샘플 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 3단계: 차트 제목 사용자 지정

잘 정의된 차트에는 제목이 있어야 합니다. 차트에 제목을 설정해 보겠습니다.

```java
// 차트 제목 설정
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## 4단계: 격자선 서식 지정

차트의 주요 격자선과 보조 격자선의 서식을 지정할 수 있습니다. 세로축 격자선의 서식을 설정해 보겠습니다.

```java
// 값 축에 대한 주요 격자선 형식 설정
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// 값 축에 대한 보조 격자선 형식 설정
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 5단계: 값 축 사용자 지정

값 축의 숫자 형식, 최대값 및 최소값을 제어할 수 있습니다. 사용자 지정 방법은 다음과 같습니다.

```java
// 설정 값 축 번호 형식
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// 차트 최대값, 최소값 설정
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## 6단계: 값 축 제목 추가

차트의 정보를 더 풍부하게 만들려면 값 축에 제목을 추가하세요.

```java
// 값 축 제목 설정
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## 7단계: 범주 축 서식 지정

일반적으로 데이터 범주를 나타내는 범주 축도 사용자 정의할 수 있습니다.

```java
// 카테고리 축에 대한 주요 격자선 형식 설정
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// 카테고리 축에 대한 보조 격자선 형식 설정
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 8단계: 범례 추가

범례는 차트의 데이터 계열을 설명하는 데 도움이 됩니다. 범례를 사용자 지정해 보겠습니다.

```java
// 범례 텍스트 속성 설정
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// 차트가 겹치지 않도록 차트 범례 표시 설정
chart.getLegend().setOverlay(true);
```

## 9단계: 프레젠테이션 저장

마지막으로 차트와 함께 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Java Slides의 차트 엔터티에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// 프레젠테이션 인스턴스화// 프레젠테이션 인스턴스화
Presentation pres = new Presentation();
try
{
	// 첫 번째 슬라이드에 접근하기
	ISlide slide = pres.getSlides().get_Item(0);
	// 샘플 차트 추가
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// 차트 제목 설정
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// 값 축에 대한 주요 격자선 형식 설정
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// 값 축에 대한 보조 격자선 형식 설정
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// 설정 값 축 번호 형식
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// 차트 최대값, 최소값 설정
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// 값 축 텍스트 속성 설정
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// 값 축 제목 설정
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// 설정 값 축선 형식: 현재 폐기됨
	// 차트.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// 카테고리 축에 대한 주요 격자선 형식 설정
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// 카테고리 축에 대한 보조 격자선 형식 설정
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// 카테고리 축 텍스트 속성 설정
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// 카테고리 제목 설정
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// 카테고리 축 레이블 위치 설정
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// 카테고리 축 레이블 회전 각도 설정
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// 범례 텍스트 속성 설정
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// 차트가 겹치지 않도록 차트 범례 표시 설정
	chart.getLegend().setOverlay(true);
	// 2차 값 축에 첫 번째 시리즈 플로팅
	// 차트.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// 차트 뒷벽 색상 설정
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// 플롯 영역 색상 설정
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// 프레젠테이션 저장
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 글에서는 Aspose.Slides for Java를 사용하여 Java Slides에서 차트 엔터티의 세계를 살펴보았습니다. 차트를 만들고, 사용자 정의하고, 조작하여 프레젠테이션을 개선하는 방법을 알아보았습니다. 차트는 데이터를 시각적으로 매력적으로 만들 뿐만 아니라, 청중이 복잡한 정보를 더 쉽게 이해할 수 있도록 도와줍니다.

## 자주 묻는 질문

### 차트 유형을 어떻게 변경합니까?

차트 유형을 변경하려면 다음을 사용하세요. `chart.setType()` 방법을 선택하고 원하는 차트 유형을 지정합니다.

### 차트에 여러 개의 데이터 시리즈를 추가할 수 있나요?

예, 다음을 사용하여 차트에 여러 데이터 시리즈를 추가할 수 있습니다. `chart.getChartData().getSeries().addSeries()` 방법.

### 차트 색상을 사용자 지정하려면 어떻게 해야 하나요?

격자선, 제목, 범례 등 다양한 차트 요소에 대한 채우기 서식을 설정하여 차트 색상을 사용자 지정할 수 있습니다.

### 3D 차트를 만들 수 있나요?

네, Aspose.Slides for Java는 3D 차트 생성을 지원합니다. `ChartType` 3D 차트 유형으로 차트를 만듭니다.

### Aspose.Slides for Java는 최신 Java 버전과 호환됩니까?

네, Aspose.Slides for Java는 최신 Java 버전을 지원하도록 정기적으로 업데이트되며 다양한 Java 환경에서 호환성을 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
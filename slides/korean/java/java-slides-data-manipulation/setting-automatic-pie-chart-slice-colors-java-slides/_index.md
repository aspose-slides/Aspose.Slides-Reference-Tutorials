---
"description": "Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 자동 슬라이스 색상이 적용된 동적 원형 차트를 만드는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드에서 자동 원형 차트 슬라이스 색상 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 자동 원형 차트 슬라이스 색상 설정"
"url": "/ko/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 자동 원형 차트 슬라이스 색상 설정


## Java 슬라이드에서 자동 원형 차트 슬라이스 색상 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 원형 차트를 만들고 차트의 자동 슬라이스 색상을 설정하는 방법을 살펴보겠습니다. 소스 코드와 함께 단계별 안내를 제공합니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 Java 프로젝트에 설치 및 설정되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다. [Java용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/java/).

## 1단계: 필요한 패키지 가져오기

먼저, Aspose.Slides for Java에서 필요한 패키지를 가져와야 합니다.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## 2단계: PowerPoint 프레젠테이션 만들기

인스턴스화 `Presentation` 새로운 PowerPoint 프레젠테이션을 만드는 수업:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 3단계: 슬라이드 추가

프레젠테이션의 첫 번째 슬라이드에 접근하여 기본 데이터가 포함된 차트를 추가합니다.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## 4단계: 차트 제목 설정

차트의 제목을 설정하세요:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 5단계: 차트 데이터 구성

첫 번째 시리즈의 값을 표시하도록 차트를 설정하고 차트 데이터를 구성합니다.

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 6단계: 카테고리 및 시리즈 추가

차트에 새로운 카테고리와 시리즈를 추가합니다.

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## 7단계: 시리즈 데이터 채우기

원형 차트의 시리즈 데이터를 채웁니다.

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## 8단계: 다양한 슬라이스 색상 활성화

파이 차트에 다양한 슬라이스 색상 활성화:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## 9단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 PowerPoint 파일로 저장합니다.

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 자동 원형 차트 슬라이스 색상 설정을 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation presentation = new Presentation();
try
{
	// 첫 번째 슬라이드에 접근하세요
	ISlide slides = presentation.getSlides().get_Item(0);
	// 기본 데이터로 차트 추가
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// 차트 제목 설정
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
	// 새로운 카테고리 추가
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// 새로운 시리즈 추가
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// 이제 시리즈 데이터를 채우고 있습니다
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 원형 차트를 성공적으로 만들고, 슬라이스 색상이 자동으로 지정되도록 설정했습니다. 이 단계별 가이드에서는 이 작업에 필요한 소스 코드를 제공합니다. 필요에 따라 차트와 프레젠테이션을 추가로 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### 파이 차트에서 각 슬라이스의 색상을 사용자 지정하려면 어떻게 해야 하나요?

파이 차트에서 개별 슬라이스의 색상을 사용자 지정하려면 다음을 사용할 수 있습니다. `getAutomaticSeriesColors` 기본 색 구성표를 검색한 후 필요에 따라 색상을 수정하는 방법입니다. 예를 들면 다음과 같습니다.

```java
// 기본 색상 구성표 가져오기
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// 필요에 따라 색상을 수정하세요
colors.get_Item(0).setColor(Color.RED); // 첫 번째 슬라이스의 색상을 빨간색으로 설정합니다.
colors.get_Item(1).setColor(Color.BLUE); // 두 번째 슬라이스의 색상을 파란색으로 설정합니다.
// 필요에 따라 색상 수정을 더 추가하세요
```

### 파이 차트에 범례를 추가하려면 어떻게 해야 하나요?

파이 차트에 범례를 추가하려면 다음을 사용할 수 있습니다. `getLegend` 방법을 선택하고 다음과 같이 구성하세요.

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // 범례 위치 설정
legend.setOverlay(true); // 차트 위에 범례 표시
```

### 제목의 글꼴과 스타일을 변경할 수 있나요?

네, 제목의 글꼴과 스타일을 변경할 수 있습니다. 다음 코드를 사용하여 제목의 글꼴과 스타일을 설정하세요.

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // 글꼴 크기 설정
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // 제목을 굵게 표시하세요
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // 제목을 이탤릭체로 만드세요
```

필요에 따라 글꼴 크기, 굵기, 기울임체 스타일을 조정할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
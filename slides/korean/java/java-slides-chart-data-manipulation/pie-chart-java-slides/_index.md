---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 멋진 원형 차트를 만드는 방법을 알아보세요. Java 개발자를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드의 파이 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 파이 차트"
"url": "/ko/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 파이 차트


## Aspose.Slides를 사용하여 Java Slides에서 파이 차트 만들기 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 원형 차트를 만드는 방법을 보여드립니다. 시작하는 데 도움이 되는 단계별 지침과 Java 소스 코드를 제공합니다. 이 가이드는 Aspose.Slides for Java를 사용하여 개발 환경을 이미 설정했다고 가정합니다.

## 필수 조건

시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 구성되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 1단계: 필요한 라이브러리 가져오기

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Aspose.Slides 라이브러리에서 필요한 클래스를 가져와야 합니다.

## 2단계: 프레젠테이션 초기화

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";

// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation presentation = new Presentation();
```

PowerPoint 파일을 나타내는 새 프레젠테이션 개체를 만듭니다. 바꾸기 `"Your Document Directory"` 프레젠테이션을 저장하려는 실제 경로를 입력합니다.

## 3단계: 슬라이드 추가

```java
// 첫 번째 슬라이드에 접근하세요
ISlide slide = presentation.getSlides().get_Item(0);
```

파이 차트를 추가하려는 프레젠테이션의 첫 번째 슬라이드를 가져옵니다.

## 4단계: 원형 차트 추가

```java
// 기본 데이터로 원형 차트 추가
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

슬라이드의 지정된 위치와 크기에 원형 차트를 추가합니다.

## 5단계: 차트 제목 설정

```java
// 차트 제목 설정
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

원형 차트의 제목을 설정합니다. 필요에 따라 제목을 사용자 지정할 수 있습니다.

## 6단계: 차트 데이터 사용자 지정

```java
// 첫 번째 시리즈를 설정하여 값을 표시합니다.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// 차트 데이터 시트의 인덱스 설정
int defaultWorksheetIndex = 0;

// 차트 데이터 워크시트 가져오기
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// 기본으로 생성된 시리즈 및 카테고리 삭제
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// 새로운 카테고리 추가
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// 새로운 시리즈 추가
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// 시리즈 데이터 채우기
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

범주와 시리즈를 추가하고 값을 설정하여 차트 데이터를 사용자 정의합니다. 이 예시에서는 세 개의 범주와 하나의 시리즈, 그리고 해당 데이터 요소가 있습니다.

## 7단계: 파이 차트 섹터 사용자 지정

```java
// 섹터 색상 설정
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// 각 섹터의 모양을 사용자 정의하세요
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// 섹터 경계 사용자 정의
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// 다른 분야도 비슷한 방식으로 사용자 정의
```

원형 차트에서 각 섹터의 모양을 사용자 지정할 수 있습니다. 색상, 테두리 스타일 및 기타 시각적 속성을 변경할 수 있습니다.

## 8단계: 데이터 레이블 사용자 지정

```java
// 데이터 레이블 사용자 정의
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// 비슷한 방식으로 다른 데이터 포인트에 대한 데이터 레이블을 사용자 정의합니다.
```

원형 차트의 각 데이터 요소에 대한 데이터 레이블을 사용자 정의합니다. 차트에 표시되는 값을 제어할 수 있습니다.

## 9단계: 지시선 표시

```java
// 차트의 리더선 표시
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

리더선을 사용하여 데이터 레이블을 해당 섹터에 연결합니다.

## 10단계: 파이 차트 회전 각도 설정

```java
// 파이 차트 섹터의 회전 각도 설정
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

원형 차트의 섹터에 대한 회전 각도를 설정합니다. 이 예에서는 180도로 설정했습니다.

## 11단계: 프레젠테이션 저장

```java
// 파이 차트로 프레젠테이션을 저장합니다.
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

파이 차트가 포함된 프레젠테이션을 지정된 디렉토리에 저장합니다.

## Java Slides의 원형 차트를 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation presentation = new Presentation();
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
// 새 버전에서는 작동하지 않습니다
// 새로운 포인트 추가 및 섹터 색상 설정
// 시리즈.색상이 다양함 = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// 섹터 경계 설정
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// 섹터 경계 설정
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// 섹터 경계 설정
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// 새 시리즈의 각 카테고리에 대한 사용자 정의 레이블을 만듭니다.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// 차트의 리더선 표시
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// 파이 차트 섹터의 회전 각도 설정
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// 차트와 함께 프레젠테이션 저장
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 원형 차트를 성공적으로 만들었습니다. 차트의 모양과 데이터 레이블은 필요에 따라 사용자 지정할 수 있습니다. 이 튜토리얼에서는 기본적인 예시를 제공하며, 필요에 따라 차트를 더욱 개선하고 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### 파이 차트에서 개별 섹터의 색상을 어떻게 바꿀 수 있나요?

원형 차트에서 각 섹터의 색상을 변경하려면 각 데이터 포인트의 채우기 색상을 사용자 지정할 수 있습니다. 제공된 코드 예제에서는 다음을 사용하여 각 섹터의 채우기 색상을 설정하는 방법을 보여주었습니다. `getSolidFillColor().setColor()` 방법입니다. 원하는 모양을 얻기 위해 색상 값을 수정할 수 있습니다.

### 파이 차트에 더 많은 카테고리와 데이터 시리즈를 추가할 수 있나요?

네, 원형 차트에 추가 범주와 데이터 시리즈를 추가할 수 있습니다. 이를 위해 다음을 사용할 수 있습니다. `getChartData().getCategories().add()` 그리고 `getChartData().getSeries().add()` 예시와 같이 방법을 사용합니다. 새 범주와 계열에 적합한 데이터와 레이블을 제공하기만 하면 차트가 확장됩니다.

### 데이터 레이블의 모양을 사용자 지정하려면 어떻게 해야 하나요?

다음을 사용하여 데이터 레이블의 모양을 사용자 정의할 수 있습니다. `getDataLabelFormat()` 각 데이터 포인트의 레이블에 대한 메서드입니다. 이 예제에서는 다음을 사용하여 데이터 레이블에 값을 표시하는 방법을 보여주었습니다. `getDataLabelFormat().setShowValue(true)`표시할 값을 제어하고, 범례 키를 표시하고, 다른 서식 옵션을 조정하여 데이터 레이블을 추가로 사용자 지정할 수 있습니다.

### 파이 차트의 제목을 변경할 수 있나요?

네, 원형 차트의 제목을 변경할 수 있습니다. 제공된 코드에서 차트 제목을 다음과 같이 설정합니다. `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. 교체할 수 있습니다 `"Sample Title"` 원하는 제목 텍스트를 넣으세요.

### 파이 차트가 포함된 생성된 프레젠테이션을 저장하려면 어떻게 해야 하나요?

파이 차트로 프레젠테이션을 저장하려면 다음을 사용하세요. `presentation.save()` 방법. 프레젠테이션을 저장할 파일 경로와 파일 이름, 그리고 저장 형식을 입력하세요. 예:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

올바른 파일 경로와 형식을 지정하세요.

### Aspose.Slides for Java를 사용하여 다른 유형의 차트를 만들 수 있나요?

네, Aspose.Slides for Java는 막대형 차트, 선형 차트 등 다양한 차트 유형을 지원합니다. `ChartType` 차트를 추가할 때. 다양한 유형의 차트를 만드는 방법에 대한 자세한 내용은 Aspose.Slides 설명서를 참조하세요.

### Java용 Aspose.Slides 사용에 대한 자세한 정보와 예제는 어디에서 찾을 수 있나요?

자세한 내용, 자세한 문서 및 추가 예제는 다음을 방문하세요. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/)도서관을 효과적으로 이용하는 데 도움이 되는 포괄적인 자료를 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
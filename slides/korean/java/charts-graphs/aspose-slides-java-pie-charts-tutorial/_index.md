---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 원형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 이 튜토리얼에서는 설정부터 고급 사용자 지정까지 모든 것을 다룹니다."
"title": "Aspose.Slides를 사용하여 Java로 파이 차트 만들기 - 종합 가이드"
"url": "/ko/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides를 사용하여 원형 차트 만들기: 완전한 튜토리얼

## 소개
역동적이고 시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 정보를 전달하는 데 필수적입니다. Aspose.Slides for Java를 사용하면 원형 차트와 같은 복잡한 차트를 슬라이드에 원활하게 통합하여 데이터 시각화를 손쉽게 향상시킬 수 있습니다. 이 종합 가이드는 Aspose.Slides Java를 사용하여 원형 차트를 만들고 사용자 지정하는 과정을 안내하며, 일반적인 프레젠테이션 과제를 쉽게 해결합니다.

**배울 내용:**
- 프레젠테이션을 초기화하고 슬라이드를 추가합니다.
- 슬라이드에서 원형 차트를 만들고 구성합니다.
- 차트 제목, 데이터 레이블, 색상 설정
- 성과를 최적화하고 리소스를 효과적으로 관리합니다.
- Maven이나 Gradle을 사용하여 Aspose.Slides를 Java 프로젝트에 통합합니다.

먼저, 따라가기 위해 필요한 모든 도구와 지식을 갖추고 있는지 확인해 보세요!

## 필수 조건
이 튜토리얼을 시작하기 전에 다음 설정이 준비되어 있는지 확인하세요.

### 필수 라이브러리, 버전 및 종속성
- **Java용 Aspose.Slides**: 버전 25.4 이상인지 확인하세요.
- **자바 개발 키트(JDK)**: 버전 16 이상이 필요합니다.

### 환경 설정 요구 사항
- Java가 설치되고 구성된 개발 환경입니다.
- IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 통합 개발 환경(IDE).

### 지식 전제 조건
- Java 프로그래밍에 대한 기본적인 이해.
- 종속성 관리를 위해 Maven이나 Gradle을 잘 알고 있어야 합니다.

## Java용 Aspose.Slides 설정
Java 프로젝트에서 Aspose.Slides를 사용하려면 라이브러리를 종속성으로 추가해야 합니다. 다양한 빌드 도구를 사용하여 추가하는 방법은 다음과 같습니다.

**메이븐**
이 스니펫을 추가하세요 `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들**
다음을 포함하세요. `build.gradle` 파일:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드**
빌드 도구를 사용하지 않으려면 다음에서 최신 릴리스를 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득 단계
- **무료 체험**: Aspose.Slides의 기능을 탐색하려면 무료 체험판을 시작하세요.
- **임시 면허**: 제한 없이 장기간 사용할 수 있는 임시 라이선스를 얻으세요.
- **구입**: 장기적으로 접근이 필요한 경우 구매를 고려하세요.

**기본 초기화 및 설정**
Aspose.Slides를 사용하려면 새 프레젠테이션 객체를 만들어 프로젝트를 초기화하세요.
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 구현 가이드
이제 파이 차트를 추가하고 사용자 지정하는 과정을 관리 가능한 단계로 나누어 살펴보겠습니다.

### 프레젠테이션 및 슬라이드 초기화
새 프레젠테이션을 설정하고 첫 번째 슬라이드에 접근하여 시작하세요. 이는 차트를 만들기 위한 캔버스입니다.
```java
import com.aspose.slides.*;

// 새로운 프레젠테이션 인스턴스를 만듭니다.
Presentation presentation = new Presentation();
// 프레젠테이션의 첫 번째 슬라이드에 접근하세요.
islide slides = presentation.getSlides().get_Item(0);
```

### 슬라이드에 파이 차트 추가
기본 데이터 세트를 사용하여 지정된 위치에 원형 차트를 삽입합니다.
```java
import com.aspose.slides.*;

// 위치(100, 100)에 크기(400, 400)의 원형 차트를 추가합니다.
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 차트 제목 설정
제목을 설정하고 가운데에 맞춰 차트를 사용자 지정하세요.
```java
import com.aspose.slides.*;

// 파이 차트에 제목을 추가합니다.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 시리즈에 대한 데이터 레이블 구성
명확성을 위해 데이터 레이블에 값이 표시되는지 확인하세요.
```java
import com.aspose.slides.*;

// 첫 번째 시리즈의 데이터 값을 표시합니다.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 차트 데이터 워크시트 준비
기존 시리즈와 범주를 지워 차트의 데이터 워크시트를 설정합니다.
```java
import com.aspose.slides.*;

// 차트 데이터 워크북을 준비합니다.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 차트에 카테고리 추가
파이 차트에 대한 범주를 정의하세요.
```java
import com.aspose.slides.*;

// 새로운 카테고리를 추가합니다.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 시리즈 추가 및 데이터 포인트 채우기
시리즈를 만들고 데이터 포인트로 채우세요.
```java
import com.aspose.slides.*;

// 새로운 시리즈를 추가하고 이름을 설정합니다.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 시리즈 색상 및 테두리 사용자 정의
색상을 설정하고 테두리를 사용자 지정하여 시각적 매력을 향상하세요.
```java
import com.aspose.slides.*;

// 시리즈 섹터에 다양한 색상을 설정합니다.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// 다른 색상과 스타일을 적용하여 다른 데이터 포인트에 대해서도 반복합니다.
```

### 사용자 정의 데이터 레이블 구성
각 데이터 포인트의 레이블을 미세 조정합니다.
```java
import com.aspose.slides.*;

// 사용자 정의 라벨을 구성합니다.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// 라벨에 대한 리더선을 활성화합니다.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 회전 각도 설정 및 프레젠테이션 저장
회전 각도를 설정하고 프레젠테이션을 저장하여 원형 차트를 완성하세요.
```java
import com.aspose.slides.*;

// 회전 각도를 설정합니다.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// 프레젠테이션을 파일로 저장합니다.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 원형 차트를 만들고 사용자 지정하는 방법을 알아보았습니다. 이 단계를 따라 하면 시각적으로 매력적인 데이터 시각화로 프레젠테이션을 더욱 풍성하게 만들 수 있습니다. 궁금한 점이 있거나 추가 도움이 필요하시면 언제든지 문의해 주세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
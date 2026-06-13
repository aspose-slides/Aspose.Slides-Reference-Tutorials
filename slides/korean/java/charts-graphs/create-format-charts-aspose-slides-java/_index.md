---
date: '2026-03-07'
description: Aspose.Slides를 사용하여 Java에서 라인 차트를 만드는 방법을 배우고, 차트 제목을 추가하고, 그리드 라인을 삽입하며,
  차트 레이블을 서식 지정하고, 전문적인 프레젠테이션을 저장하세요.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Java에서 Aspose.Slides를 사용해 라인 차트 만드는 방법 – 완전 가이드
url: /ko/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 라인 차트 만들기

## Aspose.Slides를 사용하여 Java에서 라인 차트 만들기

### 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 커뮤니케이션에 필수적입니다. 비즈니스 전문가이든 교육자이든, 정보 전달과 미적 만족을 동시에 제공하는 **create line chart** 시각 자료가 필요합니다. 이 튜토리얼에서는 **Aspose.Slides for Java**를 사용하여 라인 차트를 생성하고, 차트 제목을 추가하고, 격자선을 삽입하며, 차트 레이블을 포맷하고, 결과를 PowerPoint 파일로 저장하는 과정을 단계별로 안내합니다.

#### 빠른 답변
- **Java에서 차트를 만들기에 가장 적합한 라이브러리는 무엇인가요?** Aspose.Slides for Java
- **이 가이드에서 중점적으로 다루는 차트 유형은 무엇인가요?** Line chart with markers
- **샘플을 실행하려면 라이선스가 필요합니까?** A free temporary license works for evaluation
- **어떤 IDE를 사용할 수 있나요?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- **차트 요소는 어떻게 포맷되나요?** Using fluent API calls for titles, axes, grid lines, legends, and backgrounds

### 라인 차트란 무엇이며 Aspose.Slides를 사용하는 이유는?
라인 차트는 데이터 포인트를 직선으로 연결하여 시간에 따른 추세를 보여주기에 이상적입니다. Aspose.Slides를 사용하면 이러한 차트를 프로그래밍 방식으로 생성하고 완전히 사용자 정의할 수 있어 수동으로 PowerPoint를 편집할 필요가 없습니다.

### 전제 조건
- **Java Development Kit (JDK) 8+** 설치
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans 등)
- **Aspose.Slides for Java** 라이브러리 (Maven 또는 Gradle을 통해 추가)

#### 필요한 라이브러리 및 종속성
**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 최신 JAR 파일을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

#### 라이선스 획득
- 테스트용 [free trial license](https://purchase.aspose.com/temporary-license/)을 획득하십시오.
- 프로덕션 사용을 위해 [Aspose's official site](https://purchase.aspose.com/buy)에서 정식 라이선스를 구매하십시오.

### Aspose.Slides for Java 설정
1. 위에 표시된 종속성을 프로젝트에 추가합니다.
2. 프레젠테이션 객체를 만들기 전에 (라이선스가 있다면) **Apply the license**를 적용합니다.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## 단계별 구현

### Step 1: 출력 디렉터리 생성 (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*왜 중요한가:* 폴더가 존재함을 보장하면 나중에 프레젠테이션을 저장할 때 `FileNotFoundException`을 방지할 수 있습니다.

### Step 2: 슬라이드 추가 및 라인 차트 삽입
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*설명:* 지정된 좌표에 **line chart with markers**를 배치한 새 슬라이드를 생성합니다.

### Step 3: 차트 제목 추가 (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*팁:* 굵고 회색인 제목을 사용하면 차트를 즉시 인식할 수 있습니다.

### Step 4: 축 포맷 및 격자선 추가 (add grid lines)

#### 수직 축 포맷
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### 수평 축 포맷
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*왜 중요한가:* 명확한 격자선과 회전된 레이블은 데이터 포인트가 촘촘할 때 가독성을 향상시킵니다.

### Step 5: 범례 사용자 정의 (add chart title – 이미 다루었지만, 범례는 전체 포맷의 일부입니다)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Step 6: 배경 색상 설정 (format chart labels – 전체 시각 스타일링의 일부)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Step 7: 프레젠테이션 저장
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*결과:* 이제 완전히 포맷된 라인 차트가 포함된 PowerPoint 파일(`FormattedChart_out.pptx`)이 생성되었습니다.

## 실제 적용 사례
- **Business Reports:** 트렌드 라인을 사용하여 분기별 실적을 보여줍니다.
- **Educational Slides:** 강의를 위한 과학 데이터 시각화.
- **Project Proposals:** 마일스톤 및 예측 강조.
- **Marketing Analysis:** 캠페인 ROI 추세 제시.
- **Dashboard Integration:** 이해관계자 회의를 위해 실시간 데이터를 PowerPoint로 내보냅니다.

## 성능 고려 사항
- **Memory Management:** `Presentation` 객체를 만들기 전에 항상 `dispose()`를 호출하여 네이티브 리소스를 즉시 해제하십시오.

## 일반적인 문제 및 해결책

| 문제 | 해결책 |
|-------|----------|
| **라이선스가 적용되지 않음** | `Presentation` 객체를 만들기 전에 시험/정식 라이선스를 로드하십시오. |
| **차트가 비어 있음** | 슬라이드에 실제 데이터 시리즈가 포함되어 있는지 확인하고, 필요하면 시리즈를 추가하십시오. |
| **파일이 저장되지 않음** | 출력 디렉터리가 존재하는지 확인하십시오(“create directory java” 단계를 사용). |
| **색상이 적용되지 않음** | `java.awt.Color` 또는 `PresetColor`의 `Color` 상수를 사용하십시오. |

## 자주 묻는 질문

**Q: 라인 차트 외에 다른 차트 유형을 만들 수 있나요?**  
A: 예, Aspose.Slides는 막대, 파이, 산점도 등 다양한 차트 유형을 지원합니다.

**Q: 라인 차트에 여러 데이터 시리즈를 추가하려면 어떻게 해야 하나요?**  
A: `chart.getChartData().getSeries().add(...)`를 사용하여 포맷하기 전에 추가 시리즈를 삽입하십시오.

**Q: 차트를 이미지로 내보낼 수 있나요?**  
A: 물론 가능합니다. `chart.getChartData().getChartDataWorkbook().save(...)`를 호출하거나 슬라이드를 이미지 형식으로 렌더링하십시오.

**Q: 개발에 유료 라이선스가 필요합니까?**  
A: 평가용으로는 무료 임시 라이선스로 충분하지만, 프로덕션 배포에는 상용 라이선스가 필요합니다.

**Q: 지원되는 Java 버전은 무엇인가요?**  
A: 이 라이브러리는 JDK 8부터 JDK 22까지 지원됩니다(예: `jdk16` 분류자를 사용).

---

**마지막 업데이트:** 2026-03-07  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-08-27'
description: Aspose.Slides를 사용하여 Java에서 차트에 격자선을 추가하고, 축과 제목을 서식 지정하며, 다듬어진 PowerPoint
  라인 차트로 내보내는 방법을 배웁니다.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Aspose.Slides를 사용하여 Java에서 차트에 격자선을 추가하고, 축과 제목을 서식 지정하며, 다듬어진 PowerPoint
  라인 차트로 내보내는 방법을 배웁니다.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Aspose.Slides for Java를 사용하여 차트에 격자선을 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Aspose.Slides for Java를 사용하여 차트에 격자선을 추가하는 방법
url: /ko/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java를 사용하여 차트에 격자선 추가하는 방법

## 소개
프로그래밍 방식으로 PowerPoint 프레젠테이션에 **격자선 차트**를 추가해야 한다면, Aspose.Slides for Java는 깔끔하고 완전한 API를 제공합니다. 분기별 비즈니스 리뷰, 학술 강의, 또는 데이터 기반 영업 프레젠테이션을 준비하든, 라인 차트를 생성하고 모든 시각 요소를 맞춤 설정한 뒤 몇 초 만에 결과를 저장할 수 있습니다—PowerPoint를 직접 열 필요 없이.

## 빠른 답변
- **Java에서 차트를 생성하는 라이브러리는 무엇입니까?** Aspose.Slides for Java.
- **이 가이드에서 다루는 차트 유형은 무엇입니까?** A line chart with markers and grid lines.
- **샘플을 실행하려면 라이선스가 필요합니까?** A free temporary license works for evaluation; a commercial license is required for production.
- **어떤 IDE를 사용할 수 있나요?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
- **차트 요소는 어떻게 포맷됩니까?** Using fluent API calls for titles, axes, grid lines, legends, and background colors.

## Aspose.Slides를 사용하여 Java에서 격자선 차트를 추가하는 방법
새 `Presentation`을 로드하고, 슬라이드를 삽입한 뒤 라인 차트를 추가하고, 수직 축에 주요 격자선을 활성화합니다—코드 10줄 미만으로 가능합니다. 이 직접적인 답변은 필요한 정확한 순서를 보여주므로 복사‑붙여넣기만 하면 즉시 완전하게 포맷된 차트를 확인할 수 있습니다.

### 정의 앵커
`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 Aspose.Slides의 핵심 클래스이며, 모든 슬라이드 수준 작업은 이 객체에서 시작합니다.

## 라인 차트란 무엇이며 Aspose.Slides를 사용하는 이유는?
라인 차트는 직선으로 연결된 일련의 데이터 포인트를 플롯하여 시간에 따른 추세를 즉시 보여줍니다. Aspose.Slides는 **50개 이상의 차트 유형**을 지원하고 **시리즈당 최대 10,000개의 데이터 포인트**를 눈에 띄는 속도 저하 없이 처리할 수 있어 대용량 데이터셋에 대한 엔터프라이즈 수준 성능을 제공합니다.

### 정의 앵커
`Chart`는 모든 차트에 대한 Aspose.Slides의 최상위 객체이며, 시리즈, 카테고리 및 포맷 정보를 저장합니다.

## 전제 조건
- **Java Development Kit (JDK) 8+** 설치.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans 등).
- **Aspose.Slides for Java** 라이브러리를 Maven 또는 Gradle을 통해 추가 (아래 *aspose.slides maven dependency* 섹션 참조).

### Maven 의존성 (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 의존성
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

또는 최신 JAR를 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

## 라이선스 획득 (apply aspose license)
- 테스트를 위해 [free trial license](https://purchase.aspose.com/temporary-license/) 페이지에서 **무료 체험 라이선스**를 얻으세요.
- 운영 환경 배포를 위해 [Aspose's official site](https://purchase.aspose.com/buy)에서 정식 라이선스를 구매하세요.

## Aspose.Slides for Java 설정
1. 위에 표시된 Maven 또는 Gradle 의존성을 프로젝트에 추가합니다.
2. 모든 `Presentation` 객체를 생성하기 **전에** 라이선스 파일을 로드하여 모든 기능을 활성화합니다.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## 단계별 구현

### 단계 1: 출력 디렉터리 생성 (create directory java)
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
*이것이 중요한 이유:* 폴더가 존재함을 보장하면 나중에 프레젠테이션을 저장할 때 `FileNotFoundException`이 발생하는 것을 방지합니다.

### 단계 2: 슬라이드 추가 및 라인 차트 삽입
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
*설명:* 지정된 좌표에 **마커가 있는 라인 차트**를 배치하고 새 슬라이드를 생성합니다.

### 단계 3: 차트 제목 추가 (add chart title)
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

### 단계 4: 축 포맷 및 격자선 추가 (add grid lines)
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
*이것이 중요한 이유:* 명확한 격자선과 회전된 레이블은 특히 데이터 포인트가 밀집된 경우 가독성을 향상시킵니다.

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

### 단계 5: 범례 사용자 정의 (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### 단계 6: 배경 색상 설정 (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### 단계 7: 프레젠테이션 저장
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*결과:* 이제 완전히 포맷된 라인 차트가 포함된 PowerPoint 파일(`FormattedChart_out.pptx`)을 보유하게 됩니다.

## 실용적인 적용 사례 (generate line chart powerpoint)
- **Business reports:** 분기별 매출 추세를 선명한 격자선으로 표시합니다.
- **Academic lectures:** 여러 세션에 걸친 실험 데이터를 시각화합니다.
- **Project proposals:** 마일스톤 진행 상황과 예측 곡선을 강조합니다.
- **Marketing analysis:** 캠페인 ROI 추세를 경쟁사 데이터와 나란히 제시합니다.
- **Dashboard integration:** 실시간 분석을 PowerPoint로 내보내 이해관계자 회의에 활용합니다.

## 성능 고려 사항
- **Memory management:** 저장 후 `presentation.dispose()`를 호출하여 네이티브 리소스를 즉시 해제합니다.
- **Large datasets:** Aspose.Slides는 스트리밍을 사용해 수천 개 포인트의 차트를 처리하며, 일반 서버에서 메모리 사용량을 100 MB 이하로 유지합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **라이선스가 적용되지 않음** | 모든 `Presentation` 객체가 인스턴스화되기 **전에** 체험 또는 정식 라이선스를 로드합니다. |
| **차트가 비어 있음** | 슬라이드에 최소 하나의 데이터 시리즈가 포함되어 있는지 확인하고, 필요하면 `chart.getChartData().getSeries().add(...)`를 통해 시리즈를 추가합니다. |
| **파일이 저장되지 않음** | 출력 디렉터리가 존재하는지 확인합니다(단계 1 참조). |
| **색상이 적용되지 않음** | `java.awt.Color` 상수 또는 `PresetColor` 열거형을 사용하여 색상을 안정적으로 렌더링합니다. |

## 자주 묻는 질문

**Q: 라인 차트 외에 다른 차트 유형을 만들 수 있나요?**  
A: 예, Aspose.Slides는 막대, 원형, 산점도, 레이더 등 50개 이상의 추가 차트 유형을 지원합니다.

**Q: 라인 차트에 여러 데이터 시리즈를 추가하려면 어떻게 해야 하나요?**  
A: `chart.getChartData().getSeries().add(...)`를 사용하여 포맷 적용 전에 추가 시리즈를 삽입합니다.

**Q: 차트를 이미지로 내보낼 수 있나요?**  
A: 물론 가능합니다. `presentation.save("slide.png", SaveFormat.Png)`를 사용하여 슬라이드를 PNG, JPEG 또는 SVG로 렌더링합니다.

**Q: 개발에 유료 라이선스가 필요합니까?**  
A: 평가에는 무료 임시 라이선스로 충분하며, 운영용으로는 상용 라이선스가 필요합니다.

**Q: 지원되는 Java 버전은 무엇입니까?**  
A: 이 라이브러리는 JDK 8부터 JDK 22까지 지원하며, Maven/Gradle 의존성을 추가할 때 적절한 classifier(예: `jdk16`)를 선택합니다.

---

**마지막 업데이트:** 2026-08-27  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## 관련 튜토리얼

- [Aspose Slides Maven 의존성: Aspose.Slides for Java를 사용하여 프레젠테이션에 차트 추가 및 구성](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가 방법: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose Slides Java로 차트 추세선 만들기 및 사용자 정의](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
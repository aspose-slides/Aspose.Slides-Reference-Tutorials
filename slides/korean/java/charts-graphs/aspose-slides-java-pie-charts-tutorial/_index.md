---
date: '2026-02-19'
description: Aspose.Slides를 사용하여 Java에서 파이 차트를 만드는 방법을 배우고, 파이 차트 색상을 사용자 정의하고, 차트
  시리즈를 추가하며, 차트 데이터 워크시트 작업을 수행하고, 회전 각도를 설정합니다.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Aspose.Slides와 Java로 파이 차트 색상 맞춤하기 – 완전 가이드
url: /ko/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

 **. Keep bold.

Now produce final content.

Let's craft translation.

Be careful with markdown formatting.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용한 파이 차트 만들기: 완전 가이드

## Introduction
동적이고 시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 정보 전달에 필수적입니다. Aspose.Slides for Java를 사용하면 파이 차트와 같은 복잡한 차트를 슬라이드에 손쉽게 통합하고, **파이 차트 색상 맞춤**을 수행하며, 데이터 시각화를 손쉽게 향상시킬 수 있습니다. 이 포괄적인 가이드는 Aspose.Slides Java를 이용해 파이 차트를 생성하고 맞춤 설정하는 과정을 단계별로 안내하여 일반적인 프레젠테이션 문제를 쉽게 해결하도록 도와줍니다.

**배우게 될 내용:**
- 프레젠테이션 초기화 및 슬라이드 추가
- 슬라이드에 파이 차트 생성 및 구성
- 차트 제목, 데이터 레이블 설정 및 **파이 차트 색상 맞춤**
- 성능 최적화 및 리소스 효율적 관리
- Maven 또는 Gradle을 사용한 Java 프로젝트에 Aspose.Slides 통합

먼저 필요한 도구와 지식을 모두 준비했는지 확인해 보세요!

## Quick Answers
- **프레젠테이션을 시작하는 기본 클래스는?** `Presentation` from `com.aspose.slides`.
- **슬라이드에 파이 차트를 추가하는 메서드는?** `addChart(ChartType.Pie, …)`.
- **각 슬라이스에 다양한 색상을 적용하려면?** 시리즈 그룹에서 `setColorVaried(true)` 설정.
- **파이 차트를 회전할 수 있나요?** 차트 객체에서 `setRotationAngle(double)` 사용.
- **프로덕션 환경에서 라이선스가 필요합니까?** 상업적 배포에는 Aspose.Slides 라이선스가 필요합니다.

## What is “customize pie chart colors”?
파이 차트 색상 맞춤이란 파이의 각 조각에 서로 다른 채우기 색을 지정하여 가독성과 시각적 효과를 높이는 것을 의미합니다. Aspose.Slides에서는 색상 다양성을 활성화한 뒤 개별 데이터 포인트에 단색 채우기를 설정함으로써 이를 구현합니다.

## Why use Aspose.Slides for Java to create pie charts?
- **전체 제어**: Microsoft Office 없이 차트 외관을 완벽히 제어
- **크로스‑플랫폼** 호환성 – Windows, Linux, macOS 모두 지원
- **풍부한 API**: 데이터 바인딩, 스타일링, PPTX, PDF, 이미지 등 다양한 포맷으로 내보내기
- **유연한 라이선스** – 무료 체험 후 필요에 따라 전체 기능 업그레이드

## Prerequisites
튜토리얼을 시작하기 전에 다음 환경이 준비되어 있는지 확인하세요.

### Required Libraries, Versions, and Dependencies
- **Aspose.Slides for Java**: 버전 25.4 이상
- **Java Development Kit (JDK)**: 버전 16 이상

### Environment Setup Requirements
- Java가 설치되고 설정된 개발 환경
- IntelliJ IDEA, Eclipse, NetBeans 등 IDE

### Knowledge Prerequisites
- Java 프로그래밍 기본 이해
- Maven 또는 Gradle을 이용한 의존성 관리 경험

## Setting Up Aspose.Slides for Java
Java 프로젝트에서 Aspose.Slides를 사용하려면 라이브러리를 의존성으로 추가해야 합니다. 아래는 주요 빌드 도구별 설정 방법입니다.

**Maven**  
`pom.xml` 파일에 다음 스니펫을 추가하세요:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` 파일에 다음을 포함하세요:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
빌드 도구를 사용하지 않으려면 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 최신 버전을 다운로드하십시오.

### License Acquisition Steps
- **무료 체험**: Aspose.Slides 기능을 체험해 보세요.  
- **임시 라이선스**: 제한 없이 장기간 사용하려면 임시 라이선스를 받으세요.  
- **구매**: 장기 사용이 필요하면 정식 라이선스를 구매하세요.

**Basic Initialization and Setup**  
Aspose.Slides를 사용하려면 새 프레젠테이션 객체를 생성하여 프로젝트를 초기화합니다:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
이제 파이 차트를 추가하고 맞춤 설정하는 과정을 단계별로 살펴보겠습니다.

### Initialize Presentation and Slide
새 프레젠테이션을 설정하고 첫 번째 슬라이드에 접근합니다. 이것이 차트를 만들 캔버스가 됩니다:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Add Pie Chart to Slide
기본 데이터 세트를 사용해 지정된 위치에 파이 차트를 삽입합니다:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Set Chart Title
제목을 설정하고 중앙에 배치하여 차트를 맞춤 설정합니다:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configure Data Labels for Series
가독성을 위해 데이터 레이블에 값이 표시되도록 합니다:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Prepare Chart Data Worksheet
기존 시리즈와 카테고리를 정리하여 차트 데이터 워크시트를 초기화합니다:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Add Categories to Chart
파이 차트의 카테고리를 정의합니다:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Add Series and Populate Data Points
시리즈를 생성하고 데이터 포인트를 채웁니다 – 여기서 **차트 시리즈를 추가**합니다:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Customize Series Colors and Borders
시각적 효과를 높이기 위해 색상과 테두리를 설정합니다 – 이는 **파이 차트 색상 맞춤**에 직접 해당합니다:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configure Custom Data Labels
각 데이터 포인트에 대한 레이블을 세밀하게 조정합니다:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Set Rotation Angle and Save Presentation
**회전 각도 설정**을 마치고 파일을 저장하여 파이 차트를 완성합니다:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Common Issues and Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Ensure you enable varied colors on the series group. |
| **Data labels not showing** | `showValue` flag disabled | Call `setShowValue(true)` on the appropriate label format. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Upgrade to version 25.4 or later. |
| **License exception at runtime** | Missing or invalid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Slides.lic");` before creating the `Presentation`. |

## Frequently Asked Questions

**Q: How do I obtain an Aspose.Slides license for Java?**  
A: You can request a free trial from the Aspose website, then purchase a permanent license. Load it at runtime as shown in the Common Issues table.

**Q: Can I use this code with older JDK versions?**  
A: The API requires JDK 16 or higher; older versions are not supported.

**Q: Is it possible to export the chart as an image instead of PPTX?**  
A: Yes, call `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` after rendering.

**Q: What if I need to add more than one series to a pie chart?**  
A: Pie charts typically display a single series; for multiple series consider a doughnut chart instead.

**Q: Does the library work on Linux servers?**  
A: Absolutely – Aspose.Slides for Java is platform‑independent and runs on any OS with a compatible JDK.

---

**Last Updated:** 2026-02-19  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
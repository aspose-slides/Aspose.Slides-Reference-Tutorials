---
date: '2026-07-17'
description: Aspose.Slides for Java를 사용하여 pie chart를 회전하고, pie chart 색상을 사용자 지정하며,
  슬라이드를 PDF로 내보내는 방법을 배우세요 – 완전한 데이터 시각화 가이드.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java를 사용하여 pie chart를 회전하고 색상을 사용자 지정하세요. 슬라이드를
  PDF로 내보내고 chart data worksheet를 활용하는 방법을 배우세요.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Java에서 Pie Chart 회전 및 색상 사용자 지정 – Aspose.Slides 가이드
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Java와 Aspose.Slides를 사용하여 Pie Chart 회전 및 색상 사용자 지정 방법
url: /ko/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java로 파이 차트 만들기: 완전 가이드

## 소개
이 가이드에서는 **파이 차트 회전** 요소를 다루고, 각 슬라이스의 색상을 맞춤 설정하며, 최종 슬라이드를 PDF로 내보내는 방법을 배웁니다—모두 Aspose.Slides for Java를 사용합니다. 영업 대시보드, 재무 보고서 또는 데이터 기반 프레젠테이션을 만들 때, 이러한 기술을 마스터하면 Microsoft Office에 의존하지 않고도 명확하고 시각적으로 눈에 띄는 차트를 제공할 수 있습니다. 도구를 준비하고 바로 시작해 보세요.

## 빠른 답변
- **새 프레젠테이션을 시작하는 클래스는?** `Presentation` from `com.aspose.slides`.
- **파이 차트를 추가하는 API 호출은?** `slide.addChart(ChartType.Pie, …)`.
- **각 슬라이스에 고유한 색상을 지정하려면?** Call `series.setColorVaried(true)` and set solid fills per data point.
- **차트를 회전시키는 메서드는?** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **슬라이드를 PDF로 내보낼 수 있나요?** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## “파이 차트 색상 맞춤”이란?
파이 차트 색상 맞춤이란 파이의 각 슬라이스에 서로 다른 채우기 색상을 할당하여 가독성과 시각적 효과를 높이는 것을 의미합니다. Aspose.Slides에서는 색상 다양성을 활성화한 뒤 개별 데이터 포인트에 고체 채우기 색상을 지정함으로써 이를 구현합니다. 이 방법을 사용하면 각 데이터 구간이 프레젠테이션에서 명확히 돋보이게 됩니다.

## 왜 Aspose.Slides for Java로 파이 차트를 만들까요?
Aspose.Slides는 **150개 이상의 차트 유형**을 지원하며, 일반 서버에서 300페이지 프레젠테이션을 **5초 이하**에 렌더링할 수 있습니다. 또한 Microsoft Office가 설치되지 않아도 되며, Windows, Linux, macOS에서 모두 동작해 Java 기반 데이터 시각화 프로젝트에 크로스 플랫폼 유연성을 제공합니다.

## 전제 조건
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 or newer
- IntelliJ IDEA, Eclipse, NetBeans 등 IDE
- 기본 Java 지식 및 Maven 또는 Gradle 사용 경험

## Aspose.Slides for Java 설정
라이브러리를 빌드 구성에 추가합니다.

**Maven**  
다음 코드를 `pom.xml` 파일에 추가하세요:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
다음 내용을 `build.gradle` 파일에 포함하세요:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
수동으로 진행하고 싶다면 최신 JAR 파일을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

### 라이선스 획득 단계
- **무료 체험** – 비용 없이 모든 기능을 탐색합니다.  
- **임시 라이선스** – 짧은 기간 동안 체험 제한을 연장합니다.  
- **구매** – 프로덕션 사용을 위한 영구 라이선스를 획득합니다.

**기본 초기화 및 설정**  
`Presentation` 클래스는 메모리 내 PowerPoint 파일을 나타내며 슬라이드를 조작하는 메서드를 제공합니다.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## 구현 가이드
아래는 슬라이드 생성부터 최종 파이 차트 회전까지 모든 과정을 단계별로 설명한 walkthrough입니다.

### 프레젠테이션 및 슬라이드 초기화
새 `Presentation` 인스턴스를 만들고 첫 번째 슬라이드를 차트 캔버스로 가져옵니다.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### 슬라이드에 파이 차트 추가
`addChart`는 지정된 유형의 차트 도형을 주어진 좌표에 슬라이드에 추가합니다.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 차트 제목 설정
`setTitle`은 차트에 텍스트 제목을 할당하고 중앙에 배치합니다.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 시리즈 데이터 레이블 구성
`setShowValue(true)`는 시리즈의 각 데이터 포인트에 숫자 값 레이블을 표시하도록 활성화합니다.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 차트 데이터 워크시트 준비
`ChartDataWorkbook`은 차트 시리즈와 카테고리에 데이터를 공급하는 기본 테이블을 저장합니다.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 차트에 카테고리 추가
`addCategory`는 차트 데이터 시리즈에 새로운 카테고리 레이블을 생성합니다.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 시리즈 추가 및 데이터 포인트 채우기
`addSeries`는 데이터 시리즈를 만들고, `addDataPointForBarSeries`는 각 카테고리에 대한 숫자 값을 삽입합니다.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 시리즈 색상 및 테두리 맞춤
`setColorVaried(true)`는 슬라이스별 색상을 활성화하고, `setFillFormat`은 각 데이터 포인트에 고체 채우기를 지정합니다.  
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

### 사용자 정의 데이터 레이블 구성
`setDataLabelFormat`은 레이블의 모양, 위치 및 글꼴을 맞춤 설정하여 차트 주석을 보다 명확하게 합니다.  
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

### 회전 각도 설정 및 프레젠테이션 저장
`setRotationAngle`은 전체 파이 차트를 회전시키고, `save`는 프레젠테이션을 파일로 기록합니다.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## 파이 차트를 회전하는 방법
차트 객체를 로드하고 `chart.setRotationAngle(45.0)`(또는 원하는 각도) 를 호출한 뒤 프레젠테이션을 저장합니다. 파이 차트를 회전하면 시작 각도가 이동하여 특정 섹션을 강조할 수 있으며, 데이터 자체는 변경되지 않습니다. 이 단일 메서드 호출은 Aspose.Slides의 모든 `Chart` 인스턴스에 적용됩니다. 회전과 색상 다양성을 결합하면 가장 중요한 데이터 포인트에 시선을 집중시킬 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|-------|-----|
| **슬라이스가 모두 같은 색으로 표시됨** | `setColorVaried(true)` 호출되지 않음 | 시리즈 그룹에서 색상 다양성을 활성화했는지 확인하세요. |
| **데이터 레이블이 표시되지 않음** | `showValue` 플래그 비활성화 | 레이블 포맷에 `setShowValue(true)`를 호출하세요. |
| **회전이 적용되지 않음** | 구버전 Aspose.Slides 사용 | 버전 25.4 이상으로 업그레이드하세요. |
| **런타임 라이선스 예외** | 라이선스 파일이 없거나 유효하지 않음 | `Presentation`을 만들기 전에 `License license = new License(); license.setLicense("Aspose.Slides.lic");` 로 라이선스를 로드하세요. |

## 자주 묻는 질문

**Q: Aspose.Slides for Java 라이선스를 어떻게 얻나요?**  
A: Aspose 웹사이트에서 무료 체험을 요청한 뒤 영구 라이선스를 구매합니다. 런타임에 라이선스를 로드하는 방법은 위의 일반적인 문제 표에 나와 있습니다.

**Q: 이 코드를 오래된 JDK 버전에서 사용할 수 있나요?**  
A: API는 JDK 16 이상을 요구합니다. 오래된 버전은 지원되지 않습니다.

**Q: 차트를 PPTX 대신 이미지로 내보낼 수 있나요?**  
A: 예—렌더링 후 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` 를 호출하면 이미지 파일로 저장할 수 있습니다.

**Q: 파이 차트에 하나 이상의 시리즈가 필요하면 어떻게 해야 하나요?**  
A: 파이 차트는 단일 데이터 시리즈에 최적화되어 있습니다. 여러 시리즈가 필요하면 도넛 차트 사용을 고려하십시오.

**Q: Aspose.Slides가 Linux 서버에서 실행되나요?**  
A: 물론입니다—Aspose.Slides for Java는 플랫폼에 독립적이며 호환 가능한 JDK가 설치된 모든 OS에서 작동합니다.

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides를 사용한 Java 프레젠테이션에서 파이 차트 만들기: 종합 가이드](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Aspose.Slides를 사용한 Java 파이 차트 마스터: 종합 가이드](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Aspose.Slides를 사용한 Java 차트 텍스트 회전: 종합 가이드](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
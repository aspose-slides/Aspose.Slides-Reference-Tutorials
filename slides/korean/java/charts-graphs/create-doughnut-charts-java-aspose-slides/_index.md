---
date: '2026-03-07'
description: Aspose.Slides를 사용하여 Java에서 도넛 차트를 만드는 방법을 배워보세요. 이 단계별 가이드는 Maven Aspose
  Slides 의존성 설정, 차트 구성 및 프레젠테이션 저장을 다룹니다.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Aspose.Slides 가이드로 Java에서 도넛 차트 만들기
url: /ko/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides 가이드로 Java 도넛 차트 만들기

## 소개

프로그램matically **도넛 차트**를 생성하면 원시 데이터를 눈에 띄는 시각화로 바꿔 즉시 이야기를 전달합니다. Java에서 **Aspose.Slides**는 이 과정을 간단하게 만들어 PowerPoint를 열지 않고도 프레젠테이션용 차트를 생성할 수 있습니다. 이 튜토리얼에서는 Maven Aspose Slides 의존성을 설정하고, 시리즈와 카테고리를 사용자 정의하고, 마지막으로 프레젠테이션을 저장하는 단계별 **create doughnut chart java** 방법을 배웁니다.

이 가이드를 마치면 동적인 도넛 차트를 모든 PPTX 파일에 삽입할 수 있게 되며, 보고서, 대시보드 또는 자동 슬라이드 데크에 적합합니다.

### 빠른 답변
- **사용된 라이브러리는?** Aspose.Slides for Java  
- **주요 작업은?** Create doughnut chart java in a PPTX file  
- **라이브러리를 어떻게 추가하나요?** Use the Maven Aspose Slides dependency (or Gradle)  
- **최소 Java 버전은?** JDK 16 or higher  
- **색상과 레이블을 사용자 정의할 수 있나요?** Yes, the API provides full formatting control  

## 도넛 차트란? 그리고 왜 사용하나요?

도넛 차트는 중앙이 비어 있는 파이 차트의 변형으로, 여러 데이터 시리즈를 동심원 형태의 링으로 표시할 수 있습니다. 이는 여러 카테고리에서 전체의 일부를 비교하는 데 이상적이며, 예를 들어 여러 분기에 걸친 지역별 매출이나 부서별 예산 배분을 나타낼 수 있습니다.

## 왜 Java용 Aspose.Slides를 사용하나요?

- **Office 설치가 필요 없음** – 모든 서버에서 PPTX 파일을 생성합니다.  
- **풍부한 API** – 차트 유형, 데이터 포인트 및 스타일링을 완전하게 제어합니다.  
- **고성능** – 대용량 프레젠테이션에 최적화되었습니다.  
- **크로스 플랫폼** – Windows, Linux, macOS에서 작동합니다.

## 전제 조건

- **필요한 라이브러리:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **환경 설정:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **지식 전제 조건:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Maven Aspose Slides 의존성

Add the following Maven dependency to your `pom.xml`. This is the **maven aspose slides dependency** you need to pull the library into your project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

If you prefer Gradle, use the equivalent snippet below.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

You can also download the JAR directly from the official release page:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### 라이선스 획득

To remove the evaluation watermark and unlock the full feature set:

- **Free trial** – start with a temporary license.  
- **Temporary license** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – purchase for production use.

Apply the license in your code:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 구현 가이드

### 프레젠테이션 초기화 및 도넛 차트 추가

First, create or load a presentation and add a doughnut chart to the first slide.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 차트 데이터 워크북 구성 및 기존 데이터 정리

Next, obtain the workbook that backs the chart and clear any default series or categories.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 차트에 시리즈 추가

Now we’ll add up to 15 series. Each series can be customized—here we set the explosion, doughnut‑hole size, and first‑slice angle.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 카테고리 및 데이터 포인트 추가

We’ll create 15 categories and populate each series with a data point. The last series receives special label formatting.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### 프레젠테이션 저장

Finally, write the updated presentation to disk.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 일반적인 문제 및 해결책

- **License not found** – Verify the path to `license.lic` is correct and the file is readable.  
- **Chart appears blank** – Ensure you cleared existing series/categories before adding new ones.  
- **Incorrect colors** – Check that `FillType.Solid` is set for both fill and line formats.  
- **Performance with many series** – Limit the number of series/categories or reuse the workbook cells.

## 자주 묻는 질문

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Yes, instantiate `new Presentation()` to start from a blank slide deck.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: How do I change the doughnut hole size?**  
A: Use `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` where value is 0‑100.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Yes, move the label‑formatting block outside the `if (i == ...)` condition and apply it to each `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the appropriate classifier.

---

**마지막 업데이트:** 2026-03-07  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
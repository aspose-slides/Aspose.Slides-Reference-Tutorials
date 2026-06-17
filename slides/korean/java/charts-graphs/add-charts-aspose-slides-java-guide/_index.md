---
date: '2026-06-03'
description: aspose slides maven dependency를 사용하여 차트를 추가하고, data labels를 구성하며, Java
  프레젠테이션에서 동적 차트를 생성하는 방법을 배웁니다.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: 프레젠테이션에서 차트 추가 및 구성 - Aspose.Slides for Java
  사용'
url: /ko/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Aspose.Slides for Java를 사용하여 프레젠테이션에 차트 추가 및 구성

## 소개
**aspose slides maven dependency**는 Java 개발자가 PowerPoint를 직접 열지 않고도 프로그래밍 방식으로 PowerPoint 파일을 생성, 수정 및 풍부하게 만들 수 있게 해줍니다. 많은 비즈니스 및 학술 시나리오에서 차트를 수동으로 삽입하는 것은 시간 소모가 크고 오류가 발생하기 쉽습니다. 이 튜토리얼에서는 버블 차트를 추가하고, 데이터 레이블을 워크시트 셀에 바인딩하며, 결과를 저장하는 과정을 단계별로 보여줍니다—모두 aspose slides maven dependency를 활용한 깔끔하고 재현 가능한 방식으로 진행됩니다.

**배우게 될 내용**
- aspose slides maven dependency를 사용하여 차트 추가하기
- Maven 또는 Gradle을 사용한 Java 프로젝트 설정
- 기존 프레젠테이션을 로드하고 버블 차트 삽입하기
- 셀 참조를 사용해 데이터 레이블 구성하기 (add data labels chart)
- 업데이트된 파일을 나중에 배포할 수 있도록 저장하기
- 동적 차트 생성 및 프레젠테이션 차트 워크플로우와 같은 실제 사용 사례

## 빠른 답변
- **Which Maven artifact adds chart capabilities?** `com.aspose:aspose-slides:25.4` (or latest)  
- **Can I bind data labels to Excel‑style cells?** Yes – use `ChartDataLabel` with `setDataLabelFormat` and cell references.  
- **Is a license required for production?** A full license removes the evaluation watermark and unlocks all features.  
- **Will this work on Java 11+?** Absolutely; the library is compatible with Java 8 through Java 21.  
- **How many chart types are supported?** Over 70 distinct chart types, including Bubble, Radar, and Stock charts.

## aspose slides maven dependency란?
The **aspose slides maven dependency** is a Maven‑compatible package that provides a full‑featured API for creating and editing PowerPoint (PPTX, PPT, ODP) files in Java. By adding this dependency to your `pom.xml` or `build.gradle`, you gain access to over 70 chart types, 150+ slide layouts, and the ability to manipulate shapes, animations, and metadata without Office installed.

## 차트 자동화를 위해 aspose slides maven dependency를 사용하는 이유
Aspose.Slides processes multi‑thousand‑slide decks in under a second on standard server hardware, supports **70+ chart types**, and can render presentations up to **10,000 slides** without loading the entire file into memory. These quantified capabilities make it ideal for enterprise‑grade dynamic chart generation, where performance and scalability are non‑negotiable.

## 사전 요구 사항
- **Java Development Kit (JDK)** 8 or newer (Java 11+ recommended).  
- **Maven** 3.6+ **or** **Gradle** 6+.  
- **Aspose.Slides for Java** library (the aspose slides maven dependency, version 25.4 or later).  
- Basic familiarity with Java collections and file I/O.  
- An evaluation or full license file (`license.json`) if you plan to run the code beyond the trial period.

## Aspose.Slides를 사용하여 슬라이드에 차트를 추가하는 방법?
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### 단계 1: aspose slides maven dependency 추가
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
These snippets pull the full Aspose.Slides API—including chart support—directly from Maven Central.

### 단계 2: 프레젠테이션을 로드하고 버블 차트 삽입
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 단계 3: 차트 데이터 시리즈 및 레이블 구성
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 단계 4: 수정된 프레젠테이션 저장
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## 셀 참조를 사용하여 데이터 레이블 구성 방법
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### 직접 답변
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### 단계별
1. 레이블을 지정하려는 시리즈를 식별합니다.  
2. 각 데이터 포인트에 대한 `IDataLabel` 객체를 가져옵니다.  
3. `CellReference`가 설정된 `DataLabelFormat`과 함께 `setDataLabelFormat`을 사용합니다.  
4. 필요에 따라 글꼴, 색상 및 표시 옵션을 사용자 정의합니다.

## 수정된 프레젠테이션 저장 방법
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### 직접 답변
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## 실용적인 적용 사례
1. **Business Reports:** Generate quarterly sales charts automatically from a database dump.  
2. **Academic Lectures:** Pull live research data into lecture slides for each class session.  
3. **Sales Pitches:** Build client‑specific performance dashboards on the fly.  
4. **Project Management:** Visualize Gantt‑style timelines with dynamic data labels.  
5. **Marketing Analytics:** Embed campaign KPIs into presentations that update as new metrics arrive.

## 성능 고려 사항
- **Memory Management:** Use try‑with‑resources or explicit `presentation.dispose()` to free native memory promptly.  
- **Large Datasets:** When handling more than 10,000 data points, populate chart data via `ChartDataWorkbook` to avoid loading the entire dataset into Java objects.  
- **Thread Safety:** Each thread should work with its own `Presentation` instance; the API is not thread‑safe across shared objects.  

## 일반적인 문제 및 해결책
- **Issue:** “License file not found.”  
  **Solution:** Place `license.json` in the classpath and call `License license = new License(); license.setLicense("license.json");` before any API usage.  
- **Issue:** Chart appears blank after saving.  
  **Solution:** Ensure that the chart’s data workbook is saved with the presentation (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Issue:** Data labels show “#REF!” errors.  
  **Solution:** Verify that the cell reference string matches the exact sheet name and address, and that the referenced workbook is attached to the chart.  

## 자주 묻는 질문

**Q: Can I add other chart types besides Bubble?**  
A: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock, and more than 70 additional types.

**Q: Does the aspose slides maven dependency work with OpenJDK?**  
A: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major operating systems.

**Q: How do I embed a chart from an existing Excel file?**  
A: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell references.

**Q: Is there a limit to the number of charts per slide?**  
A: Practically no—Aspose.Slides can handle dozens of charts per slide, limited only by available memory.

**Q: What format can I export the final presentation to?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and JPEG are supported.

## 리소스
- [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/) – 최신 라이브러리 바이너리를 다운로드합니다.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – 포괄적인 API 레퍼런스 및 가이드.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – Maven/Gradle 패키지를 직접 다운로드합니다.  
- [Purchase a License](https://purchase.aspose.com/buy) – 정식 상용 라이선스를 구매합니다.  
- [Free Trial](https://releases.aspose.com/slides/java/) – 기능을 평가할 수 있는 무료 체험판을 시작합니다.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – 연장된 평가를 위한 임시 키를 요청합니다.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – 커뮤니티와 Aspose 엔지니어에게 도움을 받으세요.

## 결론
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**최종 업데이트:** 2026-06-03  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## 관련 튜토리얼

- [Aspose.Slides Java로 프레젠테이션 만들고 구성하는 방법: 단계별 가이드](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Aspose.Slides Maven로 PPTX Java 만들기 – 자동화 가이드](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Aspose.Slides를 사용한 Java 차트 만들기: 종합 가이드](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
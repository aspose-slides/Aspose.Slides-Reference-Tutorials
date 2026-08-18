---
date: '2026-06-03'
description: Узнайте, как добавить диаграммы с помощью aspose slides maven dependency,
  настроить подписи данных и генерировать динамические диаграммы в Java‑презентациях.
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
title: 'aspose slides maven dependency: Добавить и настроить диаграммы в презентациях
  с использованием Aspose.Slides for Java'
url: /ru/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Добавление и настройка диаграмм в презентациях с использованием Aspose.Slides for Java

## Введение
The **aspose slides maven dependency** lets Java developers programmatically create, modify, and enrich PowerPoint files without ever opening PowerPoint itself. In many business and academic scenarios, manually inserting charts is time‑consuming and error‑prone. This tutorial shows you step‑by‑step how to add a Bubble Chart, bind data labels to worksheet cells, and save the result—all by leveraging the aspose slides maven dependency in a clean, repeatable way.

**Что вы узнаете**
- Как добавлять диаграммы с помощью aspose slides maven dependency
- Настройка Java‑проекта с использованием Maven или Gradle
- Загрузка существующей презентации и вставка пузырчатой диаграммы
- Конфигурация подписей данных с использованием ссылок на ячейки (add data labels chart)
- Сохранение обновлённого файла для дальнейшего распространения
- Реальные сценарии использования, такие как динамическое создание диаграмм и автоматизация рабочих процессов создания презентаций

## Быстрые ответы
- **Which Maven artifact adds chart capabilities?** `com.aspose:aspose-slides:25.4` (or latest)  
- **Can I bind data labels to Excel‑style cells?** Yes – use `ChartDataLabel` with `setDataLabelFormat` and cell references.  
- **Is a license required for production?** A full license removes the evaluation watermark and unlocks all features.  
- **Will this work on Java 11+?** Absolutely; the library is compatible with Java 8 through Java 21.  
- **How many chart types are supported?** Over 70 distinct chart types, including Bubble, Radar, and Stock charts.

## Что такое aspose slides maven dependency?
The **aspose slides maven dependency** is a Maven‑compatible package that provides a full‑featured API for creating and editing PowerPoint (PPTX, PPT, ODP) files in Java. By adding this dependency to your `pom.xml` or `build.gradle`, you gain access to over 70 chart types, 150+ slide layouts, and the ability to manipulate shapes, animations, and metadata without Office installed.

## Почему использовать aspose slides maven dependency для автоматизации диаграмм?
Aspose.Slides processes multi‑thousand‑slide decks in under a second on standard server hardware, supports **70+ chart types**, and can render presentations up to **10,000 slides** without loading the entire file into memory. These quantified capabilities make it ideal for enterprise‑grade dynamic chart generation, where performance and scalability are non‑negotiable.

## Требования
- **Java Development Kit (JDK)** 8 or newer (Java 11+ recommended).  
- **Maven** 3.6+ **or** **Gradle** 6+.  
- **Aspose.Slides for Java** library (the aspose slides maven dependency, version 25.4 or later).  
- Basic familiarity with Java collections and file I/O.  
- An evaluation or full license file (`license.json`) if you plan to run the code beyond the trial period.

## Как добавить диаграмму на слайд с помощью Aspose.Slides?
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### Шаг 1: Добавьте aspose slides maven dependency
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

### Шаг 2: Загрузите презентацию и вставьте пузырчатую диаграмму
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

### Шаг 3: Настройте серии данных диаграммы и подписи
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

### Шаг 4: Сохраните изменённую презентацию
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

## Как настроить подписи данных, используя ссылки на ячейки?
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### Прямой ответ
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### Пошагово
1. Identify the series you wish to label.  
2. Retrieve the `IDataLabel` object for each data point.  
3. Use `setDataLabelFormat` with `DataLabelFormat` configured for `CellReference`.  
4. Optionally customize font, color, and display options.

## Как сохранить изменённую презентацию?
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### Прямой ответ
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## Практические применения
1. **Business Reports:** Generate quarterly sales charts automatically from a database dump.  
2. **Academic Lectures:** Pull live research data into lecture slides for each class session.  
3. **Sales Pitches:** Build client‑specific performance dashboards on the fly.  
4. **Project Management:** Visualize Gantt‑style timelines with dynamic data labels.  
5. **Marketing Analytics:** Embed campaign KPIs into presentations that update as new metrics arrive.

## Соображения по производительности
- **Memory Management:** Use try‑with‑resources or explicit `presentation.dispose()` to free native memory promptly.  
- **Large Datasets:** When handling more than 10,000 data points, populate chart data via `ChartDataWorkbook` to avoid loading the entire dataset into Java objects.  
- **Thread Safety:** Each thread should work with its own `Presentation` instance; the API is not thread‑safe across shared objects.  

## Распространённые проблемы и решения
- **Issue:** “License file not found.”  
  **Solution:** Place `license.json` in the classpath and call `License license = new License(); license.setLicense("license.json");` before any API usage.  
- **Issue:** Chart appears blank after saving.  
  **Solution:** Ensure that the chart’s data workbook is saved with the presentation (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Issue:** Data labels show “#REF!” errors.  
  **Solution:** Verify that the cell reference string matches the exact sheet name and address, and that the referenced workbook is attached to the chart.  

## Часто задаваемые вопросы

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

## Ресурсы
- [Выпуски Aspose.Slides для Java](https://releases.aspose.com/slides/java/) – download the latest library binaries.  
- [Документация Aspose.Slides](https://reference.aspose.com/slides/java/) – comprehensive API reference and guides.  
- [Скачать Aspose.Slides для Java](https://releases.aspose.com/slides/java/) – direct download page for the Maven/Gradle packages.  
- [Приобрести лицензию](https://purchase.aspose.com/buy) – obtain a full commercial license.  
- [Бесплатная пробная версия](https://releases.aspose.com/slides/java/) – start with a trial to evaluate features.  
- [Временная лицензия](https://purchase.aspose.com/temporary-license/) – request a temporary key for extended evaluation.  
- [Форум поддержки Aspose](https://forum.aspose.com/c/slides/11) – get help from the community and Aspose engineers.

## Заключение
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Похожие учебные материалы

- [How to Create and Configure Presentations with Aspose.Slides Java&#58; A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
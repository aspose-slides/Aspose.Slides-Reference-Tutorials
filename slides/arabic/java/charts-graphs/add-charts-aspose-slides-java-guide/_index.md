---
date: '2026-06-03'
description: تعلم كيفية إضافة المخططات باستخدام aspose slides maven dependency، وتكوين
  تسميات البيانات، وإنشاء مخططات ديناميكية في عروض Java التقديمية.
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
title: 'aspose slides maven dependency: إضافة وتكوين المخططات في العروض التقديمية
  باستخدام Aspose.Slides for Java'
url: /ar/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: إضافة وتكوين المخططات في العروض التقديمية باستخدام Aspose.Slides للـ Java

## المقدمة
The **aspose slides maven dependency** lets Java developers programmatically create, modify, and enrich PowerPoint files without ever opening PowerPoint itself. In many business and academic scenarios, manually inserting charts is time‑consuming and error‑prone. This tutorial shows you step‑by‑step how to add a Bubble Chart, bind data labels to worksheet cells, and save the result—all by leveraging the aspose slides maven dependency in a clean, repeatable way.

**ما ستتعلمه**
- كيفية إضافة المخططات باستخدام aspose slides maven dependency
- إعداد مشروع Java باستخدام Maven أو Gradle
- تحميل عرض تقديمي موجود وإدراج مخطط فقاعة
- تكوين تسميات البيانات باستخدام مراجع الخلايا (إضافة مخطط تسميات البيانات)
- حفظ الملف المحدث للتوزيع لاحقًا
- حالات الاستخدام الواقعية مثل إنشاء مخططات ديناميكية وإنشاء سير عمل مخططات العروض التقديمية

## إجابات سريعة
- **ما هو عنصر Maven الذي يضيف إمكانيات المخططات؟** `com.aspose:aspose-slides:25.4` (or latest)  
- **هل يمكن ربط تسميات البيانات بخلايا على نمط Excel؟** نعم – استخدم `ChartDataLabel` مع `setDataLabelFormat` ومراجع الخلايا.  
- **هل يلزم وجود ترخيص للإنتاج؟** الترخيص الكامل يزيل علامة التقييم المائية ويفتح جميع الميزات.  
- **هل سيعمل هذا على Java 11+؟** بالتأكيد؛ المكتبة متوافقة مع Java 8 حتى Java 21.  
- **كم عدد أنواع المخططات المدعومة؟** أكثر من 70 نوعًا مختلفًا من المخططات، بما في ذلك Bubble و Radar و Stock.

## ما هو aspose slides maven dependency؟
The **aspose slides maven dependency** is a Maven‑compatible package that provides a full‑featured API for creating and editing PowerPoint (PPTX, PPT, ODP) files in Java. By adding this dependency to your `pom.xml` or `build.gradle`, you gain access to over 70 chart types, 150+ slide layouts, and the ability to manipulate shapes, animations, and metadata without Office installed.

## لماذا تستخدم aspose slides maven dependency لأتمتة المخططات؟
Aspose.Slides processes multi‑thousand‑slide decks in under a second on standard server hardware, supports **70+ chart types**, and can render presentations up to **10,000 slides** without loading the entire file into memory. These quantified capabilities make it ideal for enterprise‑grade dynamic chart generation, where performance and scalability are non‑negotiable.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK)** 8 or newer (Java 11+ recommended).  
- **Maven** 3.6+ **or** **Gradle** 6+.  
- **Aspose.Slides for Java** library (the aspose slides maven dependency, version 25.4 or later).  
- إلمام أساسي بمجموعات Java وإدخال/إخراج الملفات.  
- ملف ترخيص تجريبي أو كامل (`license.json`) إذا كنت تخطط لتشغيل الكود بعد فترة التجربة.

## كيف تضيف مخططًا إلى شريحة باستخدام Aspose.Slides؟
Load the target presentation, create a new chart shape on the desired slide, and specify the chart type (Bubble in this example). The entire operation can be performed in **three concise lines of code** once the library is referenced, making it perfect for rapid prototyping and production pipelines.

### الخطوة 1: إضافة aspose slides maven dependency
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

### الخطوة 2: تحميل العرض التقديمي وإدراج مخطط فقاعة
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

### الخطوة 3: تكوين سلسلة بيانات المخطط والتسميات
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

### الخطوة 4: حفظ العرض التقديمي المعدل
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

## كيف تُكوّن تسميات البيانات باستخدام مراجع الخلايا؟
Data labels can be bound to external cell values, mirroring Excel’s “Link to Cell” feature. This approach eliminates hard‑coded values and enables **dynamic chart generation** where label content updates automatically as the underlying data changes. By linking each label to a specific workbook cell, you ensure that any modification to the source data is instantly reflected in the presentation, reducing maintenance effort and minimizing the risk of outdated information.

### الإجابة المباشرة
Call `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` and pass a `DataLabelFormat` that references a cell address such as `"Sheet1!A2"`. Aspose.Slides resolves the reference at runtime, inserting the cell’s current value into the chart label.

### خطوة بخطوة
1. Identify the series you wish to label. → حدد السلسلة التي تريد تسميةها.  
2. Retrieve the `IDataLabel` object for each data point. → احصل على كائن `IDataLabel` لكل نقطة بيانات.  
3. Use `setDataLabelFormat` with `DataLabelFormat` configured for `CellReference`. → استخدم `setDataLabelFormat` مع `DataLabelFormat` مكوَّن للـ `CellReference`.  
4. Optionally customize font, color, and display options. → يمكنك تخصيص الخط واللون وخيارات العرض اختياريًا.

## كيف تحفظ العرض التقديمي المعدل؟
Saving is a single‑method call that writes the in‑memory `Presentation` object to a file path or output stream. You can also choose the output format (PPTX, PDF, ODP) by passing the appropriate `SaveFormat` enum. This operation streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope, which helps keep memory usage low even for large decks.

### الإجابة المباشرة
Invoke `presentation.save("output.pptx", SaveFormat.Pptx)`; the library streams the result directly to disk, releasing all native resources automatically when the `Presentation` instance is closed or goes out of scope.

## التطبيقات العملية
1. **تقارير الأعمال:** إنشاء مخططات مبيعات ربع سنوية تلقائيًا من تفريغ قاعدة البيانات.  
2. **المحاضرات الأكاديمية:** سحب بيانات بحثية حية إلى شرائح المحاضرة لكل جلسة.  
3. **عروض المبيعات:** بناء لوحات أداء مخصصة للعميل بسرعة.  
4. **إدارة المشاريع:** تصور جداول زمنية على نمط Gantt مع تسميات بيانات ديناميكية.  
5. **تحليلات التسويق:** تضمين مؤشرات الأداء الرئيسية للحملات في العروض التي تتجدد مع وصول مقاييس جديدة.

## اعتبارات الأداء
- **إدارة الذاكرة:** استخدم try‑with‑resources أو `presentation.dispose()` صراحةً لتحرير الذاكرة الأصلية بسرعة.  
- **مجموعات بيانات كبيرة:** عند التعامل مع أكثر من 10,000 نقطة بيانات، املأ بيانات المخطط عبر `ChartDataWorkbook` لتجنب تحميل مجموعة البيانات بالكامل إلى كائنات Java.  
- **سلامة الخيوط:** يجب أن يعمل كل خيط مع نسخة `Presentation` خاصة به؛ الـ API غير آمن عبر مشاركة الكائنات بين الخيوط.

## المشكلات الشائعة والحلول
- **المشكلة:** “ملف الترخيص غير موجود.”  
  **الحل:** ضع `license.json` في مسار الـ classpath واستدعِ `License license = new License(); license.setLicense("license.json");` قبل أي استخدام للـ API.  
- **المشكلة:** المخطط يظهر فارغًا بعد الحفظ.  
  **الحل:** تأكد من حفظ دفتر بيانات المخطط مع العرض (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **المشكلة:** تسميات البيانات تظهر خطأ “#REF!”.  
  **الحل:** تحقق من أن سلسلة مرجع الخلية تطابق اسم الورقة والعنوان بالضبط، وأن دفتر العمل المرفق بالمخطط هو نفسه.

## الأسئلة المتكررة

**س: هل يمكنني إضافة أنواع مخططات أخرى غير الفقاعة؟**  
**ج:** نعم، تشمل تعداد `ChartType` المخططات الخطية، الشريطية، الدائرية، الرادارية، المخططات المالية، وأكثر من 70 نوعًا إضافيًا.

**س: هل يعمل aspose slides maven dependency مع OpenJDK؟**  
**ج:** بالتأكيد؛ هو متوافق تمامًا مع OpenJDK 8‑21 ويعمل على جميع أنظمة التشغيل الرئيسية.

**س: كيف يمكنني تضمين مخطط من ملف Excel موجود؟**  
**ج:** حمّل دفتر عمل Excel باستخدام `WorkbookFactory.create(new FileInputStream("data.xlsx"))`، ثم اربط `ChartDataWorkbook` للمخطط بالدفتر قبل تعيين مراجع الخلايا.

**س: هل هناك حد لعدد المخططات في كل شريحة؟**  
**ج:** عمليًا لا؛ يمكن لـ Aspose.Slides معالجة عشرات المخططات في شريحة واحدة، يقتصر فقط على الذاكرة المتاحة.

**س: إلى أي تنسيق يمكنني تصدير العرض التقديمي النهائي؟**  
**ج:** يدعم PPTX، PPT، ODP، PDF، XPS، HTML، وحتى صيغ الصور مثل PNG و JPEG.

## الموارد
- [إصدارات Aspose.Slides للـ Java](https://releases.aspose.com/slides/java/) – تحميل أحدث ملفات المكتبة.  
- [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) – مرجع API شامل وأدلة.  
- [تحميل Aspose.Slides للـ Java](https://releases.aspose.com/slides/java/) – صفحة التحميل المباشر لحزم Maven/Gradle.  
- [شراء ترخيص](https://purchase.aspose.com/buy) – الحصول على ترخيص تجاري كامل.  
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/) – ابدأ بتجربة الميزات.  
- [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) – طلب مفتاح مؤقت لتقييم ممتد.  
- [منتدى دعم Aspose](https://forum.aspose.com/c/slides/11) – احصل على مساعدة من المجتمع ومهندسي Aspose.

## الخلاصة
You now have a complete, end‑to‑end guide for using the **aspose slides maven dependency** to add, configure, and persist charts in Java presentations. By following the steps above you can automate chart creation, bind data labels to live cell values, and generate professional‑grade decks at scale. Experiment with other chart types, explore animation APIs, and integrate this workflow into your reporting pipelines for maximum impact.

---  
**آخر تحديث:** 2026-06-03  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## دروس ذات صلة

- [كيفية إنشاء وتكوين العروض التقديمية باستخدام Aspose.Slides Java: دليل خطوة بخطوة](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [إنشاء PPTX باستخدام Java و Aspose.Slides Maven – دليل الأتمتة](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [كيفية إنشاء مخطط في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
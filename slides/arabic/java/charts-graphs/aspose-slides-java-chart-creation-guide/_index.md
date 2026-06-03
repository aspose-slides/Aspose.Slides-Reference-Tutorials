---
date: '2026-06-03'
description: تعلم كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides. يغطي
  هذا الدليل تبعية Maven، خطوات إنشاء المخطط، ومعالجة البيانات.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط عمودي متجمع في Java باستخدام Aspose.Slides

## كيفية إنشاء مخطط في Java: مقدمة
غالبًا ما تتضمن العروض التقديمية الديناميكية تصور البيانات عبر المخططات. مع **Aspose.Slides for Java**، يمكنك بسهولة **إنشاء مخطط عمودي متجمع**، وتعزيز الوضوح، وإحداث تأثير أقوى على جمهورك. هذا الدليل يشرح لك خطوة بخطوة كيفية إعداد المكتبة، وإضافة مخطط عمودي متجمع، وإدارة السلاسل، وعكس القيم السلبية بشكل شرطي.

**ما ستتعلمه**
- كيفية إعداد Aspose.Slides for Java.
- خطوات **إنشاء مخطط عمودي متجمع** في عرضك التقديمي.
- تقنيات لإدارة سلاسل المخطط ونقاط البيانات.
- طرق لعكس نقاط البيانات السلبية بشكل شرطي لتحسين التصور.
- كيفية حفظ العرض التقديمي بأمان.

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Slides for Java.  
- **ما نوع المخطط المعروض؟** مخطط عمودي متجمع.  
- **هل يمكنني عكس القيم السلبية؟** نعم، باستخدام `invertIfNegative`.  
- **ما نسخة Java المطلوبة؟** JDK 16 أو أحدث.  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، ترخيص Aspose صالح.

## ما هو مخطط العمود المتجمع؟
مخطط العمود المتجمع هو تمثيل بصري يضع سلاسل بيانات متعددة جنبًا إلى جنب لكل فئة، مما يتيح مقارنة سريعة عبر المجموعات. وهو مثالي للتقارير المالية، ولوحات مبيعات، وأي سيناريو تحتاج فيه إلى مقارنة عدة مؤشرات في آن واحد.

## لماذا تستخدم Aspose.Slides لإنشاء المخططات؟
يتيح لك Aspose.Slides إنشاء وتخصيص المخططات برمجيًا بالكامل، مما يلغي الحاجة إلى تحرير PowerPoint يدويًا. يدعم **أكثر من 70 تنسيقًا للإدخال والإخراج** ويمكنه معالجة العروض التقديمية التي تحتوي على **حتى 10,000 شريحة** دون تحميل الملف بالكامل في الذاكرة، مما يضمن أداءً عاليًا للتقارير على نطاق واسع.

## المتطلبات المسبقة
1. **المكتبات المطلوبة**  
   - Aspose.Slides for Java (الإصدار 25.4 أو أحدث).  

2. **البيئة**  
   - JDK 16 أو أحدث.  
   - Maven أو Gradle لإدارة التبعيات.  

3. **المعرفة**  
   - برمجة Java الأساسية.  
   - الإلمام بأدوات البناء (Maven/Gradle).  

## إعداد Aspose.Slides for Java
### تثبيت Maven
أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تثبيت Gradle
أضف السطر التالي إلى ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتنزيل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **نسخة تجريبية مجانية:** استكشف الميزات بدون ترخيص.  
- **ترخيص مؤقت:** استخدمه أثناء التقييم.  
- **ترخيص كامل:** اشترِه للاستخدام في بيئات الإنتاج.  

### التهيئة الأساسية
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## كيف أضيف مخطط عمودي متجمع إلى شريحة؟
`Presentation` هي الفئة الأساسية التي تمثل ملف PowerPoint. حمّل `Presentation` جديدًا، أضف شريحة، واستدعِ `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. هذا الاستدعاء الواحد ينشئ مخطط عمودي متجمع كامل الوظيفة يتموضع عند الإحداثيات المحددة. يمكنك بعد ذلك الوصول إلى كائن المخطط لتعديل السلاسل، ونقاط البيانات، والأنماط البصرية.

## دليل خطوة بخطوة

### الخطوة 1: إنشاء عرض تقديمي وإضافة مخطط عمودي متجمع
فئة `Presentation` تمثل مستند PowerPoint وتسمح بإنشاء الشرائح.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### الخطوة 2: إدارة سلاسل المخطط
الآن سنقوم بمسح أي سلسلة افتراضية، وإضافة سلسلة جديدة، وتعبئتها بالقيم الإيجابية والسلبية.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### الخطوة 3: عكس نقاط البيانات السلبية بشكل شرطي
طريقة `invertIfNegative` تتيح عكس القيم السلبية في سلسلة المخطط.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## الأخطاء الشائعة والنصائح
- **هل نسيت تحرير كائن `Presentation`؟** يجب دائمًا استدعاء `dispose()` داخل كتلة `finally` لتحرير الموارد الأصلية.  
- **القيم السلبية لا تظهر معكوسة؟** تأكد من استدعاء `invertIfNegative(true)` **بعد** إضافة نقطة البيانات.  
- **مشكلات حجم المخطط:** الإحداثيات (X, Y) والأبعاد (العرض، الارتفاع) بوحدات النقاط؛ عدّلها لتناسب تخطيط الشريحة.  

## الأسئلة المتكررة

**س:** هل يمكنني إنشاء أنواع مخططات أخرى باستخدام نفس النهج؟  
ج: نعم، ما عليك سوى استبدال `ChartType.ClusteredColumn` بأي قيمة أخرى من تعداد `ChartType` (مثل `Line` أو `Pie`).  

**س:** هل أحتاج إلى ترخيص لإصدارات التطوير؟  
ج: يتطلب الوصول الكامل للميزات ترخيصًا مؤقتًا أو تجريبيًا؛ وإلا، تعمل المكتبة في وضع التجربة مع قيود العلامة المائية.  

**س:** كيف يمكنني تصدير العرض التقديمي إلى PDF بعد إضافة المخططات؟  
`SaveFormat.Pdf` يحدد PDF كتنسيق إخراج لحفظ العرض التقديمي. استخدم `pres.save("output.pdf", SaveFormat.Pdf);` بعد الانتهاء من تعديل المخطط.  

**س:** هل يمكن تنسيق أعمدة فردية (لون، حد)؟  
`IChartDataPoint` يمثل نقطة بيانات واحدة في المخطط ويسمح بالتنسيق. كل `IChartDataPoint` يوفر خيارات مثل `getFillFormat().setFillType(FillType.Solid)` و `getLineFormat()`.  

**س:** ماذا لو احتجت لتحديث بيانات المخطط بعد حفظ العرض التقديمي؟  
ج: قم بتحميل العرض مرة أخرى باستخدام `new Presentation("file.pptx")`، عدّل بيانات المخطط، ثم أعد حفظه.  

---

**آخر تحديث:** 2026-06-03  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء مخطط عمودي مكدس في Java باستخدام Aspose.Slides – دليل شامل](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [كيفية إنشاء مخطط في Java باستخدام Aspose.Slides – إتقان إنشاء المخططات والتحقق](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [إنشاء وتنسيق المخططات في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
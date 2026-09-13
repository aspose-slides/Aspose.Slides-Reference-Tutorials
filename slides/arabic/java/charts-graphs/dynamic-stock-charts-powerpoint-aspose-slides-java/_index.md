---
date: '2026-09-12'
description: تعلم كيفية استخدام Maven Aspose Slides لإضافة وتخصيص مخططات الأسهم الديناميكية
  في PowerPoint باستخدام Java. يتضمن الإعداد، إضافة سلاسل البيانات، تنسيق الخطوط،
  والحفظ.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: يوضح دليل Maven Aspose Slides كيفية إنشاء وتخصيص مخططات الأسهم الديناميكية
  في PowerPoint باستخدام Java، مع تغطية سلاسل البيانات، تنسيق الخطوط، والحفظ.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'دليل Maven Aspose Slides: إنشاء مخططات الأسهم الديناميكية في PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: إنشاء مخططات الأسهم الديناميكية في PowerPoint باستخدام
  Java'
url: /ar/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: إنشاء مخططات أسهم ديناميكية في PowerPoint باستخدام Java

## مقدمة

**Maven Aspose Slides** يتيح لك إنشاء عروض PowerPoint متقدمة برمجياً باستخدام Java. في هذا البرنامج التعليمي ستتعلم كيفية إنشاء مخططات أسهم ديناميكية، إضافة وتنسيق سلاسل البيانات، تخصيص خطوط المخطط، وأخيرًا حفظ الملف. سواءً كنت محللًا ماليًا يُعد تقارير ربع سنوية أو مطورًا يبني عروض شرائح تلقائية، فإن الخطوات أدناه توفر لك حلاً كاملاً وجاهزًا للإنتاج.

**ما ستتعلمه**
- كيفية إعداد Maven مع Aspose.Slides for Java  
- كيفية إضافة مخطط أسهم ومسح البيانات الافتراضية  
- كيفية **add data series chart** و **format chart lines**  
- كيفية **customize chart java**‑specific visual elements  
- كيفية حفظ العرض المحدث

هل أنت مستعد لتحويل الأرقام الخام إلى رسومات أسهم جذابة بصريًا؟ هيا نبدأ!

## إجابات سريعة
- **ما هو عنصر Maven الذي أحتاجه؟** `aspose-slides` version 25.4 (or newer).  
- **هل يمكنني تشغيل هذا على أي نظام تشغيل؟** نعم – المكتبة جافا صافية وتعمل على Windows، macOS، وLinux.  
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص تجريبي مجاني يعمل للاختبار؛ ترخيص كامل مطلوب للإنتاج.  
- **ما هي أنواع المخططات المدعومة؟** أكثر من 70 نوعًا مدمجًا، بما في ذلك Stock، Line، وBar.  
- **ما حجم العرض التقديمي الذي يمكنني معالجته؟** Aspose.Slides يمكنه معالجة ملفات بأكثر من 500 شريحة دون تحميل الملف بالكامل في الذاكرة.

## ما هو Maven Aspose Slides؟

`Aspose.Slides for Java` هو API جافا يتيح إنشاء، تعديل، وتحويل ملفات PowerPoint دون الحاجة إلى Microsoft Office. تكامل Maven يبسط إدارة الاعتمادات، مما يتيح سحب المكتبة مباشرةً من Maven Central.

## لماذا تستخدم Maven Aspose Slides للمخططات المالية؟

Aspose.Slides يدعم **70+ chart types** ويمكنه إنشاء عروض تقديمية متعددة المئات من الصفحات في أقل من ثانية على عتاد الخادم النموذجي. ميزات **high‑low line** و **up/down bar** تمنحك تحكمًا دقيقًا في التصورات المالية، متجاوزةً ما يقدمه واجهة PowerPoint.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** – الإصدار 11 أو أعلى.  
- **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.  
- **Aspose.Slides for Java** – الإصدار 25.4 (الأحدث في وقت الكتابة).  

### إعداد Aspose.Slides for Java

#### Maven
لدمج Aspose.Slides في مشروعك باستخدام Maven، أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
لمستخدمي Gradle، أدرج هذا في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**الحصول على الترخيص** – ابدأ بتجربة مجانية أو اطلب ترخيصًا مؤقتًا. للاستخدام التجاري، اشترِ ترخيصًا كاملاً.

للحصول على مرجع API مفصل، راجع [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## كيفية إنشاء مخطط أسهم ديناميكي خطوة بخطوة

حمّل عرضك التقديمي، أضف مخطط أسهم، امسح البيانات الافتراضية، ثم أدخل السلاسل والفئات الخاصة بك. الإجابة المباشرة على السؤال الأساسي هي:

> حمّل ملف PPTX موجود باستخدام `new Presentation("template.pptx")`، أضف `Chart` من النوع `ChartType.Stock`، امسح السلاسل والفئات الافتراضية، ثم املأه بنقاط البيانات الخاصة بك وخيارات التنسيق. أخيرًا، استدعِ `presentation.save("output.pptx", SaveFormat.Pptx)`.

### تهيئة العرض التقديمي
#### نظرة عامة
ابدأ بتحميل ملف PowerPoint موجود لتتمكن من تعديلّه في مكانه.

#### خطوة بخطوة
1. **استيراد المكتبة** – فئة `Presentation` هي نقطة الدخول لجميع عمليات الشرائح.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **تحميل ملف العرض التقديمي** – قدّم المسار إلى ملف PPTX القالب الخاص بك.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة مخطط أسهم إلى الشريحة
#### نظرة عامة
أدرج مخطط أسهم في الشريحة الأولى من العرض التقديمي.

فئة `Chart` تمثل شكل مخطط يمكن إضافته إلى شريحة.

#### إجابة مباشرة
يمكنك إضافة مخطط أسهم عن طريق استدعاء `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. هذا ينشئ كائن مخطط يمكنك التلاعب به فورًا.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### مسح سلاسل البيانات والفئات الموجودة في المخطط
#### نظرة عامة
أزل أي سلاسل أو فئات مُعبأة مسبقًا لتبدأ بمجموعة بيانات نظيفة.

كائن `ChartData` يحتفظ بالسلاسل والفئات للمخطط.

#### إجابة مباشرة
استدعِ `chart.getChartData().getSeries().clear()` و `chart.getChartData().getCategories().clear()` لمسح المحتوى الافتراضي قبل إضافة بياناتك.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة فئات إلى بيانات المخطط
#### نظرة عامة
حدد فئات المحور X (مثل التواريخ) التي تُجَمّع قيم الأسهم الخاصة بك.

`ChartCategory` تمثل تسمية محور X للمخطط.

#### إجابة مباشرة
أنشئ `ChartCategory` جديد لكل تسمية باستخدام `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`، مع التكرار لكل شهر أو فترة.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة سلاسل بيانات إلى المخطط
#### نظرة عامة
أضف السلاسل الأربعة الأساسية: Open، High، Low، و Close.

`ChartSeries` يحتفظ بمجموعة من نقاط البيانات لسلسلة معينة في المخطط.

#### إجابة مباشرة
لكل سلسلة، استدعِ `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. هذا يسجل السلسلة في دفتر بيانات المخطط.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### إضافة نقاط بيانات إلى السلسلة
#### نظرة عامة
املأ كل سلسلة بقيم عددية تمثل أسعار الأسهم.

`DataPoint` تمثل قيمة واحدة في سلسلة.

#### إجابة مباشرة
قم بالتكرار عبر مجموعة البيانات الخاصة بك واستخدم `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (أو الطريقة المناسبة لنوع السلسلة) لإدراج كل نقطة.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### تنسيق خطوط high‑low و up/down bars
#### نظرة عامة
اضبط النمط البصري للموصلات high‑low وتعبئة أشرطة up/down.

`Marker` يحدد الرمز البصري لنقطة البيانات.

#### إجابة مباشرة
عيّن `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` و اضبط `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` للتحكم في سمك الخط واللون.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### عرض أشرطة up/down
استخدم طريقة `setShowUpDownBars(true)` للمخطط لجعل أشرطة up/down مرئية.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### تخصيص تسميات البيانات على خطوط high‑low
#### نظرة عامة
اعرض القيم العددية مباشرة على خطوط high‑low للرجوع السريع.

`DataLabel` يتحكم في مظهر التسميات المرتبطة بنقاط البيانات.

#### إجابة مباشرة
فعّل تسميات البيانات باستخدام `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` وقم بتنسيقها حسب الحاجة.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### تعيين لون تعبئة أشرطة up/down
#### نظرة عامة
امنح أشرطة الصعود تعبئة خضراء وأشرطة الهبوط تعبئة حمراء لتوضيح حركة السوق بوضوح.

كائن `UpDownBars` يتيح الوصول إلى تنسيق أشرطة الصعود والهبوط.

#### إجابة مباشرة
طبق `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` واضبط اللون الصلب إلى `Color.GREEN`؛ كرّر ذلك لأشرطة الهبوط باستخدام `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### حفظ ملف PowerPoint
#### نظرة عامة
احفظ تغييراتك في ملف PPTX جديد.

طريقة `save` تكتب العرض التقديمي إلى القرص بالتنسيق المحدد.

#### إجابة مباشرة
استدعِ `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – هذا يكتب العرض المعدل إلى القرص بتنسيق PowerPoint القياسي.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## المشكلات الشائعة وإجراءات استكشاف الأخطاء
- **Chart not appearing** – تأكد من أن إحداثيات X/Y للمخطط وأبعاده ضمن حدود الشريحة.  
- **Data points missing** – تحقق من أن مؤشرات خلايا دفتر البيانات تتطابق مع السلسلة/الصف الذي تنوي تعبئته.  
- **License exception** – ينتهي الترخيص التجريبي المؤقت بعد 30 يومًا؛ استبدله بترخيص دائم لبُنى الإنتاج.  
- **Performance slowdown on large files** – استخدم `Presentation.setCacheSize(0)` لتعطيل التخزين المؤقت إذا كنت تعالج آلاف الشرائح دفعة واحدة.

## الأسئلة المتكررة
**س: هل يمكنني استخدام هذا الكود في تطبيق ويب؟**  
**ج:** نعم. المكتبة جافا صافية، لذا يمكنك تشغيلها في أي حاوية servlet أو خدمة Spring Boot.

**س: هل يدعم Aspose.Slides أنواع مخططات أخرى غير Stock؟**  
**ج:** بالتأكيد. يدعم أكثر من 70 نوعًا من المخططات، بما في ذلك Line، Bar، Pie، و Radar.

**س: كيف يمكنني إضافة عنوان مخطط برمجيًا؟**  
**ج:** استخدم `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` ثم قم بتنسيق العنوان حسب الحاجة.

**س: هل هناك حد لعدد نقاط البيانات لكل سلسلة؟**  
**ج:** عمليًا، يمكنك إضافة عشرات الآلاف من النقاط؛ استهلاك الذاكرة يتزايد خطيًا، والمكتبة تبث البيانات للحفاظ على البصمة منخفضة.

**س: ما هي إحداثيات Maven التي يجب استخدامها لأحدث نسخة؟**  
**ج:** أحدث نسخة دائمًا متاحة تحت `com.aspose:aspose-slides:25.4` (أو أحدث) على Maven Central.

---

**آخر تحديث:** 2026-09-12  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose

## دروس ذات صلة

- [اعتماد maven لـ aspose slides: إضافة وتكوين المخططات في العروض باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [إنشاء مخطط PowerPoint Java – حفظ العروض مع المخططات باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [إنشاء وتنسيق مخططات PowerPoint باستخدام Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
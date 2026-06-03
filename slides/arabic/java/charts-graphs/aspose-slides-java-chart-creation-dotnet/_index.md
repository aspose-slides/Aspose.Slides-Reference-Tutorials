---
date: '2026-06-03'
description: تعلم كيفية إنشاء charts في عروض .NET وإضافة chart إلى slide باستخدام
  Aspose.Slides for Java. اتبع هذا step‑by‑step guide لتقنية data visualization.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: إنشاء charts في .NET باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات في .NET باستخدام Aspose.Slides for Java

## مقدمة
غالبًا ما يتضمن إنشاء عروض تقديمية جذابة دمج تمثيلات بصرية للبيانات مثل المخططات لتعزيز فهم الجمهور وتفاعله. **If you want to create charts in .NET**، توفر لك Aspose.Slides for Java واجهة برمجة تطبيقات قوية غير مرتبطة بلغة معينة تعمل بسلاسة داخل تطبيقات .NET. في هذا البرنامج التعليمي ستتعلم كيفية تهيئة عرض تقديمي، إضافة مجموعة متنوعة من أنواع المخططات، إدارة دفتر بيانات المخطط، وتنسيق بيانات السلاسل — بما في ذلك التعامل مع القيم السالبة. في النهاية ستتمكن من إنشاء مخطط في ملفات العروض برمجيًا وإضافة المخطط إلى الشريحة ببضع أسطر من الشيفرة.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء مخططات في عروض .NET باستخدام Aspose.Slides for Java.  
- **ما هو إصدار المكتبة المطلوب؟** Aspose.Slides for Java 25.4 أو أحدث.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استخدام Maven أو Gradle؟** نعم — كلا نظامي البناء مدعومان.  
- **ما هي أنواع المخططات المتاحة؟** عمود مجمع، خط، دائري، شريط، مساحة، وأكثر.

## كيفية إنشاء مخططات في عروض .NET باستخدام Aspose.Slides for Java؟
تمثل الفئة `Presentation` ملف PowerPoint وتوفر طرقًا للتعامل مع الشرائح. قم بتحميل كائن `Presentation` جديد، استدعِ `slides.addEmptySlide()` للحصول على شريحة، ثم استخدم `slide.getShapes().addChart()` لإدراج نوع المخطط المطلوب عند الإحداثيات التي تحددها. بعد إضافة المخطط، املأ دفتر بياناته بالسلاسل والفئات، طبّق أي تنسيق (مثل الألوان للقيم السالبة)، وأخيرًا احفظ العرض التقديمي كملف .pptx. يتيح لك هذا التدفق **create charts in .NET** باستخدام مجموعة مختصرة من استدعاءات API.

## ما هو Aspose.Slides for Java؟
Aspose.Slides for Java هي واجهة برمجة تطبيقات متعددة المنصات تمكّن المطورين من إنشاء وتعديل وعرض ملفات PowerPoint دون الحاجة إلى Microsoft Office. تدعم **50+ input and output formats** ويمكنها معالجة عروض تحتوي على آلاف الشرائح مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت.

## لماذا تستخدم Aspose.Slides for Java في مشروع .NET؟
يعمل Aspose.Slides for Java على آلة جافا الافتراضية ويمكن استدعاؤه من .NET عبر غلاف أصلي، مما يمنح مطوري .NET إمكانية الوصول إلى محرك مخططات متطور، معالجة عالية الأداء لمجموعات البيانات الكبيرة، وتوافق كامل مع شفرة جافا الحالية دون الحاجة إلى إعادة كتابة المنطق.

## المتطلبات المسبقة
قبل الغوص في إنشاء المخططات باستخدام Aspose.Slides for Java، دعنا نحدد ما تحتاجه:

### المكتبات المطلوبة والإصدارات
- **Aspose.Slides for Java**: الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير تدعم تطبيقات .NET.  
- فهم أساسي لمفاهيم برمجة Java.

### المتطلبات المعرفية
- الإلمام بإنشاء العروض التقديمية في سياق تطبيق .NET.  
- فهم تبعيات Java وإدارتها (Maven/Gradle).

## إعداد Aspose.Slides for Java
لبدء استخدام Aspose.Slides، تحتاج إلى تضمينه كاعتماد في مشروعك. إليك كيفية القيام بذلك:

### Maven
يضيف مقطع اعتماد Maven Aspose.Slides for Java إلى مشروعك.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
أدرج هذا السطر في ملف `build.gradle` الخاص بك لجلب المكتبة من Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، يمكنك تنزيل أحدث إصدار من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **Free Trial**: ابدأ بترخيص مؤقت لاستكشاف الميزات.  
- **Purchase**: اشترِ ترخيصًا للاستخدام الإنتاجي غير المحدود.

#### التهيئة الأساسية والإعداد
يتطلب تهيئة `Slides` تعيين الترخيص وإنشاء مثيل `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

يضمن هذا الإعداد إدارة الموارد بفعالية.

## دليل التنفيذ
سوف نرشدك خلال تنفيذ الميزات خطوة بخطوة.

### تهيئة العرض التقديمي
**Overview:**  
إنشاء مثيل للعرض التقديمي يضع الأساس لجميع العمليات اللاحقة. تُظهر هذه الميزة كيفية البدء من الصفر باستخدام Aspose.Slides.

#### الخطوة 1: استيراد الحزم الضرورية
`Presentation` والفئات المرتبطة هي جزء من مساحة الأسماء `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### الخطوة 2: إنشاء كائن Presentation جديد
أنشئ كائن `Presentation` ولفه في كتلة try‑with‑resources لضمان إغلاقه.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*يضمن ذلك أن كائن العرض التقديمي يتم إغلاقه بشكل صحيح بعد الاستخدام، مما يمنع تسرب الذاكرة.*

### إضافة مخطط إلى الشريحة
**Overview:**  
إضافة مخطط إلى شريحتك يمكن أن يجعل تصور البيانات أكثر فعالية وجاذبية.

#### الخطوة 1: استيراد الحزم الضرورية
تمثل الفئة `Chart` شكل مخطط يمكن وضعه على شريحة وتخصيصه.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### الخطوة 2: تهيئة العرض وإضافة المخطط
أنشئ شريحة، ثم استدعِ `addChart` مع `ChartType.ClusteredColumn` والموقع والحجم المطلوبين.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*هنا، نضيف مخطط عمود مجمع إلى الشريحة الأولى عند الإحداثيات والأبعاد المحددة.*

### إدارة دفتر بيانات المخطط
**Overview:**  
إدارة دفتر بيانات المخطط بفعالية تتيح لك تعديل السلاسل والفئات بسهولة.

#### الخطوة 1: استيراد الحزم الضرورية
`IChartDataWorkbook` يوفّر الوصول إلى دفتر البيانات الشبيه بـ Excel المستخدم من قبل المخططات.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### الخطوة 2: الوصول إلى دفتر البيانات ومسحه
استخرج دفتر البيانات من المخطط وامسح أي بيانات موجودة للبدء من جديد.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*مسح دفتر البيانات أمر حاسم للبدء بصفحة نظيفة عند إضافة سلاسل وفئات جديدة.*

### إضافة سلاسل وفئات إلى المخطط
**Overview:**  
تظهر هذه الميزة كيفية إضافة نقاط بيانات ذات معنى من خلال إدارة السلاسل والفئات.

#### الخطوة 1: إضافة السلاسل والفئات
استخدم `chart.getChartData().getSeries().add()` و `chart.getChartData().getCategories().add()` لتحديد الهيكل.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*إضافة السلاسل والفئات يتيح تقديم بيانات أكثر تنظيمًا.*

### تعبئة بيانات السلاسل والتنسيق
**Overview:**  
قم بتعبئة المخطط بنقاط البيانات وتنسيق المظهر لتحسين القابلية للقراءة، خاصة عند التعامل مع القيم السالبة.

#### الخطوة 1: تعبئة بيانات السلسلة
قم بتعيين قيم رقمية لكل خلية في دفتر البيانات وطبق تعبئة حمراء للأرقام السالبة.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*يوضح هذا القسم كيفية تعبئة البيانات وتطبيق تنسيق اللون لتحسين التصور.*

## المشكلات الشائعة والحلول
- **LicenseNotFoundException** – تأكد من أن مسار ملف الترخيص صحيح وأن الملف قابل للوصول أثناء التشغيل.  
- **NullPointerException on chart data** – احرص دائمًا على مسح دفتر البيانات قبل إضافة سلاسل جديدة لتجنب البيانات المتبقية.  
- **Chart not rendering in .NET** – تحقق من أنك تستخدم نسخة Aspose.Slides JAR المتوافقة مع .NET وأن بيئة تشغيل Java مُكوَّنة بشكل صحيح في مشروع .NET الخاص بك.

## الأسئلة المتكررة

**س: هل يمكنني إنشاء مخطط في ملفات العروض دون واجهة رسومية؟**  
**ج:** نعم، Aspose.Slides for Java يعمل بالكامل بدون رأس (headless) ويعمل على الخوادم دون أي مكونات رسومية.

**س: ما إصدارات .NET المدعومة؟**  
**ج:** .NET Framework 4.5+، .NET Core 3.1+، .NET 5، و .NET 6 كلها مدعومة.

**س: كم عدد أنواع المخططات التي يمكنني إضافتها؟**  
**ج:** أكثر من 20 نوعًا من المخططات متاح، بما في ذلك العمود، الخط، الدائري، المساحة، ومخططات الرادار.

**س: هل يمكن تنسيق نقاط البيانات الفردية؟**  
**ج:** بالتأكيد – يمكنك تعيين ألوان التعبئة، الحدود، والعلامات لكل نقطة بيانات عبر واجهة `IDataPoint` API.

**س: هل أحتاج إلى تحويل كائنات Java إلى أنواع .NET يدويًا؟**  
**ج:** لا، يغلف Aspose.Slides for Java للـ .NET عملية تحويل الأنواع تلقائيًا.

---

**آخر تحديث:** 2026-06-03  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية تضمين المخططات في عروض .NET باستخدام Aspose.Slides لتصور البيانات الفعال](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [كيفية استرجاع نوع مصدر بيانات المخطط باستخدام Aspose.Slides لـ .NET - المخططات والرسوم البيانية](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [إتقان إنشاء وتعديل سلاسل المخططات مع Aspose.Slides .NET لتصور البيانات الفعال](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
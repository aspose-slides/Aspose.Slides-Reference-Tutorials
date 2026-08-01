---
date: '2026-08-01'
description: تعلم كيفية استخدام ترخيص Aspose Slides لإنشاء وتخصيص مخططات دائرية في
  عروض Java التقديمية. اتبع التعليمات خطوة بخطوة لتكوين بيانات المخطط الدائري وإضافة
  شرائح المخطط بكفاءة.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: تعلم كيفية استخدام ترخيص Aspose Slides لإنشاء وتخصيص مخططات دائرية
  في عروض Java التقديمية. اتبع التعليمات خطوة بخطوة لتكوين بيانات المخطط الدائري وإضافة
  شرائح المخطط بكفاءة.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: إنشاء مخططات دائرية في Java باستخدام ترخيص Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: إنشاء مخططات دائرية في Java باستخدام ترخيص Aspose Slides
url: /ar/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات دائريّة في عروض Java باستخدام Aspose.Slides

## المقدمة

إذا كنت بحاجة إلى إنتاج عروض تقديمية ذات مظهر احترافي، **an Aspose Slides license** تمنحك القدرة على إنشاء وتنسيق المخططات برمجياً. في هذا الدليل ستتعلم كيفية إنشاء مخطط دائري، تكوين بياناته، وإدراجه في مجموعة شرائح Java — دون الاعتماد على Microsoft PowerPoint. سنستعرض الإعداد، تدفق الكود، ونصائح الممارسات الأفضل لتتمكن من تقديم تقارير بصرية مصقولة في دقائق.

**ما ستتعلمه:**
- إعداد Aspose.Slides for Java مع رخصة صالحة
- خطوات إنشاء وتخصيص مخطط دائري
- كيفية تكوين بيانات المخطط الدائري وإضافة شرائح المخطط
- المشكلات الشائعة وحيل الأداء

لنبدأ بالتأكد من أن بيئتك جاهزة.

## إجابات سريعة
- **ما الذي تتيح رخصة Aspose Slides؟** إنشاء مخططات كاملة المميزات، تصدير إلى PDF/HTML، وإزالة العلامات المائية.
- **ما نسخة Java المطلوبة؟** JDK 16 أو أحدث.
- **هل أحتاج إلى Maven أو Gradle؟** كلاهما يعمل؛ المكتبة متاحة عبر كليهما.
- **كم عدد نقاط البيانات التي يمكن أن يحتويها المخطط الدائري؟** حتى 10 000 نقطة دون مشاكل الذاكرة.
- **هل يمكنني تصدير الشريحة كصورة؟** نعم – PNG، JPEG، SVG، والمزيد مدعومة.

## المتطلبات المسبقة

قبل البدء، تحقق من أنك تمتلك:
- **المكتبات المطلوبة:** Aspose.Slides for Java (الإصدار 25.4 أو أحدث) – هذا الإصدار يدعم أحدث صيغ الملفات وتحسينات الأداء.
- **إعداد البيئة:** JDK 16+ مثبت ومُكوَّن في IDE أو نظام البناء الخاص بك.
- **المعرفة الأساسية:** الإلمام بـ Java، Maven أو Gradle، ومفاهيم البرمجة الكائنية.

## إعداد Aspose.Slides for Java

لاستخدام Aspose.Slides for Java، أدرجه في مشروعك. إليك كيفية إضافة الاعتماد باستخدام أدوات البناء الأكثر شيوعاً:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direct Download:** يمكنك أيضاً تنزيل أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الرخصة

Aspose offers a free trial that unlocks all features, but a **valid Aspose Slides license** is required for production use to remove evaluation watermarks and gain performance benefits. Purchase options are listed on the [purchase page](https://purchase.aspose.com/buy). After obtaining the license file, load it once at application startup:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## دليل التنفيذ

### إنشاء وإضافة مخطط دائري إلى العرض التقديمي

#### نظرة عامة
This section explains how to create a pie chart, configure its data series, and embed the chart into a slide. You’ll see the complete flow from initializing the presentation object to saving the final file.

#### الخطوة 1: تهيئة العرض التقديمي  
`Presentation` is Aspose.Slides' top‑level object that represents a PowerPoint file in memory. Creating an instance gives you a blank slide deck ready for modification.

```java
demo.Presentation pres = new demo.Presentation();
```  
This line creates a new presentation where all subsequent changes will be applied.

#### الخطوة 2: إضافة مخطط دائري إلى الشريحة  
`Chart` is the class that encapsulates chart objects, including pie charts. Adding a chart to a slide is a single method call that specifies position and size.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` و `yPosition` يحددان الزاوية العلوية اليسرى للمخطط.  
- `width` و `height` يحددان مساحة المخطط البصرية على الشريحة.

#### الخطوة 3: تكوين بيانات المخطط الدائري  
`ChartData` يحتوي على سلسلة البيانات للمخطط.  
**كيف أقوم بتكوين بيانات المخطط الدائري؟**  
Provide a concise answer first: Use the `ChartData` collection to add a series, then populate `ChartDataPoint` objects with numeric values and category names. This approach lets you display up to 10 000 slices while preserving label formatting. After setting the data, you can customize colors, legends, and data labels to match your corporate style guide.  
الآن، إليك الكود الذي يضيف فئتين ويظهر تسمياتهما:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
The snippet creates a data series, inserts two points, and enables category labels on the chart.

#### الخطوة 4: حفظ العرض التقديمي  
Finally, persist the presentation to a file format of your choice (PPTX, PDF, or PNG). The `save` method respects the active license, ensuring no trial watermarks appear.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### المشكلات الشائعة والحلول
- **خطأ نقص الرخصة:** تأكد من أن مسار ملف الرخصة صحيح وأن كائن `License` تم إنشاؤه قبل أي استدعاءات Aspose.Slides.
- **مخطط فارغ:** تحقق من أن سلسلة `ChartData` تحتوي على الأقل على `ChartDataPoint` واحد. السلسلة الفارغة تؤدي إلى مساحة مخطط فارغة.
- **بطء الأداء مع مجموعات بيانات كبيرة:** استخدم `presentation.getSlides().removeAt(index)` لإزالة الشرائح غير المستخدمة واستدعِ `System.gc()` بعد المعالجة الثقيلة.

## التطبيقات العملية
1. **تقارير الأعمال:** تصور حصة السوق أو توزيع الإيرادات عبر المناطق باستخدام مخطط دائري واحد.
2. **العروض الأكاديمية:** عرض نتائج الاستطلاعات أو نتائج التجارب بصيغة واضحة وسهلة الفهم.
3. **لوحات معلومات المشروع:** تمثيل نسب إكمال المهام أو تخصيص الموارد فوراً على شريحة.

يمكنك أيضاً دمج Aspose.Slides مع JDBC لسحب بيانات حية من قاعدة بيانات، وإنشاء مخططات محدثة أسبوعياً للملخصات التنفيذية.

## اعتبارات الأداء
عند التعامل مع عروض تقديمية تحتوي على العديد من الصور عالية الدقة أو مجموعات بيانات كبيرة:
- تحرير الكائنات فوراً باستخدام `try‑with‑resources` أو استدعاءات `dispose()` الصريحة.
- تمكين التحميل الكسول لموارد الشرائح للحفاظ على انخفاض استهلاك الذاكرة.
- في المعالجة الدفعية، أعد استخدام كائن `Presentation` واحد قدر الإمكان لتقليل حمل JVM.

## الخلاصة
You now have a complete, production‑ready workflow for creating pie charts in Java using an **Aspose Slides license**. Experiment with additional chart types—bar, line, or doughnut—to enrich your slides further. Next, explore the API’s export capabilities to generate PDF reports or PNG images automatically.

## الأسئلة المتكررة

**س: كيف يمكنني إضافة مخططات متعددة إلى شريحة واحدة؟**  
ج: استدعِ `slide.getShapes().addChart()` لكل مخطط، مع توفير إحداثيات وأبعاد فريدة لكل نسخة.

**س: ما هي بعض البدائل لـ Aspose.Slides for Java؟**  
ج: Apache POI و JFreeChart هما بديلان شائعان، لكنهما يفتقران إلى خيارات التصدير الشاملة ونموذج الترخيص الخاص بـ Aspose.

**س: هل يمكنني تحويل العرض التقديمي إلى صيغ أخرى باستخدام Aspose.Slides؟**  
ج: نعم—يمكنك التصدير إلى PDF، XPS، HTML، PNG، JPEG، SVG، والمزيد باستخدام استدعاء `save` واحد.

**س: كيف أتعامل مع الترخيص لفريق تطوير كبير؟**  
ج: اشترِ رخصة مؤسسية تغطي عدة مطورين وخوادم؛ تواصل مع مبيعات Aspose للحصول على خصومات حجمية.

**س: ماذا لو كانت بيانات المخطط تتحديث بشكل متكرر؟**  
ج: دمج Aspose.Slides مع مصدر بيانات (مثل استعلام SQL) وإعادة بناء المخطط في وقت التشغيل؛ يدعم الـ API ربط البيانات الديناميكي.

## الموارد
- **التوثيق:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **التنزيل:** [الإصدارات الأخيرة](https://releases.aspose.com/slides/java/)
- **الشراء:** [شراء رخصة](https://purchase.aspose.com/buy)
- **التجربة المجانية:** [جرب Aspose.Slides مجاناً](https://releases.aspose.com/slides/java/)
- **رخصة مؤقتة:** [الحصول على رخصة مؤقتة](https://purchase.aspose.com/temporary-license/)
- **الدعم:** [منتدى Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-08-01  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية إضافة وتكوين المخططات في العروض باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [إنشاء وتخصيص المخططات في عروض Java باستخدام Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [كيفية إنشاء وتكوين العروض باستخدام Aspose.Slides Java: دليل خطوة بخطوة](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-07-27'
description: كيفية تخصيص المخطط باستخدام Aspose.Slides for Java. تعلم إنشاء مخطط PowerPoint،
  وتنسيق سلسلة المبعثر، وحفظ العروض التقديمية بكفاءة.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: كيفية تخصيص المخطط باستخدام Aspose.Slides for Java. يوضح هذا الدليل
  كيفية إنشاء مخطط PowerPoint، وتنسيق نقاط المبعثر، وتصدير العروض التقديمية.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'كيفية تخصيص المخطط: مخطط مبعثر Aspose في Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'كيفية تخصيص المخطط: مخطط مبعثر Aspose في Java'
url: /ar/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تخصيص مخطط مبعثر Aspose في Java

في هذا البرنامج التعليمي ستكتشف **كيفية تخصيص المخطط** — وبشكل خاص مخطط مبعثر — باستخدام مكتبة Aspose.Slides for Java القوية. سنستعرض إعداد المشروع، إنشاء مخطط مبعثر، تعديل أنواع السلاسل والرموز، وأخيرًا حفظ العرض التقديمي. في النهاية، ستكون قادرًا على إنشاء مخططات مبعثرة ذات مظهر احترافي برمجيًا وتخصيص كل تفصيل بصري ليتطابق مع علامتك التجارية أو احتياجات التقارير.

## الإجابات السريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (v25.4+).  
- **أي نسخة من Java مدعومة؟** JDK 8 أو أعلى.  
- **هل يمكنني تغيير أشكال العلامات؟** نعم – استخدم `MarkerStyleType` لاختيار النجوم أو الدوائر، إلخ.  
- **كيف أحفظ الملف؟** استدعِ `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **هل يلزم ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.

## كيفية تخصيص المخطط في Java باستخدام Aspose.Slides؟
`Presentation` هي فئة Aspose.Slides التي تمثل ملف PowerPoint كامل في الذاكرة. حمّل `Presentation` جديدًا، أضف مخططًا مبعثرًا على الشريحة الأولى، اضبط أنواع السلاسل وأنماط العلامات، ثم استدعِ `save`. هذه العملية الواحدة تنشئ مخططًا مُصممًا بالكامل في بضع أسطر من كود Java، جاهزًا للإدراج في أي عرض PowerPoint.

## ما هو “تخصيص مخطط مبعثر Aspose”؟
تخصيص مخطط مبعثر باستخدام Aspose يعني تعريف بيانات المخطط ومظهره وسلوكه برمجيًا—من إحداثيات النقاط إلى رموز العلامات—دون فتح PowerPoint يدويًا. هذا النهج مثالي للتقارير الآلية، العروض التقديمية المدفوعة بالبيانات، أو أي سيناريو يتطلب تصورات قابلة للتكرار وعالية الجودة.

## لماذا نخصص المخططات المبعثرة باستخدام Aspose.Slides؟
توفر Aspose.Slides للمطورين تحكمًا برمجيًا كاملاً في مظهر المخطط، مما يسمح بإنشاء تصورات عالية الجودة تلقائيًا، وتكامل سلس مع خطوط تقارير البيانات، وإمكانية تخصيص كل عنصر بصري دون فتح PowerPoint يدويًا، مما يوفر الوقت ويضمن التناسق عبر العروض.

- **تحكم كامل** – تعديل أنواع السلاسل، أنماط العلامات، الألوان، وأكثر عبر كود Java.  
- **أتمتة** – إنشاء العشرات من المخططات بسرعة للوحة معلومات أو تقارير دفعة.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java، دون الحاجة لتثبيت Office.  
- **الأداء** – API خفيف الوزن يعالج **أكثر من 150 نوع مخطط** ويتعامل مع عروض مئات الصفحات دون تحميل الملف بالكامل في الذاكرة.

## المتطلبات المسبقة

للمتابعة، تأكد من وجود ما يلي:

- **Aspose.Slides for Java** (v25.4 أو أحدث).  
- **Java Development Kit (JDK)** 8 + مثبت.  
- Maven أو Gradle لإدارة التبعيات (أو يمكنك تنزيل ملف JAR يدويًا).  
- معرفة أساسية بـ Java وإلمام بأداة البناء التي تختارها.

## إعداد Aspose.Slides for Java

دمج المكتبة في مشروعك باستخدام إحدى الطرق أدناه.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

أو احصل على أحدث إصدار من [Aspose Releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **نسخة تجريبية مجانية** – تقييم لمدة 30 يومًا.  
- **ترخيص مؤقت** – فترة اختبار ممتدة.  
- **ترخيص كامل** – استخدام للإنتاج مع دعم مميز.

## دليل خطوة بخطوة لتخصيص مخطط مبعثر Aspose

### 1️⃣ إعداد مجلد لملفات العرض التقديمي الخاصة بك
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*لماذا هذا مهم:* ضمان وجود مجلد الإخراج يمنع حدوث `FileNotFoundException` عند حفظ PPTX لاحقًا.

### 2️⃣ إنشاء عرض تقديمي جديد والحصول على الشريحة الأولى
`Presentation` تمثل مستند PowerPoint وتوفر الوصول إلى الشرائح والأشكال. فئة `Presentation` تمثل ملف PowerPoint كامل في الذاكرة.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ إضافة مخطط مبعثر بخطوط ناعمة
`ChartType.ScatterWithSmoothLines` ينشئ مخططًا مبعثرًا حيث يتم ربط النقاط بخطوط ناعمة.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ مسح أي سلسلة افتراضية وإضافة سلسلتك الخاصة
`IChartSeries` تمثل سلسلة بيانات داخل مخطط.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ تعبئة السلسلة الأولى بنقاط البيانات
`addDataPointForScatterSeries` يضيف نقطة X‑Y واحدة إلى سلسلة مبعثرة.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ تخصيص نوع السلسلة ومظهر العلامة
`Marker` يتحكم في الرمز البصري المستخدم لكل نقطة بيانات في سلسلة المخطط.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ حفظ العرض التقديمي
`save` يكتب العرض التقديمي إلى ملف بالتنسيق المحدد.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## حالات الاستخدام الشائعة للمخططات المبعثرة المخصصة
- **لوحات معلومات مالية** – رسم سعر السهم مقابل الحجم.  
- **البحث العلمي** – عرض القياسات التجريبية مع علامات الأخطاء.  
- **إدارة المشاريع** – مقارنة الجهد المخطط مقابل الفعلي عبر المهام.  

## نصائح الأداء
- استدعِ `pres.dispose()` بعد الحفظ لتحرير الذاكرة الأصلية.  
- للمجموعات الكبيرة من البيانات، املأ دفتر العمل أولاً ثم اربط السلسلة لتجنب تحديثات الواجهة المتكررة.  
- أعد استخدام نسخة واحدة من `IChartDataWorkbook` عند إضافة العديد من السلاسل للحفاظ على انخفاض استهلاك الذاكرة.

## الأسئلة المتكررة

**س: كيف أغير لون العلامات؟**  
ج: استخدم `series.getMarker().getFillFormat().setFillColor(Color)` حيث `Color` هو كائن من نوع `java.awt.Color` مثل `Color.RED`.

**س: هل يمكنني إضافة أكثر من سلسلتين إلى مخطط مبعثر؟**  
ج: نعم. استدعِ `chart.getChartData().getSeries().add(...)` لكل سلسلة إضافية واملأ نقاطها وفقًا لذلك.

**س: هل يمكن تعيين وسيلة إيضاح مخصصة لكل سلسلة؟**  
ج: بالتأكيد. بعد إنشاء سلسلة، استدعِ `series.getLegend().setText("Your Legend Text")` لتجاوز الاسم الافتراضي.

**س: كيف يمكنني تصدير المخطط كصورة بدلاً من PPTX؟**  
ج: استدعِ `chart.getImage().save("chart.png", ImageFormat.Png)` بعد ضبط المخطط. سيُنتج ملف PNG مستقل.

**س: ماذا لو احتجت إلى تحريك نقاط المخطط المبعثر؟**  
ج: تدعم Aspose.Slides تأثيرات الرسوم المتحركة. استخدم `chart.getTimeline().getMainSequence().addEffect(...)` لإضافة رسومات دخول أو تأكيد إلى المخطط أو إلى سلسلة معينة.

---

**آخر تحديث:** 2026-07-27  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء وتخصيص مخططات PowerPoint في Java باستخدام Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [كيفية إنشاء مخطط فقاعة في PowerPoint باستخدام Aspose.Slides for Java (دليل)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [إنشاء وتخصيص مخططات مع خطوط الاتجاه في Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
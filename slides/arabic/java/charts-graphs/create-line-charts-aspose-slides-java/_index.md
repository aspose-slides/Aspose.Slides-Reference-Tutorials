---
date: '2026-03-23'
description: تعلم كيفية استخدام Aspose.Slides for Java لإنشاء مخططات خطية مع علامات،
  وإضافة سلسلة ثانية، ومعالجة البيانات الفارغة في عروض PowerPoint التقديمية.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'كيفية استخدام Aspose.Slides للـ Java: إنشاء مخططات خطية مع العلامات الافتراضية'
url: /ar/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات خطية مع علامات افتراضية باستخدام Aspose.Slides for Java

## مقدمة
إذا كنت تتساءل **كيفية استخدام Aspose** لأتمتة إنشاء PowerPoint، فقد وجدت المكان المناسب. في هذا الدرس سنستعرض بناء **مخطط خطي مع علامات**، إضافة سلسلة ثانية، ومعالجة البيانات الفارغة—كل ذلك باستخدام Aspose.Slides for Java. في النهاية ستحصل على قطعة كود جاهزة للتنفيذ تُنتج مخططًا احترافيًا دون الحاجة لفتح PowerPoint يدويًا.

### إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (latest version recommended)  
- **هل يمكنني إضافة سلسلة ثانية؟** نعم – تسمح لك الـ API بإضافة سلاسل متعددة بسهولة.  
- **كيف يتم التعامل مع نقاط البيانات الفارغة؟** استخدم `null` في قيمة الخلية؛ سيتخطى المخطط النقطة.  
- **هل أحتاج إلى Maven؟** يعمل Maven أو Gradle؛ راجع قسم *aspose slides maven* أدناه.  
- **هل يلزم الحصول على ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.

## كيفية استخدام Aspose.Slides for Java لإنشاء مخططات خطية
إنشاء المخططات برمجياً يوفر لك ساعات من التنسيق اليدوي ويضمن الاتساق عبر العروض التقديمية. سواء كنت تبني ميزة **create powerpoint chart** في أداة تقارير أو تولد مجموعات شرائح بشكل فوري، فإن Aspose.Slides يمنحك التحكم الكامل من خلال كود Java.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن بيئة التطوير جاهزة:

1. **Libraries & Dependencies**
   - مكتبة Aspose.Slides for Java (الإصدار 25.4 موصى به) – يغطي هذا سيناريو *aspose slides maven*.
   - مجموعة تطوير جافا (JDK) الإصدار 16 أو أعلى.
2. **Environment Setup**
   - بيئة تطوير متكاملة (IDE) تدعم Maven أو Gradle.
   - ملف ترخيص Aspose صالح إذا كنت تخطط لتشغيل الكود خارج النسخة التجريبية.
3. **Knowledge Prerequisites**
   - برمجة Java أساسية.
   - إلمام بملفات بناء Maven أو Gradle.

## إعداد Aspose.Slides للغة Java
### Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
أدرج هذا في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### التحميل المباشر
بدلاً من ذلك، يمكنك تنزيل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**خطوات الحصول على الترخيص:**
- للحصول على نسخة تجريبية مجانية، زر [free trial page](https://releases.aspose.com/slides/java/).
- للحصول على ترخيص مؤقت، انتقل إلى [temporary license page](https://purchase.aspose.com/temporary-license/).
- اشترِ ترخيصًا كاملاً عبر [purchase portal](https://purchase.aspose.com/buy).

**التهيئة الأساسية:**
إليك كيفية تهيئة Aspose.Slides في تطبيق Java الخاص بك:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

الآن، دعنا ننتقل إلى إنشاء المخططات!

## دليل التنفيذ
### الميزة 1: إنشاء مخطط مع علامات افتراضية
يوضح هذا القسم كيفية إنشاء **مخطط خطي مع علامات**، وهو مثالي لتسليط الضوء على نقاط البيانات الفردية على خط الاتجاه.

#### إضافة مخطط خطي
لإضافة مخطط خطي مع علامات:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### مسح السلاسل والفئات
لبدء جديد:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### الميزة 2: إضافة سلاسل وفئات
إضافة السلاسل والفئات أمر حاسم لتعبئة مخططاتك ببيانات ذات معنى.

#### إنشاء سلسلة جديدة
لإضافة سلسلة جديدة باسم "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### تعبئة الفئات ونقاط البيانات
لإضافة الفئات ونقاط البيانات المقابلة:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### الميزة 3: إضافة سلسلة ثانية وتعبئة نقاط البيانات
إضافة سلاسل إضافية توفر عمقًا أكبر لتحليلك البصري.

#### إنشاء وتعبئة سلسلة ثانية
لإضافة "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### الميزة 4: تكوين وسيلة إيضاح المخطط
تكوين وسيلة الإيضاح يعزز قابلية قراءة المخطط، خاصة عندما **تضيف سلسلة ثانية**.

#### تعديل إعدادات وسيلة الإيضاح
للتكوين:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### الميزة 5: حفظ العرض التقديمي
بمجرد أن يصبح المخطط جاهزًا، ستحتاج إلى **create powerpoint chart** ملفات يمكن مشاركتها أو تعديلها لاحقًا.
```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## تطبيقات عملية
1. **تقارير الأعمال:** استخدم مخططًا خطيًا مع علامات لتوضيح الاتجاهات المالية عبر الأرباع.  
2. **تحليل البيانات:** تصور البيانات التجريبية حيث يبرز كل علامة نقطة قياس.  
3. **مواد تعليمية:** أنشئ شرائح محاضرات تُظهر التغييرات خطوة بخطوة في عملية ما.  
4. **إدارة المشاريع:** تتبع المعالم على خط زمني مع علامات مميزة للتواريخ الرئيسية.  
5. **عروض التسويق:** عرض ارتفاعات أداء الحملة باستخدام رموز علامات واضحة.  

## المشكلات الشائعة والحلول
- **نقاط البيانات الفارغة تسبب أخطاء:** مرّر `null` كقيمة الخلية (كما هو موضح) – سيقوم Aspose ببساطة بتخطي النقطة.  
- **المخطط يظهر بدون علامات:** تأكد من استخدام `ChartType.LineWithMarkers` بدلاً من `ChartType.Line`.  
- **وسيلة الإيضاح تتداخل مع البيانات:** اضبط `chart.getLegend().setOverlay(false)` للحفاظ على فصل وسيلة الإيضاح.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا النهج لتوليد مخططات في خدمة ويب؟**  
ج: بالتأكيد. تعمل المكتبة في أي بيئة Java، بما في ذلك التطبيقات من جانب الخادم.

**س: هل أحتاج إلى ترخيص لبنات التطوير؟**  
ج: النسخة التجريبية المجانية تعمل للتطوير والاختبار. يلزم ترخيص تجاري للاستخدام في الإنتاج.

**س: كيف يتعامل Aspose مع مجموعات البيانات الكبيرة؟**  
ج: الـ API يبث البيانات بكفاءة؛ ومع ذلك، حافظ على عدد نقاط البيانات معقولًا لتجنب أحجام ملفات ضخمة.

**س: هل هناك دعم لأنواع مخططات أخرى؟**  
ج: نعم – يدعم Aspose.Slides المخططات الشريطية، الدائرية، المبعثرة، والعديد غيرها.

**س: هل يمكنني تخصيص أشكال وألوان العلامات؟**  
ج: يمكنك تعديل تنسيق العلامة عبر خاصية `Marker` لكل نقطة بيانات.

## الخلاصة
أنت الآن تعرف **كيفية استخدام Aspose** لإنشاء مخطط خطي مع علامات افتراضية، إضافة سلسلة ثانية، معالجة البيانات الفارغة، وحفظ النتيجة كملف PowerPoint. تتيح لك هذه التقنيات أتمتة إنشاء التقارير، تحسين سرد البيانات، والحفاظ على اتساق عروضك التقديمية.

للتعمق أكثر، استكشف [official documentation](https://docs.aspose.com/slides/java/) أو انضم إلى المنتديات المجتمعية مثل Stack Overflow.

---

**آخر تحديث:** 2026-03-23  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
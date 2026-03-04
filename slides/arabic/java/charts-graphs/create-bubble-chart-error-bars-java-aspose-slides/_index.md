---
date: '2026-03-04'
description: تعلم كيفية إضافة أشرطة خطأ مخصصة إلى مخطط الفقاعات باستخدام Aspose.Slides
  للغة Java. يغطي هذا الدليل إنشاء المخطط، وتكوين أشرطة الخطأ لكل نقطة، وحفظ العرض
  التقديمي.
keywords:
- Bubble Chart Java
- Custom Error Bars Aspose.Slides
- Java Data Visualization
title: كيفية إضافة أشرطة خطأ مخصصة إلى مخطط الفقاعات في جافا باستخدام Aspose.Slides
url: /ar/java/charts-graphs/create-bubble-chart-error-bars-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة أشرطة الخطأ المخصصة إلى مخطط الفقاعات في Java باستخدام Aspose.Slides

إنشاء عروض تقديمية واضحة ومبنية على البيانات غالبًا ما يعني تجاوز المخططات البسيطة. من خلال تعلم **كيفية إضافة أشرطة الخطأ المخصصة** إلى مخطط الفقاعات، تمنح جمهورك نظرة على التباين ومستويات الثقة لكل نقطة بيانات. في هذا البرنامج التعليمي ستتعرف على كيفية إعداد مشروع Java باستخدام Aspose.Slides، إضافة مخطط فقاعات إلى شريحة، تكوين أشرطة الخطأ لكل نقطة، وأخيرًا حفظ النتيجة كملف PowerPoint.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Slides for Java (الإصدار الأحدث).  
- **أي نوع مخطط يدعم أشرطة الخطأ المخصصة؟** مخطط الفقاعات (`ChartType.Bubble`).  
- **هل يمكن ضبط أشرطة الخطأ لكل نقطة بيانات؟** نعم – استخدم `ErrorBarsCustomValues` لقيم X/Y الموجبة والسالبة.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص الكامل يزيل حدود التقييم.  
- **كم من الوقت تستغرق التنفيذ؟** حوالي 10‑15 دقيقة لمثال أساسي.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

- **مجموعة تطوير جافا (JDK):** الإصدار 8 أو أعلى.  
- **Aspose.Slides for Java:** أضف المكتبة إلى مشروعك (انظر مقتطفات Maven/Gradle أدناه).  
- **بيئة التطوير المتكاملة (IDE):** IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر تفضله.

### المكتبات والاعتمادات المطلوبة

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

يمكنك أيضًا تنزيل أحدث ملف JAR من صفحة الإصدار الرسمية: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص

- ابدأ بنسخة تجريبية مجانية لاستكشاف جميع الميزات.  
- اطلب ترخيصًا مؤقتًا للاختبار غير المحدود.  
- اشترِ ترخيص تشغيل كامل للاستخدام في الإنتاج.

## إعداد Aspose.Slides for Java

بمجرد أن تكون المكتبة في مسار الفئات (classpath)، قم بتهيئة كائن Presentation. يخلق هذا المقطع لوحة نظيفة للمخطط.

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## دليل التنفيذ

### الميزة 1: إضافة مخطط إلى الشريحة وإنشاء مخطط فقاعات

**لماذا إضافة مخطط إلى الشريحة؟**  
إدراج مخطط مباشرةً في الشريحة يتيح لك الحفاظ على السياق البصري مع أي نص أو صور محيطة، مما يجعل العرض أكثر تماسكًا.

#### الخطوة 1: استيراد الفئات المطلوبة
```java
import com.aspose.slides.*;
```

#### الخطوة 2: إضافة مخطط فقاعات إلى الشريحة الأولى
```java
// Access the first slide
ISlide slide = presentation.getSlides().get_Item(0);

// Create a bubble chart on the slide
IChart chart = slide.getShapes().addChart(
    ChartType.Bubble, 50, 50, 400, 300, true);
```
- `ChartType.Bubble` يخبر Aspose أننا نريد مخطط فقاعات.  
- الإحداثيات `(50, 50)` والحجم `(400, 300)` يضعان المخطط بشكل مناسب على الشريحة.

### الميزة 2: تكوين أشرطة الخطأ

أشرطة الخطأ تعطي المشاهدين إشارة بصرية حول موثوقية كل نقطة. سنجعلها مرئية ونضبطها لاستخدام قيم مخصصة.

#### الخطوة 3: الوصول إلى السلسلة الأولى
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### الخطوة 4: تمكين وتعيين أشرطة الخطأ المخصصة
```java
// Accessing error bar formats
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();

// Making error bars visible
errBarX.setVisible(true);
errBarY.setVisible(true);

// Setting custom value types for more detailed control
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

### الميزة 3: تعيين أشرطة الخطأ لنقاط البيانات (أشرطة الخطأ لكل نقطة)

الآن سنعيّن قيم هوامش خطأ فريدة لكل فقاعة، موضحين **أشرطة الخطأ لكل نقطة**.

#### الخطوة 5: تكوين مجموعة نقاط البيانات
```java
IChartDataPointCollection points = series.getDataPoints();

// Configuring custom values for error bars
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Loop through each data point
for (int i = 0; i < points.size(); i++) {
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```
*استخدام القيم المخصصة يتيح لك تحديد نطاق الخطأ بدقة لكل فقاعة، وهو أمر أساسي للتحليلات العلمية أو المالية.*

### الميزة 4: حفظ العرض التقديمي
```java
String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";

// Saving the presentation
presentation.save(YOUR_DOCUMENT_DIRECTORY + "/ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

## التطبيقات العملية

إضافة أشرطة الخطأ المخصصة إلى مخطط الفقاعات ذات قيمة في العديد من السيناريوهات الواقعية:

1. **البحث العلمي:** إظهار عدم اليقين في القياس لكل نتيجة تجريبية.  
2. **تحليل الأعمال:** تصور نطاقات التوقعات للمبيعات أو حصة السوق.  
3. **التعليم:** توضيح المفاهيم الإحصائية مثل فترات الثقة.

## اعتبارات الأداء

- تخلص من كائن `Presentation` بسرعة لتحرير الموارد الأصلية.  
- قلل عدد نقاط البيانات إذا كنت تولد مخططات بكميات كبيرة؛ مجموعات البيانات الضخمة قد تزيد من وقت التصيير.  
- أعد استخدام كائنات المخطط عند إنشاء عدة شرائح لتقليل الحمل الزائد.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|-----|
| **ErrorBarsCustomValues returns `null`** | السلسلة لا تحتوي على نقاط بيانات بعد. | أضف نقاط البيانات أولاً أو تأكد من أن السلسلة مملوءة قبل تكوين أشرطة الخطأ. |
| **Chart not visible on slide** | أبعاد المخطط موضوعة خارج حدود الشريحة. | قم بضبط إحداثيات X/Y والعرض/الارتفاع لتتناسب مع حجم الشريحة. |
| **License exception** | استخدام النسخة التجريبية بدون ترخيص صالح. | طبق ترخيصًا مؤقتًا أو كاملًا قبل حفظ العرض التقديمي. |

## الأسئلة المتكررة

**س: ما هو Aspose.Slides for Java؟**  
ج: إنه واجهة برمجة تطبيقات قوية تتيح لك إنشاء وتعديل وتحويل ملفات PowerPoint برمجيًا دون الحاجة إلى Microsoft Office.

**س: هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**  
ج: نعم، النسخة التجريبية المجانية تعمل للتطوير والاختبار، لكنها تضيف علامات مائية تقييمية وتحد من بعض الميزات.

**س: كيف أقوم بتحديث إلى أحدث إصدار من Aspose.Slides؟**  
ج: تحقق من صفحة الإصدارات الرسمية لـ [Aspose](https://releases.aspose.com/slides/java/) وقم بتحديث اعتماد Maven/Gradle وفقًا لذلك.

**س: لماذا إضافة أشرطة الخطأ المخصصة إلى مخطط الفقاعات؟**  
ج: إنها تنقل التباين أو الثقة لكل نقطة بيانات، مما يحول تصورًا مبسطًا إلى قصة أكثر غنى وإفادة.

**س: هل يمكنني تخصيص أنواع مخططات أخرى بأشرطة الخطأ؟**  
ج: بالتأكيد. يدعم Aspose.Slides أشرطة الخطأ للمخططات الخطية، الشريطية، العمودية، والعديد من الأنواع الأخرى.

---

**آخر تحديث:** 2026-03-04  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
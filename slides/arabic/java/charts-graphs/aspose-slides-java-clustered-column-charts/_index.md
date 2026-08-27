---
date: '2026-08-27'
description: تعلم كيفية إنشاء مخطط أعمدة متجمع في Java باستخدام Aspose.Slides، إضافة
  المخطط، ضبط ألوان السلاسل تلقائيًا، وحفظ العرض التقديمي بصيغة PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: تعلم كيفية إنشاء مخطط أعمدة متجمع في Java باستخدام Aspose.Slides،
  إضافة المخطط، ضبط ألوان السلاسل تلقائيًا، وحفظ العرض التقديمي بصيغة PPTX—كل ذلك
  مع تعليمات واضحة خطوة بخطوة.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: إنشاء مخطط أعمدة متجمع في Java باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: كيفية إنشاء مخطط أعمدة متجمع في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مخطط عمود مجمع في Java باستخدام Aspose.Slides

## مقدمة
إنشاء مخطط عمود مجمع برمجياً يوفر لك ساعات من التنسيق اليدوي ويضمن الاتساق عبر عروض تقديمية متعددة. في هذا الدرس ستتعلم **كيفية إنشاء مخطط عمود مجمع** في Java باستخدام Aspose.Slides، **كيفية إضافة مخطط**، **كيفية تعيين الألوان**، و**كيفية حفظ العرض التقديمي كملف PPTX**. سنغطي كل شيء من تثبيت المكتبة إلى تخصيص ألوان تعبئة السلاسل وحفظ الملف، حتى تتمكن من دمج تصورات بيانات غنية في أي عرض PowerPoint.

## إجابات سريعة
- **ما هي الفئة الأساسية للعمل مع العروض التقديمية؟** `Presentation` من حزمة `com.aspose.slides`.  
- **كيف يمكنني إضافة مخطط عمود مجمع؟** استدعِ `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **هل يمكن تعيين ألوان السلاسل تلقائيًا؟** نعم—فعّل `setAutomaticSeriesColor(true)` على كل سلسلة.  
- **أي تنسيق يجب أن أستخدمه لحفظ الملف؟** `SaveFormat.Pptx` ينتج ملف PowerPoint قياسي.  
- **هل يلزم وجود ترخيص للإنتاج؟** النسخة التجريبية تعمل للتطوير؛ يلزم ترخيص كامل للاستخدام التجاري.

## ما هو مخطط العمود المجمع؟
مخطط العمود المجمع يعرض عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يسهل مقارنة القيم عبر المجموعات. يدعم Aspose.Slides هذا النوع من المخططات مباشرة ويسمح لك بالتحكم في كل جانب بصري برمجياً.

## لماذا إنشاء مخطط عمود مجمع باستخدام Aspose.Slides؟
يمكن لـ Aspose.Slides معالجة **أكثر من 50 تنسيقًا للإدخال والإخراج** ومعالجة عروض تقديمية تحتوي على **مئات الشرائح** دون تحميل الملف بالكامل في الذاكرة. هذه الكفاءة تعني أنك تستطيع توليد مجموعات شرائح كبيرة في بيئة خادم مع استهلاك موارد منخفض.

## المتطلبات المسبقة
- **Java Development Kit** 16 أو أحدث.  
- **Maven** أو **Gradle** لإدارة التبعيات.  
- إلمام أساسي بصياغة Java ومفاهيم البرمجة الكائنية.  

### المكتبات والتبعيات المطلوبة
تحتاج إلى مكتبة Aspose.Slides for Java (الإصدار 25.4 أو أحدث). المكتبة متوافقة تمامًا مع JDK 16 وتوفر API غنيًا لمعالجة المخططات.

### متطلبات إعداد البيئة
يجب تكوين بيئة التطوير المتكاملة (IntelliJ IDEA، Eclipse، VS Code) لتجميع كود Java 16 وحل تبعيات Maven/Gradle.

### متطلبات المعرفة
فهم بنية شريحة PowerPoint ومصطلحات المخططات الأساسية (السلاسل، الفئات، نقاط البيانات) سيساعدك على متابعة الأمثلة بسرعة أكبر.

## إعداد Aspose.Slides لـ Java
دمج المكتبة في مشروعك باستخدام إحدى الطرق التالية.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**التنزيل المباشر** – احصل على ملف JAR من صفحة الإصدارات الرسمية: [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية** – سجِّل في موقع Aspose للحصول على ملف ترخيص مؤقت.  
- **ترخيص مؤقت** – اطلب ترخيصًا لمدة 30 يومًا لمجموعات الاختبار الكبيرة.  
- **ترخيص كامل** – اشترِ لاستخدام غير محدود في الإنتاج.

**التهيئة الأساسية والإعداد**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## كيف تضيف مخطط عمود مجمع؟
`Presentation` تمثل ملف PowerPoint في الذاكرة.  

**الإجابة المباشرة:**  
أنشئ كائن `Presentation`، والذي يمثل ملف PowerPoint في الذاكرة، استرجع الشريحة الأولى، واستدعِ `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. هذه الدعوة الواحدة تُدرج مخطط عمود مجمع كامل الوظائف، جاهز لتعبئة البيانات، وتضعه في الإحداثيات المحددة على الشريحة.

### الميزة 1: إنشاء مخطط عمود مجمع
فئة `Presentation` تمثل ملف PowerPoint في الذاكرة وتوفر الوصول إلى الشرائح، الأشكال، وكائنات المخططات.

**الخطوة 1: تهيئة العرض التقديمي**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**الخطوة 2: إضافة مخطط عمود مجمع**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**الخطوة 3: تنظيف الموارد**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## كيف تضبط ألوان المخطط؟
`Series` تمثل مجموعة من نقاط البيانات داخل المخطط.  

**الإجابة المباشرة:**  
بعد إنشاء المخطط، احصل على بياناته عبر `chart.getChartData()` وتكرار كل كائن `Series`. لكل سلسلة، استدعِ `setAutomaticSeriesColor(true)` على السلسلة الأصلية. يقوم Aspose.Slides تلقائيًا بتعيين لون مميز ومتناقض من لوحته لكل سلسلة، مما يضمن وضوحًا بصريًا دون الحاجة لاختيار اللون يدويًا.

### الميزة 2: تعيين تعبئة تلقائية لسلسلة اللون
`IChart` هو الواجهة التي تمثل شكل المخطط؛ تُظهر `getChartData()` لتعديل السلاسل.

**الخطوة 1: الوصول إلى المخطط وتكرار السلاسل**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**الخطوة 2: إدارة الموارد**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## كيف تحفظ العرض التقديمي كملف PPTX؟
`save` يكتب العرض التقديمي إلى ملف بالتنسيق المختار.  

**الإجابة المباشرة:**  
حدد مسار ملف الإخراج مثل `"output/ClusteredColumnChart.pptx"` واستدعِ `presentation.save(outputPath, SaveFormat.Pptx)`. طريقة `save` تسلسل كامل مجموعة الشرائح، بما في ذلك جميع الأشكال، المخططات، والموارد، إلى ملف PPTX قياسي يمكن فتحه بواسطة PowerPoint 2010 أو أحدث، وكذلك العديد من عارضات الإنترنت.

### الميزة 3: حفظ العرض التقديمي إلى القرص
الحفظ باستخدام `SaveFormat.Pptx` ينتج ملفًا متوافقًا مع PowerPoint 2010 وما بعده، وكذلك معظم عارضات الإنترنت.

**الخطوة 1: تحديد مسار الإخراج**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**الخطوة 2: حفظ العرض التقديمي**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## تطبيقات عملية
- **التقارير المالية** – قارن الإيرادات ربع السنوية عبر خطوط المنتجات.  
- **تحليلات التسويق** – تصور أداء الحملات حسب المنطقة.  
- **إدارة المشاريع** – عرض سرعة السبرينت أو تخصيص الموارد عبر الفرق.  

## اعتبارات الأداء
- تخلص من كائنات `Presentation` فورًا لتحرير الموارد الأصلية.  
- استخدم `presentation.getSlides().removeUnusedResources()` قبل الحفظ لتقليل حجم الملف.  
- املأ سلاسل المخطط بمجموعات خفيفة الوزن (مثل `ArrayList<Double>`) للحفاظ على انخفاض استهلاك الذاكرة.

## الخلاصة
أنت الآن تعرف **كيفية إنشاء مخطط عمود مجمع**، وتعيين **الألوان تلقائيًا**، و**حفظ العرض التقديمي كملف PPTX** باستخدام Aspose.Slides for Java. تتيح لك هذه الخطوات توليد شرائح مدفوعة بالبيانات برمجياً، مما يلغي العمل اليدوي المتكرر ويضمن اتساقًا بصريًا عبر مؤسستك.

**الخطوات التالية:**  
استكشف تخصيصات متقدمة مثل تسميات البيانات، تنسيق المحاور، وربط البيانات الديناميكي من قواعد البيانات أو ملفات CSV لإثراء عروضك التقديمية أكثر.

## الأسئلة المتكررة
**س: هل يمكنني استخدام هذا الكود في تطبيق ويب؟**  
ج: نعم—Aspose.Slides مستقل عن المنصة ويعمل في أي بيئة خادم مبنية على Java، بما في ذلك Spring Boot و Jakarta EE.

**س: هل تدعم المكتبة أنواع مخططات أخرى؟**  
ج: بالتأكيد. تعداد `ChartType` يشمل Pie، Bar، Line، Area، Radar، والعديد غيرها.

**س: ماذا لو لم يكن مجلد الإخراج موجودًا؟**  
ج: تأكد من إنشاء الدليل مسبقًا أو استخدم `Files.createDirectories(Paths.get(folder))` لتجنب `FileNotFoundException`.

**س: كيف أتعامل مع مجموعات بيانات كبيرة (آلاف النقاط)؟**  
ج: املأ السلاسل باستخدام واجهات برمجة تطبيقات البث أو الإدخالات الدفعية، وفكّر في تعطيل رسوم المتحركة للمخطط لتحسين سرعة العرض.

**س: أين يمكنني العثور على مزيد من عينات الكود؟**  
ج: زر الوثائق الرسمية ومستودع العينات: [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/).

## موارد
- **الوثائق:** [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **المرجع:** [مرجع Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **التنزيل:** [احصل على Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **الشراء:** [شراء ترخيص](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية:** [ابدأ نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت:** [اطلب هنا](https://purchase.aspose.com/temporary-license/)  
- **الدعم:** [منتدى Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-08-27  
**تم الاختبار مع:** Aspose.Slides 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء مخطط PowerPoint Java – حفظ العروض التقديمية مع المخططات باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [اعتماد Maven لـ Aspose Slides: إضافة وتكوين المخططات في العروض التقديمية باستخدام Aspose.Slides لـ Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [إضافة حركة إلى مخطط PowerPoint باستخدام Aspose.Slides لـ Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-03-20'
description: تعلم كيفية إضافة مخطط عمودي مجمع إلى عرض تقديمي في PowerPoint، وتخصيص
  مخطط PowerPoint، وإدراج مخطط سلسلة البيانات باستخدام Aspose.Slides for Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: كيفية إضافة مخطط عمود متجمع في PowerPoint باستخدام Aspose.Slides للـ Java
url: /ar/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط عمودي مجمع في PowerPoint باستخدام Aspose.Slides for Java

## مقدمة

عندما تحتاج إلى **إضافة مخطط عمودي مجمع** إلى عرض PowerPoint، يمكن للمرئيات الواضحة تحويل الأرقام الخام إلى قصة مفهومة على الفور. إن القيام بذلك يدويًا في PowerPoint قد يستغرق وقتًا طويلاً، خاصةً عندما يتعين عليك إنشاء العديد من الشرائح برمجيًا. **Aspose.Slides for Java** يزيل هذه العوائق – فهو يتيح لك إنشاء مخطط PowerPoint وتخصيصه وإدراج سلسلة بيانات بالمخطط ببضع أسطر من الشيفرة فقط.

في هذا الدرس ستتعلم كيفية:
- تهيئة عرض PowerPoint جديد باستخدام Aspose.Slides for Java.
- **إضافة مخطط إلى الشريحة** وتكوينه كمخطط عمودي مجمع.
- **إنشاء مخطط عمودي مجموع** عن طريق تعريف مستويات التجميع للفئات.
- **إدراج سلسلة بيانات إلى المخطط** بحيث يتم عرض بياناتك بشكل صحيح.
- حفظ العرض النهائي كملف PPTX.

دعنا نتأكد من أن لديك كل ما تحتاجه قبل الغوص في الشيفرة.

## إجابات سريعة
- **ما هو الصنف الأساسي؟** `Presentation` من `com.aspose.slides`.
- **ما هو نوع المخطط المستخدم؟** `ChartType.ClusteredColumn`.
- **هل أحتاج إلى ترخيص للاختبار؟** النسخة التجريبية المجانية تعمل، لكن الترخيص يزيل حدود التقييم.
- **ما نسخة Java المدعومة؟** JDK 16 أو أحدث (المثال يستخدم JDK 16).
- **كيف أشغل العينة؟** أضف تبعية Maven/Gradle، ثم قم بالترجمة وتشغيل طريقة `main`.

## ما هو “إضافة مخطط عمودي مجمع”؟

*المخطط العمودي المجمع* (المعروف أيضًا باسم مخطط عمودي مجموع) يعرض عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يسهل مقارنة القيم عبر المجموعات. في PowerPoint هذا النوع من المخططات مثالي للمبيعات الفصلية، نتائج الاستطلاعات، أو أي سيناريو تحتاج فيه إلى مقارنة عدة مجموعات بيانات داخل نفس الفئة.

## لماذا نستخدم Aspose.Slides لإضافة مخطط عمودي مجمع؟

- **أتمتة كاملة** – إنشاء العشرات من الشرائح دون جهد يدوي.
- **تخصيص دقيق** – التحكم بالألوان، التسميات، مستويات التجميع، وأكثر.
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.
- **بدون الحاجة لتثبيت Office** – إنشاء ملفات PPTX على الخوادم أو خطوط أنابيب CI.

## المتطلبات المسبقة

- مكتبة **Aspose.Slides for Java** (يفضل أحدث إصدار).  
- JDK 16 أو أحدث.  
- أداة بناء Maven أو Gradle (أو يمكنك إضافة ملف JAR يدويًا).  
- بيئة تطوير متكاملة أو محرر نصوص لتشغيل شيفرة Java.

## إعداد Aspose.Slides for Java

أضف المكتبة إلى مشروعك باستخدام أحد سكريبتات البناء التالية.

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

بدلاً من ذلك، يمكنك تنزيل أحدث إصدار مباشرة من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص

قبل النشر في بيئة الإنتاج، احصل على ترخيص:
- **نسخة تجريبية مجانية** – استكشف جميع الميزات دون شراء.
- **ترخيص مؤقت** – قيم القدرات الموسعة لفترة قصيرة.
- **ترخيص كامل** – يفتح الاستخدام غير المحدود. احصل عليه من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

## دليل التنفيذ

سنستعرض كل خطوة، موضحين **كيفية إضافة مخطط** و**تخصيص مخطط PowerPoint** على طول الطريق.

### تهيئة العرض

أولًا، أنشئ كائن `Presentation` جديد واحصل على الشريحة الافتراضية.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### إضافة مخطط إلى الشريحة

الآن **نضيف مخططًا إلى الشريحة** باستخدام النوع `ClusteredColumn` ونمسح أي بيانات افتراضية.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### إعداد دفتر عمل بيانات المخطط

المخطط يخزن بياناته في دفتر عمل داخلي. نقوم بمسحه للبدء من الصفر.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### إضافة الفئات مع مستويات التجميع

تجميع الفئات يخلق تأثير **المخطط العمودي المجموع**. يمكن لكل فئة أن تنتمي إلى مجموعة منطقية.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### إضافة سلاسل البيانات إلى المخطط

هنا **نُدرج سلاسل البيانات** التي ستُعرض كأعمدة منفصلة.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### حفظ العرض مع المخطط

أخيرًا، اكتب ملف PPTX إلى القرص.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## تطبيقات عملية

- **تقارير الأعمال** – مقارنة إيرادات الربع عبر المناطق.  
- **البحوث الأكاديمية** – عرض نتائج تجارب مُجَمَّعة حسب ظروف الاختبار.  
- **إدارة المشاريع** – تصور معدلات إكمال المهام لعدة فرق في شريحة واحدة.

## اعتبارات الأداء

- **إدارة الذاكرة** – حرّر دفاتر العمل الكبيرة بعد الاستخدام.  
- **عمليات الدفعة** – تجنّب تحديث المخطط داخل حلقات ضيقة؛ اجمع البيانات أولًا ثم طبّقها.  
- **تحسينات مدمجة** – توفر Aspose.Slides طرقًا مثل `Presentation.optimize()` للملفات الكبيرة.

## الأخطاء الشائعة والنصائح

- **الخطأ:** نسيان مسح السلاسل/الفئات الموجودة قد يؤدي إلى تكرار البيانات.  
  **النصيحة:** دائمًا استدعِ `clear()` قبل ملء بيانات جديدة.  
- **الخطأ:** استخدام عنوان خلية غير صحيح (مثل `"c2"` بدلاً من `"C2"`).  
  **النصيحة:** مراجع الخلايا غير حساسة لحالة الأحرف، لكن حافظ على الاتساق للقراءة السهلة.  
- **نصيحة:** استخدم `setGroupingItem` لإنشاء تسميات مجموعة ذات معنى؛ تظهر تلقائيًا في وسيلة إيضاح المخطط.

## الأسئلة المتكررة

**س1: كيف يمكنني إضافة عدة سلاسل إلى المخطط؟**  
ج1: استدعِ `ch.getChartData().getSeries().add()` بشكل متكرر، مع توفير اسم فريد ونقاط بيانات لكل سلسلة.

**س2: ما هي المشكلات الشائعة مع مخططات Aspose.Slides؟**  
ج2: غالبًا ما تنشأ المشكلات من نطاقات بيانات غير متطابقة أو خلايا دفتر عمل مفقودة. تأكد من أن كل فئة ونقطة بيانات لها خلية مقابلة.

**س3: هل يمكنني استخدام Aspose.Slides مع لغات برمجة أخرى؟**  
ج3: نعم، توفر Aspose مكتبات مكافئة لـ .NET، C++، Python، وأكثر.

**س4: كيف أُحدّث مخططًا موجودًا في عرض تقديمي؟**  
ج4: حمّل العرض، حدد المخطط عبر `slide.getShapes().get_Item(index)`، ثم عدّل سلاسله أو تنسيقه حسب الحاجة.

**س5: هل هناك قيود على أنواع المخططات في Aspose.Slides؟**  
ج5: تدعم المكتبة مجموعة واسعة من أنواع المخططات، لكن تحقق دائمًا من أحدث الوثائق لأي أنواع مضافة أو مهجورة حديثًا.

## موارد

- **الوثائق:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **التنزيل:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **الشراء:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **النسخة التجريبية المجانية:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **الترخيص المؤقت:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **منتدى الدعم:** [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-20  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose
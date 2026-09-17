---
date: '2026-09-17'
description: تعلم كيفية إضافة مخطط clustered column chart إلى عرض تقديمي في PowerPoint،
  وتخصيص مخطط PowerPoint، وإدراج مخطط data series باستخدام Aspose.Slides for Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: تعلم كيفية إضافة مخطط clustered column chart إلى عرض تقديمي في PowerPoint
  باستخدام Aspose.Slides for Java، بما في ذلك خطوات إدراج data series، وتخصيص grouping،
  وحفظ الملف بصيغة PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: إضافة مخطط clustered column chart إلى PowerPoint باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: كيفية إضافة مخطط clustered column chart إلى PowerPoint باستخدام Aspose.Slides
  for Java
url: /ar/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة مخطط عمود مجمع في PowerPoint باستخدام Aspose.Slides for Java

## مقدمة

عندما تحتاج إلى **إضافة مخطط عمود مجمع** إلى عرض PowerPoint، يمكن للمرئيات الواضحة تحويل الأرقام الخام إلى قصة مفهومة على الفور. القيام بذلك يدويًا في PowerPoint قد يكون مستهلكًا للوقت، خاصةً عندما تحتاج إلى إنشاء العديد من الشرائح برمجيًا. **Aspose.Slides for Java** يزيل العوائق – فهو يتيح لك إنشاء وتخصيص مخطط PowerPoint، وإدراج مخطط سلسلة بيانات ببضع أسطر من الشيفرة فقط.

في هذا الدرس ستتعلم كيفية:
- إنشاء عرض PowerPoint جديد باستخدام Aspose.Slides for Java.  
- **إضافة مخطط إلى الشريحة** وتكوينه كمخطط عمود مجمع.  
- **إنشاء مخطط عمود مجمع** عن طريق تعريف مستويات التجميع للفئات.  
- **إدراج مخطط سلسلة بيانات** بحيث يتم عرض بياناتك بشكل صحيح.  
- حفظ العرض النهائي كملف PPTX.

## إجابات سريعة
- **ما هي الفئة الأساسية؟** `Presentation` from `com.aspose.slides`.  
- **ما هو نوع المخطط المستخدم؟** `ChartType.ClusteredColumn`.  
- **هل أحتاج إلى ترخيص للاختبار؟** A free trial works, but a license removes evaluation limits.  
- **ما نسخة Java المدعومة؟** JDK 16 or newer (the example uses JDK 16).  
- **كيف أشغل العينة؟** Add the Maven/Gradle dependency, compile, and run the `main` method.

## ما هو “إضافة مخطط عمود مجمع”؟
يعرض مخطط العمود المجمع عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يتيح لك مقارنة القيم عبر المجموعات في مرئٍ واحد. إنه مثالي للمبيعات ربع السنوية، نتائج الاستطلاعات، أو أي سيناريو تحتاج فيه إلى مقارنة عدة مجموعات بيانات داخل نفس الفئة.

## لماذا تستخدم Aspose.Slides لإضافة مخطط عمود مجمع؟
يمكنك إنشاء العشرات من الشرائح تلقائيًا، تخصيص كل عنصر مرئي، وتشغيل الشيفرة على أي نظام تشغيل يدعم Java—دون الحاجة إلى تثبيت Microsoft Office. يدعم Aspose.Slides **أكثر من 50 نوعًا من المخططات** ويمكنه معالجة العروض التي تحتوي على **ما يصل إلى 500 شريحة** دون تحميل الملف بالكامل في الذاكرة، مما يجعله مناسبًا لأنابيب التقارير على نطاق واسع.

## المتطلبات المسبقة
- مكتبة **Aspose.Slides for Java** (يوصى بأحدث نسخة).  
- JDK 16 أو أحدث.  
- أداة بناء Maven أو Gradle (أو يمكنك إضافة ملف JAR يدويًا).  
- بيئة تطوير متكاملة (IDE) أو محرر نصوص لتشغيل شيفرة Java.

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

بدلاً من ذلك، يمكنك تنزيل أحدث إصدار مباشرةً من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
قبل النشر في بيئة الإنتاج، احصل على ترخيص:
- **نسخة تجريبية مجانية** – استكشف جميع الميزات دون شراء.  
- **ترخيص مؤقت** – تقييم القدرات الموسعة لفترة قصيرة.  
- **ترخيص كامل** – يتيح لك الاستخدام غير المحدود. احصل عليه من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

## كيفية إضافة مخطط عمود مجمع في PowerPoint باستخدام Aspose.Slides for Java؟
قم بتحميل `Presentation` جديد، أضف شريحة، أدخل `Chart` من النوع `ChartType.ClusteredColumn`، واملأ دفتر العمل الداخلي بالفئات والسلاسل، ثم احفظ الملف كملف PPTX. هذه السلسلة من الخطوات تنشئ مخطط عمود مجمع كامل الوظائف باستخدام عدد قليل فقط من استدعاءات API.

### تهيئة العرض
`Presentation` هي الفئة التي تمثل ملف PowerPoint في الذاكرة، مما يتيح لك إضافة الشرائح والأشكال والمخططات برمجيًا.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### إضافة مخطط إلى الشريحة
`ChartType.ClusteredColumn` يخبر Aspose.Slides برسم مخطط عمود مجمع.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### إعداد دفتر بيانات المخطط
يخزن المخطط بياناته في دفتر عمل داخلي. مسحه يمنحك مساحة فارغة لإدخال بيانات مخصصة.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### إضافة فئات مع مستويات التجميع
إن تجميع الفئات يخلق تأثير مخطط العمود المجمع. يمكن أن تنتمي كل فئة إلى مجموعة منطقية تظهر في تسميات المحور.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### إضافة سلاسل بيانات إلى المخطط
كائنات `Series` تمثل الأعمدة الفردية في المخطط. إضافة عدة سلاسل ينتج عنه أعمدة جنبًا إلى جنب لكل فئة.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### حفظ العرض مع المخطط
حفظ الـ `Presentation` يكتب ملف PPTX قياسي يمكن فتحه في أي عارض PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## تطبيقات عملية
- **تقارير الأعمال** – مقارنة الإيرادات ربع السنوية عبر المناطق.  
- **البحث الأكاديمي** – عرض نتائج التجارب مجمعة حسب ظروف الاختبار.  
- **إدارة المشاريع** – تصور معدلات إكمال المهام لعدة فرق في شريحة واحدة.

## اعتبارات الأداء
- **إدارة الذاكرة** – حرر دفاتر العمل الكبيرة بعد الاستخدام.  
- **عمليات الدفعات** – تجنب تحديث المخطط داخل حلقات ضيقة؛ اجمع البيانات أولاً، ثم طبّقها.  
- **تحسينات مدمجة** – يوفر Aspose.Slides طرقًا مثل `Presentation.optimize()` للملفات الكبيرة، مما يقلل استهلاك الذاكرة بنسبة تصل إلى **30 %**.

## الأخطاء الشائعة والنصائح
- **مشكلة:** نسيان مسح السلاسل/الفئات الموجودة قد يؤدي إلى تكرار البيانات.  
  **نصيحة:** دائمًا استدعِ `clear()` قبل ملء البيانات الجديدة.  
- **مشكلة:** استخدام عنوان خلية خاطئ (مثال: `"c2"` بدلاً من `"C2"`).  
  **نصيحة:** مراجع الخلايا غير حساسة لحالة الأحرف، لكن حافظ على توحيدها للقراءة السهلة.  
- **نصيحة:** استخدم `setGroupingItem` لإنشاء تسميات مجموعات ذات معنى؛ تظهر تلقائيًا في وسيلة إيضاح المخطط.

## الأسئلة المتكررة
**س1: كيف يمكنني إضافة عدة سلاسل إلى مخططي؟**  
ج1: استدعِ `ch.getChartData().getSeries().add()` بشكل متكرر، مع توفير اسم فريد ونقاط بيانات لكل سلسلة.

**س2: ما هي بعض المشكلات الشائعة مع مخططات Aspose.Slides؟**  
ج2: غالبًا ما تنبع المشكلات من نطاقات بيانات غير متطابقة أو خلايا دفتر عمل مفقودة. تأكد من أن كل فئة ونقطة بيانات لها خلية مقابلة.

**س3: هل يمكنني استخدام Aspose.Slides مع لغات برمجة أخرى؟**  
ج3: نعم، توفر Aspose مكتبات مكافئة لـ .NET، C++، Python، وغيرها.

**س4: كيف يمكنني تحديث مخطط موجود في عرض تقديمي؟**  
ج4: قم بتحميل العرض، حدد المخطط عبر `slide.getShapes().get_Item(index)`، ثم عدّل سلاسله أو تنسيقه حسب الحاجة.

**س5: هل هناك قيود على أنواع المخططات في Aspose.Slides؟**  
ج5: تدعم المكتبة أكثر من **50 نوعًا من المخططات** وتضيف أنواعًا جديدة باستمرار؛ تحقق دائمًا من أحدث الوثائق للحصول على القائمة الأكثر تحديثًا.

## الموارد
- **الوثائق:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **التنزيل:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **الشراء:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **منتدى الدعم:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-09-17  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة
- [إنشاء دليل إنشاء المخططات في Java باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [إضافة حركة إلى مخطط PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
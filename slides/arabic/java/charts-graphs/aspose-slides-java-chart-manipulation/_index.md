---
date: '2026-06-08'
description: تعلم كيفية إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides، إعداد
  تبعية Maven، إضافة مخطط clustered column chart، وحفظه كملف PPTX.
keywords:
- java create powerpoint chart
- maven dependency aspose slides
- chart manipulation in presentations
- java presentation library
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to java create powerpoint chart with Aspose.Slides, set up
    the Maven dependency, add a clustered column chart, and save as PPTX.
  headline: Java create powerpoint chart using Aspose.Slides
  type: TechArticle
- questions:
  - answer: Use the `ChartType` enum (e.g., `ChartType.Pie`, `ChartType.Line`) when
      calling `addChart`.
    question: How do I add other chart types?
  - answer: Yes, modify the series’ fill format or the chart’s palette via the `IChart`
      API.
    question: Can I customize chart colors?
  - answer: Verify that the output directory path is correct, exists, and is writable.
      Also ensure no other process holds a lock on the file.
    question: My presentation won’t save—what’s wrong?
  - answer: Process slides in batches, dispose of each `Presentation` after use, and
      consider increasing the JVM heap size if needed.
    question: How can I handle very large presentations efficiently?
  - answer: A free trial is available for evaluation, but a purchased license is required
      for commercial deployment.
    question: Is Aspose.Slides free for commercial projects?
  type: FAQPage
title: إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides

## مقدمة
في هذا الدليل ستتمكن من **إنشاء مخطط PowerPoint باستخدام Java** بسهولة مع Aspose.Slides for Java. سنستعرض تثبيت حزمة Maven أو Gradle، تهيئة كائن `Presentation`، إدراج مخطط عمودي مجمع، ضبط منطقة الرسم بدقة، وأخيرًا حفظ النتيجة كملف PPTX. في النهاية ستحصل على مقتطف جاهز للاستخدام يعمل في أي مشروع Java، سواء كنت تبني تقريرًا تجاريًا أو مولد شرائح تلقائي.

**ما ستتعلمه**
- كيفية إضافة تبعية Maven لـ Aspose.Slides  
- كيفية **إنشاء مخطط PowerPoint باستخدام Java** وإدراج مخطط عمودي مجمع  
- كيفية تعديل منطقة الرسم (الموقع، الحجم، هدف التخطيط)  
- كيفية **حفظ العرض التقديمي كملف pptx** مع تنظيف الموارد بشكل صحيح  

هل أنت مستعد لتحويل البيانات الخام إلى شرائح جذابة؟ لنبدأ!

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (متاحة عبر Maven أو Gradle).  
- **ما نوع المخطط الذي تم توضيحه؟** مخطط عمودي مجمع.  
- **كيف أحفظ الملف؟** استدعِ `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تغيير منطقة الرسم؟** نعم – اضبط X، Y، العرض، الارتفاع واختر نوع هدف التخطيط.

## ما هو إنشاء مخطط PowerPoint باستخدام Java؟
`java create powerpoint chart` يشير إلى إنشاء مخطط برمجيًا، تعبئته بالبيانات، وإدراجه في شريحة PowerPoint باستخدام مكتبة Java. Aspose.Slides يُجرد تنسيق Open XML بحيث يمكنك التركيز على التصميم البصري بدلاً من تفاصيل الملف الداخلية.

## لماذا إضافة مخطط عمودي مجمع باستخدام Aspose.Slides؟
مخطط عمودي مجمع مثالي لمقارنة سلاسل بيانات متعددة جنبًا إلى جنب. يُستخدم على نطاق واسع في التقارير التجارية، لوحات التحكم، والعروض التقديمية. يمنحك Aspose.Slides تحكمًا كاملًا في الألوان، العلامات، المحاور، والتخطيط دون الحاجة لفتح PowerPoint يدويًا. يتيح لك تسليط الضوء على الاتجاهات عبر الفئات، مما يجعل رؤى البيانات أوضح لأصحاب المصلحة. مع Aspose.Slides يمكنك تعديل تنسيق السلاسل، مقياس المحاور، وتسميات البيانات برمجيًا، لضمان توافق المخطط مع هوية الشركة ومعاييرها البصرية.

## المتطلبات المسبقة
- **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).  
- **JDK 16** أو أحدث.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- معرفة أساسية بـ Java.

## إعداد Aspose.Slides for Java
### Maven
أضف التبعية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```

### Gradle
ضمن المكتبة في `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4'
```

### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث إصدار من [الموقع الرسمي لـ Aspose](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
استخدم نسخة تجريبية مجانية أو ترخيص مؤقت للاختبار. اشترِ ترخيصًا كاملًا للنشر في بيئة الإنتاج.

## التهيئة الأساسية والإعداد
`Presentation` هي الفئة المدخلية لإنشاء ومعالجة ملفات PowerPoint. ابدأ بفئة Java جديدة واستورد الفئة الأساسية:

```java
import com.aspose.slides.Presentation;
```

## دليل التنفيذ
سنستعرض كل خطوة مع شروحات واضحة.

### تهيئة العرض التقديمي ومعالجة الشرائح
#### تعريف العنصر
`Presentation` هو كائن المستوى الأعلى في Aspose.Slides يمثل ملف PowerPoint كامل في الذاكرة.  

#### نظرة عامة
أولاً، أنشئ عرضًا تقديميًا جديدًا واحصل على الشريحة الأولى حيث سيُوضع المخطط.

**1. إنشاء وتهيئة عرض تقديمي**

```java
Presentation presentation = new Presentation();
```

**2. الوصول إلى الشريحة الأولى**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. إضافة مخطط عمودي مجمع**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **نصيحة احترافية:** احرص دائمًا على وضع استخدام العرض التقديمي داخل كتلة `try‑finally` واستدعِ `presentation.dispose()` في الـ `finally` لتحرير الموارد الأصلية.

### تكوين منطقة الرسم
#### نظرة عامة
قم بضبط منطقة الرسم للمخطط بدقة للتحكم في موضع عرض البيانات داخل الشريحة.

**1. ضبط الموقع والحجم**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. تحديد نوع هدف التخطيط**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### حفظ العرض التقديمي
#### نظرة عامة
بعد تخصيص المخطط، احفظ العرض التقديمي كملف PPTX.

**1. حفظ إلى ملف**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **تحذير:** تأكد من وجود دليل الإخراج وأن التطبيق يمتلك صلاحيات الكتابة؛ وإلا سيفشل عملية الحفظ.

## حالات الاستخدام الشائعة
- **تقارير الأعمال:** تضمين اتجاهات المبيعات ومؤشرات الأداء المالية.  
- **شرائح تعليمية:** تصور نتائج التجارب أو البيانات الإحصائية.  
- **اقتراحات المشاريع:** إبراز المراحل الرئيسية وتخصيص الموارد.  
- **عروض التسويق:** عرض أداء الحملات باستخدام مخططات حية.  
- **تخطيط الفعاليات:** عرض ديموغرافية الحضور أو تفاصيل الجدول الزمني.

## اعتبارات الأداء
- تخلص من كائنات `Presentation` فورًا لتجنب تسرب الذاكرة.  
- للمجموعات الكبيرة من البيانات، قم بملء سلاسل المخطط تدريجيًا بدلاً من تحميل كل شيء مرة واحدة.  
- استخدم أدوات التحليل المدمجة في Java لمراقبة استهلاك الذاكرة أثناء إنشاء المخطط.

## الأسئلة المتكررة

**س: كيف أضيف أنواع مخططات أخرى؟**  
**ج:** استخدم تعداد `ChartType` (مثل `ChartType.Pie`، `ChartType.Line`) عند استدعاء `addChart`.

**س: هل يمكنني تخصيص ألوان المخطط؟**  
**ج:** نعم، عدل تنسيق تعبئة السلسلة أو لوحة ألوان المخطط عبر واجهة `IChart`.

**س: لا يتم حفظ العرض التقديمي—ما الخطأ؟**  
**ج:** تأكد من صحة مسار دليل الإخراج، وجوده، وإمكانية الكتابة فيه. كما يجب التأكد من عدم وجود عملية أخرى تحتجز الملف.

**س: كيف يمكنني التعامل مع عروض تقديمية ضخمة بكفاءة؟**  
**ج:** عالج الشرائح على دفعات، وتخلص من كل `Presentation` بعد الاستخدام، وفكر في زيادة حجم heap للـ JVM إذا لزم الأمر.

**س: هل Aspose.Slides مجاني للمشاريع التجارية؟**  
**ج:** تتوفر نسخة تجريبية مجانية للتقييم، لكن يلزم الحصول على ترخيص مدفوع للنشر التجاري.

## الموارد
- [الوثائق](https://reference.aspose.com/slides/java/)
- [تحميل Aspose.Slides](https://releases.aspose.com/slides/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)
- [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى الدعم](https://forum.aspose.com/c/slides/11)

ابدأ الآن في إنشاء عروض تقديمية بصرية مذهلة باستخدام Aspose.Slides for Java اليوم!

**آخر تحديث:** 2026-06-08  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

## دروس ذات صلة

- [كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [كيفية إضافة وتكوين المخططات في العروض باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [إنشاء PowerPoint متحرك Java – تحريك مخططات PowerPoint باستخدام Aspose.Slides](/slides/java/animations-transitions/animate-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
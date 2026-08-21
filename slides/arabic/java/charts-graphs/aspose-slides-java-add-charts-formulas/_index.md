---
date: '2026-08-21'
description: تعلم كيفية إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides for Java،
  وبناء مخططات عمودية مجمّعة ديناميكية، وحساب صيغ المخطط في العروض التقديمية المؤتمتة.
keywords:
- create powerpoint chart java
- Aspose.Slides Java
- dynamic PowerPoint charts
lastmod: '2026-08-21'
og_description: إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides for Java. بناء
  مخططات عمودية مجمّعة ديناميكية، تطبيق الصيغ، وأتمتة العروض التقديمية بفعالية.
og_image_alt: Screenshot of a Java-generated PowerPoint chart using Aspose.Slides
og_title: إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create PowerPoint chart java using Aspose.Slides for Java,
    build dynamic clustered column charts, and calculate chart formulas in automated
    presentations.
  headline: How to create PowerPoint chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create PowerPoint chart java using Aspose.Slides for Java,
    build dynamic clustered column charts, and calculate chart formulas in automated
    presentations.
  name: How to create PowerPoint chart in Java with Aspose.Slides
  steps:
  - name: initialize the presentation
    text: The `Presentation` class represents a PowerPoint file in memory, allowing
      you to add slides, shapes, and charts.
  - name: access the first slide
    text: The `ISlide` interface represents an individual slide within a presentation.
  - name: add a clustered column chart
    text: The `IChart` interface defines chart objects that can be added to a slide.
      **Parameters explained** - `ChartType` – specifies the type of chart (here,
      a clustered column chart). - Coordinates (`x`, `y`) – position on the slide.
      - Width and height – dimensions of the chart.
  - name: access the chart data workbook
    text: The `IWorkbook` object stores the chart's underlying data table.
  - name: setting formulas (calculate chart formulas)
    text: '**Formula in cell B2** **R1C1‑style formula in cell C2** These formulas
      let the chart update automatically whenever the underlying data changes.'
  - name: calculate all formulas
    text: The `calculateFormulas()` method evaluates all formulas in the workbook.
  - name: save your presentation
    text: The `save` method writes the presentation to a file. Make sure to replace
      `YOUR_OUTPUT_DIRECTORY` with an actual path where you want to store the file.
  type: HowTo
- questions:
  - answer: JDK 16 or higher is recommended for compatibility and performance reasons.
    question: What is the minimum JDK version required for Aspose.Slides?
  - answer: Yes, but with limitations on functionality. Acquire a temporary or full
      license for unrestricted use.
    question: Can I use Aspose.Slides without a license?
  - answer: Use try‑finally blocks to ensure resources are released, as shown in the
      basic initialization example.
    question: How do I handle exceptions when using Aspose.Slides?
  - answer: Absolutely—create and position each chart individually within the slide’s
      bounds.
    question: Can I add multiple charts to the same slide?
  - answer: Yes—directly manipulate the chart data workbook and recalculate formulas.
    question: Is it possible to update chart data without regenerating the entire
      presentation?
  type: FAQPage
tags:
- create powerpoint chart
- Aspose.Slides
- Java presentation automation
title: كيفية إنشاء مخطط PowerPoint في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-add-charts-formulas/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان Aspose.Slides Java: إضافة المخططات والصيغ إلى عروض PowerPoint

## المقدمة

في هذا الدليل ستتعلم كيفية **إنشاء مخطط PowerPoint Java** باستخدام Aspose.Slides for Java، أتمتة إنشاء مخططات الأعمدة المجمعة الديناميكية، وتطبيق الصيغ المحسوبة—كل ذلك دون فتح واجهة PowerPoint. إنشاء عروض تقديمية جذابة أمر حيوي عندما تحتاج إلى نقل بيانات معقدة بسرعة، وتتيح لك إنشاء المخططات برمجياً دمج البيانات الجديدة في الشرائح فوراً.

**ما ستتعلمه**
- إعداد Aspose.Slides for Java
- إنشاء عرض PowerPoint وإدراج المخططات
- الوصول إلى بيانات المخطط وتعديلها باستخدام الصيغ
- حساب صيغ المخطط وحفظ العرض التقديمي

لنبدأ بمراجعة المتطلبات المسبقة!

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء مخطط PowerPoint تلقائيًا باستخدام Aspose.Slides for Java.  
- **ما نوع المخطط المعروض؟** مخطط أعمدة مجمعة.  
- **هل يمكن حساب الصيغ؟** نعم—استخدم `calculateFormulas()` لتقييم المخططات الديناميكية في PowerPoint.  
- **ما أداة البناء الموصى بها؟** Maven (أو Gradle) لتكامل Aspose Slides.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص الكامل يزيل قيود التقييم.

## ما هو “إضافة مخطط إلى PowerPoint” باستخدام Aspose.Slides؟

يتيح لك Aspose.Slides for Java إنشاء وتعديل ملفات PowerPoint برمجياً، بما في ذلك إدراج المخططات، دون فتح واجهة PowerPoint. هذه القدرة تمكّن من إعداد تقارير آلية وعروض شرائح مدفوعة بالبيانات مباشرةً من كود Java. يمكنك تحديد أنواع المخططات، تعيين نطاقات البيانات، وتطبيق الصيغ، مما يجعله مثالياً للعروض المالية، المبيعات، والتحليلات.

## لماذا نستخدم مخطط أعمدة مجمعة؟

يمكّن مخطط الأعمدة المجمعة من مقارنة عدة سلاسل بيانات جنبًا إلى جنب، بحيث تصبح الاتجاهات والفروقات واضحة فورًا. يدعم حتى 20 سلسلة لكل مخطط ويولد رسومات عالية الدقة مناسبة للطباعة. وبما أن كل سلسلة تُجمع حسب الفئة، يمكن لأصحاب المصلحة رصد الفجوات في الأداء عبر المناطق أو المنتجات أو الفترات الزمنية بنظرة واحدة.

## كيفية إنشاء مخطط PowerPoint باستخدام Aspose.Slides for Java

لإنشاء مخطط PowerPoint باستخدام Aspose.Slides for Java، أولاً تقوم بإعداد المكتبة، ثم تهيئة عرض تقديمي، إضافة شريحة، إدراج مخطط أعمدة مجمعة، ملء دفتر بياناته، تطبيق أي صيغ مطلوبة، إعادة حسابها، وأخيرًا حفظ الملف. يضمن هذا سير العمل أن يعكس المخطط أحدث البيانات والصيغ قبل إنشاء العرض.

### المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود:

- **مكتبة Aspose.Slides for Java** – الإصدار 25.4 أو أحدث، الذي يدعم **أكثر من 50 نوع مخطط** ويمكنه معالجة عروض تحتوي على **أكثر من 500 شريحة** دون تحميل الملف بالكامل في الذاكرة.  
- **مجموعة تطوير جافا (JDK)** – يجب تثبيت JDK 16 أو أعلى وتكوينه على نظامك.  
- **بيئة التطوير** – IntelliJ IDEA، Eclipse، أو أي بيئة تطوير متوافقة مع Java.  

فهم أساسي لفئات Java، الطرق، ومعالجة الاستثناءات ضروري. إذا كنت جديدًا على هذه المواضيع، فكر في مراجعة دروس Java التمهيدية أولاً.

#### إعداد Aspose.Slides for Java

#### تبعية Maven (maven for aspose slides)

أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### تبعية Gradle

إذا كنت تستخدم Gradle، أدرج هذا في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### التحميل المباشر

بدلاً من ذلك، قم بتحميل أحدث نسخة من Aspose.Slides for Java من [Aspose Releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **نسخة تجريبية مجانية** – ابدأ بنسخة تجريبية لاستكشاف القدرات.  
- **ترخيص مؤقت** – احصل على ترخيص مؤقت لاختبار موسع [temporary license request](https://purchase.aspose.com/temporary-license/).  
- **شراء** – فكر في شراء ترخيص كامل إذا وجدت الأداة ذات قيمة.

### التهيئة الأساسية

بعد الإعداد، قم بتهيئة بيئة Aspose.Slides:

```java
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## دليل التنفيذ

هذا القسم مقسم إلى خطوات لمساعدتك على فهم كل جزء بوضوح.

### الخطوة 1: تهيئة العرض التقديمي

تمثل فئة `Presentation` ملف PowerPoint في الذاكرة، مما يسمح لك بإضافة شرائح، أشكال، ومخططات.

```java
Presentation presentation = new Presentation();
```

### الخطوة 2: الوصول إلى الشريحة الأولى

تمثل واجهة `ISlide` شريحة فردية داخل العرض التقديمي.  

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

### الخطوة 3: إضافة مخطط أعمدة مجمعة

تعرف واجهة `IChart` كائنات المخططات التي يمكن إضافتها إلى شريحة.  

```java
IChart chart = slide.getShapes().addChart(
    ChartType.ClusteredColumn, 
    150, 150, 
    500, 300
);
```
**شرح المعلمات**
- `ChartType` – يحدد نوع المخطط (هنا، مخطط أعمدة مجمعة).  
- الإحداثيات (`x`, `y`) – الموقع على الشريحة.  
- العرض والارتفاع – أبعاد المخطط.

### الخطوة 4: الوصول إلى دفتر بيانات المخطط

كائن `IWorkbook` يخزن جدول البيانات الأساسي للمخطط.

```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```

### الخطوة 5: تعيين الصيغ (حساب صيغ المخطط)

**الصيغة في الخلية B2**  

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

**صيغة بنمط R1C1 في الخلية C2**  

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

تسمح هذه الصيغ للمخطط بالتحديث تلقائيًا كلما تغيرت البيانات الأساسية.

### الخطوة 6: حساب جميع الصيغ

طريقة `calculateFormulas()` تقيم جميع الصيغ في دفتر العمل.

```java
workbook.calculateFormulas();
```

### الخطوة 7: حفظ العرض التقديمي

طريقة `save` تكتب العرض التقديمي إلى ملف.

```java
String outpptxFile = "YOUR_OUTPUT_DIRECTORY" + File.separator + "ChartDataCell_Formulas_out.pptx";
presentation.save(outpptxFile, SaveFormat.Pptx);
```

تأكد من استبدال `YOUR_OUTPUT_DIRECTORY` بمسار فعلي حيث تريد تخزين الملف.

## التطبيقات العملية

- **التقارير المالية** – أتمتة المخططات الشهرية أو الربع سنوية للميزانيات وبيانات الأرباح والخسائر.  
- **التعليم** – توليد شرائح مدفوعة بالبيانات لتدريس الإحصاءات أو النتائج العلمية.  
- **تحليلات الأعمال** – دمج لوحات مؤشرات KPI حية في العروض، مع تحديث تلقائي عند تغير البيانات المصدر.

دمج Aspose.Slides في سير عملك الحالي يبسط إعداد العروض، خاصةً عند التعامل مع مجموعات بيانات كبيرة تتطلب تحديثات متكررة.

## اعتبارات الأداء

حسّن الأداء عن طريق:

- تحرير كائنات `Presentation` فورًا لتحرير الموارد الأصلية.  
- تقليل تعقيد المخطط على شريحة واحدة إذا كنت تحتاج إلى أوقات معالجة تحت الثانية.  
- استخدام عمليات دفعية لإضافة أو تحديث عدة مخططات في تمريرة واحدة، مما يقلل الحمل بنسبة تصل إلى 30 % على العروض الكبيرة.

اتباع هذه الممارسات يضمن تشغيلًا سلسًا حتى في البيئات ذات الموارد المحدودة.

## الخلاصة

بحلول الآن، يجب أن تكون مجهزًا جيدًا لإنشاء **مخطط PowerPoint Java** باستخدام Aspose.Slides for Java، بناء عروض تقديمية ديناميكية، والاستفادة من صيغ المخططات المحسوبة. توفر هذه المكتبة القوية الوقت وترفع جودة تصورات البيانات. استكشف المزيد من الميزات عبر [Aspose Documentation](https://reference.aspose.com/slides/java/) وفكر في توسيع مشروعك بقدرات إضافية من Aspose.Slides.

### الخطوات التالية

- جرب أنواعًا مختلفة من المخططات وتنسيقاتها.  
- دمج وظائف Aspose.Slides في تطبيقات Java أكبر.  
- استكشف مكتبات Aspose الأخرى لتعزيز معالجة المستندات عبر الصيغ.

## الأسئلة المتكررة

**س: ما هو الحد الأدنى لإصدار JDK المطلوب لـ Aspose.Slides؟**  
ج: يُنصح بـ JDK 16 أو أعلى لضمان التوافق والأداء.

**س: هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**  
ج: نعم، لكن مع قيود على الوظائف. احصل على ترخيص مؤقت أو كامل للاستخدام غير المقيد.

**س: كيف أتعامل مع الاستثناءات عند استخدام Aspose.Slides؟**  
ج: استخدم كتل try‑finally لضمان تحرير الموارد، كما هو موضح في مثال التهيئة الأساسية.

**س: هل يمكنني إضافة عدة مخططات إلى نفس الشريحة؟**  
ج: بالتأكيد—أنشئ وضعّع كل مخطط على حدة داخل حدود الشريحة.

**س: هل يمكن تحديث بيانات المخطط دون إعادة توليد العرض بالكامل؟**  
ج: نعم—قم بالتلاعب مباشرةً في دفتر بيانات المخطط وأعد حساب الصيغ.

استكشف المزيد من الموارد عبر الروابط أدناه:
- [Aspose Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-08-21  
**تم الاختبار مع:** Aspose.Slides 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< blocks/products/pf/backtop-button >}}

## دروس ذات صلة

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create Chart Creation Guide in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
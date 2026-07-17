---
date: '2026-07-17'
description: تعلم كيفية إضافة مخطط إلى PowerPoint بإنشاء مخطط Pie of Pie باستخدام
  Aspose.Slides for Java. يتضمن الإعداد، الكود، التخصيص، وحفظه كملف PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: أضف مخططًا إلى PowerPoint باستخدام Aspose.Slides for Java. يوضح هذا
  الدليل كيفية إنشاء وتخصيص وحفظ مخطط Pie of Pie كملف PPTX خلال دقائق.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: إضافة مخطط إلى PowerPoint – إنشاء مخطط Pie of Pie في Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: إضافة مخطط إلى PowerPoint – إنشاء مخطط Pie of Pie في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة مخطط إلى PowerPoint – إنشاء مخطط فطيرة داخل فطيرة في Java باستخدام Aspose.Slides

## المخططات والرسوم البيانية

### مقدمة

في العروض التقديمية الحديثة المعتمدة على البيانات، **إضافة مخطط إلى PowerPoint** غالبًا ما تكون أسرع طريقة لتحويل الأرقام الخام إلى بصيرة بصرية. يعمل مخطط الفطيرة العادي جيدًا لعدد قليل من الفئات، ولكن عندما تكون بعض الشرائح صغيرة جدًا تصبح غير قابلة للقراءة. يحل مخطط *Pie of Pie* هذه المشكلة عن طريق استخراج تلك الشرائح الصغيرة إلى فطيرة ثانوية، مما يحافظ على نظافة المخطط الرئيسي وإتاحة التفاصيل.

في هذا الدرس ستتعلم كيفية **إضافة مخطط إلى PowerPoint** عن طريق إنشاء مخطط Pie of Pie باستخدام Aspose.Slides for Java. سنستعرض إعداد البيئة، إنشاء المخطط، تخصيص التسميات، ضبط موضع الانقسام، وأخيرًا حفظ العرض التقديمي كملف PPTX. في النهاية ستكون جاهزًا لتضمين مخططات متقدمة في أي مجموعة شرائح.

## إجابات سريعة
في Aspose.Slides، `Presentation` تمثل ملف PPTX، `ChartType.PieOfPie` يختار مخطط Pie of Pie، `setShowValue(true)` يعرض القيم على التسميات، و `save` يكتب الملف.

- **ما هو الصنف الأساسي للتعامل مع PowerPoint؟** `Presentation` – it represents an entire PPTX file in memory.  
- **أي نوع مخطط ينشئ فطيرة ثانوية للشرائح الصغيرة؟** `ChartType.PieOfPie`.  
- **كيف تعرض القيم على كل شريحة؟** Set `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **هل يمكنك حفظ الملف مباشرة كـ PPTX؟** Yes – call `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **هل تحتاج إلى ترخيص للتطوير؟** A free 30‑day trial works for testing; a permanent license removes evaluation watermarks.

## ما هو مخطط Pie of Pie؟
مخطط **Pie of Pie** هو تصور فطيرة من مستويين يعزل شريحة أو أكثر صغيرة إلى فطيرة منفصلة مرتبطة، مما يجعلها أسهل للقراءة. يدعم Aspose.Slides هذا النوع من المخططات مباشرة، مما يتيح لك التحكم في حجم الانقسام، الموضع، وتنسيق التسميات.

## لماذا إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides؟
يمكن لـ Aspose.Slides إنشاء وتحرير وعرض ملفات PowerPoint دون الحاجة إلى تثبيت Microsoft Office. يدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، يعالج العروض التقديمية التي تحتوي على **ما يصل إلى 500 شريحة** في أقل من ثانية على خوادم عادية، ويوفر **تحكمًا كاملاً في API** على تنسيق المخطط، تسميات البيانات، وتخطيطها—مثالي لأنابيب التقارير الآلية.

## المتطلبات المسبقة

- **Java Development Kit (JDK) 16+** مثبت.  
- بيئة تطوير متكاملة مثل **IntelliJ IDEA**، **Eclipse**، أو **NetBeans**.  
- Maven أو Gradle لإدارة التبعيات (انظر الأقسام أدناه).  
- معرفة أساسية بـ Java وإلمام ببناء المشاريع.

## إعداد Aspose.Slides لـ Java

### معلومات التثبيت

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

**Direct Download:** يمكنك تنزيل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **Free Trial:** ابدأ بتجربة مجانية لمدة 30 يومًا لاستكشاف جميع الميزات.  
- **Temporary License:** اطلب مفتاحًا مؤقتًا لتقييم ممتد.  
- **Purchase:** احصل على ترخيص دائم للاستخدام الإنتاجي لإزالة العلامات المائية للتقييم.

### التهيئة الأساسية والإعداد
`Presentation` هو الكائن الرئيسي لإنشاء ملفات PowerPoint، و`Chart` يمثل شكل مخطط داخل شريحة.

```java
Presentation presentation = new Presentation();
```  

هذا ينشئ عرضًا تقديميًا فارغًا جاهزًا للشرائح والمخططات.

## دليل التنفيذ

### كيف تضيف مخططًا إلى PowerPoint باستخدام Aspose.Slides for Java؟

حمّل `Presentation` جديدًا، أضف شريحة، وأدرج `Chart` من النوع `PieOfPie`. سلسلة استدعاءات API مختصرة: إنشاء المخطط، تعبئة بيانات السلسلة، تعديل رؤية التسميات، ضبط حجم الفطيرة الثانوية، وأخيرًا الحفظ. عادةً ما يتناسب العملية بأكملها مع أقل من 20 سطرًا من الشيفرة، مما يجعلها مثالية لإنشاء تقارير آلية.

### إنشاء مخطط 'Pie of Pie'

#### نظرة عامة
سنقوم بإنشاء مخطط Pie of Pie على الشريحة الأولى، نفصل أصغر الشرائح، ونضع تسمية لكل جزء بقيمته.

#### الخطوة 1: إنشاء مثال من فئة Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
هذا يهيئ الحاوية لجميع الشرائح والمخططات اللاحقة.

#### الخطوة 2: إضافة مخطط 'Pie of Pie' على الشريحة الأولى
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
هنا نحدد `ChartType.PieOfPie` ونعرّف موضع المخطط (X, Y) وحجمه (العرض، الارتفاع) على لوحة الشريحة.

#### الخطوة 3: ضبط تسميات البيانات لإظهار القيم للسلسلة
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
تمكين `showValue` يجعل كل شريحة تعرض قيمتها الرقمية، وهو أمر أساسي لتفسير البيانات بسرعة.

#### الخطوة 4: ضبط حجم الفطيرة الثانية والانقسام حسب النسبة المئوية
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
تتيح لك هذه الخيارات تحديد مقدار المخطط المخصص للفطيرة الثانوية وأي الشرائح تُنقل بناءً على عتبة النسبة المئوية.

#### الخطوة 5: حفظ العرض التقديمي على القرص بصيغة PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **نصيحة احترافية:** استخدم مسارًا مطلقًا أو `Paths.get()` في Java لتجنب الفواصل الخاصة بالمنصة.

## المشكلات الشائعة والحلول

`License` class يحمل ملف ترخيص لإزالة قيود التقييم.

- **Missing license warning:** إذا رأيت "Evaluation Only" على المخطط، تأكد من تطبيق ملف ترخيص صالح عبر `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Incorrect slice split:** تحقق من أن خاصية `splitBy` مضبوطة على `SplitBy.Percentage` وأن `secondPieSize` قيمة بين 0 و 100.
- **Data not displaying:** تأكد من أن سلسلة المخطط تحتوي على نقطة بيانات واحدة على الأقل؛ وإلا سيظهر المخطط فارغًا.

## الأسئلة المتكررة

`IChart` يمثل كائن مخطط يمكن إضافته إلى شريحة.

**س: هل يمكنني إنشاء مخططات متعددة في عرض تقديمي واحد؟**  
ج: نعم، أنشئ `IChart` جديدًا لكل شريحة أو موقع؛ تسمح API بوجود عدد غير محدود من كائنات المخطط في الملف.

`SaveFormat.Pdf` يحدد صيغة الإخراج PDF للحفظ.

**س: هل يدعم Aspose.Slides الحفظ كملف PDF أيضًا؟**  
ج: بالتأكيد – استدعِ `presentation.save("output.pdf", SaveFormat.Pdf)` لتصدير مجموعة الشرائح نفسها إلى PDF.

`IPortion` يمثل شريحة فردية من مخطط الفطيرة.

**س: ما هو الحد الأقصى لعدد نقاط البيانات التي يمكن لمخطط Pie of Pie التعامل معها؟**  
ج: المكتبة تدعم ما يصل إلى **10,000** نقطة بيانات لكل سلسلة، يحدها فقط الذاكرة المتاحة.

**س: هل يمكن تخصيص ألوان الشرائح الفردية؟**  
ج: نعم، يمكن الوصول إلى كل `IPortion` عبر `chart.getChartData().getSeries().get_Item(0).getPortions()` وتعيين `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**س: كيف يمكنني تضمين ملف PPTX المُولد في تطبيق ويب؟**  
ج: بعد حفظ الملف، قم ببثه مباشرة إلى العميل باستخدام `HttpServletResponse` مع `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## الخلاصة

أنت الآن تمتلك وصفة كاملة وجاهزة للإنتاج **لإضافة مخطط إلى PowerPoint** عن طريق إنشاء مخطط Pie of Pie باستخدام Aspose.Slides for Java. جرّب عتبات انقسام مختلفة، صيغ التسميات، وأنماط الألوان لتتناسب مع إرشادات علامتك التجارية. بعد ذلك، استكشف أنواع مخططات أخرى—مثل الشريط المكدس أو الرادار—لتعزيز مجموعات الشرائح الآلية الخاصة بك.

---

**آخر تحديث:** 2026-07-17  
**تم الاختبار مع:** Aspose.Slides for Java 24.12  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [إنشاء مخطط ديناميكي Java – دروس مخططات PowerPoint لـ Aspose.Slides](/slides/java/charts-graphs/)
- [كيفية إضافة مخطط فطيرة إلى PowerPoint باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
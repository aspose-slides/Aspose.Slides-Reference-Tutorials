---
date: '2026-07-27'
description: تعلم كيفية إنشاء مخطط دونات Java باستخدام Aspose.Slides – دليل سريع لإعداد
  المكتبة، إضافة مخطط دونات قابل للتخصيص، تعديل حجم الفتحة، وحفظ العرض التقديمي.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: تعلم كيفية إنشاء مخطط دونات Java باستخدام Aspose.Slides – دليل سريع
  لإعداد المكتبة، إضافة مخطط دونات قابل للتخصيص، تعديل حجم الفتحة، وحفظ العرض التقديمي.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: إنشاء مخطط دونات Java – خطوة بخطوة مع Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: إنشاء مخطط دونات Java – خطوة بخطوة مع Aspose.Slides
url: /ar/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات الدونات في Java باستخدام Aspose.Slides للعروض التقديمية

## مقدمة
إنشاء عروض تقديمية جذابة بصريًا أمر ضروري لنقل المعلومات بفعالية. **Create doughnut chart java** هو طلب شائع عندما تحتاج إلى توضيح البيانات النسبية بمظهر حديث. في هذا البرنامج التعليمي ستتعلم كيفية إعداد Aspose.Slides for Java، بناء مخطط الدونات، تخصيص حجم الفتحة والألوان، وأخيرًا حفظ ملف العرض التقديمي. في النهاية ستحصل على نمط قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع Java يولد عروض PowerPoint تلقائيًا.

**ما ستتعلمه:**
- إعداد Aspose.Slides for Java
- إنشاء وتكوين مخططات الدونات في العروض التقديمية
- ضبط جمالية المخطط مثل حجم الفتحة
- حفظ العرض التقديمي مع المخطط الجديد الخاص بك

لنبدأ بإعداد بيئتنا!

## إجابات سريعة
- **أي مكتبة تُنشئ مخطط الدونات java؟** Aspose.Slides for Java.  
- **كم عدد أسطر الكود المطلوبة لإنشاء مخطط دونات أساسي؟** حوالي 8–10 أسطر بعد إنشاء العرض التقديمي.  
- **هل يمكنني تغيير حجم الفتحة؟** نعم، طريقة `setHoleSize(double)` تقبل قيمًا من 0 % إلى 100 %.  
- **ما صيغ الإخراج المدعومة؟** PPTX، PDF، XPS، PNG، JPEG والعديد من الصيغ الأخرى (أكثر من 50 إجمالًا).  
- **هل أحتاج إلى ترخيص للإنتاج؟** يُطلب ترخيص تجاري للاستخدام غير المحدود؛ نسخة تجريبية مجانية تعمل للتقييم.

## ما هو Aspose.Slides for Java؟
**Aspose.Slides for Java** هو واجهة برمجة تطبيقات مُدارة بالكامل تمكّن المطورين من إنشاء وتعديل وتحويل وعرض ملفات PowerPoint دون الحاجة إلى Microsoft Office. يدعم أكثر من 50 تنسيق ملف ويمكنه التعامل مع عروض تقديمية تحتوي على آلاف الشرائح مع الحفاظ على استهلاك الذاكرة منخفضًا.

## لماذا نستخدم مخططات الدونات في العروض التقديمية؟
مخططات الدونات تعرض علاقات الجزء إلى الكل مع إتاحة مساحة في المركز للتسميات أو الصور. يمكن لـ Aspose.Slides عرض مخططات الدونات حتى **500 شريحة في الدقيقة** على خادم عادي بسرعة 2.5 GHz، وتُعالج **عروض تقديمية متعددة المئات من الصفحات** دون تحميل الملف بالكامل إلى الذاكرة، مما يجعلها مثالية لحلول التقارير على نطاق واسع.

## المتطلبات المسبقة
قبل البدء، تأكد من استيفاء المتطلبات التالية:

### المكتبات المطلوبة والإصدارات
للعمل مع Aspose.Slides for Java، أدرجه في مشروعك عبر Maven أو Gradle، أو قم بتنزيله مباشرة.

#### متطلبات إعداد البيئة
- مجموعة تطوير Java (JDK) تعمل، ويفضل أن تكون الإصدار 8 أو أعلى.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

### المتطلبات المعرفية
الإلمام بـ Java ومفاهيم البرمجة الأساسية مفيد. المعرفة الأساسية بـ Maven أو Gradle ستساعد في تبسيط عملية الإعداد.

## إعداد Aspose.Slides for Java
يمكن دمج Aspose.Slides في مشروعك بعدة طرق:

**Maven:**  
أضف هذه الاعتمادية إلى ملف `pom.xml` الخاص بك:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
أدرج هذا في ملف `build.gradle` الخاص بك:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**تحميل مباشر:**  
بدلاً من ذلك، قم بتنزيل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **Free Trial:** ابدأ بتنزيل نسخة تجريبية لاستكشاف ميزات Aspose.Slides.  
- **Temporary License:** احصل على ترخيص مؤقت للحصول على وظائف موسعة دون قيود.  
- **Purchase:** للاستخدام المستمر، يلزم شراء ترخيص.

بعد إعداد المكتبة وتهيئة بيئتك، لننتقل إلى تنفيذ مخطط الدونات الخاص بنا.

## كيفية إنشاء مخطط الدونات في Java؟
حمّل كائن `Presentation` جديد، أضف مخطط دونات إلى شريحة، حدد حجم الفتحة، واحفظ الملف – كل ذلك في عدد قليل من استدعاءات API البسيطة. يمنحك هذا النهج تحكمًا كاملاً في بيانات المخطط ومظهره وتنسيق التصدير، ويعمل دون الحاجة إلى تثبيت Microsoft PowerPoint على الخادم.

### تهيئة كائن Presentation
فئة `Presentation` هي الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
هذه الخطوة تنشئ عرضًا تقديميًا فارغًا يمكنك من خلاله إضافة شرائح وأشكال ومخططات.

### إضافة مخطط الدونات إلى الشريحة
`ISlide` هو الواجهة لشريحة واحدة؛ يمكنك استرجاع الشريحة الأولى أو إضافة شريحة جديدة.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
طريقة `addChart` تنشئ مخطط دونات؛ المعلمات تحدد موقعه (X, Y) وحجمه (العرض، الارتفاع) على الشريحة.

### ضبط حجم فتحة الدونات
`Chart` يتيح `setHoleSize(double)` للتحكم في نصف القطر الداخلي كنسبة مئوية من نصف قطر المخطط.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
ضبط حجم الفتحة إلى 90 % يجعل المخطط يبدو كدائرة شبه كاملة، وهو مفيد عندما تريد إبراز القطاعات الخارجية.

### حفظ العرض التقديمي
`presentation.save(String, SaveFormat)` يكتب الملف إلى القرص بالتنسيق المختار.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
يحفظ المثال النتيجة كملف `DoughnutHoleSize_out.pptx`، لكن يمكنك أيضًا اختيار PDF أو PNG أو أي من الصيغ المدعومة التي تزيد عن 50 صيغة.

### تنظيف الموارد
استدعاء `presentation.dispose()` يحرر الموارد الأصلية ويمنع تسرب الذاكرة، وهو مهم خاصة في تطبيقات الخادم التي تعمل لفترات طويلة.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## تطبيقات عملية
مخططات الدونات متعددة الاستخدامات. إليك بعض السيناريوهات التي تتألق فيها:
1. **Budget Allocation:** عرض كيفية توزيع الميزانية عبر الأقسام.  
2. **Survey Results:** تصور الردود على الأسئلة ذات الإجابات المتعددة.  
3. **Website Traffic Sources:** إظهار نسبة الزيارات القادمة من قنوات مختلفة (عضوية، مدفوعة، إحالة، إلخ).

## اعتبارات الأداء
عند العمل مع Aspose.Slides، ضع في اعتبارك هذه النصائح لتحقيق الأداء الأمثل:
- قم بتحرير كائنات `Presentation` بمجرد الانتهاء لتفريغ الذاكرة الأصلية.  
- استخدم التدفقات (`FileInputStream`، `ByteArrayOutputStream`) لمجموعات البيانات الكبيرة لتجنب تحميل الملفات بالكامل إلى الذاكرة.  
- أعد استخدام كائنات المخطط عند إنشاء العديد من الشرائح في حلقة لتقليل عبء إنشاء الكائنات.

## المشكلات الشائعة والحلول
- **Error while saving:** تحقق من وجود دليل الإخراج وأن التطبيق يمتلك أذونات الكتابة.  
- **Missing chart data:** تأكد من ملء مجموعة `ChartData` للمخطط قبل استدعاء `setHoleSize`.  
- **Memory spikes:** بالنسبة للعروض التي تحتوي على آلاف الشرائح، فعّل `Presentation.setSlideSize` إلى حجم أصغر وتخلص من الشرائح الوسيطة بسرعة.

## الأسئلة المتكررة

**Q: هل يمكنني تعديل ألوان شرائح مخطط الدونات؟**  
A: نعم. استخدم `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` ثم حدد اللون RGB المطلوب.

**Q: كيف يمكنني إضافة تسميات البيانات إلى المخطط؟**  
A: استدعِ `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` لعرض القيمة داخل كل شريحة.

**Q: هل يمكن حفظ المخططات بصيغ غير PPTX؟**  
A: بالطبع. يدعم Aspose.Slides صيغ PDF، XPS، PNG، JPEG، TIFF، والعديد من الصيغ الأخرى—أكثر من 50 صيغة إجمالًا.

**Q: ماذا أفعل إذا واجهت استثناءً أثناء تحميل عرض تقديمي كبير؟**  
A: استخدم مُنشئ `Presentation` الذي يقبل تدفقًا وقم بتمكين `loadOptions.setLoadFormat(LoadFormat.Pptx)` لتدفق الملف وتقليل استهلاك الذاكرة.

**Q: هل يمكنني أتمتة تحديثات المخطط باستخدام مصادر بيانات حية؟**  
A: نعم. استخرج البيانات من قاعدة بيانات أو واجهة REST API، حدّث مجموعة `ChartData`، واستدعِ `chart.refresh()` قبل حفظ العرض التقديمي.

## الموارد
- **Documentation:** استكشف مراجع API التفصيلية على [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** احصل على أحدث نسخة من المكتبة من [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** للحصول على وصول كامل، اشترِ ترخيصًا عبر [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** جرّب Aspose.Slides بنسخة تجريبية مجانية متاحة على صفحة التحميل الخاصة بهم.  
- **Temporary License:** احصل على ترخيص مؤقت لاختبار موسع دون قيود.  
- **Support:** هل لديك أسئلة؟ زر [Aspose Forum](https://forum.aspose.com/c/slides/11) للحصول على المساعدة.

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [كيفية إنشاء مخطط في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
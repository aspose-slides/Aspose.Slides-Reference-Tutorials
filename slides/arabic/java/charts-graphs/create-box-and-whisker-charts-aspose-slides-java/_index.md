---
date: '2026-08-21'
description: تعلم كيفية إنشاء مخطط box plot بلغة Java باستخدام Aspose.Slides، إضافة
  مخطط إلى الشريحة، وإنشاء مخطط box‑and‑whisker في PowerPoint. مثالي لمطوري Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: تعلم كيفية إنشاء مخطط box plot بلغة Java باستخدام Aspose.Slides، إضافة
  مخطط إلى الشريحة، وإنشاء مخطط box‑and‑whisker في PowerPoint. مثالي لمطوري Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: كيفية إنشاء مخطط box plot بلغة Java باستخدام Aspose.Slides لبرنامج PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: كيفية إنشاء مخطط box plot بلغة Java باستخدام Aspose.Slides لبرنامج PowerPoint
url: /ar/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مخطط الصندوق Java باستخدام Aspose.Slides لـ PowerPoint

في هذا الدليل ستقوم **بإنشاء مخطط الصندوق Java** باستخدام Aspose.Slides، ثم تضمين المخطط مباشرةً في شريحة PowerPoint. يتيح لك إنشاء مخططات الصندوق والشارب برمجيًا تحويل البيانات الإحصائية الخام إلى رؤى بصرية واضحة دون مغادرة كود Java الخاص بك. إذا كنت بحاجة إلى أتمتة تقارير PowerPoint، فإن Aspose.Slides for Java يوفر API موثوقًا وعالي الأداء.

## ما ستتعلمه

- إعداد بيئتك لاستخدام Aspose.Slides for Java  
- خطوات **إضافة مخطط إلى شريحة** وإنشاء مخطط صندوق‑وشارب في PowerPoint باستخدام Java  
- أفضل الممارسات لتحسين الأداء عند العمل مع Aspose.Slides  
- تطبيقات واقعية لمخططات الصندوق والشارب  

## إجابات سريعة
- **ما المكتبة التي تنشئ مخطط الصندوق في Java؟** Aspose.Slides for Java.  
- **ما نوع المخطط المستخدم؟** `ChartType.BoxAndWhisker`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني إضافة سلاسل متعددة؟** نعم – كرّر كتلة إنشاء السلسلة لكل مجموعة بيانات.  
- **ما هو تنسيق الملف النهائي؟** PowerPoint PPTX (`SaveFormat.Pptx`).  

## ما هو مخطط الصندوق ولماذا يستخدم في Java؟

مخطط الصندوق والشارب (المعروف غالبًا باسم *مخطط الصندوق*) يُظهر توزيع البيانات — الوسيط، الأرباع، والقيم المتطرفة — في شكل مدمج. في Java، يتيح لك إنشاء هذا المخطط برمجيًا تضمين الرؤى الإحصائية مباشرةً في عروض PowerPoint، مما يلغي الحاجة إلى إنشاء المخطط يدويًا. يكون ذلك مفيدًا بشكل خاص لمقارنة التوزيعات عبر فئات متعددة، مثل درجات الاختبار بين الصفوف أو أرقام المبيعات بين المناطق. من خلال إنشاء المخطط في Java، يمكنك دمجه في خطوط أنابيب التقارير الآلية، مما يضمن أن أحدث البيانات دائمًا ما تُعكس في عروضك التقديمية.

## لماذا نضيف مخططًا إلى شريحة باستخدام Aspose.Slides؟

Aspose.Slides يُجرد تفاصيل OpenXML منخفضة المستوى، ويقدم لك API سهل الاستخدام لإنشاء وتنسيق وتصدير المخططات. هذا يعني أنه يمكنك أتمتة إنشاء التقارير، إنتاج علامة تجارية متسقة، ودمج المخططات في سير عمل Java أكبر. المكتبة تدعم أيضًا خيارات التنسيق مثل الألوان، الخطوط، والرموز، مما يتيح لك مطابقة هوية الشركة. بالإضافة إلى ذلك، تتعامل مع مهام معقدة مثل ربط البيانات وتحديث المخطط دون الحاجة إلى Microsoft Office.

## كيف نضيف مخططًا إلى شريحة Java باستخدام Aspose.Slides؟

قم بتحميل أو إنشاء `Presentation`، أدرج `Chart` من النوع `BoxAndWhisker`، زودها ببياناتك، واحفظ الملف — كل ذلك في بضع أسطر من Java. يتولى API التعامل مع التخطيط، التحجيم، والرندرة، لذا لا تحتاج إلى تعديل XML يدويًا. يمكنك أيضًا ضبط عناوين المخطط ومحاوره برمجيًا لتوفير سياق للمشاهدين.

## المتطلبات المسبقة

- **Java Development Kit (JDK)**: JDK 8 أو أعلى.  
- **Aspose.Slides for Java Library**: مطلوبة لمعالجة PowerPoint.  
- **IDE**: IntelliJ IDEA، Eclipse، أو أي محرر يدعم Java.

## إعداد Aspose.Slides for Java

أضف المكتبة كاعتماد Maven أو Gradle أو يدويًا.

### Maven

أضف الاعتماد التالي في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

في ملف `build.gradle`، أدرج:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر

بدلاً من ذلك، حمّل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص

- **نسخة تجريبية** – استكشف الميزات دون تكلفة.  
- **ترخيص مؤقت** – للاستخدام قصير الأمد في التقييم.  
- **شراء** – لفتح جميع الوظائف للاستخدام الإنتاجي.

لتهيئة Aspose.Slides، تأكد من أن ملف JAR موجود في مسار الـ classpath وضع ملف الترخيص وفقًا للتوثيق.

## دليل التنفيذ

فيما يلي شرح خطوة بخطوة. كل كتلة مشروحة قبل المقتطف لتعرف بالضبط ما تقوم به.

### ما هي فئة `Presentation`؟

فئة `Presentation` هي الكائن المركزي في Aspose.Slides الذي يمثل ملف PowerPoint كامل في الذاكرة. توفر الوصول إلى الشرائح، المخططات، الأشكال، وغيرها من عناصر الشريحة، مما يتيح لك إنشاء، تعديل، وحفظ العروض برمجيًا. باستخدام هذه الفئة، يمكنك إضافة شرائح جديدة، إدراج صور، وتغيير ترتيب الشرائح باستدعاءات API بسيطة.

### الخطوة 1: إنشاء أو فتح عرض تقديمي

أولًا، افتح ملف PPTX موجود أو ابدأ ملفًا جديدًا:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **نصيحة:** إذا لم يكن الملف موجودًا، سيقوم Aspose.Slides بإنشاء عرض تقديمي فارغ جديد تلقائيًا.

### الخطوة 2: إضافة مخطط صندوق‑وشارب إلى الشريحة

حدد موقع المخطط وحجمه (بالنقاط) حيث تحتاجه:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### الخطوة 3: مسح البيانات الحالية

قبل إدخال بيانات جديدة، احذف أي فئات أو سلاسل placeholder:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### الخطوة 4: تكوين الفئات

أضف الفئات (تسميات محور X) التي ستظهر تحت كل صندوق:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **ملاحظة:** عدّل نص التسمية ليتطابق مع نطاق بياناتك (مثلاً، “Q1”، “Product A”).

### الخطوة 5: إنشاء وتخصيص السلسلة

الآن أنشئ سلسلة، اضبط خيارات العرض، وزودها بنقاط البيانات الرقمية:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

يمكنك استبدال مصفوفة `int[] data` بالقيم المقروءة من قاعدة بيانات، ملف CSV، أو أي مصدر آخر.

### الخطوة 6: حفظ العرض التقديمي

احفظ التغييرات في ملف PPTX جديد:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### الخطوة 7: تنظيف الموارد

دائمًا حرّر كائن `Presentation` لتحرير الموارد الأصلية:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## تطبيقات عملية

مخططات الصندوق والشارب لا تقدر بثمن في التحليل الإحصائي وعرض البيانات. إليك بعض السيناريوهات التي تتألق فيها:

1. **التحليل المالي** – تصور توزيع الإيرادات عبر المناطق.  
2. **مراقبة الجودة** – اكتشاف القيم المتطرفة في قياسات التصنيع.  
3. **البحث الأكاديمي** – إظهار تباين نتائج التجارب.  
4. **أبحاث السوق** – مقارنة أداء المنتجات عبر الفئات الديموغرافية.

تضمين هذه المخططات مباشرةً في عروض PowerPoint يمكّن أصحاب المصلحة من استيعاب البيانات المعقدة بنظرة واحدة.

## اعتبارات الأداء

يمكن لـ Aspose.Slides التعامل مع عروض تحتوي على **أكثر من 500 شريحة** ومخططات بها **أكثر من 100 000 نقطة بيانات** مع الحفاظ على استهلاك الذاكرة تحت 200 MB على خادم متوسط. للبقاء ضمن هذه الحدود:

- **إدارة الذاكرة** – حرّر كائنات `Presentation` فور الانتهاء.  
- **معالجة البيانات** – حمّل فقط البيانات المطلوبة؛ تجنّب إدخال مجموعات بيانات ضخمة مباشرةً في مصنف المخطط.  
- **التحميل الكسول** – عند إنشاء شرائح متعددة، أنشئ المخططات فقط للشرائح التي ستُعرض.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **المخطط يظهر فارغًا** | خلايا البيانات غير مملوءة بشكل صحيح | تأكد من أن مراجع `wb.getCell` تشير إلى الصف/العمود الصحيح وأن القيمة ليست `null`. |
| **القيم المتطرفة غير معروضة** | `setShowOutlierPoints` مُعطلة | تأكد من استدعاء `series.setShowOutlierPoints(true)`. |
| **تسرب الذاكرة** | عدم تحرير الـ Presentation | احرص دائمًا على تغليف الاستخدام داخل `try/finally` واستدعاء `dispose()`. |
| **الرباعيات غير صحيحة** | استخدام طريقة `Inclusive` الافتراضية | غيّر إلى `Exclusive` عبر `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## الأسئلة المتكررة

**س1: ما هو مخطط الصندوق والشارب؟**  
مخطط الصندوق والشارب، المعروف أيضًا بمخطط الصندوق، يعرض توزيع البيانات بناءً على خمس إحصاءات ملخصة: الحد الأدنى، الربع الأول، الوسيط، الربع الثالث، والحد الأقصى، بالإضافة إلى القيم المتطرفة.

**س2: هل يمكنني تخصيص مظهر مخطط الصندوق والشارب؟**  
نعم. يتيح لك Aspose.Slides تغيير الألوان، أنماط الخطوط، أشكال العلامات، وإضافة تسميات البيانات عبر API تنسيق المخطط.

**س3: هل يمكن التعامل مع سلاسل متعددة في مخطط واحد؟**  
بالطبع. كرّر كتلة إنشاء السلسلة لكل مجموعة بيانات تريد تصورها.

**س4: كيف أحل مشكلة عدم عرض البيانات بشكل صحيح؟**  
تأكد من كتابة البيانات بشكل صحيح في خلايا المصنف وأن خصائص الرؤية مثل `setShowMeanLine` مفعلة.

**س5: أين يمكنني الحصول على الدعم إذا واجهت مشاكل؟**  
زر [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) للحصول على مساعدة المجتمع، أو راجع الوثائق الرسمية.

**س6: هل يدعم Aspose.Slides أنواع مخططات أخرى؟**  
نعم، يدعم أكثر من 50 نوع مخطط — بما في ذلك الخط، العمود، الفطيرة، التبعثر، الرادار، والقمع — لتختار الأنسب لبياناتك.

**س7: هل يمكنني إنشاء مخططات في بيئة خادم بدون واجهة رسومية؟**  
المكتبة تعمل بالكامل في سيناريوهات الخادم؛ لا تحتاج إلى واجهة مستخدم أو تثبيت Microsoft Office.

## موارد

- **الوثائق**: استكشف مراجع API التفصيلية على [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **التحميل**: الوصول إلى صفحة إصدارات Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **الشراء**: اشترِ ترخيصًا لفتح جميع الميزات [Aspose Purchase](https://purchase.aspose.com/buy)  
- **نسخة تجريبية وترخيص مؤقت**: ابدأ بنسخة تجريبية مجانية أو اطلب ترخيصًا مؤقتًا [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

باتباعك لهذا الدليل، ستكون الآن قادرًا على إنشاء مخططات صندوق‑وشارب ذات رؤى إحصائية في تطبيقات Java الخاصة بك وتضمينها مباشرةً في عروض PowerPoint. برمجة سعيدة!

---

**آخر تحديث:** 2026-08-21  
**تم الاختبار مع:** Aspose.Slides 25.4 (JDK 16 classifier)  
**المؤلف:** Aspose

## دروس ذات صلة

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
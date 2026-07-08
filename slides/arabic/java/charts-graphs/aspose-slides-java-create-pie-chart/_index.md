---
date: '2026-07-08'
description: تعلم كيفية إضافة مخططات دائرية إلى عروض PowerPoint باستخدام Aspose.Slides
  for Java. اتبع هذا الدليل خطوة بخطوة لإنشاء وتخصيص مخططات دائرية احترافية.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: إضافة مخطط دائري إلى PowerPoint باستخدام Aspose.Slides for Java. يوضح
  هذا البرنامج التعليمي كيفية إنشاء وتخصيص المخططات الدائرية برمجيًا، وهو مثالي للتقارير
  الآلية.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: إضافة مخطط دائري إلى PowerPoint باستخدام Aspose.Slides for Java – دليل سريع
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: كيفية إضافة مخطط دائري إلى PowerPoint باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة مخطط دائري PowerPoint باستخدام Aspose.Slides for Java

## مقدمة

إذا كنت بحاجة إلى **إضافة مخطط دائري PowerPoint** إلى الشرائح دون فتح PowerPoint يدويًا، فأنت في المكان الصحيح. في هذا الدليل سنستعرض إعداد Aspose.Slides for Java، وإنشاء مخطط دائري، وتخصيص كل شريحة—مثالي للتقارير الآلية، ولوحات التحكم، أو العروض التقديمية المخصصة. في النهاية ستحصل على مقتطف Java قابل لإعادة الاستخدام يولد ملف PowerPoint بمخطط دائري مصقول في ثوانٍ.

### أسئلة سريعة
- **ما المكتبة التي تنشئ المخطط؟** Aspose.Slides for Java (أحدث إصدار).  
- **هل يمكن تشغيله بدون واجهة؟** نعم—لا يلزم تثبيت Office.  
- **ما نسخة Java المثالية؟** JDK 16+ لأفضل أداء وتحسينات جمع القمامة.  
- **كيف أقوم بتفجير شريحة؟** استدعِ `setExplosion` على `IDataPoint` وحدد إزاحة بالبكسل.  
- **هل أحتاج إلى ترخيص للإنتاج؟** النسخة التجريبية تعمل للتطوير؛ الترخيص الدائم يزيل جميع قيود التقييم.

## لماذا إضافة مخطط دائري PowerPoint باستخدام Aspose.Slides for Java؟

يمكنك إنشاء تقارير بصرية محدثة مباشرةً من خدمات الواجهة الخلفية الخاصة بك، مما يلغي أخطاء النسخ واللصق اليدوية ويضمن تنسيقًا متسقًا مع العلامة التجارية. يدعم Aspose.Slides **أكثر من 70 نوعًا من المخططات** ويمكنه معالجة العروض التقديمية التي تحتوي على **أكثر من 10,000 شريحة** دون تحميل الملف بالكامل إلى الذاكرة، مما يجعله مثاليًا للأتمتة على نطاق واسع.

## المتطلبات المسبقة

- **Aspose.Slides for Java** – يشير الدليل إلى الإصدار 25.4 (الأحدث وقت الكتابة).  
- **Java Development Kit** – يوصى بـ JDK 16 أو أحدث.  
- **Maven** أو **Gradle** لإدارة التبعيات.  

## إعداد Aspose.Slides for Java

### Maven
أضف هذه التبعية إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
ضمن التالي في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، قم بتنزيل أحدث إصدار مباشرةً من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### الترخيص
لاستخدام Aspose.Slides بدون قيود:

- ابدأ بـ **نسخة تجريبية مجانية** لتقييم الـ API.  
- اطلب **ترخيصًا مؤقتًا** للاختبار الموسع على صفحة [الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).  
- اشترِ اشتراكًا كاملًا عبر [صفحة الشراء](https://purchase.aspose.com/buy).

## كيفية إضافة مخطط دائري PowerPoint باستخدام Aspose.Slides for Java

حمّل عرض تقديمي جديد، أدرج مخططًا دائريًا، واحفظ الملف—كل ذلك في ثلاث خطوات مختصرة. هذا النمط يعمل مع أي مجموعة بيانات ويمكن تغليفه داخل حلقة لتوليد العشرات من الشرائح تلقائيًا. النهج خفيف الوزن، يتطلب فقط بضع أسطر من الشيفرة ولا يحتاج إلى موارد خارجية، مما يجعله مناسبًا لكل من الأدوات الصغيرة والوظائف الدفعية الكبيرة.

### الخطوة 1: تهيئة العرض التقديمي
تمثل الفئة `Presentation` ملف PowerPoint واحد في الذاكرة. إنشاء نسخة يمنحك مجموعة شرائح جديدة وفارغة للعمل معها.
```java
Presentation pres = new Presentation();
```

### الخطوة 2: إضافة المخطط الدائري
أدرج مخططًا دائريًا على الشريحة الأولى. الإحداثيات (50, 50) والحجم (600 × 400) يتناسبان مع تخطيط قياسي 16:9 ويتركان مساحة للعناوين.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### الخطوة 3: حفظ العرض التقديمي
اكتب العرض التقديمي إلى القرص. استبدل `YOUR_OUTPUT_DIRECTORY` بالمجلد الذي تريد حفظ الملف فيه.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### الخطوة 4: تنظيف الموارد
قم بتحرير كائن `Presentation` لتحرير الموارد الأصلية وتجنب تسرب الذاكرة.
```java
if (pres != null) pres.dispose();
```

## كيفية تخصيص انفجار نقطة البيانات واللون؟

حمّل المخطط، حدد نقطة البيانات المستهدفة، ثم طبّق إزاحة انفجار ولون تعبئة صلبة. هذا يجعل الشريحة بارزة للتأكيد. تساعد هذه التعديلات على جذب انتباه الجمهور إلى القيم الحرجة وتحسين قابلية قراءة المخطط بشكل عام.

### الخطوة 1: تحميل عرض تقديمي موجود (أو إعادة استخدام العرض الذي أنشأته للتو)
يقوم كائن `Presentation` بتحميل ملف PowerPoint موجود إلى الذاكرة، مما يتيح لك تعديل محتوياته.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### الخطوة 2: الوصول إلى المخطط ونقطة البيانات المستهدفة
تمثل الواجهة `IDataPoint` نقطة بيانات فردية (شريحة) داخل سلسلة المخطط.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### الخطوة 3: تطبيق الانفجار واللون
`setExplosion(int)` يحدد المسافة، بالبكسل، التي تُبعد الشريحة عن مركز المخطط. افصل الشريحة بصريًا باستخدام `setExplosion(20)` وغير تعبئتها إلى اللون الأزرق باستخدام `setFillType(FillType.Solid)` و `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### الخطوة 4: حفظ وتحرير
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## تطبيقات عملية
- **تقارير المبيعات:** إبراز المنتجات الأكثر مبيعًا باستخدام شرائح منفجرة.  
- **تحليل الميزانية:** تخصيص ألوان مميزة للأقسام للمقارنة البصرية السريعة.  
- **شرائح تعليمية:** تقسيم المفاهيم المعقدة إلى أقسام مخطط سهلة الفهم.  

## اعتبارات الأداء
- **تحرير الكائنات** فورًا لتجنب تسرب الذاكرة، خاصةً عند إنشاء العديد من الشرائح في حلقة.  
- **مراقبة استخدام الذاكرة** للعروض الكبيرة؛ استخدم نسخة `Save` التي تقبل `OutputStream` لتدفق البيانات والحفاظ على بصمة الذاكرة منخفضة.  
- التزم بـ **JDK 16+** للاستفادة من أحدث تحسينات جمع القمامة، والتي يمكن أن تقلل وقت المعالجة بنسبة تصل إلى 30 % لعروض مكونة من 1,000 شريحة.

## الخلاصة
أصبح لديك الآن سير عمل كامل وجاهز للإنتاج **لإضافة مخططات دائرية PowerPoint** باستخدام Aspose.Slides for Java. جرب مسافات انفجار مختلفة، ألوان، ومجموعات بيانات لتتناسب مع علامتك التجارية. عندما تكون مستعدًا، استكشف أنواع مخططات أخرى—شريطية، خطية، أو مبعثرة—لبناء لوحة تحكم تحليلية كاملة داخل PowerPoint.

## الأسئلة المتكررة

**س: ما هي أكبر ميزة لاستخدام Aspose.Slides for Java؟**  
ج: يتيح لك إنشاء وتحرير وعرض ملفات PowerPoint برمجيًا دون الحاجة إلى تثبيت Microsoft Office، ويدعم أكثر من 70 نوعًا من المخططات وأكثر من 100 صيغة ملف.

**س: هل يمكنني إنشاء ملف PowerPoint من الصفر؟**  
ج: نعم، أنشئ كائن `Presentation`، أضف شرائح أو مخططات أو أشكال، ثم استدعِ `save`—كل ذلك باستخدام شفرة Java صافية.

**س: كيف أقوم بتفجير شريحة دائرية محددة؟**  
ج: احصل على `IDataPoint` الخاصة بالشريحة واستدعِ `setExplosion(pixelOffset)`. تحدد الإزاحة مدى بُعد الشريحة عن المركز.

**س: هل هناك حد لعدد الشرائح التي يمكنني إنشاؤها؟**  
ج: يمكن لـ Aspose.Slides معالجة عروض تقديمية تصل إلى **10,000 شريحة** في ملف واحد، بشرط أن تقوم بتدفق الإخراج لتجنب تحميل كل شيء في الذاكرة.

**س: أين يمكنني العثور على أمثلة متقدمة لتخصيص المخططات؟**  
ج: راجع [توثيق Aspose.Slides الرسمي](https://reference.aspose.com/slides/java/) للحصول على مراجع API مفصلة ومشروعات نموذجية.

## الموارد
- **التوثيق:** [مستندات Aspose.Slides Java](https://reference.aspose.com/slides/java/)  
- **تنزيل المكتبة:** [إصدارات Aspose](https://releases.aspose.com/slides/java/)  
- **شراء الترخيص:** [شراء Aspose.Slides](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية:** [جرب Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت:** [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)  
- **منتدى الدعم:** [دعم Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-07-08  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [تحريك المخططات في PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [إنشاء والتحقق من تخطيطات المخططات في PowerPoint باستخدام Aspose.Slides for Java | دليل محسّن لتحسين محركات البحث](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
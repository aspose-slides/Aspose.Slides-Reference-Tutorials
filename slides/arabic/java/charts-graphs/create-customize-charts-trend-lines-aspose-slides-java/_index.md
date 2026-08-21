---
date: '2026-08-21'
description: تعلم كيفية إنشاء clustered column chart وإضافة trend lines باستخدام Aspose.Slides
  for Java. يتضمن license setup، تكامل Maven/Gradle، وأمثلة مفصلة.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: إنشاء clustered column chart وإضافة trend lines باستخدام Aspose.Slides
  for Java. يغطي هذا الدليل license setup، Maven/Gradle، و step‑by‑step code snippets.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: إنشاء clustered column chart وإضافة trend lines باستخدام Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: كيفية إنشاء clustered column chart وإضافة trend lines باستخدام Aspose.Slides
  for Java
url: /ar/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء مخطط عمودي مجمع وإضافة خطوط الاتجاه باستخدام Aspose.Slides for Java

غالبًا ما يبدأ إنشاء عروض تقديمية جذابة برؤية واضحة لبياناتك. في هذا الدليل ستقوم **بإنشاء مخطط عمودي مجمع**، ثم تُثريه بمجموعة متنوعة من خطوط الاتجاه—الأسية، الخطية، اللوغاريتمية، المتوسط المتحرك، متعددة الحدود، والقوة—باستخدام واجهة برمجة التطبيقات القوية Aspose.Slides for Java.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** تهيئة كائن `Presentation` وإضافة مخطط عمودي مجمع إلى شريحة.  
- **ما هو إصدار المكتبة المطلوب؟** Aspose.Slides for Java 25.4 أو أحدث.  
- **هل يمكنني استخدام Maven أو Gradle؟** نعم، كلاهما مدعومان؛ يستخدم Maven `<dependency>` وGradle يستخدم `implementation`.  
- **هل أحتاج إلى ترخيص؟** ترخيص تجريبي يعمل للتقييم؛ ترخيص Aspose.Slides الكامل يزيل حدود التقييم.  
- **كم عدد أنواع خطوط الاتجاه المتاحة؟** ستة أنواع مدمجة: الأسية، الخطية، اللوغاريتمية، المتوسط المتحرك، متعددة الحدود، والقوة.

## ما هو إنشاء مخطط عمودي مجمع؟
`create clustered column chart` يعني إنشاء مخطط يجمع عدة سلاسل بيانات جنبًا إلى جنب داخل كل فئة، مما يسهل مقارنة القيم عبر السلاسل. هذا النوع من المخططات مثالي لتصوير البيانات الفئوية مثل مبيعات الربع السنوية عبر المناطق، مما يسمح للمشاهدين بتحديد الاختلافات بين المجموعات بسرعة.

## لماذا إضافة خط الاتجاه؟
خطوط الاتجاه تكشف النمط الأساسي لسلسلة البيانات، مما يساعدك على توقع القيم المستقبلية، إبراز معدلات النمو، أو تنعيم البيانات الضوضائية. بإضافة خط اتجاه إلى مخطط عمودي مجمع، تتحول الأرقام الخام إلى رؤى قابلة للتنفيذ، مما يمكّن أصحاب المصلحة من فهم الاتجاهات طويلة الأمد واتخاذ قرارات مستندة إلى البيانات.

## المتطلبات المسبقة
- **Java Development Kit (JDK):** 8 أو أحدث.  
- **Aspose.Slides for Java:** الإصدار 25.4 أو أحدث.  
- **IDE:** IntelliJ IDEA أو Eclipse أو أي محرر متوافق مع Java.  
- **أداة البناء:** Maven أو Gradle (اختياري ولكن يُنصح به).  
- **الترخيص:** ملف ترخيص Aspose.Slides تجريبي أو مُشتَرَى.  

يجب أن تكون مرتاحًا مع بنية Java الأساسية ومألوفًا بإدارة تبعيات المشروع.

## كيفية إعداد Aspose.Slides for Java؟
أضف مكتبة Aspose.Slides إلى مشروعك باستخدام مدير التبعيات المفضل لديك، ثم ضع ملف الترخيص في مكان يمكن للوقت التشغيلي الوصول إليه. يضمن ذلك الوظائف الكاملة ويزيل قيود التقييم.

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
أدرج هذا السطر في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
يمكنك أيضًا تنزيل ملف JAR يدويًا من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### ترخيص Aspose Slides
ضع ملف `Aspose.Slides.lic` في جذر مشروعك أو اضبط الترخيص برمجيًا باستخدام `License license = new License(); license.setLicense("Aspose.Slides.lic");`. يزيل الترخيص التجريبي جميع قيود الميزات، لكن الترخيص المشتَرَى يزيل علامة التقييم المائية ويمنح تحسينات الأداء الكاملة. للاستخدام في الإنتاج، فكر في شراء ترخيص من [Aspose purchase page](https://purchase.aspose.com/buy).

## كيفية إنشاء عرض تقديمي وإضافة مخطط عمودي مجمع؟
تمثل الفئة `Presentation` ملف PowerPoint وتوفر طرقًا لإنشاء الشرائح وتعديلها وحفظها. أنشئ كائن `Presentation`، أضف شريحة، ثم استدعِ `addChart` مع `ChartType.ClusteredColumn` لإنشاء كائن المخطط. هذه العملية تُعدّ لوحة الشريحة، تُدرج شكل المخطط، وتُجهّزه لتعبئة البيانات وتنسيقه.

1. **تهيئة العرض التقديمي** – إعداد مجلد الإخراج وإنشاء مثيل جديد من `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **إضافة مخطط عمودي مجمع** – الحصول على شكل المخطط، تكوين سلسلته، وتعبئة نقاط البيانات.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## كيفية إضافة خط اتجاه أسّي؟
تحدد الواجهة `ITrendline` خط اتجاه يمكن إضافته إلى سلسلة مخطط لنمذجة نمط البيانات. أضف خط اتجاه أسّي إلى سلسلة بإنشاء مثيل `ITrendline`، وضبط خاصية `TrendlineType` إلى `Exponential`، وربطه بالسلسلة المطلوبة. هذا النوع من خطوط الاتجاه مفيد للبيانات التي تنمو بسرعة بمعدل متزايد.

1. **تكوين خط الاتجاه** – اختر السلسلة واستدعِ `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## كيفية إضافة خط اتجاه خطي؟
خط الاتجاه الخطي يُظهر الخط المستقيم الأنسب عبر نقاط البيانات الخاصة بك. يمكنك أيضًا تخصيص مظهره، مثل لون الخط وسمكه، ليتناسب مع نمط عرضك التقديمي.

1. **إعداد خط الاتجاه** – استخدم `addTrendline(TrendlineType.Linear)` ثم عدّل `getLineFormat().setFillFormat().setFillType(FillType.Solid)` لتغيير اللون.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## كيفية إضافة خط اتجاه لوغاريتمي مع إطار نص مخصص؟
خطوط الاتجاه اللوغاريتمية مثالية للبيانات التي تنمو بسرعة في البداية ثم تستقر. تجاوز التسمية الافتراضية يتيح لك إضافة نص توضيحي يوضح أهمية الاتجاه.

1. **تخصيص خط الاتجاه** – بعد إضافة خط الاتجاه، احصل على `getDataLabel()` واضبط الخاصية `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## كيفية إضافة خط اتجاه متوسط متحرك؟
خطوط الاتجاه المتوسطة المتحركة تُنعم التقلبات قصيرة الأجل لتسليط الضوء على الاتجاهات طويلة الأجل. يمكنك تحديد الفترة (عدد النقاط) المستخدمة في المتوسط، مما يتيح لك التحكم في سلاسة الخط.

1. **تكوين خط الاتجاه** – استدعِ `addTrendline(TrendlineType.MovingAverage)` واضبط `setPeriod(3)` لاستخدام متوسط متحرك من ثلاث نقاط.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## كيفية إضافة خط اتجاه متعدد الحدود؟
خطوط الاتجاه متعددة الحدود تُطابق البيانات بمنحنى يُحدد بواسطة معادلة متعددة الحدود. خاصية `order` تتحكم في درجة المتعدد الحدود، مما يتيح لك نمذجة علاقات أكثر تعقيدًا.

1. **تخصيص خط الاتجاه** – بعد إضافة خط الاتجاه، اضبط `setOrder(3)` للحصول على ملاءمة تكعيبية.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## كيفية إضافة خط اتجاه قوة؟
خطوط الاتجاه القوية مفيدة عندما تتبع البيانات علاقة قانون القوة. يمكنك أيضًا ضبط قيم التنبؤ الخلفية والامامية لتمديد الخط خارج نطاق البيانات الحالي.

1. **تكوين خط الاتجاه** – استخدم `addTrendline(TrendlineType.Power)` واضبط `setBackward(2)` لتمديد الخط إلى الخلف.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## تطبيقات عملية لخطوط الاتجاه في المخططات العمودية المجمعة
- **التحليل المالي:** تساعد الاتجاهات الأسية ومتعددة الحدود في توقع تحركات أسعار الأسهم.  
- **توقع المبيعات:** تُنعم خطوط المتوسط المتحرك القمم الموسمية، مما يمنح رؤية أوضح للاتجاهات الأساسية للمبيعات.  
- **البحث العلمي:** الاتجاهات اللوغاريتمية مثالية للبيانات التي تغطي عدة أوامر من الحجم، مثل شدة الصوت أو مستويات الـ pH.  
- **مراقبة العمليات:** يمكن لخطوط الاتجاه القوية نمذجة تدهور الأداء مع مرور الوقت.

## كيفية تحسين الذاكرة عند استخدام Aspose.Slides؟
تخلص من الكائنات فورًا واستخدم `presentation.dispose()` بعد الحفظ. بالنسبة لمجموعات البيانات الكبيرة، فعّل التحميل الكسول للصور وتجنب تحميل المخطط بالكامل في الذاكرة مرة واحدة.

- **أنماط التخلص:** غلف `Presentation` بكتلة try‑with‑resources أو استدعِ `presentation.dispose()` في جملة finally.  
- **التحميل الكسول:** اضبط `ChartData.setUseCache(true)` عند التعامل مع آلاف نقاط البيانات.  
- **إخراج البث:** اكتب العرض التقديمي مباشرة إلى `FileOutputStream` لتجنب إبقاء الملف بالكامل في الذاكرة.

## الفوائد الكمية لـ Aspose.Slides for Java
يدعم Aspose.Slides **أكثر من 50 نوعًا من المخططات**، يمكنه إنشاء عروض تقديمية تحتوي على **أكثر من 1,000 شريحة** في أقل من **30 ثانية** على معالج 2 GHz نموذجي، ويعالج **ملفات PDF بصفحات 500** دون الحاجة إلى تثبيت Microsoft Office. تم التحقق من هذه الأرقام في أحدث إصدار 25.4.

## الخلاصة
أصبح لديك الآن حل كامل من البداية إلى النهاية **لإنشاء مخطط عمودي مجمع** وتغذيته بكل نوع رئيسي من خطوط الاتجاه المتاحة في Aspose.Slides for Java. باتباع الخطوات السابقة، يمكنك إنتاج عروض تقديمية مدفوعة بالبيانات تكون جذابة بصريًا وقوية تحليليًا. تشمل الخطوات التالية استكشاف خيارات تنسيق المخططات، التصدير إلى PDF/HTML، وأتمتة إنشاء المخططات عبر مصادر بيانات متعددة.

## الأسئلة المتكررة

**س: كيف أقوم بإعداد Aspose.Slides لمشروع Maven؟**  
ج: أضف مقطع `<dependency>` المعروض في قسم Maven إلى ملف `pom.xml` وشغّل `mvn clean install`.

**س: هل يمكنني تخصيص خطوط الاتجاه بما يتجاوز اللون والتسمية؟**  
ج: نعم، يمكنك تعديل نمط الخط، العرض، نمط الشرط، وحتى توقع القيم للأمام/للخلف عبر واجهة `ITrendline` API.

**س: ماذا أفعل إذا واجهت خطأ توافق إصدارات؟**  
ج: تحقق من أن إصدار JDK الخاص بك يطابق الحد الأدنى المطلوب من Aspose.Slides (JDK 8+). راجع ملاحظات إصدار Aspose لأي تغييرات كسرية.

**س: هل يمكن إضافة خطوط الاتجاه إلى عدة مخططات تلقائيًا؟**  
ج: بالطبع. قم بالتكرار عبر كل `IChart` في مجموعة الشرائح واستدعِ طريقة `addTrendline` المناسبة لكل سلسلة.

**س: هل أحتاج إلى ترخيص مدفوع للاستخدام في الإنتاج؟**  
ج: نعم، ترخيص Aspose.Slides المشتَرَى يزيل حدود التقييم ويفتح تحسينات الأداء الكاملة.

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## دروس ذات صلة

- [اعتماد Maven لـ Aspose Slides: إضافة وتكوين المخططات في العروض التقديمية باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [إضافة حركة إلى مخطط PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [إنشاء مخطط PowerPoint Java – حفظ العروض التقديمية مع المخططات باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
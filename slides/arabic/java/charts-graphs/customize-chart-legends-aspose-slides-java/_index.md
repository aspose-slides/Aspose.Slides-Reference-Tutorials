---
date: '2026-08-06'
description: تعلم كيفية تغيير legend font color وتعديل نص chart legend باستخدام Aspose.Slides
  for Java. اتبع تعليمات خطوة بخطوة لتخصيص chart legends بسرعة.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: تعلم كيفية تغيير legend font color وتعديل نص chart legend مع Aspose.Slides
  for Java. يوضح لك هذا الدليل الخطوات الدقيقة والـ best practices.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: كيفية تغيير legend font color في Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: كيفية تغيير legend font color في Aspose.Slides for Java
url: /ar/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تغيير لون خط وسيلة الإيضاح في Aspose.Slides for Java

## مقدمة
إذا كنت بحاجة إلى **تغيير لون خط وسيلة الإيضاح** في مخطط، فإن Aspose.Slides for Java يمنحك التحكم الكامل في كل عنصر من عناصر وسيلة الإيضاح. يشرح هذا الدرس كيفية تخصيص أنماط نص وسيلة الإيضاح، وتطبيق الخط العريض أو المائل، وتعيين ألوان صلبة بحيث تبدو مخططاتك بالضبط كما تريد. بنهاية هذا الدليل ستتمكن من تعديل نص وسيلة إيضاح المخطط بثقة ودمج التغييرات في أي عرض تقديمي موجود.

**ما ستتعلمه**
- كيفية **تغيير لون خط وسيلة الإيضاح** برمجياً.  
- طرق **تعديل نص وسيلة إيضاح المخطط** مثل الخط العريض، المائل، والحجم.  
- نصائح لتطبيق التغييرات على مخططات متعددة في عرض تقديمي واحد.  
- كيفية دمج هذه الخطوات في سير عمل أتمتة أكبر.  

## إجابات سريعة
- **هل يمكنني تغيير لون عنصر وسيلة الإيضاح المفرد؟** نعم – يمكن الوصول إلى العنصر عبر فهرسه وتعيين تنسيق التعبئة إلى لون صلب.  
- **هل أحتاج إلى ترخيص لاستخدام هذه الـ APIs؟** يلزم ترخيص مؤقت أو مدفوع للإنتاج؛ النسخة التجريبية المجانية تكفي للتقييم.  
- **ما نسخة Java المدعومة؟** Aspose.Slides for Java 25.4+ تعمل مع JDK 16 وما فوق.  
- **هل ستؤثر التغييرات على عناصر المخطط الأخرى؟** لا، تنسيق وسيلة الإيضاح معزل عن تنسيق سلاسل البيانات.  
- **هل المعالجة الدفعية ممكنة؟** بالتأكيد – يمكن تكرار الشرائح والمخططات لتطبيق نفس إعدادات وسيلة الإيضاح عبر مجموعة كاملة.  

## ما هو تغيير لون خط وسيلة الإيضاح؟
`change legend font color` يشير إلى العملية البرمجية لتعيين لون نص عناصر وسيلة إيضاح المخطط باستخدام Aspose.Slides API. هذه العملية تُحدّث المظهر البصري لوسيلة الإيضاح دون تعديل البيانات الأساسية.  

## لماذا تخصيص وسائط إيضاح المخططات؟
Aspose.Slides يدعم **50+ تنسيقات إدخال وإخراج** ويمكنه التعامل مع عروض تقديمية تحتوي على **500+ شريحة** مع الحفاظ على استهلاك الذاكرة أقل من 200 ميغابايت. تحسين وسائط الإيضاح يعزز قابلية القراءة، ويعزز ألوان العلامة التجارية، ويضمن بروز نقاط البيانات الرئيسية—خاصة في العروض التجارية أو التعليمية حيث الوضوح البصري يدفع اتخاذ القرار.  

## المتطلبات المسبقة
- مكتبة **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).  
- Java Development Kit (JDK) 16 أو أعلى.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans.  
- Maven أو Gradle لإدارة التبعيات.  
- معرفة أساسية ببرمجة Java.  

## إعداد Aspose.Slides for Java
لبدء تخصيص وسائط إيضاح المخططات، أضف المكتبة إلى مشروعك باستخدام إحدى الطرق أدناه.

### Maven
أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:
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
يمكنك أيضًا الحصول على أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بنسخة تجريبية مجانية لاستكشاف ميزات Aspose.Slides.  
- **ترخيص مؤقت:** قدّم طلبًا للحصول على ترخيص مؤقت لتقييم ممتد.  
- **شراء:** للحصول على وصول كامل، فكر في شراء ترخيص من [Aspose Purchase](https://purchase.aspose.com/buy).

#### التهيئة الأساسية والإعداد
بعد إضافة المكتبة إلى مشروعك:
1. قم بتهيئة Aspose.Slides في تطبيق Java الخاص بك.  
2. حمّل عرض تقديمي موجود أو أنشئ عرضًا جديدًا.  

## كيفية تغيير لون خط وسيلة الإيضاح؟
لتغيير لون خط وسيلة الإيضاح، حمّل العرض التقديمي، احصل على كائن المخطط، استخرج وسيلة الإيضاح، ثم عدّل تنسيق النص لكل عنصر من عناصر وسيلة الإيضاح عن طريق تعيين نوع التعبئة إلى صلب وتحديد اللون المطلوب. هذه العملية الواحدة تُحدّث لون نص وسيلة الإيضاح فورًا دون الحاجة إلى إعادة رسم الشريحة بالكامل. مثال: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` هذا النهج يعمل مع أي نوع مخطط ولا يتطلب إعادة تصيير الشريحة بأكملها.  

### الوصول وتعديل خصائص نص وسيلة الإيضاح

#### تعريف المرجع
واجهة `IChart` تمثل كائن مخطط على شريحة، وطريقة `getLegend()` الخاصة بها تُعيد كائن `ILegend` يحتوي على مجموعة من عناصر `ILegendEntry`.  

#### إضافة مخطط إلى عرضك التقديمي
1. **حمّل العرض التقديمي:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **أضف مخطط عمودي مجمع:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### تخصيص خصائص الخط
3. **الوصول إلى تنسيق نص عنصر وسيلة الإيضاح:**  
   هنا، `legendEntry` هو كائن `ILegendEntry` يمثل عنصرًا واحدًا في وسيلة إيضاح المخطط.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **تعيين الأنماط العريضة والمائلة بارتفاع محدد:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **تغيير نوع التعبئة إلى لون صلب لتحسين الرؤية:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### حفظ العرض التقديمي
6. **احفظ التغييرات:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### المشكلات الشائعة واستكشاف الأخطاء
- تحقق من أن فهرس عنصر وسيلة الإيضاح يطابق ترتيب السلاسل في المخطط.  
- تأكد من أنك تستخدم نسخة المكتبة التي تدعم `setSolidFillColor` (متاحة منذ الإصدار 20.9).  

## تطبيقات عملية
تخصيص نص وسيلة الإيضاح مفيد في العديد من السيناريوهات الواقعية:

1. **عروض الأعمال:** مواءمة ألوان وسيلة الإيضاح مع هوية الشركة للحصول على مظهر مصقول.  
2. **المواد التعليمية:** إبراز سلاسل البيانات الرئيسية باستخدام ألوان وسيلة إيضاح متباينة.  
3. **عروض التسويق:** التأكيد على مؤشرات الأداء باستخدام وسائط إيضاح غامقة وملونة لجذب انتباه أصحاب المصلحة.  

يمكنك أيضًا أتمتة تحديثات وسيلة الإيضاح بسحب قيم الألوان من قاعدة بيانات أو ملف إعدادات.  

## اعتبارات الأداء
عند معالجة مجموعات شرائح كبيرة، ضع في اعتبارك النصائح التالية:

- **إدارة الذاكرة بفعالية:** استدعِ `presentation.dispose()` بعد الحفظ لتحرير الموارد الأصلية.  
- **حمّل الشرائح المطلوبة فقط:** استخدم `Presentation.load(String path, LoadOptions options)` مع `LoadOptions.setLoadOnlySlideIds()` إذا كنت تحتاج مجموعة فرعية.  
- **المعالجة الدفعية:** اجمع تحديثات وسيلة الإيضاح لكل شريحة لتقليل عدد استدعاءات الـ API وتحسين الإنتاجية.  

## الخلاصة
أنت الآن تعرف كيفية **تغيير لون خط وسيلة الإيضاح** و**تعديل نص وسيلة إيضاح المخطط** باستخدام Aspose.Slides for Java. هذه التخصيصات تعزز الوضوح البصري وتساعدك على نقل البيانات بفعالية أكبر. جرّب خطوطًا، أحجامًا، وألوانًا مختلفة لتتناسب مع دليل نمط عرضك، واستكشف ميزات تنسيق المخططات الأخرى لإنشاء عروض احترافية حقًا.  

**الخطوات التالية**
- جرّب تطبيق نفس تنسيق وسيلة الإيضاح على المخططات الدائرية والخطية.  
- اجمع تخصيص وسيلة الإيضاح مع تنسيق تسميات البيانات للحصول على مخطط يحمل العلامة التجارية بالكامل.  

هل أنت مستعد للارتقاء بعروضك التقديمية؟ نفّذ الخطوات أعلاه وشاهد الفرق فورًا!  

## قسم الأسئلة الشائعة
1. **كيف يمكنني تغيير لون نص عنصر وسيلة الإيضاح؟**  
   استخدم `getFillFormat().setFillType(FillType.Solid)` ثم `setSolidFillColor(Color.YOUR_COLOR)` على تنسيق نص عنصر وسيلة الإيضاح.  

2. **هل يمكنني تطبيق هذه التغييرات على جميع وسائط الإيضاح في عرض تقديمي؟**  
   نعم – كرّر عبر كل شريحة، ابحث عن كل مخطط، وقم بتحديث عناصر وسيلة الإيضاح داخل حلقة.  

3. **هل من الممكن تعديل حجم الخط ديناميكياً بناءً على طول النص؟**  
   يمكنك حساب الحجم المطلوب باستخدام `TextFrame.getTextFrameFormat().getFontHeight()` وتعيينه عبر `setFontHeight(double)`.  

4. **ماذا لو واجهت مشاكل مع فهرسة عناصر وسيلة الإيضاح؟**  
   تحقق مرة أخرى من أن الفهرس الذي تستخدمه يطابق ترتيب السلاسل؛ تذكر أن الفهارس تبدأ من الصفر.  

5. **أين يمكنني العثور على المزيد من أمثلة Aspose.Slides؟**  
   استكشف [Aspose Documentation](https://reference.aspose.com/slides/java/) للحصول على أدلة شاملة ومراجع API.  

**أسئلة وإجابات إضافية**

**س: هل يؤثر تغيير لون خط وسيلة الإيضاح على ملفات PDF المصدرة؟**  
**ج:** لا، يتم الحفاظ على تغيير اللون في جميع صيغ التصدير المدعومة من Aspose.Slides، بما في ذلك PDF و PPTX.  

**س: هل يمكنني استخدام تدرج لوني بدلاً من لون صلب؟**  
**ج:** نعم – عيّن `FillType.Gradient` وقم بتكوين نقاط التدرج عبر `getGradientStyle()`.  

**س: كم عدد عناصر وسيلة الإيضاح التي يمكن أن يحتويها المخطط؟**  
**ج:** يمكن للمخطط أن يحتوي على ما يصل إلى 256 عنصرًا من وسيلة الإيضاح، يحدها فقط عدد سلاسل البيانات التي تضيفها.  

## الموارد
- **الوثائق:** دليل شامل لاستخدام ميزات Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **التنزيل:** احصل على أحدث نسخة من Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/)).  
- **الشراء:** اشترِ ترخيصًا لفتح جميع القدرات ([Link](https://purchase.aspose.com/buy)).  
- **نسخة تجريبية مجانية & ترخيص مؤقت:** ابدأ بنسخ تجريبية مجانية وقدّم طلبًا للحصول على تراخيص مؤقتة ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **الدعم:** احصل على مساعدة من المجتمع في منتدى الدعم الخاص بـ Aspose ([Link](https://forum.aspose.com/c/slides/11)).  

---

**آخر تحديث:** 2026-08-06  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose  

## دروس ذات صلة
- [تحسين مخططات PowerPoint: تخصيص الخط والمحور باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)  
- [Aspose.Slides for Java: دليل إطارات النص الديناميكية وتخصيص الخط](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)  
- [تحريك مخططات PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
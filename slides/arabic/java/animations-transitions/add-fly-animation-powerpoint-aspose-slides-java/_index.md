---
date: '2026-09-22'
description: تعلم كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides for
  Java، وكيفية إضافة الرسوم المتحركة، وكيفية تكوين تبعية Maven الخاصة بـ Aspose Slides.
keywords:
- how to save powerpoint
- how to add animation
- save powerpoint with animation
- aspose slides maven dependency
- java add slide animation
lastmod: '2026-09-22'
og_description: كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides for
  Java. يوضح هذا الدليل كيفية إضافة الرسوم المتحركة، وتكوين تبعية Maven، وإنشاء شرائح
  ديناميكية.
og_image_alt: 'Developer guide: save PowerPoint with animation using Aspose.Slides
  for Java'
og_title: كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to save PowerPoint with animation using Aspose.Slides for
    Java, how to add animation, and how to configure the Aspose Slides Maven dependency.
  headline: How to save PowerPoint with animation using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to save PowerPoint with animation using Aspose.Slides for
    Java, how to add animation, and how to configure the Aspose Slides Maven dependency.
  name: How to save PowerPoint with animation using Aspose.Slides for Java
  steps:
  - name: initialize the presentation object
    text: 'Create and initialize a `Presentation` object that points to your existing
      PowerPoint file: Here, we’re opening an existing presentation named `Presentation1.pptx`.
      The constructor automatically parses the file structure, making every slide
      and shape available through the object model.'
  - name: access the target slide and shape
    text: 'Retrieve the first slide and its first auto‑shape (which contains the text
      you want to animate): We assume the shape is an `AutoShape` with a text frame,
      which is the most common container for paragraph‑level animations.'
  - name: apply the fly animation effect
    text: 'Add a **fly animation PowerPoint** effect to the first paragraph of the
      shape. This example configures the animation to fly in from the left and trigger
      on a mouse click: The `EffectTriggerType` enum determines when the animation
      starts (e.g., `OnClick` or `AfterPrevious`). The `EffectSubtype` enum '
  - name: save the presentation with animation
    text: 'Persist the changes by saving the file. This step **saves the presentation
      with animation** intact: Saving as `SaveFormat.Pptx` guarantees that all animation
      data is written to the output file.'
  type: HowTo
- questions:
  - answer: Modify the `EffectSubtype` parameter in the `addEffect()` call to `Right`,
      `Top`, or `Bottom`.
    question: How do I change the animation direction?
  - answer: Yes. Loop through each paragraph in the shape’s text frame and call `addEffect`
      for each one.
    question: Can I apply the fly animation to multiple paragraphs at once?
  - answer: Double‑check your Maven/Gradle configuration, ensure the correct classifier
      (`jdk16`), and verify that the Aspose license is correctly loaded.
    question: What should I do if I encounter errors during setup?
  - answer: Visit the [temporary Aspose license page](https://purchase.aspose.com/temporary-license/)
      and follow the request process.
    question: How do I obtain a temporary Aspose license for testing?
  - answer: Wrap file‑access and animation code in try‑catch blocks, and always close
      the `Presentation` object in a finally block or use try‑with‑resources.
    question: What is the best way to handle exceptions when working with presentations?
  type: FAQPage
tags:
- save PowerPoint
- Aspose.Slides
- Java animation
- fly animation
- PowerPoint API
title: كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides for Java
url: /ar/java/animations-transitions/add-fly-animation-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides for Java

## مقدمة

في هذا الدليل ستكتشف **كيفية حفظ ملفات PowerPoint** مع الحفاظ على الرسوم المتحركة المتقدمة. ستتعلم إضافة تأثير طيران إلى فقرة، ضبط مشغل الرسوم المتحركة، وإنشاء ملف `.pptx` نهائي يبدو تمامًا كعرض شرائح تم إنشاؤه يدويًا. باستخدام **Aspose.Slides for Java**، يمكنك أتمتة إنشاء العروض على الخادم دون الحاجة إلى تثبيت Microsoft Office، وهو مثالي للمعالجة الدفعية، خدمات الويب، وخطوط أنابيب CI.

## إجابات سريعة
- **ما المكتبة التي تضيف حركة الطيران إلى PowerPoint؟** Aspose.Slides for Java.  
- **ما أداة البناء التي يمكنني استخدامها؟** كل من Maven (`aspose‑slides` Maven dependency) و Gradle مدعومان.  
- **كيف أضبط مشغل الرسوم المتحركة؟** استخدم `EffectTriggerType.OnClick` أو `AfterPrevious` في استدعاء `addEffect`.  
- **هل يمكنني الاختبار بدون ترخيص مدفوع؟** نعم — استخدم نسخة تجريبية مجانية أو **ترخيص Aspose مؤقت** أثناء التطوير.  
- **ما الصيغة التي يجب حفظها للحفاظ على الرسوم المتحركة؟** احفظ كـ `.pptx`؛ الصيغ القديمة تحذف بيانات الرسوم المتحركة.  

## لماذا استخدام Aspose.Slides for Java؟

حمّل عرضك، أضف حركة طيران، واحفظه — كل ذلك في كودين مختصرين. يدعم Aspose.Slides **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه معالجة عروض تحتوي على **أكثر من 500 شريحة** دون تحميل الملف بالكامل في الذاكرة، مما يجعله أحد أكثر مكتبات Java قابلية للتوسع لأتمتة الشرائح.

## المتطلبات المسبقة

قبل البدء، تأكد من أنك تمتلك:

- **Java Development Kit (JDK) 16 أو أعلى** مثبتًا.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans.  
- إلمام أساسي بـ Java I/O وأدوات البناء Maven أو Gradle.  

### المكتبات المطلوبة
- **Aspose.Slides for Java** – الإصدار 25.4 أو أحدث (يفضل أحدث إصدار).  

### المتطلبات المعرفية
- فهم إنشاء كائنات Java ومعالجة الاستثناءات.  
- معرفة مفاهيم PowerPoint مثل الشرائح، الأشكال، وتأثيرات الرسوم المتحركة.

## إعداد Aspose.Slides for Java

لبدء العمل، أضف مكتبة Aspose.Slides إلى مشروعك.

### تبعية Maven لـ Aspose Slides
أضف هذه التبعية إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### إعداد Gradle
أدرج هذا في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
حمّل أحدث إصدار من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية** – ابدأ بنسخة تجريبية لاستكشاف جميع الميزات.  
- **ترخيص مؤقت** – احصل على ترخيص مؤقت للوصول الكامل أثناء التطوير.  
- **شراء** – فكر في ترخيص كامل للنشر في بيئات الإنتاج.

بعد إكمال الإعداد، لننتقل إلى تنفيذ تأثير **الطيران في PowerPoint**.

## كيفية حفظ PowerPoint مع الرسوم المتحركة باستخدام Aspose.Slides for Java

فيما يلي دليل خطوة بخطوة يرافقك عبر العملية بالكامل، من تحميل الملف إلى حفظ النتيجة المتحركة.

### ما هي فئة Presentation؟

فئة `Presentation` تمثل ملف PowerPoint في الذاكرة، وتوفر الوصول إلى الشرائح، الأشكال، والرسوم المتحركة. حمّل ملف المصدر، عدّله، ثم احفظه مرة أخرى — كل ذلك دون لمس نظام الملفات حتى استدعاء `save` النهائي.

### الخطوة 1: تهيئة كائن العرض

أنشئ وتهيئ كائن `Presentation` يشير إلى ملف PowerPoint الموجود لديك:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation presentation = new Presentation(dataDir + "/Presentation1.pptx");
```
هنا نفتح عرضًا موجودًا اسمه `Presentation1.pptx`. يقوم المُنشئ تلقائيًا بتحليل بنية الملف، مما يجعل كل شريحة وشكل متاحًا عبر نموذج الكائن.

### الخطوة 2: الوصول إلى الشريحة والشكلة المستهدفة

استرجع الشريحة الأولى وشكلها الأول من نوع auto‑shape (الذي يحتوي على النص الذي تريد تحريكه):
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape autoShape = (IAutoShape) slide.getShapes().get_Item(0);
```
نفترض أن الشكل هو `AutoShape` يحتوي على إطار نص، وهو الحاوية الأكثر شيوعًا لتطبيق الرسوم المتحركة على مستوى الفقرة.

### الخطوة 3: تطبيق تأثير حركة الطيران

أضف تأثير **الطيران في PowerPoint** إلى الفقرة الأولى من الشكل. يضبط هذا المثال الرسوم المتحركة لتطير من اليسار وتُشغل عند النقر بالفأرة:
```java
IParagraph paragraph = autoShape.getTextFrame().getParagraphs().get_Item(0);
IEffect effect = slide.getTimeline().getMainSequence().addEffect(
    paragraph,
    EffectType.Fly,
    EffectSubtype.Left,
    EffectTriggerType.OnClick
);
```
تحدد قيمة التعداد `EffectTriggerType` متى يبدأ التحريك (مثل `OnClick` أو `AfterPrevious`).  
تحدد قيمة التعداد `EffectSubtype` اتجاه حركة الطيران (مثل `Left` أو `Right`).  
يمكنك تغيير `EffectSubtype` إلى `Right` أو `Top` أو `Bottom` لتعديل الاتجاه، وتعديل `EffectTriggerType` إلى `AfterPrevious` إذا كنت تفضّل بدءًا تلقائيًا.

#### تكوين مشغل الرسوم المتحركة

معامل `EffectTriggerType` يتيح لك **تكوين سلوك مشغل الرسوم المتحركة**. `OnClick` ينتظر نقرة المستخدم، بينما `AfterPrevious` يبدأ تلقائيًا بعد انتهاء الرسوم المتحركة السابقة.

### الخطوة 4: حفظ العرض مع الرسوم المتحركة

احفظ التغييرات عن طريق حفظ الملف. هذه الخطوة **تحفظ العرض مع الرسوم المتحركة** كما هي:
```java
presentation.save("YOUR_OUTPUT_DIRECTORY/AnimationEffectinParagraph.pptx", SaveFormat.Pptx);
```
الحفظ كـ `SaveFormat.Pptx` يضمن كتابة جميع بيانات الرسوم المتحركة إلى ملف الإخراج.

## تطبيقات عملية

يمكن استخدام حركات الطيران في العديد من السيناريوهات الواقعية:

- **العروض التعليمية** – إبراز المفاهيم الرئيسية أو كشف النقاط النقطية واحدة تلو الأخرى.  
- **الاجتماعات المؤسسية** – تسليط الضوء على النتائج الربعية، الرسوم البيانية، أو المبادرات الإستراتيجية.  
- **الحملات التسويقية** – إنشاء عروض تقديمية ديناميكية لإطلاق المنتجات تجذب انتباه الجمهور.  

نظرًا لأن الإخراج هو ملف `.pptx` قياسي، فإن أي عارض عروض حديث (PowerPoint، Google Slides، LibreOffice) سيعرض الرسوم المتحركة بشكل صحيح.

## اعتبارات الأداء

على الرغم من قوة Aspose.Slides، احرص على مراعاة النصائح التالية للحفاظ على الأداء المثالي:

- **تخصيص مساحة heap كافية** – العروض الكبيرة (مئات الشرائح) قد تحتاج إلى `-Xmx2g` أو أكثر.  
- **تحرير الموارد فورًا** – استخدم try‑with‑resources أو كتلة `finally` لإغلاق كائن `Presentation`.  
- **تجنب الحلقات غير الضرورية** – عالج فقط الشرائح والأشكال التي تحتاجها؛ العمليات الضخمة قد تزيد من ضغط الذاكرة.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **OutOfMemoryError** عند معالجة ملفات كبيرة | زد حجم heap في JVM (`-Xmx`) وعالج الشرائح على دفعات. |
| **License not found** error | حمّل ملف الترخيص المؤقت أو المدفوع قبل إنشاء كائن `Presentation`. |
| **Animation not visible after saving** | تأكد من حفظك كـ `SaveFormat.Pptx`؛ الصيغ القديمة تحذف بيانات الرسوم المتحركة. |

## الأسئلة المتكررة

**س: كيف أغير اتجاه الرسوم المتحركة؟**  
ج: عدّل معامل `EffectSubtype` في استدعاء `addEffect()` إلى `Right` أو `Top` أو `Bottom`.

**س: هل يمكنني تطبيق حركة الطيران على فقرات متعددة في آنٍ واحد؟**  
ج: نعم. قم بالتكرار عبر كل فقرة في إطار النص الخاص بالشكل واستدعِ `addEffect` لكل منها.

**س: ماذا أفعل إذا واجهت أخطاءً أثناء الإعداد؟**  
ج: تحقق من تكوين Maven/Gradle، تأكد من صحة المصنف (`jdk16`)، وتأكد من تحميل ترخيص Aspose بشكل صحيح.

**س: كيف أحصل على ترخيص Aspose مؤقت للاختبار؟**  
ج: زر [temporary Aspose license page](https://purchase.aspose.com/temporary-license/) واتبع عملية الطلب.

**س: ما هي أفضل طريقة للتعامل مع الاستثناءات عند العمل مع العروض؟**  
ج: احطّ كود الوصول إلى الملفات والرسوم المتحركة بكتل try‑catch، واغلق كائن `Presentation` دائمًا في كتلة finally أو استخدم try‑with‑resources.

## موارد

- **الوثائق**: [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)  
- **التنزيل**: [Latest Releases](https://releases.aspose.com/slides/java/)  
- **الشراء**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية**: [Get a Free License](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت**: [Apply for Temporary Access](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [Aspose Forums](https://forum.aspose.com/c/slides/11)

ابدأ بأتمتة عروض الشرائح اليوم وتمتع بزيادة الإنتاجية التي تأتي من إضافة الرسوم المتحركة المتقدمة برمجيًا.

**آخر تحديث:** 2026-09-22  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose

## دروس ذات صلة

- [Create Dynamic Powerpoint Java – Aspose.Slides Animation Types Guide](/slides/java/animations-transitions/aspose-slides-java-animation-comparison-guide/)
- [How to Create an Animation Analysis Tool - Retrieve PowerPoint Animation Effects Using Aspose.Slides for Java](/slides/java/animations-transitions/retrieve-powerpoint-animations-aspose-slides-java/)
- [How to Set Transitions in PowerPoint Slides Using Aspose.Slides for Java](/slides/java/animations-transitions/master-slide-transitions-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
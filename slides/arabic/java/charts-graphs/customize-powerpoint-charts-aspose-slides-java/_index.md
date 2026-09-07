---
date: '2026-09-07'
description: تعلم كيفية إضافة خطوط مخصصة إلى مخطط Aspose Slides باستخدام Java. دليل
  خطوة بخطوة يحسن مخططات PowerPoint لتوضيح أفضل للبيانات.
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: تعلم كيفية إضافة خطوط مخصصة إلى مخطط Aspose Slides باستخدام Java.
  دليل خطوة بخطوة يحسن مخططات PowerPoint لتوضيح أفضل للبيانات.
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: كيفية إضافة خطوط مخصصة إلى مخطط Aspose Slides باستخدام Java
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: كيفية إضافة خطوط مخصصة إلى مخطط Aspose Slides باستخدام Java
url: /ar/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة خطوط مخصصة إلى مخطط Aspose Slides في Java

## مقدمة

في هذا البرنامج التعليمي ستكتشف كيفية إضافة خطوط مخصصة إلى **aspose slides chart** باستخدام Java. تساعدك الخطوط المخصصة على إبراز الحدود، الاتجاهات، أو نقاط البيانات الرئيسية، مما يحول المخطط العادي إلى قصة بصرية قوية. بنهاية الدليل ستكون قادرًا على دمج Aspose.Slides في مشروعك، ورسم خطوط على المخطط، وضبط مظهرها بدقة لتحقيق أقصى تأثير.

**ما ستتعلمه**
- كيفية تثبيت وترخيص Aspose.Slides لـ Java
- الخطوات الدقيقة لرسم خط مخصص على مخطط
- طرق تنسيق الخط (اللون، السمك، نمط الشرط)
- سيناريوهات واقعية حيث تحسن الخطوط المخصصة التواصل البياني

## إجابات سريعة
- **ما هي الفئة الرئيسية لإنشاء عرض تقديمي؟** `Presentation` تمثل ملف PowerPoint في الذاكرة.  
- **أي طريقة تضيف مخططًا إلى شريحة؟** `slide.getShapes().addChart(...)` تنشئ كائن مخطط.  
- **كيف ترسم خطًا على مخطط؟** استخدم `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.  
- **هل يمكنني ضبط لون الخط إلى الأحمر؟** نعم—قم بتعيين تعبئة الخط إلى الأحمر الصلب `Color.RED`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** الترخيص الكامل يزيل حدود التقييم؛ النسخة التجريبية تعمل للاختبار.  

`ShapeType.Line` هو قيمة تعداد تخبر Aspose.Slides بإنشاء شكل تلقائي على شكل خط.

## ما هو مخطط Aspose Slides؟

إن **Aspose Slides chart** هو كائن مخطط قابل للبرمجة يعيش داخل شريحة PowerPoint، مما يتيح لك إنشاء وتعديل وتنسيق المخططات بالكامل من خلال كود Java. يدعم العديد من أنواع المخططات (عمودي، شريطي، خطي، دائري، إلخ)، ويوفر تحكمًا كاملاً في السلاسل والمحاور والوسائط، ويمكن دمجه مع عناصر شريحة أخرى مثل الصور والأشكال المخصصة، مما يجعله مناسبًا للتقارير الآلية والعروض التقديمية الديناميكية.

## لماذا نضيف خطوطًا مخصصة إلى مخطط Aspose Slides؟

تتيح لك الخطوط المخصصة توضيح المخططات بإشارات بصرية دقيقة. يدعم Aspose.Slides **أكثر من 50 تنسيقًا للإدخال والإخراج** ويمكنه معالجة العروض التقديمية التي تحتوي على **مئات الشرائح** مع استهلاك أقل من **150 ميغابايت من الذاكرة** على جهاز تطوير عادي، مما يجعله مثاليًا للتقارير على نطاق واسع.

## المتطلبات المسبقة

- **Aspose.Slides for Java** – الإصدار 25.4 (أو أحدث)  
- **JDK 16+** – أي بيئة تشغيل Java حديثة  
- IDE مثل IntelliJ IDEA أو Eclipse  
- معرفة أساسية بـ Java وإلمام بمفاهيم PowerPoint  

### المكتبات المطلوبة
- Aspose.Slides for Java (الإصدار 25.4)

### إعداد البيئة
- تثبيت JDK 16 أو أحدث  
- استخدام Maven أو Gradle لإدارة التبعيات (الأمثلة أدناه)  

## إعداد Aspose.Slides لـ Java

أضف المكتبة إلى مشروعك باستخدام أحد أدوات البناء التالية.

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

للتنزيل اليدوي، زر [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/) للحصول على أحدث حزمة.

### الحصول على الترخيص
- **Free trial:** ابدأ الاختبار دون شراء.  
- **Temporary license:** استخدم لتقييم ممتد دون علامات مائية.  
- **Full license:** افتح جميع الميزات لأعباء العمل الإنتاجية.  

قم بتهيئة الترخيص في الكود كما هو موضح هنا:
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License` هي الفئة المستخدمة لتحميل وتطبيق ملف ترخيص Aspose.Slides على التطبيق.

## كيف تضيف خطوطًا مخصصة إلى مخطط Aspose Slides؟

حمّل أو أنشئ عرضًا تقديميًا، أدخل مخططًا، ثم أضف شكل خط إلى مجموعة user‑shapes الخاصة بالمخطط. يمكن وضع الخط وتحديد حجمه وتنسيقه ليتناسب مع احتياجات التقارير الخاصة بك. يعمل هذا النهج مع مخططات الأعمدة المجمعة، الشريطية، الخطية، والمساحية على حد سواء.

## دليل التنفيذ

### إضافة خطوط مخصصة إلى مخطط

#### نظرة عامة
تجذب الخطوط المخصصة الانتباه إلى قيم محددة—مثل حد الميزانية أو خط الهدف—مما يجعل مخططاتك أكثر فائدة.

#### الخطوة 1: إنشاء كائن عرض تقديمي
فئة `Presentation` هي الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint واحد في الذاكرة.  
```java
Presentation pres = new Presentation();
```  

#### الخطوة 2: إضافة مخطط عمودي مجمع
أدرج مخطط عمودي مجمع في الشريحة الأولى عند الإحداثيات (100, 100) بعرض 500 بكسل وارتفاع 400 بكسل.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### الخطوة 3: إضافة شكل خط تلقائي إلى المخطط
أضف شكل خط إلى مجموعة `userShapes` الخاصة بالمخطط، التي تخزن كائنات الرسم المخصصة.  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes` هي مجموعة تحتفظ بالأشكال المخصصة المرسومة مباشرة على المخطط، مما يتيح لك إضافة خطوط أو أسهم أو تعليقات توضيحية أخرى.

#### الخطوة 4: تخصيص خصائص الخط
قم بتعيين نوع تعبئة الخط إلى صلب، غير لونه إلى الأحمر، ويمكنك تعديل السمك أو نمط الشرط إذا رغبت.  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل إلى القرص.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### العمل مع فئة Presentation
توفر فئة `Presentation` طرقًا لتحميل وإنشاء وحفظ ملفات PowerPoint، بالإضافة إلى الوصول إلى الشرائح والأشكال الفردية.

### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من أن مسار الملف المستخدم في `save` قابل للكتابة؛ استخدم مسارات مطلقة للموثوقية.  
- إذا لم يظهر المخطط، تحقق مرة أخرى من إحداثيات X/Y وتأكد من صحة فهرس الشريحة.  

## التطبيقات العملية

تكون الخطوط المخصصة مفيدة بشكل خاص في:
1. **Financial reports** – إبراز حدود الميزانية أو أهداف الأرباح.  
2. **Sales dashboards** – رسم خط لأهداف المبيعات ربع السنوية.  
3. **Healthcare analytics** – وضع علامات على الحدود الحرجة في اتجاهات مؤشرات حيوية للمرضى.  

يمكنك أيضًا أتمتة وضع الخطوط عن طريق سحب قيم الحدود من قاعدة بيانات أو API، مما يتيح تقارير في الوقت الفعلي.

## اعتبارات الأداء

- قم بتحرير كائنات `Presentation` باستخدام `presentation.dispose()` عند الانتهاء لتحرير الذاكرة الأصلية.  
- استخدم دقة صور ومخططات معتدلة (مثلاً 150 dpi) للحفاظ على حجم الملف تحت السيطرة.  
- أثناء التطوير، يزيل الترخيص المؤقت علامات التقييم المائية مع الاستمرار في توفير وصول كامل إلى API.

## الخلاصة

أنت الآن تعرف كيفية إضافة خطوط مخصصة إلى **aspose slides chart** في Java، مما يمنحك تحكمًا كاملًا في توضيح المخطط والتأكيد البصري. جرب أنماط خطوط مختلفة، ومواقع، وأنواع مخططات لإنشاء تقارير تنقل البيانات فورًا.

## قسم الأسئلة المتكررة

**س1: هل يمكنني تغيير لون الخطوط المخصصة؟**  
A1: نعم، قم بتخصيص ألوان الخط عن طريق ضبط خاصية `SolidFillColor` إلى أي `java.awt.Color` مرغوب.

**س2: هل Aspose.Slides متوافق مع جميع بيئات تطوير Java؟**  
A2: نعم، طالما أن بيئة التطوير تدعم Maven أو Gradle، يمكنك دمج Aspose.Slides دون مشاكل.

**س3: ما أنواع المخططات المدعومة لإضافة خطوط مخصصة؟**  
A3: يمكن إضافة خطوط مخصصة إلى مخططات الأعمدة المجمعة، الشريطية، الخطية، المساحية، والدائرية، وغيرها.

**س4: كيف أقوم باستكشاف مشاكل حفظ العروض التقديمية؟**  
A4: تأكد من وجود دليل الإخراج، صحة مسار الملف، وأن التطبيق يمتلك أذونات الكتابة.

**س5: هل هناك أي قيود عند استخدام ترخيص تجريبي؟**  
A5: قد يضيف النسخة التجريبية علامات مائية ويقيد بعض الميزات المتميزة؛ الترخيص المؤقت أو الكامل يزيل هذه القيود.

## الموارد
- **Documentation**: [توثيق Aspose.Slides Java](https://reference.aspose.com/slides/java/)  
- **Download**: [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/)  
- **Purchase**: [شراء Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [احصل على نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [الحصول على ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)  
- **Support**: [منتدى دعم Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-09-07  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء وتخصيص خطوط الاتجاه للمخططات Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [كيفية تعديل بيانات مخطط PowerPoint باستخدام Aspose.Slides for Java: دليل شامل](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [كيفية تدوير عناوين محاور المخطط في PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-09-17'
description: تعلم كيفية إنشاء bubble chart PowerPoint باستخدام Aspose.Slides for Java.
  يوضح هذا الدليل كيفية إضافة chart إلى slide، وتكوين حجم bubble، وحفظ ملف PPTX بكفاءة.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: تعلم كيفية إنشاء bubble chart PowerPoint باستخدام Aspose.Slides for
  Java. يشرح هذا الدليل كيفية إضافة chart إلى slide، وضبط حجم bubble، وحفظ العرض التقديمي
  بكفاءة.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: إنشاء bubble chart PowerPoint باستخدام Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: إنشاء bubble chart PowerPoint باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مخطط فقاعة في PowerPoint باستخدام Aspose.Slides للـ Java

## المقدمة
إذا كنت بحاجة إلى **create bubble chart powerpoint** عروض تقديمية برمجياً، فإن Aspose.Slides للـ Java يزودك بواجهة برمجة تطبيقات نظيفة تعمل على الخادم دون الحاجة إلى Microsoft Office. في هذا الدرس ستتعلم كيفية إضافة مخطط إلى شريحة، التحكم في أحجام الفقاعات، وحفظ ملف PPTX النهائي مع إدارة الموارد بكفاءة. تم تقسيم الخطوات بحيث يمكنك نسخ‑لصق الشيفرة في أي مشروع Java ورؤية النتائج فوراً.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java
- **ما نسخة Java المطلوبة؟** JDK 16 أو أعلى
- **كيف أضيف مخطط فقاعة؟** Call `addChart(ChartType.Bubble, …)` on a slide
- **هل يمكنني تغيير حجم الفقاعة؟** Yes, via `setBubbleSizeScale()`
- **كيف أحفظ الملف؟** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## ما هو create bubble chart powerpoint؟
إنشاء مخطط فقاعة في PowerPoint يعني توليد مخطط برمجياً حيث يتم تمثيل كل نقطة بيانات بفقاعة يكون موقعها X وموقعها Y وحجمها يعكس ثلاثة أبعاد من البيانات. تتولى Aspose.Slides للـ Java عملية العرض، لذا لا تحتاج إلى تثبيت PowerPoint.

## لماذا تستخدم Aspose.Slides للـ Java؟
يدعم Aspose.Slides **أكثر من 50 نوعًا من المخططات**، ويمكنه معالجة العروض التقديمية حتى **2 GB** دون تحميل الملف بالكامل إلى الذاكرة، ويعمل على أي منصة تدعم Java 16+. تجعل هذه القدرات الم quantified تجعلها خيارًا موثوقًا للتقارير على مستوى المؤسسات.

## المتطلبات المسبقة
- **Java Development Kit** 16 أو أحدث مثبت.
- مكتبة **Aspose.Slides للـ Java** (أضفها عبر Maven أو Gradle أو تحميل JAR مباشرة).
- إلمام أساسي بتركيب Java وبرمجة الكائنات.

## إعداد Aspose.Slides للـ Java
لبدء استخدام Aspose.Slides، قم بإضافة المكتبة إلى نظام البناء الخاص بك.

### Maven
أضف الاعتمادية التالية إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
أدرج هذا في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
يمكنك أيضًا الحصول على أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **Free trial** – استكشاف جميع الميزات دون تكلفة.  
- **Temporary license** – تقييم ممتد للمشاريع الكبيرة.  
- **Full license** – مطلوب للنشر في بيئات الإنتاج.

### التهيئة الأساسية والإعداد
فئة `Presentation` هي نقطة الدخول لإنشاء أو تحميل ملفات PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## دليل التنفيذ
فيما يلي دليل خطوة بخطوة لإنشاء مخطط فقاعة وإدارة الموارد.

## كيفية إنشاء مخطط فقاعة في PowerPoint
في هذا القسم ستتعلم التسلسل الدقيق لاستدعاءات API اللازمة لإنشاء مخطط فقاعة، ضبط خصائصه البصرية، وحفظ النتيجة كملف PPTX. تعمل هذه الطريقة مع أي مشروع Java يتضمن Aspose.Slides ويتبع ممارسات إدارة الموارد المثلى.

حمّل العرض التقديمي، أضف مخطط فقاعة، اضبط مظهره، واحفظ الملف.

### الجواب المباشر
أنشئ كائن `Presentation` جديدًا، استدعِ `addChart(ChartType.Bubble, …)` على الشريحة المطلوبة، اضبط مقياس حجم الفقاعات باستخدام `setBubbleSizeScale(150)`، ثم احفظ باستخدام `pres.save("Result.pptx", SaveFormat.Pptx)`. يضيف هذا التسلسل مخطط فقاعة كامل الوظيفة في بضع أسطر فقط من Java.

- **`ChartType.Bubble`** يمثل نوع مخطط الفقاعة.  
- **`addChart`** يدرج مخططًا جديدًا من النوع المحدد على شريحة.  
- **`setBubbleSizeScale`** يضبط الحجم الكلي للفقاعات في المخطط.  
- **`SaveFormat.Pptx`** يحدد تنسيق ملف PPTX للحفظ.  

#### تنفيذ خطوة بخطوة
**1. تهيئة العرض** – إنشاء كائن `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. إضافة مخطط فقاعة** – إدراج المخطط في الإحداثيات المختارة.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` يخبر Aspose.Slides بإنشاء مخطط فقاعة.  
- المعاملات الرقمية تحدد موضع X/Y والعرض/الارتفاع بالنقاط.

**3. ضبط مقياس حجم الفقاعات** – تكبير الفقاعات لتحسين التأثير البصري.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- ضبط المقياس إلى **150 %** يجعل كل فقاعة أكبر بمقدار 1.5 × من الحجم الافتراضي.

**4. حفظ العرض** – كتابة ملف PPTX إلى القرص.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من أذونات الكتابة للمجلد الهدف.  
- تأكد من أن JAR الخاص بـ Aspose.Slides يتطابق مع نسخة JDK التي تستخدمها.

## كيفية إدارة موارد PowerPoint بفعالية
إدارة الموارد بفعالية تمنع تسرب الذاكرة وتحافظ على حجم الذاكرة المستخدمة من قبل JVM منخفضًا، خاصةً عند معالجة مجموعات شرائح كبيرة أو التشغيل في بيئة خادم. اتبع النمط أدناه لضمان تحرير الموارد الأصلية حتى في حالة حدوث استثناء.

### الجواب المباشر
بعد الانتهاء من العمل مع كائن `Presentation`، احرص دائمًا على استدعاء `pres.dispose()` داخل كتلة `try‑finally`؛ فهذا يحرر الموارد الأصلية ويسمح لـ JVM باستعادة الذاكرة بسرعة.

- **`pres.dispose()`** يحرر الموارد الأصلية المستخدمة من قبل العرض.

**1. إنشاء وتعديل** – العمل مع العرض حسب الحاجة.  
```java
Presentation pres = new Presentation();
```

**2. تحرير الموارد** – تحرير الذاكرة بمجرد اكتمال المعالجة.  
```java
if (pres != null) pres.dispose();
```

## التطبيقات العملية
تتفوق مخططات الفقاعات في السيناريوهات التي تحتاج إلى تصور ثلاث أبعاد من البيانات في آن واحد:
1. **Market analysis** – حجم الفقاعة يمثل الإيرادات بينما تمثل محوري X/Y النمو وحصة السوق.  
2. **Performance metrics** – مقارنة إنتاجية الموظفين (X)، الرضا (Y)، والتأثير (الحجم).  
3. **Geographical data** – رسم المدن مع ترميز عدد السكان في حجم الفقاعة.  
4. **Project management** – تصور الجدول الزمني (X)، التكلفة (Y)، والمخاطر (الحجم) على شريحة واحدة.

## اعتبارات الأداء
- **استخدام الموارد** – حرر العروض التقديمية فورًا للحفاظ على انخفاض استهلاك الذاكرة.  
- **إدارة ذاكرة Java** – غلف عمل العرض في كتلة `try‑finally` لضمان التحرير حتى عند حدوث استثناءات.  
- **ابقَ محدثًا** – قم بترقية إلى أحدث نسخة من Aspose.Slides للاستفادة من تحسينات الأداء وإصلاح الأخطاء.

## الأسئلة المتكررة

**س: ما هو Aspose.Slides للـ Java؟**  
ج: Aspose.Slides للـ Java هي مكتبة مستقلة تتيح لك إنشاء وتحرير وتحويل ملفات PowerPoint دون الحاجة إلى Microsoft Office.

**س: كيف أدمج Aspose.Slides مع مشروع Java الحالي؟**  
ج: أضف اعتماد Maven أو Gradle الموضح سابقًا، أو ضع ملف JAR في مسار الفئات (classpath)، ثم استورد `com.aspose.slides.*`.

**س: هل يمكنني استخدام Aspose.Slides للعروض التقديمية الكبيرة؟**  
ج: نعم، تتعامل المكتبة بكفاءة مع عروض تقديمية تصل إلى **2 GB** وتدعم البث لتجنب تحميل الملف بالكامل إلى الذاكرة.

**س: ما هي أنواع المخططات المتاحة غير مخططات الفقاعات؟**  
ج: يتم دعم أكثر من **50 نوعًا من المخططات**، بما في ذلك المخططات الشريطية، الخطية، الدائرية، الرادارية، والشلالية.

**س: هل هناك دعم مدمج لتنسيق عناصر المخطط؟**  
ج: بالتأكيد. يمكنك تخصيص الألوان، الخطوط، الحدود، وعناوين البيانات عبر كائنات `ChartSeries` و `ChartTitle` الخاصة بالمخطط.

## الموارد
- **التوثيق**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **التنزيل**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **الشراء**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **نسخة تجريبية مجانية**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **ترخيص مؤقت**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **الدعم**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-09-17  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides للـ Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [إنشاء مخطط PowerPoint باستخدام Java و Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [إنشاء مخطط PowerPoint Java – حفظ العروض التقديمية مع المخططات باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-10-08'
description: تعلم كيفية ضبط مستوى التكبير لشرائح PowerPoint باستخدام Aspose.Slides
  for Java، بما في ذلك اعتماد Maven، وضبط تكبير عرض الشريحة وعرض الملاحظات، وحفظ الملف
  بصيغة PPTX.
keywords:
- how to set zoom
- slide zoom powerpoint
- maven aspose slides
- save presentation pptx
- adjust slide zoom
lastmod: '2026-10-08'
og_description: كيفية ضبط التكبير في PowerPoint باستخدام Aspose.Slides for Java. إضافة
  اعتماد Maven، ضبط مستويات تكبير عرض الشريحة وعرض الملاحظات، وحفظ ملف PPTX بكفاءة.
og_image_alt: Guide showing how to set zoom for PowerPoint slides using Aspose.Slides
  Java API
og_title: كيفية ضبط التكبير في PowerPoint باستخدام Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to set zoom for PowerPoint slides with Aspose.Slides for
    Java, including Maven dependency, slide view and notes view adjustments, and saving
    as PPTX.
  headline: How to set zoom in PowerPoint using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to set zoom for PowerPoint slides with Aspose.Slides for
    Java, including Maven dependency, slide view and notes view adjustments, and saving
    as PPTX.
  name: How to set zoom in PowerPoint using Aspose.Slides for Java
  steps:
  - name: instantiate presentation
    text: 'Create a new instance of `Presentation`:'
  - name: adjust slide zoom level
    text: '`setScale(int percent)` sets the zoom level for the slide view as a percentage
      of the original size. *Why this step?* Setting the scale guarantees that all
      slide elements fit within the visible area, eliminating the need for manual
      adjustments during a live demo.'
  - name: save the presentation
    text: 'Write the changes back to a PPTX file: *Why save in PPTX?* PPTX retains
      all view settings and is widely supported by modern presentation tools.'
  type: HowTo
- questions:
  - answer: Yes, pass any integer percentage to `setScale()` to match your layout
      requirements.
    question: Can I set custom zoom levels other than 100 %?
  - answer: Check directory write permissions and ensure the file isn’t locked by
      another application.
    question: What if my presentation doesn't save properly?
  - answer: Process files in a secure environment, apply encryption if needed, and
      comply with relevant data‑protection regulations.
    question: How do I handle presentations with sensitive data using Aspose.Slides?
  - answer: The `jdk16` classifier targets JDK 16, but Aspose provides classifiers
      for JDK 8, 11, 17, and 21—choose the one that matches your runtime.
    question: Does the Maven Aspose Slides dependency support other JDK versions?
  - answer: Yes, place the code inside a loop that loads each presentation, sets the
      scale, and saves the file.
    question: Can I apply the same zoom settings to multiple presentations automatically?
  type: FAQPage
tags:
- slide zoom
- Aspose.Slides
- Java presentation automation
title: كيفية ضبط التكبير في PowerPoint باستخدام Aspose.Slides for Java
url: /ar/java/animations-transitions/set-zoom-levels-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تكبير الشريحة في PowerPoint باستخدام Aspose.Slides for Java – دليل

## المقدمة
في هذا الدليل ستتعلم **كيفية تعيين التكبير** لشرائح PowerPoint باستخدام Aspose.Slides for Java. التحكم في مستوى تكبير الشريحة في PowerPoint يتيح لك تقديم عرض ثابت وقابل للقراءة سواء كان الجمهور يستخدم حاسوبًا محمولًا أو جهاز عرض شاشة كبيرة. سنغطي الاعتماد المطلوب من Maven لـ Aspose Slides، وكيفية تعيين مستويات التكبير لكل من عرض الشريحة وعرض الملاحظات إلى 100 ٪، وكيفية حفظ الملف المحدث كملف PPTX.

ستمر عبر:
- تهيئة عرض تقديمي PowerPoint باستخدام Aspose.Slides
- تعيين مستوى تكبير عرض الشريحة إلى 100 ٪
- ضبط مستوى تكبير عرض الملاحظات إلى 100 ٪
- حفظ التعديلات بصيغة PPTX

لنؤكد المتطلبات المسبقة قبل أن نبدأ.

## إجابات سريعة
- **ما هو فعل “set slide zoom PowerPoint”?** يحدد مقياس العرض المرئي للشرائح أو الملاحظات، مما يضمن أن جميع المحتويات تتناسب مع العرض.  
- **ما نسخة المكتبة المطلوبة؟** Aspose.Slides for Java 25.4 (أو أحدث).  
- **هل أحتاج إلى اعتماد Maven؟** نعم – أضف اعتماد Maven Aspose Slides إلى ملف `pom.xml` الخاص بك.  
- **هل يمكنني تغيير التكبير إلى قيمة مخصصة؟** بالتأكيد؛ استبدل `100` بأي نسبة مئوية صحيحة.  
- **هل الترخيص مطلوب للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Slides صالح للحصول على الوظائف الكاملة.

## ما هو “slide zoom PowerPoint”؟
تعيين تكبير الشريحة في PowerPoint يحدد المقياس الذي تُعرض به الشريحة أو ملاحظاتها. من خلال التحكم برمجياً في هذه القيمة، تضمن أن كل عنصر في عرضك التقديمي مرئي بالكامل، وهو أمر مفيد بشكل خاص في سيناريوهات إنشاء الشرائح تلقائيًا أو المعالجة الدفعية.

## لماذا يعتبر تعيين تكبير الشريحة في PowerPoint مهمًا؟
يضمن تعيين تكبير الشريحة في PowerPoint تجربة بصرية متسقة عبر الأجهزة، ويحسن قابلية القراءة بإلغاء الحاجة إلى التكبير اليدوي، ويتيح أتمتة موثوقة عند إنشاء العروض بسرعة. عندما يكون مستوى التكبير محددًا مسبقًا، لا يحتاج المقدمون إلى تعديل العرض أثناء الجلسة الحية، مما يقلل من التشتيت. كما يضمن أن المخططات والرسوم البيانية والنصوص تحتفظ بنسبها المقصودة، مما يجعل العرض يبدو احترافيًا على أي شاشة.

## لماذا تستخدم Aspose.Slides for Java؟
توفر Aspose.Slides for Java واجهة برمجة تطبيقات Java صافية تعمل دون الحاجة إلى تثبيت Microsoft Office. تدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، وتعالج عروضًا تقديمية مئات الصفحات دون تحميل الملف بالكامل إلى الذاكرة، وتتكامل بسلاسة مع Maven، مما يجعل إدارة الاعتمادات بسيطة. كما تقدم المكتبة عرضًا عالي الأداء، مما يتيح لك تحويل الشرائح إلى صور أو ملفات PDF بسرعة، وتدعم ميزات متقدمة مثل الرسوم المتحركة والمخططات وSmartArt.

## المتطلبات المسبقة
- **المكتبات المطلوبة**: Aspose.Slides for Java الإصدار 25.4 (أو أحدث)  
- **البيئة**: JDK 16 أو أحدث  
- **المعرفة**: برمجة Java الأساسية ومعرفة بهياكل ملفات PowerPoint  

## إعداد Aspose.Slides for Java
### معلومات التثبيت
**Maven**  
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
أدرج هذا في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct download**  
للذين لا يستخدمون Maven أو Gradle، قم بتنزيل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
لاستغلال إمكانيات Aspose.Slides بالكامل:
- **تجربة مجانية** – ابدأ برخصة مؤقتة لاستكشاف الميزات.  
- **رخصة مؤقتة** – احصل عليها عبر [صفحة الترخيص المؤقتة من Aspose](https://purchase.aspose.com/temporary-license/) للاستخدام التجريبي غير المقيد.  
- **شراء** – اشترِ رخصة من [موقع Aspose](https://purchase.aspose.com/buy) للنشر في بيئات الإنتاج.

### التهيئة الأساسية
تمثل الفئة `Presentation` ملف PowerPoint في الذاكرة وتوفر الوصول إلى خصائص العرض، ومجموعات الشرائح، وأكثر. لتهيئة Aspose.Slides في تطبيق Java الخاص بك:

```java
import com.aspose.slides.Presentation;
// Initialize presentation object for an empty file
Presentation presentation = new Presentation();
```

## دليل التنفيذ
يوضح لك هذا القسم كيفية تعيين مستويات التكبير باستخدام Aspose.Slides.

### كيفية تعيين تكبير الشريحة في PowerPoint – عرض الشريحة
حمّل العرض التقديمي، عيّن تكبير عرض الشريحة إلى النسبة المطلوبة، ثم احفظ.

**الإجابة المباشرة:** استدعِ `presentation.getViewProperties().getSlideViewProperties().setScale(100)` على كائن `Presentation`، ثم احفظ الملف باستخدام `presentation.save("output.pptx", SaveFormat.Pptx)`. يضمن هذا النهج المكوّن من خطوتين أن يفتح عرض الشريحة عند تكبير 100 ٪.

#### الخطوة 1: إنشاء كائن العرض التقديمي
أنشئ مثيلًا جديدًا من `Presentation`:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class SetZoomFeature {
    public static void main(String[] args) {
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation presentation = new Presentation();
```

#### الخطوة 2: ضبط مستوى تكبير الشريحة
`setScale(int percent)` يحدد مستوى التكبير لعرض الشريحة كنسبة مئوية من الحجم الأصلي.

```java
// Set slide view zoom to 100%
presentation.getViewProperties().getSlideViewProperties().setScale(100);
```  
*لماذا هذه الخطوة؟* يضمن ضبط المقياس أن جميع عناصر الشريحة تتناسب مع المنطقة المرئية، مما يلغي الحاجة إلى تعديلات يدوية أثناء العرض الحي.

#### الخطوة 3: حفظ العرض التقديمي
اكتب التغييرات مرة أخرى إلى ملف PPTX:

```java
// Save with PPTX format
try {
    presentation.save(dataDir + "Zoom_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```  
*لماذا الحفظ بصيغة PPTX؟* يحتفظ PPTX بجميع إعدادات العرض وهو مدعوم على نطاق واسع من قبل أدوات العرض الحديثة.

### كيفية تعيين تكبير الشريحة في PowerPoint – عرض الملاحظات
ضبط عرض الملاحظات بحيث يتم عرض ملاحظات المقدم أيضًا بالمقياس الصحيح.

**الإجابة المباشرة:** استدعِ `presentation.getViewProperties().getNotesViewProperties().setScale(100)` قبل الحفظ؛ هذا يطابق تكبير عرض الملاحظات مع عرض الشريحة.

#### ضبط تكبير الملاحظات
`setScale(int percent)` يحدد مستوى التكبير لعرض الملاحظات كنسبة مئوية من الحجم الأصلي.

```java
// Set notes view zoom to 100%
presentation.getViewProperties().getNotesViewProperties().setScale(100);
```  
*لماذا هذه الخطوة؟* يضمن التكبير المتسق عبر الشرائح والملاحظات تجربة سلسة للمقدمين الذين ينتقلون بين العروض.

## التطبيقات العملية
سيناريوهات واقعية حيث يكون تعديل التكبير ذا قيمة:
1. **العروض التعليمية** – ضمان أن تكون المخططات والمعادلات مرئية بالكامل للمتعلمين.  
2. **اجتماعات الأعمال** – الحفاظ على قابلية قراءة المقاييس الرئيسية دون الحاجة إلى التكبير اليدوي.  
3. **المؤتمرات عن بُعد** – ضمان أن جميع المشاركين يرون نفس العرض، مما يقلل من سوء التواصل.

## اعتبارات الأداء
للحفاظ على استجابة تطبيق Java الخاص بك عند استخدام Aspose.Slides:
- **إدارة الذاكرة** – استدعِ `presentation.dispose()` بمجرد الانتهاء لتحرير الموارد.  
- **التكبير الفعال** – غير مستويات التكبير فقط عند الحاجة؛ المكالمات غير الضرورية تضيف عبئًا.  
- **المعالجة الدفعية** – عالج عدة عروض تقديمية دفعةً لتقليل وقت إحماء JVM.

## المشكلات الشائعة والحلول
- **العرض لا يمكن حفظه** – تحقق من أذونات الكتابة للمجلد المستهدف وتأكد من عدم قفل الملف من عملية أخرى.  
- **قيمة التكبير تبدو متجاهلة** – تأكد من أنك تصل إلى `getViewProperties()` على نفس كائن `Presentation` قبل استدعاء `save()`.  
- **أخطاء نفاد الذاكرة** – استدعِ `presentation.dispose()` داخل كتلة `finally` وفكر في معالجة العروض الكبيرة على أجزاء أصغر.

## الأسئلة المتكررة

**س: هل يمكنني تعيين مستويات تكبير مخصصة غير 100 ٪؟**  
ج: نعم، مرّر أي نسبة مئوية صحيحة إلى `setScale()` لتتناسب مع متطلبات التخطيط الخاصة بك.

**س: ماذا لو لم يتم حفظ العرض التقديمي بشكل صحيح؟**  
ج: تحقق من أذونات الكتابة للمجلد وتأكد من أن الملف غير مقفل من قبل تطبيق آخر.

**س: كيف أتعامل مع العروض التقديمية التي تحتوي على بيانات حساسة باستخدام Aspose.Slides؟**  
ج: عالج الملفات في بيئة آمنة، طبق التشفير إذا لزم الأمر، وامتثل للوائح حماية البيانات ذات الصلة.

**س: هل يدعم اعتماد Maven Aspose Slides إصدارات JDK أخرى؟**  
ج: المصنف `jdk16` يستهدف JDK 16، لكن Aspose توفر مصنفات لـ JDK 8، 11، 17، و 21—اختر ما يتطابق مع بيئة تشغيلك.

**س: هل يمكنني تطبيق نفس إعدادات التكبير على عدة عروض تقديمية تلقائيًا؟**  
ج: نعم، ضع الكود داخل حلقة تقوم بتحميل كل عرض تقديمي، تعيين المقياس، وحفظ الملف.

## الموارد
- **الوثائق**: [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)  
- **التنزيل**: [Latest Release](https://releases.aspose.com/slides/java/)  
- **شراء الترخيص**: [Buy Now](https://purchase.aspose.com/buy)  
- **تجربة مجانية**: [Get Started](https://releases.aspose.com/slides/java/)  
- **رخصة مؤقتة**: [Apply Here](https://purchase.aspose.com/temporary-license/)  
- **منتدى الدعم**: [Aspose Community Support](https://forum.aspose.com/c/slides/11)

استكشف هذه الموارد لتعميق فهمك وتعزيز عروض PowerPoint الخاصة بك باستخدام Aspose.Slides for Java. تقديم موفق!

---

**Last Updated:** 2026-10-08  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية تغيير عرض شريحة Master في PowerPoint برمجيًا باستخدام Aspose.Slides for Java](/slides/java/animations-transitions/set-presentation-view-type-aspose-slides-java/)
- [إنشاء صور مصغرة لملاحظات شرائح PowerPoint باستخدام Aspose.Slides for Java](/slides/java/headers-footers-notes/create-powerpoint-slide-notes-thumbnail-aspose-slides-java/)
- [كيفية تحويل شريحة PowerPoint إلى PDF مع الملاحظات باستخدام Aspose.Slides for Java](/slides/java/presentation-operations/convert-powerpoint-slide-to-pdf-notes-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
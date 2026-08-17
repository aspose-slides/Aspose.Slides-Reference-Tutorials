---
date: '2026-05-29'
description: دليل خطوة بخطوة لتحريك المخطط في PowerPoint باستخدام Aspose.Slides for
  Java. تعلم كيفية إضافة الرسوم المتحركة إلى فئات المخطط، وضبط التأثيرات، وتصدير العرض.
keywords:
- animate chart in powerpoint
- how to animate chart
- add animation to chart
- create animated chart powerpoint
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Step‑by‑step guide to animate chart in PowerPoint with Aspose.Slides
    for Java. Learn to add animation to chart categories, set effects, and export
    the deck.
  headline: How to animate chart in PowerPoint using Aspose.Slides for Java
  type: TechArticle
- description: Step‑by‑step guide to animate chart in PowerPoint with Aspose.Slides
    for Java. Learn to add animation to chart categories, set effects, and export
    the deck.
  name: How to animate chart in PowerPoint using Aspose.Slides for Java
  steps:
  - name: '**Load the Presentation**'
    text: '**Load the Presentation**'
  - name: '**Retrieve the Chart**'
    text: '**Retrieve the Chart**'
  - name: '**Build the Animation Timeline**'
    text: '**Build the Animation Timeline**'
  - name: '**Save the Modified Presentation**'
    text: '**Save the Modified Presentation**'
  - name: '**Business Reports:** Animate quarterly KPIs to keep executives engaged.'
    text: '**Business Reports:** Animate quarterly KPIs to keep executives engaged.'
  - name: '**Educational Slides:** Reveal data points one at a time during lectures
      for better retention.'
    text: '**Educational Slides:** Reveal data points one at a time during lectures
      for better retention.'
  - name: '**Product Launch Decks:** Highlight launch metrics with dynamic visuals
      that draw investor attention.'
    text: '**Product Launch Decks:** Highlight launch metrics with dynamic visuals
      that draw investor attention.'
  type: HowTo
- questions:
  - answer: A free trial lets you develop and test, but a full license is required
      for production deployments.
    question: Do I need a paid license to use animation features?
  - answer: Aspose.Slides for Java supports JDK 16 and newer, including JDK 17, 19,
      21.
    question: Which Java versions are supported?
  - answer: Yes – set the loop to target a specific series or use `EffectChartMinorGroupingType.BySeries`
      to focus on one series.
    question: Can I animate only a single series instead of all categories?
  - answer: Use Aspose.Slides’ `SlideShow` API to render the slide deck as a video
      or GIF for quick previews.
    question: How can I preview animations without opening PowerPoint?
  - answer: Animations are stored in the PPTX format and are supported by modern desktop
      PowerPoint, PowerPoint Online, and most mobile PowerPoint apps.
    question: Will the animated chart work on all PowerPoint viewers?
  type: FAQPage
title: كيفية تحريك المخطط في PowerPoint باستخدام Aspose.Slides for Java
url: /ar/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تحريك المخطط في PowerPoint باستخدام Aspose.Slides for Java

## المقدمة
تحويل المخطط في PowerPoint من أرقام ثابتة إلى قصة تجذب الانتباه. في هذا الدرس ستتعلم **كيفية تحريك المخطط في PowerPoint** برمجياً باستخدام Aspose.Slides for Java، بحيث يمكنك إضافة حركة لكل فئة من فئات المخطط، التحكم في التوقيت، وتقديم عرض مصقول دون جهد يدوي.

**ما ستتعلمه**
- تثبيت وتكوين Aspose.Slides for Java.  
- تطبيق تأثيرات التحريك على فئات المخطط الفردية.  
- حفظ العرض التقديمي مع الحفاظ على بيانات التحريك.  

قبل أن نبدأ، دعنا نتأكد من المتطلبات المسبقة التي تحتاجها.

## إجابات سريعة
- **ماذا يعني “تحريك المخطط في PowerPoint”؟** يعني تطبيق تأثيرات حركة (تلاشي، ظهور، طيران‑إلى الداخل، إلخ) على عناصر المخطط بحيث تُعرض تلقائياً أثناء عرض الشرائح.  
- **أي مكتبة توفر هذه القدرة؟** Aspose.Slides for Java (الإصدار 25.4 أو أحدث).  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة [Free Trial](https://releases.aspose.com/slides/java/) تكفي للبرمجة والاختبار؛ الترخيص الكامل مطلوب للنشر في بيئات الإنتاج.  
- **هل يمكن استهداف فئة مخطط واحدة؟** نعم – يمكنك تحريك الفئات واحدةً تلو الأخرى أو تجميعها حسب السلسلة.  
- **ما نسخة Java المدعومة؟** JDK 16 أو أحدث (بما في ذلك JDK 17، 19، 21).

## ما هو تحريك المخطط في PowerPoint؟
*تشير عبارة “تحريك المخطط في PowerPoint” إلى إضافة تأثيرات بصرية زمنية إلى عناصر المخطط بحيث تظهر بشكل متسلسل أثناء عرض الشرائح. يساعد هذا النهج على توجيه انتباه الجمهور، وتأكيد نقاط البيانات الرئيسية، وجعل العرض التقديمي أكثر جاذبية وتذكراً.*

## لماذا تستخدم Aspose.Slides for Java لتحريك المخططات؟
Aspose.Slides يدعم **أكثر من 50 تنسيق إخراج** ويمكنه معالجة عروض تقديمية تحتوي على **حتى 500 شريحة** دون تحميل الملف بالكامل إلى الذاكرة، مما يحقق **تقليل بنسبة 30 % في استهلاك الذاكرة** مقارنةً بأتمتة Office الأصلية. توفر واجهة برمجة التحريك تحكمًا دقيقًا في نوع التأثير، المشغل، والتوقيت—كل ذلك من خلال كود Java نقي.

## المتطلبات المسبقة
- **JDK 16 أو أحدث** مثبت على جهاز التطوير الخاص بك.  
- معرفة أساسية ببرمجة Java.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو أي محرر نصوص تفضله.  

## المكتبات والاعتمادات المطلوبة
ستحتاج إلى Aspose.Slides for Java. اختر مدير الحزم الذي يتوافق مع نظام البناء الخاص بك.

### تثبيت Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تثبيت Gradle
أدخل هذا السطر في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
احصل على أحدث الملفات الثنائية من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/). يمكنك أيضاً الاطلاع على [Documentation](https://reference.aspose.com/slides/java/) الكاملة.

#### الحصول على الترخيص
ابدأ بـ [Free Trial](https://releases.aspose.com/slides/java/) أو اطلب ترخيصًا مؤقتًا. للاستخدام التجاري، يمكنك [Purchase a License](https://purchase.aspose.com/buy) أو [Request Temporary License](https://purchase.aspose.com/temporary-license/). إذا احتجت مساعدة، زر [Aspose Support Forum](https://forum.aspose.com/c/slides/11).

## التهيئة الأساسية والإعداد
فئة `Presentation` هي الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة. أنشئ مثيلاً لتحميل أو بناء عرض تقديمي:

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // Perform operations on the presentation...
        pres.dispose();  // Remember to dispose when done
    }
}
```

## دليل التنفيذ

### كيف تحرك فئات المخطط في PowerPoint باستخدام Aspose.Slides for Java؟
حمّل العرض التقديمي، حدد المخطط، أنشئ خطًا زمنيًا للتحريك، ثم احفظ الملف. يتعامل هذا التدفق المكوّن من أربع خطوات مع كل شيء من إدخال/إخراج الملفات إلى تكوين التأثيرات بنمط مختصر وقابل لإعادة الاستخدام.

### تحريك عناصر فئات المخطط
يمكن أن يحسن تحريك فئات المخطط من فهم البيانات بشكل كبير. فيما يلي دليل خطوة بخطوة.

#### تنفيذ خطوة بخطوة
1. **Load the Presentation**  
   فئة `Presentation` تقوم بتحميل ملف PPTX موجود يحتوي بالفعل على مخطط.  

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation presentation = new Presentation(dataDir + "/ExistingChart.pptx");
```

2. **Retrieve the Chart**  
   فئة `Chart` تمثل شكل المخطط؛ تحصل عليها من مجموعة الأشكال في الشريحة.  

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0); // Assumes the first shape is a chart
```

3. **Build the Animation Timeline**  
   `Effect` يمثل تأثير تحريك يُطبق على عنصر شريحة، مثل التلاشي أو الطيران‑إلى الداخل. يتيح لك خط الزمن `ISlide` إضافة كائنات `Effect`. `EffectType.Fade` يُنشئ تلاشيًا، بينما `EffectTriggerType.OnClick` يحدد متى يبدأ التأثير.  

```java
import com.aspose.slides.Sequence;
import com.aspose.slides.EffectType;
import com.aspose.slides.EffectSubtype;
import com.aspose.slides.EffectTriggerType;

Sequence mainSequence = (Sequence) slide.getTimeline().getMainSequence();

// Add fade effect to the entire chart
mainSequence.addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Animate each category element in the chart
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        mainSequence.addEffect(chart,
            EffectChartMinorGroupingType.ByElementInCategory,
            i, j,
            EffectType.Appear,
            EffectSubtype.None,
            EffectTriggerType.AfterPrevious);
    }
}
```

   *نصيحة:* استخدم `EffectChartMinorGroupingType.ByCategory` لتحريك كل فئة على حدة.

4. **Save the Modified Presentation**  
   احفظ التغييرات باستخدام `presentation.save`. يضمن `SaveFormat.Pptx` بقاء الملف قابلاً للتحرير بالكامل في PowerPoint.  

```java
String outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.save(outputDir + "/AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## المشكلات الشائعة والحلول
- **Chart not found:** تحقق من أن المخطط هو الشكل الأول (`slide.getShapes().get_Item(0)`) أو عدل الفهرس وفقًا لذلك.  
- **IllegalArgumentException:** تأكد من توافق قيم `EffectType` و `EffectTriggerType` مع عدد سلاسل المخطط.  
- **Memory leaks:** استدعِ دائمًا `presentation.dispose()` بعد المعالجة لتحرير الموارد الأصلية.

## التطبيقات العملية
1. **Business Reports:** تحريك مؤشرات الأداء ربع السنوية لإبقاء التنفيذيين مهتمين.  
2. **Educational Slides:** كشف نقاط البيانات واحدةً تلو الأخرى أثناء المحاضرات لتحسين الاستيعاب.  
3. **Product Launch Decks:** إبراز مقاييس الإطلاق بصور ديناميكية تجذب انتباه المستثمرين.

## اعتبارات الأداء
- **Memory Management:** `presentation.dispose()` يحرر الذاكرة الأصلية؛ إهماله قد يسبب أخطاء نفاد الذاكرة في العروض الكبيرة.  
- **Animation Load:** قلل عدد التحريكات إلى **لا تزيد عن 150 تأثيرًا لكل شريحة** للحفاظ على سلاسة التشغيل على الأجهزة القديمة.  
- **Version Updates:** حافظ على تحديث Aspose.Slides؛ كل إصدار يضيف أنواع تأثيرات جديدة وتحسينات في الأداء.

## الخلاصة
باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية تحريك المخطط في PowerPoint** باستخدام Aspose.Slides for Java. لقد قمت بتثبيت المكتبة، بناء خط زمني للتحريك لفئات المخطط، وتصدير ملف PPTX متحرك بالكامل. جرّب قيم `EffectType` أخرى مثل `FlyIn` أو `Zoom` وادمجها مع انتقالات الشرائح للحصول على تجربة أغنى.

## الأسئلة المتكررة

**س: هل أحتاج إلى ترخيص مدفوع لاستخدام ميزات التحريك؟**  
ج: نسخة التجربة المجانية تسمح لك بالتطوير والاختبار، لكن الترخيص الكامل مطلوب للنشر في بيئات الإنتاج.

**س: ما إصدارات Java المدعومة؟**  
ج: Aspose.Slides for Java يدعم JDK 16 وأحدث، بما في ذلك JDK 17، 19، 21.

**س: هل يمكن تحريك سلسلة واحدة فقط بدلاً من جميع الفئات؟**  
ج: نعم – اضبط الحلقة لاستهداف سلسلة محددة أو استخدم `EffectChartMinorGroupingType.BySeries` للتركيز على سلسلة واحدة.

**س: كيف يمكنني معاينة التحريكات دون فتح PowerPoint؟**  
ج: استخدم API `SlideShow` في Aspose.Slides لتوليد عرض الشرائح كفيديو أو GIF لمعاينات سريعة.

**س: هل سيعمل المخطط المتحرك على جميع عارضات PowerPoint؟**  
ج: تُحفظ التحريكات في تنسيق PPTX وتُدعمها إصدارات PowerPoint الحديثة على سطح المكتب، PowerPoint Online، ومعظم تطبيقات PowerPoint على الهواتف المحمولة.

---

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

## دروس ذات صلة

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create and Format PowerPoint Charts Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)
- [Create Dynamic Powerpoint Java – Aspose.Slides Animation Types Guide](/slides/java/animations-transitions/aspose-slides-java-animation-comparison-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
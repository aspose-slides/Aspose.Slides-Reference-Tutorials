---
date: '2026-07-17'
description: تعلم كيفية إضافة مخططات Sunburst في PowerPoint باستخدام Aspose Slides
  for Java. دليل خطوة بخطوة يغطي الإعداد، إنشاء المخطط، التخصيص، وحالات الاستخدام
  الواقعية.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: كيفية إضافة مخططات Sunburst في PowerPoint باستخدام Aspose Slides for
  Java. اتبع هذا البرنامج التعليمي لإعداد المكتبة، إنشاء مخطط، تخصيص نقاط البيانات،
  وتطبيقه على المشاريع الحقيقية.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: كيفية إضافة مخططات Sunburst في PowerPoint باستخدام Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: كيفية إضافة مخططات Sunburst في PowerPoint باستخدام Aspose (Java)
url: /ar/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخططات Sunburst في PowerPoint باستخدام Aspose (Java)

## المقدمة

إضافة مخطط Sunburst إلى عرض PowerPoint يمكن أن يحول جدول بيانات مسطح إلى هيكل بصري جذاب على الفور. في هذا الدرس ستتعلم **كيفية إضافة مخططات Sunburst** في PowerPoint باستخدام Aspose.Slides for Java، بدءًا من إعداد البيئة إلى ضبط الألوان والتسميات بدقة. سواء كنت تبني لوحة تحكم مبيعات، أو تفصيل مهام مشروع، أو مجموعة شرائح تعليمية، فإن الخطوات أدناه ستوفر لك حلاً جاهزًا للإنتاج.

**ما ستتعلمه**
- كيفية تكوين Aspose.Slides في مشروع Maven أو Gradle  
- كيفية إنشاء عرض تقديمي جديد وإدراج مخطط Sunburst  
- كيفية تخصيص نقاط البيانات، والتسميات، وألوان التعبئة  
- سيناريوهات واقعية حيث تتألق مخططات Sunburst  

لنبدأ ولنرَ مدى سهولة تحويل بيانات الهيكل الهرمي الخام إلى تصور PowerPoint مصقول.

## إجابات سريعة
- **المكتبة الأساسية؟** Aspose.Slides for Java  
- **نوع المخطط المدعوم؟** Sunburst (هرمي شعاعي)  
- **الحد الأدنى لإصدار Java؟** JDK 16  
- **الوقت النموذجي للتنفيذ؟** 10‑15 دقيقة لمخطط أساسي  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، ترخيص Aspose صالح  

## ما هو مخطط Sunburst؟
مخطط Sunburst هو رسم بياني شعاعي يُظهر البيانات الهرمية عن طريق تداخل الحلقات من نقطة مركزية إلى الخارج. إنه مثالي لعرض العلاقات متعددة المستويات مثل هياكل المنظمة، فئات المنتجات، أو شجرات نظام الملفات. كل حلقة متحدة المركز تمثل مستوىً من الهرمية، وحجم كل قطاع يعكس قيمته الكمية، مما يتيح للمشاهدين فهم الهيكل والحجم بسرعة.

## لماذا تستخدم Aspose.Slides for Java؟
يدعم Aspose.Slides **أكثر من 50 نوعًا من المخططات** ويمكنه معالجة العروض التقديمية التي تحتوي على **ما يصل إلى 10,000 شريحة** دون تحميل الملف بالكامل إلى الذاكرة، مما يوفر أداءً عاليًا لتقارير على نطاق المؤسسة. يعمل عبر الأنظمة، ويقدم تغطية شاملة للـ API، ويتضمن خيارات ترخيص قوية تُزيل حدود التقييم، مما يجعله مثاليًا لبيئات الإنتاج.

## المتطلبات المسبقة
- **Java Development Kit (JDK)** 16 أو أحدث  
- **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر متوافق مع Java  
- إلمام أساسي بصياغة Java وأدوات بناء Maven/Gradle  

## إعداد Aspose.Slides for Java

### تبعية Maven
أضف قطعة Aspose.Slides Maven إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تبعية Gradle
إذا كنت تفضل Gradle، أدرج السطر التالي في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
يمكنك أيضًا تنزيل أحدث ملف JAR مباشرةً من صفحة الإصدارات الرسمية: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
لتشغيل البرنامج دون حدود التقييم، احصل على ترخيص:
- **نسخة تجريبية مجانية** – ترخيص مؤقت للتقييم السريع.  
- **ترخيص مؤقت** – اطلب واحدًا من [موقع Aspose](https://purchase.aspose.com/temporary-license).  
- **شراء كامل** – اشترِ اشتراكًا للاستخدام غير المحدود في الإنتاج.

### التهيئة الأساسية
فئة `Presentation` هي نقطة الدخول لإنشاء أو فتح ملفات PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## دليل التنفيذ

### كيفية إضافة مخطط Sunburst إلى عرض PowerPoint باستخدام Aspose.Slides for Java؟

حمّل `Presentation` جديدًا، أضف شريحة، أدخل `IChart` من النوع `ChartType.Sunburst`، ثم استدعِ `save`. هذا النمط المكوّن من ثلاث خطوات يخلق مخطط Sunburst كامل الوظائف جاهزًا لمزيد من التخصيص.

#### الخطوة 1: تهيئة الـ Presentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### الخطوة 2: إضافة مخطط Sunburst
واجهة `IChart` تُعرّف كائن مخطط يمكن وضعه على أي شريحة. هنا نضيف مخطط Sunburst عند الإحداثيات (100, 100) بحجم 450 × 400 نقطة.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### الخطوة 3: حفظ الـ Presentation
احفظ دائمًا تغييراتك باستدعاء `save`. يمكنك اختيار PPTX أو PDF أو أي من أكثر من 50 تنسيق إخراج مدعوم.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### تعديل نقاط البيانات في المخطط

#### نظرة عامة
يمكنك تخصيص كل شريحة من مخطط Sunburst—التسميات، الألوان، والظهور—من خلال مجموعة نقاط البيانات الخاصة بالمخطط.

#### الخطوة 1: الوصول إلى مجموعة نقاط البيانات
السلسلة الأولى في المخطط تحتوي على مجموعة من كائنات `IChartDataPoint` التي تمثل كل شريحة.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### الخطوة 2: إظهار القيمة لنقطة بيانات محددة
عيّن `IsValueShown` إلى `true` على نقطة البيانات المطلوبة لعرض قيمتها الرقمية مباشرةً على الشريحة.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### الخطوة 3: تعديل تنسيقات التسميات
ضبط ظهور التسميات، لون الخط، والخلفية لتحسين قابلية القراءة.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### الخطوة 4: تعيين لون التعبئة لنقاط البيانات
خصص لون تعبئة الشرائح الفردية ليتطابق مع لوحة ألوان علامتك التجارية أو لتسليط الضوء على القطاعات الرئيسية.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### الخطوة 5: حفظ العرض المعدل
احفظ المخطط المخصص عن طريق حفظ العرض مرة أخرى.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## تطبيقات عملية

1. **تحليلات الأعمال** – تصور المبيعات حسب المنطقة → خط المنتج → SKU في عرض شعاعي واحد.  
2. **إدارة المشاريع** – إظهار هياكل تفصيل العمل، من المراحل إلى المهام إلى المهام الفرعية.  
3. **التعليم** – رسم خرائط هياكل المنهج، مثل الأقسام → الدورات → الوحدات.  

## اعتبارات الأداء

- **كفاءة الذاكرة:** Aspose.Slides يبث البيانات، لذا حتى مجموعة مكوّنة من 500 صفحة مع مخططات متعددة تبقى تحت 200 ميغابايت من الذاكرة.  
- **جمع القمامة:** حرّر كائنات الشرائح (`slide.dispose()`) عندما لا تكون بحاجة إليها لتجنب تسرب الذاكرة.  

## الأسئلة المتكررة

**س: ما هو مخطط Sunburst؟**  
**ج:** مخطط Sunburst يُظهر البيانات الهرمية في حلقات متحدة المركز، حيث تمثل كل حلقة مستوىً من الهرمية.

**س: كيف أقوم بتثبيت Aspose.Slides for Java باستخدام Maven؟**  
**ج:** أضف تبعية Maven الموضحة في قسم “Maven Dependency” إلى ملف `pom.xml` وشغّل `mvn clean install`.

**س: هل يمكنني تخصيص أنواع مخططات أخرى باستخدام Aspose.Slides؟**  
**ج:** نعم، المكتبة تدعم أكثر من 50 نوعًا من المخططات، بما في ذلك الأعمدة، الخطوط، الدوائر، ومخططات الرادار.

**س: عرضي التقديمي لا يتم حفظه—ماذا يجب أن أتحقق؟**  
**ج:** تأكد من صحة مسار الملف، وجود الدليل، وأن لديك صلاحيات كتابة. كما تأكد من استدعاء طريقة `Presentation.save()`.

**س: أين يمكنني الحصول على مزيد من المساعدة أو الأمثلة؟**  
**ج:** زر [منتدى Aspose](https://forum.aspose.com/c/slides/11) أو استشر [مرجع Aspose.Slides الرسمي](https://reference.aspose.com/slides/java/).

## موارد
- **الوثائق:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **المرجع (lowercase):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **منتدى المجتمع:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **التنزيلات:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**آخر تحديث:** 2026-07-17  
**تم الاختبار مع:** Aspose.Slides for Java 24.12  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [تحريك المخططات في PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [إنشاء مخطط في Java باستخدام Aspose.Slides – إضافة وتحقق من المخططات](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-03-15'
description: تعلم كيفية إنشاء مخطط PowerPoint باستخدام Aspose.Slides للغة Java، وبناء
  مخططات أعمدة مجمعة ديناميكية، وحساب صيغ المخطط في العروض التقديمية الآلية.
keywords:
- Aspose.Slides Java
- dynamic PowerPoint charts
- PowerPoint presentation automation
title: كيفية إنشاء مخطط PowerPoint باستخدام Aspose.Slides للغة Java
url: /ar/java/charts-graphs/aspose-slides-java-add-charts-formulas/
weight: 1
---

 all shortcodes and code block placeholders unchanged.

We need to keep markdown formatting.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان Aspose.Slides Java: إضافة المخططات والصيغ إلى عروض PowerPoint

## مقدمة

إنشاء عروض PowerPoint جذابة أمر حاسم عند نقل البيانات المعقدة بفعالية. باستخدام Aspose.Slides for Java، يمكنك **إنشاء مخطط PowerPoint** برمجيًا، أتمتة إنشاء مخططات PowerPoint ديناميكية، وإدراج صيغ مخطط محسوبة—كل ذلك دون الحاجة إلى فتح واجهة المستخدم. يشرح هذا البرنامج التعليمي كيفية إعداد المكتبة، إدراج مخطط عمودي مجمع، تطبيق الصيغ، وحفظ الملف النهائي.

**ما ستتعلمه:**
- إعداد Aspose.Slides for Java
- إنشاء عرض PowerPoint وإدراج المخططات
- الوصول إلى بيانات المخطط وتعديلها باستخدام الصيغ
- حساب صيغ المخطط وحفظ العرض التقديمي

لنبدأ بمراجعة المتطلبات المسبقة!

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إنشاء مخطط PowerPoint تلقائيًا باستخدام Aspose.Slides for Java.  
- **ما نوع المخطط الذي تم توضيحه؟** مخطط عمودي مجمع.  
- **هل يمكن حساب الصيغ؟** نعم—استخدم `calculateFormulas()` لتقييم مخططات PowerPoint الديناميكية.  
- **ما أداة البناء الموصى بها؟** Maven (أو Gradle) لتكامل Aspose Slides.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص الكامل يزيل قيود التقييم.

## ما هو “إضافة مخطط إلى PowerPoint” باستخدام Aspose.Slides؟
توفر Aspose.Slides for Java واجهة برمجة تطبيقات غنية تتيح للمطورين إنشاء ملفات PowerPoint وتعديلها وحفظها برمجيًا. باستخدام قدرة **add chart to PowerPoint**، يمكنك توليد تمثيلات بصرية للبيانات في الوقت الفعلي، وهو مثالي للتقارير، ولوحات التحكم، أو عروض الشرائح الآلية.

## لماذا نستخدم مخطط عمودي مجمع؟
يتيح لك مخطط عمودي مجمع مقارنة عدة سلاسل بيانات جنبًا إلى جنب، مما يجعل الاتجاهات والاختلافات واضحة على الفور. وهو خيار شائع للتقارير المالية، ولوحات مبيعات، ومقاييس الأداء—بالضبط في السيناريوهات التي تتألق فيها مخططات PowerPoint الديناميكية.

## كيفية إنشاء مخطط PowerPoint باستخدام Aspose.Slides for Java

### المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

- **مكتبة Aspose.Slides for Java**: الإصدار 25.4 أو أحدث مطلوب.  
- **مجموعة تطوير جافا (JDK)**: يجب تثبيت JDK 16 أو أعلى وتكوينه على نظامك.  
- **بيئة التطوير**: يوصى باستخدام IDE مثل IntelliJ IDEA أو Eclipse ولكن ليس إلزاميًا.  

فهم أساسي لمفاهيم برمجة جافا مثل الفئات، والطرق، ومعالجة الاستثناءات ضروري. إذا كنت جديدًا على هذه المواضيع، فكر في مراجعة دروس تمهيدية أولاً.

#### إعداد Aspose.Slides for Java

##### تبعية Maven (maven for aspose slides)
لإضافة Aspose.Slides إلى مشروعك باستخدام Maven، أضف التبعية التالية إلى ملف `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

##### تبعية Gradle
إذا كنت تستخدم Gradle، أضف هذا إلى ملف `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

##### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث نسخة من Aspose.Slides for Java من [Aspose Releases](https://releases.aspose.com/slides/java/).

##### الحصول على الترخيص
- **نسخة تجريبية مجانية**: ابدأ بنسخة تجريبية مجانية لاستكشاف الإمكانات.  
- **ترخيص مؤقت**: احصل على ترخيص مؤقت لاختبار موسع [هنا](https://purchase.aspose.com/temporary-license/).  
- **شراء**: فكر في شراء ترخيص كامل إذا وجدت الأداة ذات قيمة.

### التهيئة الأساسية

بعد الإعداد، قم بتهيئة بيئة Aspose.Slides الخاصة بك:

```java
Presentation presentation = new Presentation();
try {
    // Your code here
} finally {
    if (presentation != null) presentation.dispose();
}
```

## دليل التنفيذ

تم تقسيم هذا القسم إلى خطوات لمساعدتك على فهم كل جزء بوضوح.

### الخطوة 1: تهيئة العرض التقديمي
ابدأ بإنشاء كائن `Presentation` جديد:

```java
Presentation presentation = new Presentation();
```

### الخطوة 2: الوصول إلى الشريحة الأولى
احصل على الشريحة الأولى حيث ستضع المخطط الخاص بك:

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

### الخطوة 3: إضافة مخطط عمودي مجمع
أضف المخطط إلى الشريحة عند الإحداثيات والأبعاد المحددة:

```java
IChart chart = slide.getShapes().addChart(
    ChartType.ClusteredColumn, 
    150, 150, 
    500, 300
);
```
**شرح المعلمات:**
- `ChartType`: يحدد نوع المخطط (هنا، مخطط عمودي مجمع).  
- الإحداثيات (x, y): الموقع على الشريحة.  
- العرض والارتفاع: أبعاد المخطط.

### الخطوة 4: الوصول إلى دفتر بيانات المخطط
احصل على دفتر العمل المرتبط بالمخطط الخاص بك:

```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```

### الخطوة 5: تعيين الصيغ (calculate chart formulas)

**الصيغة في الخلية B2**  
```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

**صيغة نمط R1C1 في الخلية C2**  
```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```
تسمح هذه الصيغ للمخطط بالتحديث تلقائيًا كلما تغيرت البيانات الأساسية.

### الخطوة 6: حساب جميع الصيغ
استدعِ طريقة الحساب على دفتر العمل الخاص بك بحيث يعكس المخطط القيم الأحدث:

```java
workbook.calculateFormulas();
```

### الخطوة 7: حفظ العرض التقديمي الخاص بك
احفظ عملك باستخدام اسم ملف وتنسيق محددين:

```java
String outpptxFile = "YOUR_OUTPUT_DIRECTORY" + File.separator + "ChartDataCell_Formulas_out.pptx";
presentation.save(outpptxFile, SaveFormat.Pptx);
```
تأكد من استبدال `YOUR_OUTPUT_DIRECTORY` بمسار فعلي حيث تريد تخزين الملف.

## تطبيقات عملية
- **التقارير المالية**: أتمتة إنشاء المخططات للتقارير المالية الشهرية أو الربع سنوية.  
- **تصوير البيانات في التعليم**: توليد شرائح مدفوعة بالبيانات بسرعة لتعليم المفاهيم المعقدة.  
- **تحليلات الأعمال**: تحسين العروض التقديمية برؤى بيانات ديناميكية باستخدام الصيغ المحسوبة.

فكر في دمج Aspose.Slides في سير العمل الحالي لتبسيط إعداد العروض، خاصةً عند التعامل مع مجموعات بيانات كبيرة تتطلب تحديثات متكررة.

## اعتبارات الأداء
حسّن الأداء عن طريق:

- إدارة الموارد بكفاءة؛ دائمًا قم بتحرير كائنات `Presentation`.  
- تقليل عدد المخططات وتعقيدها على شريحة واحدة إذا كان وقت المعالجة أمرًا حاسمًا.  
- استخدام عمليات دفعة لعدة مخططات لتقليل الحمل.

اتباع هذه الممارسات المثلى يضمن تشغيلًا سلسًا حتى في بيئات ذات موارد محدودة.

## الخلاصة
بحلول الآن، يجب أن تكون مجهزًا جيدًا **لإنشاء مخطط PowerPoint** باستخدام Aspose.Slides for Java، بناء عروض تقديمية ديناميكية، والاستفادة من صيغ المخططات المحسوبة. هذه المكتبة القوية توفر الوقت وترفع جودة تصورات البيانات الخاصة بك. استكشف المزيد من الميزات من خلال الغوص في [Aspose Documentation](https://reference.aspose.com/slides/java/) وفكر في توسيع مشروعك بقدرات إضافية من Aspose.Slides.

### الخطوات التالية
- جرّب أنواعًا مختلفة من المخططات والتصاميم.  
- دمج وظائف Aspose.Slides في تطبيقات جافا الأكبر.  
- استكشف مكتبات Aspose الأخرى لتعزيز معالجة المستندات عبر الصيغ.

## الأسئلة المتكررة

**س: ما هو الحد الأدنى لإصدار JDK المطلوب لـ Aspose.Slides؟**  
ج: يوصى بـ JDK 16 أو أعلى لأسباب التوافق والأداء.

**س: هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**  
ج: نعم، ولكن مع قيود على الوظائف. احصل على ترخيص مؤقت أو كامل للاستخدام غير المقيد.

**س: كيف أتعامل مع الاستثناءات عند استخدام Aspose.Slides؟**  
ج: استخدم كتل try‑finally لضمان تحرير الموارد، كما هو موضح في مثال التهيئة الأساسية.

**س: هل يمكنني إضافة مخططات متعددة إلى نفس الشريحة؟**  
ج: بالتأكيد—أنشئ وضع كل مخطط على حدة داخل حدود الشريحة.

**س: هل يمكن تحديث بيانات المخطط دون إعادة إنشاء العرض التقديمي بالكامل؟**  
ج: نعم—قم بالتلاعب مباشرةً بدفتر بيانات المخطط وأعد حساب الصيغ.

استكشف المزيد من الموارد عبر الروابط أدناه:
- [Aspose Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-03-15  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
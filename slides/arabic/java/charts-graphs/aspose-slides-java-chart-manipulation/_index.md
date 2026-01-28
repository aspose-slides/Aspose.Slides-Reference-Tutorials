---
date: '2026-01-17'
description: تعلم كيفية إنشاء مخطط في جافا باستخدام Aspose.Slides، إضافة مخطط عمودي
  مجمع، وحفظ العرض التقديمي كملف pptx. دليل خطوة بخطوة لمطوري جافا.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: كيفية إنشاء مخطط في جافا باستخدام Aspose.Slides لجافا
url: /ar/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط في جافا باستخدام Aspose.Slides for Java

## مقدمة
إنشاء تجربة **create chart in java** تبدو احترافية لا يجب أن تكون صداعًا. باستخدام **Aspose.Slides for Java**، يمكنك إضافة المخططات وتنسيقها وحفظها برمجيًا—مثل مخطط عمودي مجمع—مباشرة داخل عروض PowerPoint. في هذا البرنامج التعليمي سنستعرض إعداد المكتبة، تهيئة عرض تقديمي، إدراج مخطط عمودي مجمع، تعديل منطقة الرسم، وأخيرًا حفظ الملف كملف PPTX. في النهاية، ستحصل على مقتطف شفرة قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع جافا.

**ما ستتعلمه**
- كيفية إعداد تبعية Aspose.Slides لـ Maven أو Gradle  
- كيفية **create chart in java** وإضافة مخطط عمودي مجمع  
- كيفية تكوين منطقة الرسم (الموقع، الحجم، التخطيط)  
- كيفية **save presentation as pptx** مع معالجة الموارد بشكل صحيح  

هل أنت مستعد لجعل بياناتك تتحدث بصريًا؟ هيا نبدأ!

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (Maven/Gradle).  
- **ما نوع المخطط الذي تم توضيحه؟** مخطط عمودي مجمع.  
- **كيف أحفظ الملف؟** استخدم `presentation.save(..., SaveFormat.Pptx)`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تغيير منطقة الرسم؟** نعم، يمكنك تعيين X، Y، العرض، الارتفاع ونوع هدف التخطيط.

## ما هو create chart in java؟
إنشاء مخطط في جافا يعني استخدام مكتبة لتوليد كائنات مخطط، تعبئتها بالبيانات، وتضمينها في مستند—هنا، شريحة PowerPoint. تقوم Aspose.Slides بتجريد تفاصيل Office Open XML منخفضة المستوى، مما يتيح لك التركيز على النتيجة البصرية.

## لماذا إضافة مخطط عمودي مجمع باستخدام Aspose.Slides؟
مخطط عمودي مجمع مثالي لمقارنة سلاسل بيانات متعددة جنبًا إلى جنب. يُستخدم على نطاق واسع في تقارير الأعمال، لوحات التحكم، والعروض التقديمية. تمنحك Aspose.Slides تحكمًا كاملاً في الألوان، العلامات، المحاور، والتخطيط دون الحاجة لفتح PowerPoint يدويًا.

## المتطلبات المسبقة
- مكتبة **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).  
- **JDK 16** (أو أحدث) مثبت.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- إلمام أساسي بصياغة Java.

## إعداد Aspose.Slides for Java
### Maven
أضف التبعية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
قم بتضمين المكتبة في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث إصدار من [الموقع الرسمي لـ Aspose](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
استخدم نسخة تجريبية مجانية أو ترخيصًا مؤقتًا للاختبار. اشترِ ترخيصًا كاملًا للنشر في بيئات الإنتاج.

### التهيئة الأساسية والإعداد
ابدأ فئة Java جديدة واستورد الفئة الأساسية:

```java
import com.aspose.slides.Presentation;
```

## دليل التنفيذ
سنستعرض كل خطوة مع شروحات واضحة.

### تهيئة العرض التقديمي ومعالجة الشرائح
#### نظرة عامة
أولاً، أنشئ عرضًا تقديميًا جديدًا واحصل على الشريحة الأولى حيث سيعيش المخطط.

**1. إنشاء وتهيئة عرض تقديمي**

```java
Presentation presentation = new Presentation();
```

**2. الوصول إلى الشريحة الأولى**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. إضافة مخطط عمودي مجمع**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **نصيحة احترافية:** احرص دائمًا على تغليف استخدام العرض التقديمي داخل كتلة `try‑finally` واستدعِ `presentation.dispose()` في قسم `finally` لتحرير الموارد الأصلية.

### تكوين منطقة الرسم
#### نظرة عامة
قم بضبط منطقة رسم المخطط بدقة للتحكم في مكان عرض البيانات داخل الشريحة.

**1. تعيين الموقع والحجم**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. تعريف نوع هدف التخطيط**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### حفظ العرض التقديمي
#### نظرة عامة
بعد تخصيص المخطط، احفظ العرض التقديمي كملف PPTX.

**1. حفظ إلى ملف**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **تحذير:** تأكد من وجود دليل الإخراج وأن التطبيق يمتلك أذونات كتابة؛ وإلا سيفشل عملية الحفظ.

## حالات الاستخدام الشائعة
- **تقارير الأعمال:** تضمين اتجاهات المبيعات ومؤشرات الأداء المالية.  
- **شرائح تعليمية:** تصور نتائج التجارب أو البيانات الإحصائية.  
- **اقتراحات المشاريع:** إبراز المراحل الرئيسية وتخصيص الموارد.  
- **عروض التسويق:** إظهار أداء الحملات بمخططات حية.  
- **تخطيط الفعاليات:** عرض ديموغرافيات الحضور أو تفاصيل الجدول الزمني.

## اعتبارات الأداء
- تخلص من كائنات `Presentation` فورًا لتجنب تسرب الذاكرة.  
- للمجموعات الكبيرة من البيانات، قم بملء سلاسل المخطط تدريجيًا بدلاً من تحميل كل شيء مرة واحدة.  
- استخدم أدوات التحليل المدمجة في Java لمراقبة استخدام الذاكرة أثناء إنشاء المخطط.

## الأسئلة المتكررة

**س: كيف يمكنني إضافة أنواع مخططات أخرى؟**  
ج: استخدم تعداد `ChartType` (مثلًا `ChartType.Pie`، `ChartType.Line`) عند استدعاء `addChart`.

**س: هل يمكنني تخصيص ألوان المخطط؟**  
ج: نعم، يمكنك تعديل تنسيق تعبئة السلسلة أو لوحة ألوان المخطط عبر واجهة `IChart`.

**س: عرضي التقديمي لا يحفظ—ما الخطأ؟**  
ج: تحقق من أن `YOUR_OUTPUT_DIRECTORY` صحيح، موجود، وقابل للكتابة. كما يجب فحص أي أقفال ملفات متبقية.

**س: كيف يمكنني التعامل مع عروض تقديمية ضخمة جدًا بكفاءة؟**  
ج: عالج الشرائح على دفعات، حرّر كل `Presentation` بعد الاستخدام، وفكّر في زيادة حجم الذاكرة المخصصة للـ JVM إذا لزم الأمر.

**س: هل Aspose.Slides مجانية للمشاريع التجارية؟**  
ج: تتوفر نسخة تجريبية مجانية للتقييم، لكن الترخيص المشتري مطلوب للنشر التجاري.

## الموارد
- [التوثيق](https://reference.aspose.com/slides/java/)
- [تحميل Aspose.Slides](https://releases.aspose.com/slides/java/)
- [شراء الترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)
- [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى الدعم](https://forum.aspose.com/c/slides/11)

ابدأ في إنشاء عروض تقديمية بصرية مذهلة باستخدام Aspose.Slides for Java اليوم!

---

**آخر تحديث:** 2026-01-17  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

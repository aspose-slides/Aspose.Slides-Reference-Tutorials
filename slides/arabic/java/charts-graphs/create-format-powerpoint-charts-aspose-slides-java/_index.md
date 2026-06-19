---
date: '2026-03-15'
description: تعلم كيفية إضافة مخطط عمودي مجمع إلى شريحة PowerPoint باستخدام Aspose.Slides
  for Java، مع تغطية خطوات إضافة المخطط إلى الشريحة وإنشاء شريحة PowerPoint باستخدام
  Java بكفاءة.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: إضافة مخطط أعمدة متجمع إلى PPT باستخدام Aspose.Slides Java
url: /ar/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة مخطط عمود مجمع إلى PPT باستخدام Aspose.Slides Java

## المقدمة
في هذا الدليل سوف **تضيف مخطط عمود مجمع** إلى عرض PowerPoint برمجيًا باستخدام Aspose.Slides for Java. سواءً كنت تُنشئ تقارير أعمال، أو عروض تعليمية، أو عروض تسويقية، فإن أتمتة إنشاء المخططات توفر الوقت وتضمن التناسق. سنستعرض إعداد المكتبة، إنشاء شريحة، إضافة المخطط، تطبيق أنماط الخطوط والزوايا المستديرة، وأخيرًا حفظ الملف. في النهاية ستصبح مرتاحًا مع سير العمل الكامل **لإضافة مخطط إلى شريحة** وحتى **إنشاء حلول شريحة PowerPoint مبنية على Java**.

### إجابات سريعة
- **ما هو الصف الأساسي للبدء؟** `Presentation`
- **ما هو نوع المخطط المستخدم؟** `ChartType.ClusteredColumn`
- **كيف تقوم بتمكين الزوايا المستديرة؟** `chart.setRoundedCorners(true);`
- **ما هو التنسيق الموصى به للحفظ؟** `SaveFormat.Pptx`
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم الحصول على ترخيص مدفوع للإنتاج.

## ما هو مخطط العمود المجمع؟
مخطط العمود المجمع يجمع عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يجعله مثاليًا لمقارنة القيم عبر مجموعات مختلفة. يتيح لك Aspose.Slides إنشاء هذا النوع من المخططات بالكامل عبر الكود دون الحاجة لفتح PowerPoint.

## لماذا تستخدم Aspose.Slides for Java لإضافة مخطط عمود مجمع؟
- **أتمتة كاملة** – لا حاجة لتفاعل يدوي مع الواجهة.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **تنسيق غني** – التحكم في أنماط الخطوط، التعبئات، الزوايا المستديرة، وأكثر.  
- **بدون تبعيات COM** – على عكس Office Interop، يعمل بأمان على الخوادم.

## المتطلبات المسبقة
- **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث)  
- **JDK 16** (أو أحدث)  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans  

## إعداد Aspose.Slides for Java
يمكنك إضافة المكتبة عبر Maven أو Gradle أو تحميلها مباشرة.

### استخدام Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### استخدام Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
قم بتحميل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية** – اختبر جميع الميزات دون حدود زمنية.  
- **ترخيص مؤقت** – اطلبه من بوابة Aspose لتقييم كامل الميزات.  
- **شراء** – احصل على ترخيص دائم للاستخدام في الإنتاج.

## دليل التنفيذ

### إنشاء عرض تقديمي وإضافة شريحة
#### نظرة عامة
أولاً، نقوم بإنشاء كائن `Presentation` جديد ونستخرج الشريحة الافتراضية التي تأتي مع ملف جديد.

#### خطوة بخطوة
**1. تهيئة كائن Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. الوصول إلى الشريحة الأولى**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. تحرير الموارد**  
```java
if (presentation != null) presentation.dispose();
```

### إضافة مخطط إلى شريحة
#### نظرة عامة
الآن نقوم بدمج **مخطط عمود مجمع** داخل الشريحة التي أعددناها للتو.

#### خطوة بخطوة
**1. تهيئة كائن Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. الوصول إلى الشريحة الأولى**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. إضافة مخطط عمود مجمع**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. تحرير الموارد**  
```java
if (presentation != null) presentation.dispose();
```

### تنسيق نمط خط المخطط وتعيين الزوايا المستديرة
#### نظرة عامة
حسّن المظهر البصري بتطبيق تعبئة خط صلبة، نمط خط واحد، وزوايا مستديرة.

#### خطوة بخطوة
**1. تهيئة كائن Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. الوصول إلى الشريحة الأولى**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. إضافة مخطط عمود مجمع**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. تعيين تنسيق الخط إلى نوع تعبئة صلبة**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. تطبيق نمط خط واحد**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. تمكين الزوايا المستديرة لمنطقة المخطط**  
```java
chart.setRoundedCorners(true);
```

**7. تحرير الموارد**  
```java
if (presentation != null) presentation.dispose();
```

### حفظ العرض التقديمي
#### نظرة عامة
أخيرًا، نكتب العرض التقديمي إلى القرص بصيغة PPTX.

#### خطوة بخطوة
**1. تهيئة كائن Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. تعريف دليل الإخراج واسم الملف**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. حفظ العرض التقديمي بصيغة PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. تحرير الموارد**  
```java
if (presentation != null) presentation.dispose();
```

## تطبيقات عملية
- **تقارير الأعمال** – أتمتة عروض الشرائح المالية الفصلية بمخططات ديناميكية.  
- **المحتوى التعليمي** – توليد شرائح محاضرات تستخرج البيانات من قاعدة بيانات.  
- **العروض التسويقية** – تصور اتجاهات المنتجات بمخططات مصقولة.

## اعتبارات الأداء
- **إدارة الموارد** – احرص دائمًا على استدعاء `dispose()` أو استخدم try‑with‑resources.  
- **تحسين الذاكرة** – عالج مجموعات البيانات الكبيرة على دفعات أصغر.  
- **أفضل الممارسات** – يفضَّل استخدام هياكل بيانات غير قابلة للتغيير لسلاسل المخطط كلما أمكن.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | تأكد من أن كائن `Presentation` تم إنشاؤه بنجاح قبل الوصول إلى الشرائح. |
| **Chart not appearing** | تحقق من أن أبعاد المخطط (x, y, العرض, الارتفاع) تقع داخل حدود الشريحة. |
| **License not applied** | حمّل ملف الترخيص قبل إنشاء كائن `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## الأسئلة المتكررة

**س: كيف يمكنني إضافة أنواع مختلفة من المخططات باستخدام Aspose.Slides؟**  
ج: استبدل `ChartType.ClusteredColumn` بأي قيمة أخرى من الـ enum مثل `ChartType.Pie` أو `ChartType.Line` أو `ChartType.Bar`.

**س: ماذا أفعل إذا واجهت أخطاء تجميع؟**  
ج: تحقق مرة أخرى من أنك تستخدم JDK 16 أو أحدث وأن تبعية Maven/Gradle تتطابق مع الإصدار المذكور أعلاه.

**س: هل يمكنني ملء المخطط ببيانات من قاعدة بيانات؟**  
ج: نعم. احصل على مجموعة `getChartData()` للمخطط، أنشئ السلاسل والفئات، واملأها بالقيم المستخرجة في وقت التشغيل.

**س: كيف يمكنني تحسين الأداء لعروض تقديمية ضخمة جدًا؟**  
ج: قسّم العمل إلى عدة كائنات `Presentation`، أعد استخدام قوالب المخططات، وتأكد دائمًا من تحرير الكائنات فور الانتهاء.

## الخلاصة
أصبح لديك الآن وصفة شاملة من البداية إلى النهاية **لإضافة مخطط عمود مجمع** إلى شريحة PowerPoint باستخدام Aspose.Slides for Java. جرّب أنواع مخططات أخرى، اربط مصادر بيانات حية، ودمج هذه المنطق في خطوط تقارير أكبر لأتمتة سير عمل العروض التقديمية.

---

**آخر تحديث:** 2026-03-15  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java (JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
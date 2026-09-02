---
date: '2026-09-02'
description: تعلم كيفية إضافة مخطط عمودي مجمع إلى شريحة PowerPoint باستخدام Aspose.Slides
  for Java، مع تغطية إنشاء المخطط، التنسيق، وحفظه كملف PPTX.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: تعلم كيفية إضافة مخطط عمودي مجمع إلى شريحة PowerPoint باستخدام Aspose.Slides
  for Java، مع تغطية إنشاء المخطط، التنسيق، وحفظه كملف PPTX.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: إضافة مخطط عمودي مجمع إلى PPT باستخدام Aspose.Slides Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: إضافة مخطط عمودي مجمع إلى PPT باستخدام Aspose.Slides Java
url: /ar/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مخطط عمود مجمع إلى PPT باستخدام Aspose.Slides Java

## المقدمة
في هذا الدليل ستقوم **بإضافة مخطط عمود مجمع** إلى عرض PowerPoint برمجياً باستخدام Aspose.Slides for Java. سواءً كنت تبني تقارير أعمال، أو عروض تعليمية، أو عروض تسويق، فإن أتمتة إنشاء المخططات توفر الوقت وتضمن الاتساق. سنستعرض إعداد المكتبة، إنشاء شريحة، إضافة المخطط، تطبيق أنماط الخطوط والزوايا المستديرة، وأخيراً حفظ الملف بصيغة PPTX. في النهاية ستكون مرتاحاً مع سير العمل الكامل **لإضافة مخطط إلى شريحة** وحتى **إنشاء حلول شريحة PowerPoint باستخدام Java**.

### إجابات سريعة
- **ما هو الصنف الأساسي للبدء؟** `Presentation`
- **أي نوع مخطط يُستخدم؟** `ChartType.ClusteredColumn`
- **كيف يتم تمكين الزوايا المستديرة؟** `chart.setRoundedCorners(true);`
- **ما الصيغة الموصى بها للحفظ؟** `SaveFormat.Pptx`
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم ترخيص مدفوع للإنتاج.

## ما هو مخطط العمود المجمع؟
مخطط العمود المجمع يجمع عدة سلاسل بيانات جنباً إلى جنب لكل فئة، مما يجعله مثالياً لمقارنة القيم عبر مجموعات مختلفة. يتيح لك Aspose.Slides إنشاء هذا النوع من المخططات بالكامل عبر الكود دون فتح PowerPoint، ويمكنك تخصيص الألوان والعلامات وخيارات المحاور لتتناسب مع علامتك التجارية.

## لماذا تستخدم Aspose.Slides for Java لإضافة مخطط عمود مجمع؟
يمكنك أتمتة كامل خط أنابيب إنشاء المخطط دون تفاعل واجهة المستخدم، وهو أمر أساسي لتوليد التقارير على الخادم. يعمل Aspose.Slides على أي نظام تشغيل يدعم Java، ويتعامل مع عروض تقديمية تصل إلى 500 شريحة دون تحميلها بالكامل، ويوفر أكثر من 50 نمط مخطط مدمج. هذا يزيل الاعتماد على COM ويسمح لك بدمج رسومات عالية الجودة مباشرة من Java.

## المتطلبات المسبقة
- **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث) – يدعم أكثر من 50 نوع مخطط و30 صيغة صورة.  
- **JDK 16** (أو أحدث) – مطلوب لأحدث ميزات اللغة.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans.  

## إعداد Aspose.Slides for Java
يمكنك إضافة المكتبة عبر Maven أو Gradle أو تحميل مباشر.

### باستخدام Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### باستخدام Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
قم بتحميل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية** – اختبر جميع الميزات دون حدود زمنية.  
- **ترخيص مؤقت** – اطلب واحداً من بوابة Aspose لتقييم كامل الميزات.  
- **شراء** – احصل على ترخيص دائم للاستخدام في الإنتاج.

## دليل التنفيذ

### إنشاء عرض تقديمي وإضافة شريحة
`Presentation` هو كائن Aspose.Slides الأساسي الذي يمثل ملف PowerPoint في الذاكرة. بعد إنشاءه، يمكنك الوصول إلى الشرائح أو تعديلها أو إضافة شرائح جديدة.

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
`IChart` هو الواجهة التي تمثل أي مخطط يُضاف إلى شريحة. بتحديد `ChartType.ClusteredColumn` تخبر Aspose.Slides بإنشاء مخطط عمود مجمع.

#### نظرة عامة
الآن ندمج **مخطط عمود مجمع** في الشريحة التي أعددناها للتو.

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
`Chart` يوفر طريقة `getChartFormat()` التي تُعيد كائن `ChartFormat`، يمكنك من خلاله تعديل تعبئة الخطوط، أنماط الشرط، وتدوير الزوايا.

`Chart` هو الصنف المطبق لـ `IChart` ويمثل كائن المخطط على الشريحة.

#### نظرة عامة
عزز المظهر البصري بتطبيق تعبئة خط صلبة، نمط خط واحد، وزوايا مستديرة.

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
`SaveFormat.Pptx` هو الصيغة الموصى بها لملفات PowerPoint الحديثة، حيث يحافظ على جميع تنسيقات المخطط ويسمح بالتعديل اللاحق.

#### نظرة عامة
أخيراً، نكتب العرض التقديمي إلى القرص بصيغة PPTX، وهي الصيغة القياسية لعمليات **حفظ PowerPoint كـ PPTX**.

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

## التطبيقات العملية
- **تقارير الأعمال** – أتمتة عروض المالية الفصلية بمخططات ديناميكية.  
- **المحتوى التعليمي** – توليد شرائح محاضرات تستخرج البيانات من قاعدة بيانات.  
- **العروض التسويقية** – تصور اتجاهات المنتج بمخططات مصقولة ومطابقة للعلامة التجارية.  

## اعتبارات الأداء
- **إدارة الموارد** – استدعِ دائمًا `dispose()` أو استخدم try‑with‑resources لتحرير الذاكرة الأصلية.  
- **تحسين الذاكرة** – عالج مجموعات البيانات الكبيرة على دفعات أصغر؛ يمكن لـ Aspose.Slides التعامل مع عروض تصل إلى 500 ميغابايت دون تحميل كامل.  
- **أفضل الممارسات** – فضل استخدام هياكل بيانات غير قابلة للتغيير لسلاسل المخطط كلما أمكن؛ هذا يقلل من ضغط الـ GC ويحسن معدل النقل.  

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **`NullPointerException` على `getSlides()`** | تأكد من أن كائن `Presentation` تم إنشاؤه بنجاح قبل الوصول إلى الشرائح. |
| **المخطط لا يظهر** | تحقق من أن أبعاد المخطط (x, y, العرض, الارتفاع) ضمن حدود الشريحة وأنه تم استخدام `ChartType.ClusteredColumn`. |
| **الترخيص غير مُطبق** | حمّل ملف الترخيص قبل إنشاء كائن `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## الأسئلة المتكررة

**س: كيف يمكنني إضافة أنواع مختلفة من المخططات باستخدام Aspose.Slides؟**  
ج: استبدل `ChartType.ClusteredColumn` بأي قيمة تعداد أخرى مثل `ChartType.Pie` أو `ChartType.Line` أو `ChartType.Bar`.

**س: ماذا أفعل إذا واجهت أخطاء تجميع؟**  
ج: تحقق مرة أخرى من أنك تستخدم JDK 16 أو أحدث وأن نسخة الاعتماد في Maven/Gradle تتطابق مع المكتبة التي قمت بتحميلها.

**س: هل يمكنني ملء المخطط ببيانات من قاعدة بيانات؟**  
ج: نعم. الوصول إلى مجموعة `getChartData()` للمخطط، إنشاء السلاسل والفئات، وتعبئتها بالقيم المستخرجة في وقت التشغيل.

**س: كيف يمكنني تحسين الأداء للعروض التقديمية الكبيرة جدًا؟**  
ج: قسم العمل إلى عدة كائنات `Presentation`، أعد استخدام قوالب المخططات، وتأكد دائمًا من تحرير الكائنات بسرعة.

## الخاتمة
أصبح لديك الآن وصفة شاملة من البداية إلى النهاية **لإضافة مخطط عمود مجمع** إلى شريحة PowerPoint باستخدام Aspose.Slides for Java. جرّب أنواع مخططات أخرى، اربط مصادر بيانات حية، ودمج هذه المنطق في خطوط أنابيب تقارير أكبر لأتمتة سير عمل العروض التقديمية.

---

**آخر تحديث:** 2026-09-02  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [إنشاء مخطط PowerPoint Java – حفظ العروض التقديمية مع المخططات باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [إضافة حركة إلى مخطط PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
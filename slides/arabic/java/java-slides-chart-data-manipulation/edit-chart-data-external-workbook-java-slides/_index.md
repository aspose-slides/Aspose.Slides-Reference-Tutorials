---
title: تحرير بيانات المخطط في المصنف الخارجي في شرائح Java
linktitle: تحرير بيانات المخطط في المصنف الخارجي في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحرير بيانات المخطط في مصنف خارجي باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع كود المصدر.
type: docs
weight: 17
url: /ar/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## مقدمة لتحرير بيانات المخطط في المصنف الخارجي في شرائح Java

سنوضح في هذا الدليل كيفية تحرير بيانات المخطط في مصنف خارجي باستخدام Aspose.Slides for Java. ستتعلم كيفية تعديل بيانات المخطط ضمن عرض PowerPoint التقديمي برمجياً. تأكد من تثبيت مكتبة Aspose.Slides الخاصة بـ Java وتكوينها في مشروعك.

## المتطلبات الأساسية

- Aspose.Slides لجافا
- بيئة تطوير جافا

## الخطوة 1: قم بتحميل العرض التقديمي

 أولاً، نحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي نريد تحرير بياناته. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## الخطوة 2: الوصول إلى المخطط

بمجرد تحميل العرض التقديمي، نحتاج إلى الوصول إلى المخطط داخل العرض التقديمي. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى وهو الشكل الأول في تلك الشريحة.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## الخطوة 3: تعديل بيانات المخطط

الآن، دعونا تعديل بيانات المخطط. سنركز على تغيير نقطة بيانات محددة في المخطط. في هذا المثال، قمنا بتعيين قيمة نقطة البيانات الأولى في السلسلة الأولى على 100. ويمكنك ضبط هذه القيمة حسب الحاجة.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## الخطوة 4: احفظ العرض التقديمي

بعد إجراء التغييرات اللازمة على بيانات المخطط، قم بحفظ العرض التقديمي المعدل في ملف جديد. يمكنك تحديد مسار ملف الإخراج وتنسيقه وفقًا لمتطلباتك.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## الخطوة 5: التنظيف

لا تنس التخلص من كائن العرض التقديمي لتحرير أي موارد.

```java
if (pres != null) pres.dispose();
```

لقد قمت الآن بتحرير بيانات المخطط بنجاح في مصنف خارجي داخل عرض PowerPoint التقديمي الخاص بك باستخدام Aspose.Slides for Java. يمكنك تخصيص هذا الرمز ليناسب احتياجاتك الخاصة ودمجه في تطبيقات Java الخاصة بك.

## كود المصدر الكامل

```java
        // انتبه، بالكاد يتم حفظ المسار إلى المصنف الخارجي في العرض التقديمي
        // لذا يرجى نسخ الملف ExternalWorkbook.xlsx من دليل البيانات/المخطط D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ قبل تشغيل المثال
        // المسار إلى دليل المستندات.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## خاتمة

في هذا الدليل الشامل، اكتشفنا كيفية تحرير بيانات المخطط في المصنفات الخارجية ضمن عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. باتباع الإرشادات خطوة بخطوة وأمثلة التعليمات البرمجية المصدر، اكتسبت المعرفة والمهارات اللازمة لتعديل بيانات المخطط برمجيًا بسهولة.

## الأسئلة الشائعة

### كيف يمكنني تحديد مخطط أو شريحة مختلفة؟

 للوصول إلى مخطط أو شريحة مختلفة، قم بتعديل الفهرس المناسب في`getSlides().get_Item()` و`getShapes().get_Item()`طُرق. تذكر أن الفهرسة تبدأ من 0.

### هل يمكنني تحرير البيانات في مخططات متعددة داخل نفس العرض التقديمي؟

نعم، يمكنك تحرير البيانات في مخططات متعددة داخل نفس العرض التقديمي عن طريق تكرار خطوات تعديل بيانات المخطط لكل مخطط.

### ماذا لو كنت أرغب في تحرير البيانات في مصنف خارجي بتنسيق مختلف؟

يمكنك تكييف التعليمات البرمجية للتعامل مع تنسيقات المصنفات الخارجية المختلفة باستخدام فئات وأساليب Aspose.Cells المناسبة لقراءة البيانات وكتابتها بهذا التنسيق.

### كيف يمكنني أتمتة هذه العملية لعروض تقديمية متعددة؟

يمكنك إنشاء حلقة لمعالجة عروض تقديمية متعددة، وتحميل كل منها، وإجراء التغييرات المطلوبة، وحفظ العروض التقديمية المعدلة واحدًا تلو الآخر.
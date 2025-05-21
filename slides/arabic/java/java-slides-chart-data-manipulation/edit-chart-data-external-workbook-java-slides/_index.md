---
"description": "تعرّف على كيفية تحرير بيانات المخططات في مصنف خارجي باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "تحرير بيانات الرسم البياني في المصنف الخارجي في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحرير بيانات الرسم البياني في المصنف الخارجي في شرائح Java"
"url": "/ar/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحرير بيانات الرسم البياني في المصنف الخارجي في شرائح Java


## مقدمة لتحرير بيانات الرسم البياني في المصنف الخارجي في شرائح Java

في هذا الدليل، سنوضح كيفية تحرير بيانات المخططات في مصنف خارجي باستخدام Aspose.Slides لجافا. ستتعلم كيفية تعديل بيانات المخططات برمجيًا ضمن عرض تقديمي في PowerPoint. تأكد من تثبيت مكتبة Aspose.Slides لجافا وتكوينها في مشروعك.

## المتطلبات الأساسية

- Aspose.Slides لـ Java
- بيئة تطوير جافا

## الخطوة 1: تحميل العرض التقديمي

أولاً، علينا تحميل عرض PowerPoint الذي يحتوي على المخطط الذي نريد تعديل بياناته. استبدل `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## الخطوة 2: الوصول إلى الرسم البياني

بعد تحميل العرض التقديمي، نحتاج إلى الوصول إلى المخطط داخله. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى وهو الشكل الأول فيها.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## الخطوة 3: تعديل بيانات الرسم البياني

الآن، لنُعدِّل بيانات الرسم البياني. سنركز على تغيير نقطة بيانات محددة فيه. في هذا المثال، عيّننا قيمة أول نقطة بيانات في السلسلة الأولى إلى ١٠٠. يمكنك تعديل هذه القيمة حسب الحاجة.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## الخطوة 4: حفظ العرض التقديمي

بعد إجراء التغييرات اللازمة على بيانات الرسم البياني، احفظ العرض التقديمي المُعدَّل في ملف جديد. يمكنك تحديد مسار ملف الإخراج وتنسيقه وفقًا لاحتياجاتك.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## الخطوة 5: التنظيف

لا تنس التخلص من كائن العرض لتحرير أي موارد.

```java
if (pres != null) pres.dispose();
```

لقد نجحت الآن في تحرير بيانات الرسم البياني في مصنف خارجي ضمن عرض PowerPoint التقديمي باستخدام Aspose.Slides لجافا. يمكنك تخصيص هذا الكود ليناسب احتياجاتك الخاصة ودمجه في تطبيقات جافا.

## الكود المصدر الكامل

```java
        // انتبه إلى أن المسار إلى المصنف الخارجي لا يتم حفظه في العرض التقديمي
        // لذا يرجى نسخ الملف externalWorkbook.xlsx من دليل البيانات/الرسم البياني D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ قبل تشغيل المثال
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

في هذا الدليل الشامل، استكشفنا كيفية تحرير بيانات المخططات في مصنفات خارجية ضمن عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع التعليمات خطوة بخطوة وأمثلة الكود المصدري، اكتسبت المعرفة والمهارات اللازمة لتعديل بيانات المخططات برمجيًا بسهولة.

## الأسئلة الشائعة

### كيف يمكنني تحديد مخطط أو شريحة مختلفة؟

للوصول إلى مخطط أو شريحة مختلفة، قم بتعديل الفهرس المناسب في `getSlides().get_Item()` و `getShapes().get_Item()` الأساليب. تذكر أن الفهرسة تبدأ من 0.

### هل يمكنني تحرير البيانات في مخططات متعددة ضمن نفس العرض التقديمي؟

نعم، يمكنك تحرير البيانات في مخططات متعددة ضمن نفس العرض التقديمي عن طريق تكرار خطوات تعديل بيانات المخطط لكل مخطط.

### ماذا لو أردت تحرير البيانات في مصنف خارجي بتنسيق مختلف؟

بإمكانك تكييف الكود للتعامل مع تنسيقات المصنفات الخارجية المختلفة باستخدام فئات وطرق Aspose.Cells المناسبة لقراءة البيانات وكتابتها بهذا التنسيق.

### كيف يمكنني أتمتة هذه العملية لعروض تقديمية متعددة؟

يمكنك إنشاء حلقة لمعالجة عروض تقديمية متعددة، وتحميل كل منها، وإجراء التغييرات المطلوبة، وحفظ العروض التقديمية المعدلة واحدة تلو الأخرى.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
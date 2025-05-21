---
"description": "حسّن شرائح جافا لديك باستخدام Aspose.Slides لجافا. تعلّم كيفية ضبط زوايا دوران عناصر النص. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "ضبط زاوية الدوران في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ضبط زاوية الدوران في شرائح جافا"
"url": "/ar/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط زاوية الدوران في شرائح جافا


## مقدمة لضبط زاوية الدوران في شرائح جافا

في هذا البرنامج التعليمي، سنستكشف كيفية ضبط زاوية دوران النص في عنوان محور الرسم البياني باستخدام مكتبة Aspose.Slides لجافا. بضبط زاوية الدوران، يمكنك تخصيص مظهر عناوين محاور الرسم البياني لتناسب احتياجات عرضك التقديمي بشكل أفضل.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني واتباع تعليمات التثبيت الواردة في وثائقها.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، عليك إنشاء عرض تقديمي جديد أو تحميل عرض تقديمي موجود. في هذا المثال، سننشئ عرضًا تقديميًا جديدًا:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، سنضيف مخططًا إلى الشريحة. في هذا المثال، نضيف مخططًا عموديًا مجمعًا:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## الخطوة 3: تعيين زاوية الدوران لعنوان المحور

لضبط زاوية دوران عنوان المحور، ستحتاج إلى الوصول إلى عنوان المحور الرأسي للرسم البياني وضبط زاوية دورانه. إليك كيفية القيام بذلك:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

في هذا المقطع البرمجي، نضبط زاوية الدوران على 90 درجة، مما يُؤدي إلى تدوير النص عموديًا. يمكنك ضبط الزاوية حسب القيمة التي تريدها.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## الكود المصدر الكامل لضبط زاوية الدوران في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية ضبط زاوية دوران النص في عنوان محور الرسم البياني باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة تخصيص مظهر الرسوم البيانية لإنشاء عروض تقديمية جذابة بصريًا. جرّب زوايا دوران مختلفة لتحقيق المظهر المطلوب لرسومك البيانية.

## الأسئلة الشائعة

### كيف يمكنني تغيير زاوية الدوران لعناصر النص الأخرى في الشريحة؟

يمكنك تغيير زاوية دوران عناصر نصية أخرى، مثل الأشكال أو مربعات النص، باتباع نهج مماثل. تعرّف على تنسيق النص الخاص بالعنصر واضبط زاوية الدوران حسب الحاجة.

### هل يمكنني تدوير النص في عنوان المحور الأفقي أيضًا؟

نعم، يمكنك تدوير النص في عنوان المحور الأفقي بضبط زاوية الدوران. ما عليك سوى ضبط زاوية الدوران على القيمة المطلوبة، مثل 90 درجة للنص الرأسي أو 0 درجة للنص الأفقي.

### ما هي خيارات التنسيق الأخرى المتاحة لعناوين المخططات؟

يوفر Aspose.Slides لجافا خيارات تنسيق متنوعة لعناوين المخططات، بما في ذلك أنماط الخطوط والألوان والمحاذاة. يمكنك الاطلاع على الوثائق لمزيد من التفاصيل حول تخصيص عناوين المخططات.

### هل من الممكن تحريك دوران النص في عنوان محور الرسم البياني؟

نعم، يمكنك إضافة تأثيرات متحركة إلى عناصر النص، بما في ذلك عناوين محاور المخطط، باستخدام Aspose.Slides لجافا. راجع الوثائق لمزيد من المعلومات حول إضافة الرسوم المتحركة إلى عروضك التقديمية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
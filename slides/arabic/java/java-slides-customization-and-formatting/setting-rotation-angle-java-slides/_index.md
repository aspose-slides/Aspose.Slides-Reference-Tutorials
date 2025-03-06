---
title: ضبط زاوية الدوران في شرائح جافا
linktitle: ضبط زاوية الدوران في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين شرائح Java الخاصة بك باستخدام Aspose.Slides لـ Java. تعلم كيفية ضبط زوايا التدوير لعناصر النص. دليل خطوة بخطوة مع كود المصدر.
weight: 17
url: /ar/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضبط زاوية الدوران في شرائح جافا


## مقدمة لإعداد زاوية الدوران في شرائح جافا

في هذا البرنامج التعليمي، سوف نستكشف كيفية تعيين زاوية التدوير للنص في عنوان محور المخطط باستخدام مكتبة Aspose.Slides for Java. من خلال ضبط زاوية التدوير، يمكنك تخصيص مظهر عناوين محاور المخطط الخاص بك لتناسب احتياجات العرض التقديمي بشكل أفضل.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني واتباع تعليمات التثبيت المتوفرة في وثائقها.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، تحتاج إلى إنشاء عرض تقديمي جديد أو تحميل عرض موجود. في هذا المثال، سنقوم بإنشاء عرض تقديمي جديد:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، سنقوم بإضافة مخطط إلى الشريحة. في هذا المثال، نقوم بإضافة مخطط عمودي متفاوت المسافات:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## الخطوة 3: ضبط زاوية الدوران لعنوان المحور

لتعيين زاوية التدوير لعنوان المحور، ستحتاج إلى الوصول إلى عنوان المحور الرأسي للمخطط وضبط زاوية التدوير الخاصة به. وإليك كيف يمكنك القيام بذلك:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

في مقتطف الشفرة هذا، نقوم بتعيين زاوية التدوير على 90 درجة، مما يؤدي إلى تدوير النص عموديًا. يمكنك ضبط الزاوية حسب القيمة المطلوبة.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## كود المصدر الكامل لتحديد زاوية التدوير في شرائح جافا

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

في هذا البرنامج التعليمي، تعلمت كيفية تعيين زاوية التدوير للنص في عنوان محور المخطط باستخدام Aspose.Slides لـ Java. تتيح لك هذه الميزة تخصيص مظهر مخططاتك لإنشاء عروض تقديمية جذابة. قم بتجربة زوايا دوران مختلفة لتحقيق المظهر المطلوب لمخططاتك.

## الأسئلة الشائعة

### كيف يمكنني تغيير زاوية التدوير لعناصر النص الأخرى في الشريحة؟

يمكنك تغيير زاوية التدوير لعناصر النص الأخرى، مثل الأشكال أو مربعات النص، باستخدام أسلوب مماثل. قم بالوصول إلى تنسيق النص الخاص بالعنصر وضبط زاوية التدوير حسب الحاجة.

### هل يمكنني تدوير النص في عنوان المحور الأفقي أيضًا؟

نعم، يمكنك تدوير النص في عنوان المحور الأفقي عن طريق ضبط زاوية التدوير. ما عليك سوى ضبط زاوية التدوير على القيمة المطلوبة، مثل 90 درجة للنص الرأسي أو 0 درجة للنص الأفقي.

### ما هي خيارات التنسيق الأخرى المتوفرة لعناوين المخططات؟

يوفر Aspose.Slides for Java خيارات تنسيق متنوعة لعناوين المخططات، بما في ذلك أنماط الخطوط والألوان والمحاذاة. يمكنك استكشاف الوثائق لمزيد من التفاصيل حول تخصيص عناوين المخططات.

### هل من الممكن تحريك دوران النص في عنوان محور المخطط؟

نعم، يمكنك إضافة تأثيرات الحركة إلى عناصر النص، بما في ذلك عناوين محاور المخطط، باستخدام Aspose.Slides لـ Java. راجع الوثائق للحصول على معلومات حول إضافة الرسوم المتحركة إلى العروض التقديمية الخاصة بك.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

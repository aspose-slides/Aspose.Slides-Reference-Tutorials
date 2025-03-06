---
title: الوصول إلى تنسيقات التخطيط في شرائح Java
linktitle: الوصول إلى تنسيقات التخطيط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الوصول إلى تنسيقات التخطيط ومعالجتها في Java Slides باستخدام Aspose.Slides for Java. قم بتخصيص أنماط الأشكال والخطوط بسهولة في عروض PowerPoint التقديمية.
weight: 10
url: /ar/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الوصول إلى تنسيقات التخطيط في شرائح Java


## مقدمة إلى تنسيقات تخطيط الوصول في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية الوصول إلى تنسيقات التخطيط في Java Slides والعمل معها باستخدام Aspose.Slides for Java API. تسمح لك تنسيقات التخطيط بالتحكم في مظهر الأشكال والخطوط داخل شرائح تخطيط العرض التقديمي. سنغطي كيفية استرداد تنسيقات التعبئة وتنسيقات الخطوط للأشكال الموجودة على شرائح التخطيط.

## المتطلبات الأساسية

1. Aspose.Slides لمكتبة جافا.
2. عرض تقديمي لـ PowerPoint (تنسيق PPTX) مع شرائح تخطيطية.

## الخطوة 1: قم بتحميل العرض التقديمي

 أولاً، نحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على شرائح التخطيط. يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## الخطوة 2: الوصول إلى تنسيقات التخطيط

الآن، دعنا نتنقل عبر شرائح التخطيط في العرض التقديمي ونصل إلى تنسيقات التعبئة وتنسيقات خطوط الأشكال في كل شريحة تخطيط.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // الوصول إلى تنسيقات تعبئة الأشكال
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // الوصول إلى تنسيقات خطوط الأشكال
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

في الكود أعلاه:

- نحن نكرر من خلال كل شريحة تخطيط باستخدام`for` حلقة.
- لكل شريحة تخطيط، نقوم بإنشاء صفائف لتخزين تنسيقات التعبئة وتنسيقات الخطوط للأشكال الموجودة في تلك الشريحة.
-  نحن نستخدم متداخلة`for` حلقات للتكرار عبر الأشكال الموجودة على شريحة التخطيط واسترداد تنسيقات التعبئة والخط الخاصة بها.

## الخطوة 3: العمل مع تنسيقات التخطيط

الآن بعد أن وصلنا إلى تنسيقات التعبئة وتنسيقات الخطوط للأشكال الموجودة على شرائح التخطيط، يمكنك إجراء عمليات متنوعة عليها حسب الحاجة. على سبيل المثال، يمكنك تغيير لون التعبئة أو نمط الخط أو خصائص الأشكال الأخرى.

## كود المصدر الكامل لتنسيقات تخطيط الوصول في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية الوصول إلى تنسيقات التخطيط ومعالجتها في Java Slides باستخدام Aspose.Slides for Java API. تعد تنسيقات التخطيط ضرورية للتحكم في مظهر الأشكال والخطوط داخل شرائح التخطيط في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون تعبئة الشكل؟

 لتغيير لون تعبئة الشكل، يمكنك استخدام`IFillFormat`أساليب الكائن. هنا مثال:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // اضبط نوع التعبئة على اللون الصلب
fillFormat.getSolidFillColor().setColor(Color.RED); // اضبط لون التعبئة على اللون الأحمر
```

### كيف يمكنني تغيير نمط خط الشكل؟

 لتغيير نمط خط الشكل، يمكنك استخدام`ILineFormat`أساليب الكائن. هنا مثال:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // اضبط نمط الخط على فردي
lineFormat.setWidth(2.0); // اضبط عرض الخط على 2.0 نقطة
lineFormat.getSolidFillColor().setColor(Color.BLUE); // اضبط لون الخط على اللون الأزرق
```

### كيف يمكنني تطبيق هذه التغييرات على شكل في شريحة التخطيط؟

لتطبيق هذه التغييرات على شكل معين في شريحة تخطيط، يمكنك الوصول إلى الشكل باستخدام فهرسه في مجموعة الأشكال في شريحة التخطيط. على سبيل المثال:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // قم بالوصول إلى الشكل الأول على شريحة التخطيط
```

 يمكنك بعد ذلك استخدام`IFillFormat` و`ILineFormat` الطرق كما هو موضح في الإجابات السابقة لتعديل تنسيقات تعبئة الشكل والخط.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "تعرّف على كيفية الوصول إلى تنسيقات التخطيط وتعديلها في شرائح جافا باستخدام Aspose.Slides لجافا. خصّص أنماط الأشكال والخطوط بسهولة في عروض PowerPoint التقديمية."
"linktitle": "تنسيقات تخطيط Access في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تنسيقات تخطيط Access في شرائح Java"
"url": "/ar/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنسيقات تخطيط Access في شرائح Java


## مقدمة إلى تنسيقات تخطيط Access في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية الوصول إلى تنسيقات التخطيط والعمل بها في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تتيح لك تنسيقات التخطيط التحكم في مظهر الأشكال والخطوط داخل شرائح تخطيط العرض التقديمي. سنتناول كيفية استرداد تنسيقات التعبئة وتنسيقات الخطوط للأشكال في شرائح التخطيط.

## المتطلبات الأساسية

1. Aspose.Slides لمكتبة Java.
2. عرض تقديمي بتنسيق PowerPoint (تنسيق PPTX) مع شرائح تخطيطية.

## الخطوة 1: تحميل العرض التقديمي

أولاً، نحتاج إلى تحميل عرض PowerPoint الذي يحتوي على شرائح التخطيط. استبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## الخطوة 2: الوصول إلى تنسيقات التخطيط

الآن، دعنا ننتقل عبر شرائح التخطيط في العرض التقديمي ونصل إلى تنسيقات التعبئة وتنسيقات الخطوط للأشكال الموجودة في كل شريحة تخطيط.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // الوصول إلى تنسيقات التعبئة للأشكال
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // تنسيقات خطوط الوصول للأشكال
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

- نقوم بالتكرار خلال كل شريحة تخطيط باستخدام `for` حلقة.
- بالنسبة لكل شريحة تخطيط، نقوم بإنشاء صفوف لتخزين تنسيقات التعبئة وتنسيقات الخطوط للأشكال الموجودة على تلك الشريحة.
- نحن نستخدم المتداخلة `for` حلقات للتنقل عبر الأشكال الموجودة على شريحة التخطيط واسترداد تنسيقات التعبئة والخطوط الخاصة بها.

## الخطوة 3: العمل مع تنسيقات التخطيط

بعد أن تعرفنا على تنسيقات التعبئة والخطوط للأشكال في شرائح التخطيط، يمكنك إجراء عمليات متنوعة عليها حسب الحاجة. على سبيل المثال، يمكنك تغيير لون التعبئة أو نمط الخطوط أو خصائص أخرى للأشكال.

## الكود المصدر الكامل لتنسيقات تخطيط Access في شرائح Java

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

في هذا البرنامج التعليمي، استكشفنا كيفية الوصول إلى تنسيقات التخطيط ومعالجتها في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تُعد تنسيقات التخطيط أساسية للتحكم في مظهر الأشكال والخطوط داخل شرائح التخطيط في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون تعبئة الشكل؟

لتغيير لون تعبئة الشكل، يمكنك استخدام `IFillFormat` طرق الكائن. إليك مثال:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // تعيين نوع التعبئة إلى لون ثابت
fillFormat.getSolidFillColor().setColor(Color.RED); // تعيين لون التعبئة إلى اللون الأحمر
```

### كيف يمكنني تغيير نمط خط الشكل؟

لتغيير نمط خط الشكل، يمكنك استخدام `ILineFormat` طرق الكائن. إليك مثال:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // تعيين نمط الخط إلى واحد
lineFormat.setWidth(2.0); // ضبط عرض الخط إلى 2.0 نقطة
lineFormat.getSolidFillColor().setColor(Color.BLUE); // تعيين لون الخط إلى اللون الأزرق
```

### كيف يمكنني تطبيق هذه التغييرات على شكل في شريحة التخطيط؟

لتطبيق هذه التغييرات على شكل محدد في شريحة تخطيط، يمكنك الوصول إلى الشكل باستخدام فهرسه في مجموعة الأشكال بشريحة التخطيط. على سبيل المثال:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // الوصول إلى الشكل الأول على شريحة التخطيط
```

يمكنك بعد ذلك استخدام `IFillFormat` و `ILineFormat` الطرق كما هو موضح في الإجابات السابقة لتعديل تنسيقات التعبئة والخط للشكل.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
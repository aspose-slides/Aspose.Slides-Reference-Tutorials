---
title: إضافة خطوط مخصصة في شرائح جافا
linktitle: إضافة خطوط مخصصة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين شرائح Java الخاصة بك باستخدام خطوط مخصصة. دليل خطوة بخطوة باستخدام Aspose.Slides لـ Java. تعلم كيفية إضافة الخطوط وتخصيصها في العروض التقديمية للحصول على صور مؤثرة.
weight: 10
url: /ar/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خطوط مخصصة في شرائح جافا


## مقدمة لإضافة خطوط مخصصة في شرائح جافا

ستتعلم في هذا البرنامج التعليمي كيفية إضافة خطوط مخصصة إلى شرائح Java الخاصة بك باستخدام Aspose.Slides for Java. يمكن استخدام الخطوط المخصصة لتحسين التمثيل المرئي لشرائحك وإبراز محتوى محدد. سنزودك بتعليمات خطوة بخطوة بالإضافة إلى الكود المصدري لتحقيق ذلك. هيا بنا نبدأ!

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إعداد مكتبة Aspose.Slides لجافا في مشروع Java الخاص بك. يمكنكم تحميل المكتبة من الموقع:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## الخطوة 1: تهيئة العرض التقديمي

أولا، تحتاج إلى إنشاء عرض تقديمي جديد. في هذا المثال، سنقوم بإنشاء عرض تقديمي فارغ.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا إلى الشريحة. في هذا المثال، نقوم بإضافة مخطط عمودي متفاوت المسافات. يمكنك اختيار نوع الرسم البياني الذي يناسب احتياجاتك.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## الخطوة 3: إضافة سطر مخصص

 الآن، دعونا نضيف خطًا مخصصًا إلى المخطط. سوف نقوم بإنشاء`IAutoShape` من النوع`ShapeType.Line` ووضعه داخل المخطط.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## الخطوة 4: تخصيص الخط

يمكنك تخصيص مظهر الخط عن طريق تعيين خصائصه. في هذا المثال، قمنا بتعيين لون الخط إلى اللون الأحمر.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في الموقع الذي تريده.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لإضافة خطوط مخصصة في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في إضافة سطر مخصص إلى شريحة Java الخاصة بك باستخدام Aspose.Slides for Java. يمكنك تخصيص خصائص الخط بشكل أكبر لتحقيق التأثيرات المرئية المطلوبة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

لتغيير لون الخط استخدم الكود التالي:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 يستبدل`YOUR_COLOR` مع اللون المطلوب.

### هل يمكنني إضافة خطوط مخصصة إلى أشكال أخرى؟

 نعم، يمكنك إضافة خطوط مخصصة إلى أشكال مختلفة، وليس فقط المخططات. ببساطة قم بإنشاء`IAutoShape` وتخصيصها وفقا لاحتياجاتك.

### كيف يمكنني تغيير سمك الخط؟

 يمكنك تغيير سمك الخط عن طريق ضبط`Width` خاصية تنسيق الخط. على سبيل المثال:
```java
shape.getLineFormat().setWidth(2); // اضبط سمك الخط على نقطتين
```

### هل من الممكن إضافة أسطر متعددة إلى الشريحة؟

نعم، يمكنك إضافة أسطر متعددة إلى الشريحة عن طريق تكرار الخطوات المذكورة في هذا البرنامج التعليمي. يمكن تخصيص كل سطر بشكل مستقل.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "حسّن عروضك التقديمية بلغة جافا بخطوط مخصصة. دليل خطوة بخطوة لاستخدام Aspose.Slides في جافا. تعلم كيفية إضافة وتخصيص الخطوط في العروض التقديمية للحصول على عروض مرئية مؤثرة."
"linktitle": "إضافة خطوط مخصصة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة خطوط مخصصة في شرائح Java"
"url": "/ar/java/customization-and-formatting/adding-custom-lines-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خطوط مخصصة في شرائح Java


## مقدمة حول إضافة خطوط مخصصة في شرائح Java

في هذا البرنامج التعليمي، ستتعلم كيفية إضافة خطوط مخصصة إلى شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك استخدام الخطوط المخصصة لتحسين العرض المرئي لشرائحك وإبراز محتوى محدد. سنزودك بتعليمات خطوة بخطوة مع الكود المصدري لتحقيق ذلك. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيل المكتبة من الموقع الإلكتروني: [Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/)

## الخطوة 1: تهيئة العرض التقديمي

أولاً، عليك إنشاء عرض تقديمي جديد. في هذا المثال، سننشئ عرضًا تقديميًا فارغًا.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا إلى الشريحة. في هذا المثال، سنضيف مخططًا عموديًا مجمعًا. يمكنك اختيار نوع المخطط الذي يناسب احتياجاتك.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## الخطوة 3: إضافة خط مخصص

الآن، لنُضِف خطًا مُخصَّصًا إلى الرسم البياني. سنُنشئ `IAutoShape` من النوع `ShapeType.Line` ووضعه داخل الرسم البياني.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## الخطوة 4: تخصيص الخط

يمكنك تخصيص مظهر الخط من خلال ضبط خصائصه. في هذا المثال، قمنا بتعيين لون الخط إلى الأحمر.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في الموقع المطلوب.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## الكود المصدر الكامل لإضافة خطوط مخصصة في شرائح Java

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

تهانينا! لقد نجحت في إضافة خط مخصص إلى شريحة جافا باستخدام Aspose.Slides لجافا. يمكنك تخصيص خصائص الخط لتحقيق التأثيرات المرئية المطلوبة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

لتغيير لون الخط استخدم الكود التالي:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

يستبدل `YOUR_COLOR` مع اللون المطلوب.

### هل يمكنني إضافة خطوط مخصصة إلى أشكال أخرى؟

نعم، يمكنك إضافة خطوط مخصصة إلى أشكال مختلفة، وليس فقط إلى المخططات البيانية. ما عليك سوى إنشاء `IAutoShape` وتخصيصها وفقًا لاحتياجاتك.

### كيف يمكنني تغيير سمك الخط؟

يمكنك تغيير سمك الخط عن طريق ضبط `Width` خاصية تنسيق الخط. على سبيل المثال:
```java
shape.getLineFormat().setWidth(2); // ضبط سمك الخط إلى نقطتين
```

### هل من الممكن إضافة خطوط متعددة إلى شريحة واحدة؟

نعم، يمكنك إضافة عدة أسطر إلى الشريحة بتكرار الخطوات المذكورة في هذا البرنامج التعليمي. يمكن تخصيص كل سطر على حدة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
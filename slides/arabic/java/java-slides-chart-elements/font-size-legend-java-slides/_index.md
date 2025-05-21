---
"description": "حسّن عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تعرّف على كيفية تخصيص أحجام خطوط الأيقونات والمزيد في دليلنا المفصل."
"linktitle": "أسطورة حجم الخط في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "أسطورة حجم الخط في شرائح Java"
"url": "/ar/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# أسطورة حجم الخط في شرائح Java


## مقدمة إلى أسطورة حجم الخط في شرائح Java

في هذا البرنامج التعليمي، ستتعلم كيفية تخصيص حجم خط الشرح التوضيحي في شريحة PowerPoint باستخدام Aspose.Slides لجافا. سنقدم تعليمات خطوة بخطوة وشيفرة المصدر لتحقيق هذه المهمة.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

أولاً، قم باستيراد الفئات اللازمة وقم بتشغيل عرض PowerPoint الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

يستبدل `"Your Document Directory"` مع المسار الفعلي لملف PowerPoint الخاص بك.

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا إلى الشريحة ونحدد حجم الخط الخاص بالأسطورة.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

في هذا الكود، ننشئ مخططًا عموديًا مجمعًا على الشريحة الأولى ونضبط حجم خط نص التسمية التوضيحية إلى ٢٠ نقطة. يمكنك تعديل `setFontHeight` قيمة لتغيير حجم الخط حسب الحاجة.

## الخطوة 3: تخصيص قيم المحور

الآن، دعنا نقوم بتخصيص قيم المحور الرأسي للرسم البياني.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

هنا، نحدد الحد الأدنى والحد الأقصى لقيم المحور الرأسي. يمكنك تعديل القيم وفقًا لمتطلبات بياناتك.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل في ملف جديد.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

يحفظ هذا الكود العرض التقديمي المعدل باسم "output.pptx" في الدليل المحدد.

## كود المصدر الكامل لأسطورة حجم الخط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

لقد نجحتَ في تخصيص حجم خطّ شرح شريحة جافا باوربوينت باستخدام Aspose.Slides لجافا. يمكنكَ استكشاف المزيد من إمكانيات Aspose.Slides لإنشاء عروض تقديمية تفاعلية وجذابة بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم الخط الخاص بنص الأسطورة في الرسم البياني؟

لتغيير حجم الخط الخاص بنص الأسطورة في الرسم البياني، يمكنك استخدام الكود التالي:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

في هذا الكود، ننشئ مخططًا ونضبط حجم خط نص التسمية التوضيحية إلى ٢٠ نقطة. يمكنك تعديل `setFontHeight` قيمة لتغيير حجم الخط.

### هل يمكنني تخصيص خصائص أخرى للأسطورة في الرسم البياني؟

نعم، يمكنك تخصيص خصائص متنوعة للتوضيح في مخطط بياني باستخدام Aspose.Slides. من بين الخصائص الشائعة التي يمكنك تخصيصها تنسيق النص، والموضع، والرؤية، وغيرها. على سبيل المثال، لتغيير موضع التوضيح، يمكنك استخدام:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

يُعيّن هذا الكود التسمية التوضيحية لتظهر أسفل الرسم البياني. اطّلِع على وثائق Aspose.Slides لمزيد من خيارات التخصيص.

### كيف أقوم بتعيين الحد الأدنى والحد الأقصى للقيم للمحور الرأسي في الرسم البياني؟

لتعيين الحد الأدنى والحد الأقصى للقيم للمحور الرأسي في الرسم البياني، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

هنا، نُعطّل التحجيم التلقائي للمحور ونحدد الحد الأدنى والأقصى لقيم المحور الرأسي. عدّل القيم حسب الحاجة لبيانات الرسم البياني.

### أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Slides؟

يمكنك العثور على وثائق شاملة ومراجع لواجهة برمجة التطبيقات (API) لـ Aspose.Slides لـ Java على موقع وثائق Aspose. تفضل بزيارة [هنا](https://reference.aspose.com/slides/java/) لمزيد من المعلومات التفصيلية حول استخدام المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
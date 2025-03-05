---
title: أسطورة حجم الخط في شرائح جافا
linktitle: أسطورة حجم الخط في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تعرف على كيفية تخصيص أحجام الخطوط الإيضاحية والمزيد في دليلنا التفصيلي خطوة بخطوة.
type: docs
weight: 13
url: /ar/java/chart-elements/font-size-legend-java-slides/
---

## مقدمة إلى وسيلة إيضاح حجم الخط في شرائح Java

ستتعلم في هذا البرنامج التعليمي كيفية تخصيص حجم خط وسيلة الإيضاح في شريحة PowerPoint باستخدام Aspose.Slides for Java. سنقدم تعليمات خطوة بخطوة وكود المصدر لتحقيق هذه المهمة.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

أولاً، قم باستيراد الفئات الضرورية وتهيئة عرض PowerPoint التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 يستبدل`"Your Document Directory"` بالمسار الفعلي لملف PowerPoint الخاص بك.

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا إلى الشريحة ونضبط حجم خط وسيلة الإيضاح.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 في هذا الكود، نقوم بإنشاء مخطط عمودي متفاوت المسافات على الشريحة الأولى ونضبط حجم خط نص وسيلة الإيضاح على 20 نقطة. يمكنك ضبط`setFontHeight`القيمة لتغيير حجم الخط حسب الحاجة.

## الخطوة 3: تخصيص قيم المحور

الآن، دعونا نخصص قيم المحور الرأسي للمخطط.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

هنا، قمنا بتعيين القيم الدنيا والقصوى للمحور الرأسي. يمكنك تعديل القيم وفقًا لمتطلبات البيانات الخاصة بك.

## الخطوة 4: احفظ العرض التقديمي

وأخيراً، احفظ العرض التقديمي المعدل في ملف جديد.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

يحفظ هذا الرمز العرض التقديمي المعدل باسم "output.pptx" في الدليل المحدد.

## كود المصدر الكامل لأسطورة حجم الخط في شرائح جافا

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

لقد نجحت في تخصيص حجم خط وسيلة الإيضاح في شريحة Java PowerPoint باستخدام Aspose.Slides for Java. يمكنك أيضًا استكشاف إمكانيات Aspose.Slides لإنشاء عروض تقديمية تفاعلية وجذابة بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم خط نص وسيلة الإيضاح في المخطط؟

لتغيير حجم خط نص وسيلة الإيضاح في المخطط، يمكنك استخدام التعليمة البرمجية التالية:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 في هذا الكود، نقوم بإنشاء مخطط ونضبط حجم خط نص وسيلة الإيضاح على 20 نقطة. يمكنك ضبط`setFontHeight` القيمة لتغيير حجم الخط.

### هل يمكنني تخصيص خصائص أخرى لوسيلة الإيضاح في مخطط؟

نعم، يمكنك تخصيص خصائص مختلفة لوسيلة الإيضاح في مخطط باستخدام Aspose.Slides. تتضمن بعض الخصائص الشائعة التي يمكنك تخصيصها تنسيق النص والموضع والرؤية والمزيد. على سبيل المثال، لتغيير موضع وسيلة الإيضاح، يمكنك استخدام:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

يقوم هذا الرمز بتعيين وسيلة الإيضاح لتظهر في أسفل المخطط. استكشف وثائق Aspose.Slides لمزيد من خيارات التخصيص.

### كيف أقوم بتعيين الحد الأدنى والحد الأقصى لقيم المحور الرأسي في المخطط؟

لتعيين الحد الأدنى والحد الأقصى لقيم المحور العمودي في المخطط، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

هنا، نقوم بتعطيل القياس التلقائي للمحور ونحدد القيم الدنيا والقصوى للمحور الرأسي. اضبط القيم حسب الحاجة لبيانات المخطط الخاص بك.

### أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Slides؟

 يمكنك العثور على وثائق شاملة ومراجع واجهة برمجة التطبيقات لـ Aspose.Slides for Java على موقع وثائق Aspose. يزور[هنا](https://reference.aspose.com/slides/java/) للحصول على معلومات مفصلة حول استخدام المكتبة.
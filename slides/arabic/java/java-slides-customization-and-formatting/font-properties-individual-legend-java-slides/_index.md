---
title: خصائص الخط لوسيلة الإيضاح الفردية في شرائح Java
linktitle: خصائص الخط لوسيلة الإيضاح الفردية في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية باستخدام أنماط الخطوط والأحجام والألوان المخصصة للأساطير الفردية في Java Slides باستخدام Aspose.Slides for Java.
weight: 12
url: /ar/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى خصائص الخط لوسيلة الإيضاح الفردية في شرائح Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية تعيين خصائص الخط لوسيلة إيضاح فردية في Java Slides باستخدام Aspose.Slides for Java. من خلال تخصيص خصائص الخط، يمكنك جعل وسائل الإيضاح الخاصة بك أكثر جاذبية وغنية بالمعلومات في عروض PowerPoint التقديمية.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروعك. يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي وإضافة الرسم البياني

أولاً، لنبدأ بتهيئة عرض PowerPoint التقديمي وإضافة مخطط إليه. في هذا المثال، سوف نستخدم مخططًا عموديًا متفاوت المسافات كمثال توضيحي.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // بقية الكود يذهب هنا
} finally {
    if (pres != null) pres.dispose();
}
```

 يستبدل`"Your Document Directory"` مع الدليل الفعلي الذي يوجد به مستند PowerPoint الخاص بك.

## الخطوة 2: تخصيص خصائص الخط لوسيلة الإيضاح

الآن، دعونا نخصص خصائص الخط لإدخال وسيلة إيضاح فردية داخل المخطط. في هذا المثال، نستهدف إدخال وسيلة الإيضاح الثاني (الفهرس 1)، ولكن يمكنك ضبط الفهرس وفقًا لمتطلباتك المحددة.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

وإليك ما يفعله كل سطر من التعليمات البرمجية:

- `get_Item(1)` يسترد إدخال وسيلة الإيضاح الثاني (الفهرس 1). يمكنك تغيير الفهرس لاستهداف إدخال وسيلة إيضاح مختلفة.
- `setFontBold(NullableBool.True)` يضبط الخط على غامق.
- `setFontHeight(20)` يضبط حجم الخط على 20 نقطة.
- `setFontItalic(NullableBool.True)` يضبط الخط على مائل.
- `setFillType(FillType.Solid)` يحدد أن نص إدخال وسيلة الإيضاح يجب أن يكون له تعبئة ثابتة.
- `getSolidFillColor().setColor(Color.BLUE)` يضبط لون التعبئة على اللون الأزرق. يمكنك استبدال`Color.BLUE` مع اللون الذي تريده.

## الخطوة 3: احفظ العرض التقديمي المعدل

وأخيرًا، احفظ العرض التقديمي المعدل في ملف جديد للحفاظ على تغييراتك.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 يستبدل`"output.pptx"` مع اسم ملف الإخراج المفضل لديك.

هذا كل شيء! لقد نجحت في تخصيص خصائص الخط لإدخال وسيلة إيضاح فردية في العرض التقديمي لـ Java Slides باستخدام Aspose.Slides for Java.

## أكمل كود المصدر لخصائص الخط للأسطورة الفردية في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تخصيص خصائص الخط لوسيلة إيضاح فردية في Java Slides باستخدام Aspose.Slides for Java. من خلال ضبط أنماط الخطوط وأحجامها وألوانها، يمكنك تحسين المظهر المرئي والوضوح لعروض PowerPoint التقديمية الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

 لتغيير لون الخط استخدم`tf.getPortionFormat().getFontColor().setColor(yourColor)` بدلاً من تغيير لون التعبئة. يستبدل`yourColor` مع لون الخط المطلوب .

### كيف يمكنني تعديل خصائص وسيلة الإيضاح الأخرى؟

يمكنك تعديل العديد من الخصائص الأخرى لوسيلة الإيضاح، مثل الموضع والحجم والتنسيق. راجع وثائق Aspose.Slides for Java للحصول على معلومات مفصلة حول العمل مع وسائل الإيضاح.

### هل يمكنني تطبيق هذه التغييرات على إدخالات وسيلة الإيضاح المتعددة؟

 نعم، يمكنك تكرار إدخالات وسيلة الإيضاح وتطبيق هذه التغييرات على إدخالات متعددة عن طريق ضبط الفهرس فيها`get_Item(index)` وتكرار رمز التخصيص.

تذكر التخلص من كائن العرض التقديمي عند الانتهاء من تحرير الموارد:

```java
if (pres != null) pres.dispose();
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

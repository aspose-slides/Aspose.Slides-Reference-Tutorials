---
"description": "قم بتعزيز عروض PowerPoint باستخدام أنماط الخطوط والأحجام والألوان المخصصة للأساطير الفردية في Java Slides باستخدام Aspose.Slides for Java."
"linktitle": "خصائص الخط للأسطورة الفردية في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خصائص الخط للأسطورة الفردية في شرائح Java"
"url": "/ar/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خصائص الخط للأسطورة الفردية في شرائح Java


## مقدمة لخصائص الخط للأسطورة الفردية في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية ضبط خصائص الخط لمفتاح توضيحي فردي في Java Slides باستخدام Aspose.Slides for Java. بتخصيص خصائص الخط، يمكنك جعل مفاتيحك التوضيحية أكثر جاذبية بصريًا وغنية بالمعلومات في عروض PowerPoint التقديمية.

## المتطلبات الأساسية

قبل البدء، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروعك. يمكنك تنزيلها من [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي وإضافة الرسم البياني

أولاً، لنبدأ بتهيئة عرض تقديمي في PowerPoint وإضافة مخطط إليه. في هذا المثال، سنستخدم مخططًا عموديًا مجمعًا كمثال توضيحي.

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

يستبدل `"Your Document Directory"` مع الدليل الفعلي الذي يوجد به مستند PowerPoint الخاص بك.

## الخطوة 2: تخصيص خصائص الخط للأسطورة

الآن، لنُخصّص خصائص الخط لكل مُدخل من مُدخلات الأسطورة داخل الرسم البياني. في هذا المثال، نُركّز على مُدخل الأسطورة الثاني (الفهرس ١)، ولكن يُمكنك تعديل الفهرس وفقًا لمتطلباتك الخاصة.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

إليك ما يفعله كل سطر من التعليمات البرمجية:

- `get_Item(1)` يسترجع مدخل الأسطورة الثاني (الفهرس ١). يمكنك تغيير الفهرس لاستهداف مدخل أسطورة مختلف.
- `setFontBold(NullableBool.True)` تعيين الخط إلى غامق.
- `setFontHeight(20)` تعيين حجم الخط إلى 20 نقطة.
- `setFontItalic(NullableBool.True)` تعيين الخط إلى مائل.
- `setFillType(FillType.Solid)` يحدد أن نص إدخال الأسطورة يجب أن يحتوي على تعبئة صلبة.
- `getSolidFillColor().setColor(Color.BLUE)` يُعيّن لون التعبئة إلى الأزرق. يمكنك استبدال `Color.BLUE` باللون الذي تريده.

## الخطوة 3: حفظ العرض التقديمي المعدّل

وأخيرًا، احفظ العرض التقديمي المعدّل في ملف جديد للحفاظ على التغييرات.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

يستبدل `"output.pptx"` مع اسم ملف الإخراج المفضل لديك.

هذا كل شيء! لقد نجحت في تخصيص خصائص الخط لمدخلة تعريفية فردية في عرض تقديمي باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لخصائص الخطوط لكل عنوان على حدة في شرائح Java

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

في هذا البرنامج التعليمي، تعلمنا كيفية تخصيص خصائص الخطوط لمفتاح معين في Java Slides باستخدام Aspose.Slides for Java. من خلال تعديل أنماط الخطوط وأحجامها وألوانها، يمكنك تحسين المظهر المرئي ووضوح عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

لتغيير لون الخط، استخدم `tf.getPortionFormat().getFontColor().setColor(yourColor)` بدلاً من تغيير لون التعبئة. استبدل `yourColor` مع لون الخط المطلوب.

### كيف يمكنني تعديل خصائص الأسطورة الأخرى؟

يمكنك تعديل خصائص أخرى متنوعة للمفتاح، مثل الموضع والحجم والتنسيق. راجع وثائق Aspose.Slides لجافا لمزيد من المعلومات حول التعامل مع المفاتيح.

### هل يمكنني تطبيق هذه التغييرات على إدخالات الأسطورة المتعددة؟

نعم، يمكنك تكرار إدخالات الأسطورة وتطبيق هذه التغييرات على إدخالات متعددة عن طريق ضبط الفهرس في `get_Item(index)` وتكرار كود التخصيص.

تذكر التخلص من كائن العرض التقديمي عند الانتهاء من تحرير الموارد:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
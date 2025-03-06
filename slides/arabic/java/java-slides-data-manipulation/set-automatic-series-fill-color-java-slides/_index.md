---
title: قم بتعيين لون التعبئة التلقائية للسلسلة في شرائح Java
linktitle: قم بتعيين لون التعبئة التلقائية للسلسلة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين لون التعبئة التلقائي للسلسلة في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية للعروض التقديمية الديناميكية.
weight: 14
url: /ar/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتعيين لون التعبئة التلقائية للسلسلة في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية تعيين لون التعبئة التلقائي للسلسلة في Java Slides باستخدام Aspose.Slides for Java API. Aspose.Slides for Java هي مكتبة قوية تتيح لك إنشاء عروض PowerPoint التقديمية ومعالجتها وإدارتها برمجيًا. بحلول نهاية هذا الدليل، ستكون قادرًا على إنشاء مخططات وتعيين ألوان التعبئة التلقائية للسلسلة دون عناء.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن وضعنا مخططنا التفصيلي، فلنبدأ بالدليل خطوة بخطوة.

## الخطوة 1: مقدمة إلى Aspose.Slides لـ Java

Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java تتيح للمطورين العمل مع عروض PowerPoint التقديمية. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح والمخططات والأشكال وتحريرها ومعالجتها والمزيد.

## الخطوة الثانية: إعداد مشروع جافا الخاص بك

قبل أن نبدأ البرمجة، تأكد من أنك قمت بإعداد مشروع Java في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروعك.

## الخطوة 3: إنشاء عرض تقديمي ل PowerPoint

للبدء، قم بإنشاء عرض تقديمي جديد لـ PowerPoint باستخدام مقتطف التعليمات البرمجية التالي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 يستبدل`"Your Document Directory"` بالمسار الذي تريد حفظ العرض التقديمي فيه.

## الخطوة 4: إضافة مخطط إلى العرض التقديمي

بعد ذلك، دعونا نضيف مخططًا عموديًا متفاوت المسافات إلى العرض التقديمي. سنستخدم الكود التالي لإنجاز ذلك:

```java
// إنشاء مخطط عمود متفاوت المسافات
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

يقوم هذا الرمز بإنشاء مخطط عمودي متفاوت المسافات على الشريحة الأولى من العرض التقديمي.

## الخطوة 5: ضبط لون التعبئة التلقائية للسلسلة

الآن يأتي الجزء الرئيسي - تحديد لون التعبئة التلقائي للسلسلة. سنقوم بالتكرار خلال سلسلة المخططات ونضبط تنسيق التعبئة الخاص بها على الوضع التلقائي:

```java
// ضبط تنسيق تعبئة السلسلة على الوضع التلقائي
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

يضمن هذا الرمز ضبط لون تعبئة السلسلة على الوضع التلقائي.

## الخطوة 6: حفظ العرض التقديمي

لحفظ العرض التقديمي استخدم الكود التالي:

```java
// اكتب ملف العرض التقديمي على القرص
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 يستبدل`"AutoFillSeries_out.pptx"` مع اسم الملف المطلوب.

## أكمل كود المصدر لتعيين لون التعبئة التلقائي للسلسلة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط عمود متفاوت المسافات
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// ضبط تنسيق تعبئة السلسلة على الوضع التلقائي
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// اكتب ملف العرض التقديمي على القرص
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في تعيين لون التعبئة التلقائي للسلسلة في شريحة Java باستخدام Aspose.Slides لـ Java. يمكنك الآن استخدام هذه المعرفة لإنشاء عروض PowerPoint تقديمية ديناميكية وجذابة بصريًا في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع المخطط إلى نمط مختلف؟

 يمكنك تغيير نوع المخطط عن طريق الاستبدال`ChartType.ClusteredColumn` مع نوع المخطط المطلوب، مثل`ChartType.Line` أو`ChartType.Pie`.

### هل يمكنني تخصيص مظهر المخطط بشكل أكبر؟

نعم، يمكنك تخصيص مظهر المخطط عن طريق تعديل خصائص المخطط المختلفة، مثل الألوان والخطوط والتسميات.

### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟

نعم، يمكن استخدام Aspose.Slides for Java لكل من المشاريع الشخصية والتجارية. يمكنك الرجوع إلى شروط الترخيص الخاصة بهم لمزيد من التفاصيل.

### هل هناك أي ميزات أخرى يقدمها Aspose.Slides لـ Java؟

نعم، يقدم Aspose.Slides for Java مجموعة واسعة من الميزات، بما في ذلك معالجة الشرائح وتنسيق النص ودعم الرسوم المتحركة.

### أين يمكنني العثور على المزيد من الموارد والوثائق؟

 يمكنك الوصول إلى الوثائق الشاملة لـ Aspose.Slides for Java على[هنا](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

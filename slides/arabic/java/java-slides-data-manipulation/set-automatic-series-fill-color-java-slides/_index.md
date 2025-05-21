---
"description": "تعرّف على كيفية ضبط لون تعبئة السلسلة تلقائيًا في عروض Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة برمجية للعروض التقديمية الديناميكية."
"linktitle": "تعيين لون التعبئة التلقائي للسلسلة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين لون التعبئة التلقائي للسلسلة في شرائح Java"
"url": "/ar/java/data-manipulation/set-automatic-series-fill-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين لون التعبئة التلقائي للسلسلة في شرائح Java


## مقدمة لتعيين لون التعبئة التلقائي للسلسلة في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية تعيين لون تعبئة السلاسل تلقائيًا في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. Aspose.Slides لجافا هي مكتبة فعّالة تتيح لك إنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا. بنهاية هذا الدليل، ستتمكن من إنشاء مخططات وتعيين ألوان تعبئة السلاسل تلقائيًا بسهولة.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تمت إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن أصبح لدينا مخططنا التفصيلي، فلنبدأ بالدليل خطوة بخطوة.

## الخطوة 1: مقدمة إلى Aspose.Slides لـ Java

Aspose.Slides for Java هي واجهة برمجة تطبيقات Java تُمكّن المطورين من العمل على عروض PowerPoint التقديمية. تُوفر مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح والمخططات والأشكال وتحريرها ومعالجتها، وغيرها.

## الخطوة 2: إعداد مشروع Java الخاص بك

قبل البدء بالبرمجة، تأكد من إعداد مشروع جافا في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروعك.

## الخطوة 3: إنشاء عرض تقديمي في PowerPoint

للبدء، قم بإنشاء عرض تقديمي جديد في PowerPoint باستخدام مقتطف التعليمات البرمجية التالي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

يستبدل `"Your Document Directory"` مع المسار الذي تريد حفظ العرض التقديمي فيه.

## الخطوة 4: إضافة مخطط إلى العرض التقديمي

الآن، لنُضِف مخططًا عموديًا مُجمّعًا إلى العرض التقديمي. سنستخدم الكود التالي لتحقيق ذلك:

```java
// إنشاء مخطط عمودي مجمع
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

يقوم هذا الكود بإنشاء مخطط عمودي مجمع على الشريحة الأولى من العرض التقديمي.

## الخطوة 5: ضبط لون التعبئة التلقائي للسلسلة

الآن يأتي الجزء الأهم - ضبط لون تعبئة السلسلة تلقائيًا. سنمر على سلسلة الرسم البياني ونضبط تنسيق التعبئة على تلقائي:

```java
// ضبط تنسيق تعبئة السلسلة إلى تلقائي
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

يضمن هذا الرمز أن يتم ضبط لون تعبئة السلسلة على الوضع التلقائي.

## الخطوة 6: حفظ العرض التقديمي

لحفظ العرض التقديمي، استخدم الكود التالي:

```java
// كتابة ملف العرض التقديمي على القرص
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

يستبدل `"AutoFillSeries_out.pptx"` مع اسم الملف المطلوب.

## كود المصدر الكامل لتعيين لون التعبئة التلقائي للسلسلة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط عمودي مجمع
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// ضبط تنسيق تعبئة السلسلة إلى تلقائي
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// كتابة ملف العرض التقديمي على القرص
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في ضبط لون التعبئة التلقائية للسلسلة في شريحة جافا باستخدام Aspose.Slides لجافا. يمكنك الآن استخدام هذه المعرفة لإنشاء عروض تقديمية ديناميكية وجذابة بصريًا على PowerPoint في تطبيقات جافا.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني إلى نمط مختلف؟

يمكنك تغيير نوع الرسم البياني عن طريق استبدال `ChartType.ClusteredColumn` مع نوع الرسم البياني المطلوب، مثل `ChartType.Line` أو `ChartType.Pie`.

### هل يمكنني تخصيص مظهر الرسم البياني بشكل أكبر؟

نعم، يمكنك تخصيص مظهر الرسم البياني عن طريق تعديل خصائص مختلفة للرسم البياني، مثل الألوان والخطوط والعلامات.

### هل Aspose.Slides for Java مناسب للاستخدام التجاري؟

نعم، يُمكن استخدام Aspose.Slides for Java للمشاريع الشخصية والتجارية. يُمكنك مراجعة شروط ترخيصه لمزيد من التفاصيل.

### هل هناك أي ميزات أخرى يوفرها Aspose.Slides لـ Java؟

نعم، يوفر Aspose.Slides for Java مجموعة واسعة من الميزات، بما في ذلك معالجة الشرائح وتنسيق النص ودعم الرسوم المتحركة.

### أين يمكنني العثور على المزيد من الموارد والوثائق؟

يمكنك الوصول إلى الوثائق الشاملة لـ Aspose.Slides for Java على [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
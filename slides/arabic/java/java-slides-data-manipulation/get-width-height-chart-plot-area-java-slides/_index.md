---
title: احصل على العرض والارتفاع من منطقة رسم المخطط في شرائح Java
linktitle: احصل على العرض والارتفاع من منطقة رسم المخطط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية استرداد أبعاد مساحة رسم المخطط في Java Slides باستخدام Aspose.Slides لـ Java. تعزيز مهاراتك في أتمتة PowerPoint.
weight: 21
url: /ar/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة

تعد المخططات طريقة فعالة لتصور البيانات في عروض PowerPoint التقديمية. في بعض الأحيان، قد تحتاج إلى معرفة أبعاد منطقة رسم المخطط لأسباب مختلفة، مثل تغيير حجم العناصر أو إعادة تحديد موضعها داخل المخطط. سيوضح هذا الدليل كيفية الحصول على العرض والارتفاع لمساحة الرسم باستخدام Java وAspose.Slides لـ Java.

## المتطلبات الأساسية

 قبل أن نتعمق في التعليمات البرمجية، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من موقع Aspose[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد البيئة

تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروع Java الخاص بك. يمكنك القيام بذلك عن طريق تضمين المكتبة في تبعيات مشروعك أو عن طريق إضافة ملف JAR يدويًا.

## الخطوة الثانية: إنشاء عرض تقديمي لـ PowerPoint

لنبدأ بإنشاء عرض تقديمي لـ PowerPoint وإضافة شريحة إليه. سيكون هذا بمثابة حاوية لمخططنا.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 يستبدل`"Your Document Directory"` مع المسار إلى دليل المستندات الخاص بك.

## الخطوة 3: إضافة مخطط

الآن، دعونا نضيف مخططًا عموديًا متفاوت المسافات إلى الشريحة. سنقوم أيضًا بالتحقق من صحة تخطيط المخطط.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

يقوم هذا الرمز بإنشاء مخطط عمودي متفاوت المسافات في الموضع (100، 100) بأبعاد (500، 350).

## الخطوة 4: الحصول على أبعاد مساحة الأرض

للحصول على العرض والارتفاع لمساحة رسم المخطط، يمكننا استخدام الكود التالي:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 والآن المتغيرات`x`, `y`, `w` ، و`h` تحتوي على القيم الخاصة بإحداثي X وإحداثي Y والعرض والارتفاع لمنطقة الرسم.

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع المخطط.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 تأكد من استبدال`"Chart_out.pptx"` مع اسم ملف الإخراج المطلوب.

## أكمل كود المصدر للحصول على العرض والارتفاع من منطقة رسم المخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// حفظ العرض التقديمي مع الرسم البياني
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذه المقالة، تناولنا كيفية الحصول على عرض وارتفاع منطقة رسم المخطط في Java Slides باستخدام Aspose.Slides for Java API. يمكن أن تكون هذه المعلومات ذات قيمة عندما تحتاج إلى ضبط تخطيط مخططاتك ديناميكيًا داخل عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع المخطط إلى شيء آخر غير الأعمدة المجمعة؟

 يمكنك تغيير نوع المخطط عن طريق الاستبدال`ChartType.ClusteredColumn` مع تعداد نوع المخطط المطلوب، مثل`ChartType.Line` أو`ChartType.Pie`.

### هل يمكنني تعديل خصائص أخرى للمخطط؟

نعم، يمكنك تعديل الخصائص المختلفة للمخطط، مثل البيانات والتسميات والتنسيق، باستخدام Aspose.Slides for Java API. راجع الوثائق لمزيد من التفاصيل.

### هل Aspose.Slides for Java مناسب لأتمتة PowerPoint الاحترافية؟

نعم، Aspose.Slides for Java هي مكتبة قوية لأتمتة مهام PowerPoint في تطبيقات Java. فهو يوفر ميزات شاملة للعمل مع العروض التقديمية والشرائح والأشكال والمخططات والمزيد.

### كيف يمكنني معرفة المزيد حول Aspose.Slides لـ Java؟

 يمكنك العثور على وثائق وأمثلة موسعة على صفحة وثائق Aspose.Slides for Java[هنا](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
